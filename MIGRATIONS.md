# V3 Migration Guide

## Breaking Changes to Components

All components will fail snapshot tests as palette colours have been altered.

**Buttons**

`NesButton` and `NesIconButton` no longer reserve a minimum touch-target height around their
visible surface. Compact buttons now occupy only their visual height. Compose still expands
their touch targets to the platform minimum without affecting layout measurements.

Containing layouts must leave enough space between controls to avoid overlapping expanded touch
targets. For example, two 32.dp-high icon buttons need at least 16.dp of vertical spacing for
separate centered 48.dp touch targets. If a layout needs an explicitly reserved area, apply sizing
or spacing in that layout. `NesButtonSettings.useMinTouchHeight` is deprecated and has no effect.
Compact-button layout snapshots will need updating.

**Chips**

1. `NesChipAction` and `NesChipDismissible` don't not support `NesBadge` anymore. This property has been removed.
2. Deprecated components overloads removed for `NesChipAction` and `NesChipFilter`. 

**Divider**

1. `NesDividerType.Strong` and `NesDividerType.Alpha` have been removed.

**Error Message**

1. `NesError` has now been removed. Use `NesErrorMessage` instead.

**Sticker**

1. `Informative` Sticker type has now been removed. Use `Default` instead.

**Text Field, Text Area, Search Input and Credit Card**

1. These components no longer depend on Material. The `colors` parameter of `NesTextField`,
   `NesTextArea` and `NesSearchInput` is now a Nessie-owned `NesTextFieldColors`
   instead of Material's `TextFieldColors`. `NesTextFieldDefaults.textFieldColors(...)` keeps the same
   parameters and now returns `NesTextFieldColors`, so callers using it need no changes.
2. Custom Material colors can be bridged temporarily with the deprecated
   `TextFieldColors.toNesTextFieldColors()` adapter. It will be removed in the next major version;
   migrate to `NesTextFieldDefaults.textFieldColors(...)` or your own `NesTextFieldColors`.
3. The border is now drawn outside a 1.dp inset surface while the total height stays 48.dp. The
   focused (2.dp) border extends 1.dp beyond the component bounds. The dark-mode elevation overlay
   was removed and horizontal content padding follows the density layout tokens. Snapshots of
   screens containing these inputs will need updating.

### Labeled input overloads

Use the overloads of `NesTextField`, `NesTextArea`, `NesSearchInput` and `NesCreditcard` with a
required `label`. The unlabeled overloads are deprecated but retain their existing behavior.
Both `String` and `TextFieldValue` variants are available where previously supported.

The labeled APIs and deprecated unlabeled wrappers share non-deprecated input implementations.
Removing the wrappers later does not require refactoring the labeled components.

The labeled overloads include `NesFormRow` directly and expose its `helpText`, `optional`,
`errorMessage`, `errorMessageInvisibleToUser` and `testTag` properties. Do not wrap these
overloads in another `NesFormRow`. `modifier` applies to the complete row; use `inputModifier` for
input-only sizing.

Labeled text and card inputs and OTP inputs use the same `spaceXs` gap before the input,
whether it follows the label directly or optional help text. The label-to-help-text gap remains
`space2xs`. The generic `NesFormRow` and the range slider retain their existing spacing.

```kotlin
NesTextField(
    label = "Name",
    value = name,
    onValueChange = { name = it },
    helpText = "Enter your name as shown on your ticket",
    optional = true,
    errorMessage = validationError
)
```

A nonempty `errorMessage` enables the error state by default and is displayed below the input.
Set `isError` explicitly if validation state is controlled separately. Setting
`errorMessageInvisibleToUser` hides the detailed error from accessibility, not from the screen;
the input still announces the generic error state.

The labeled `NesTextField` shows the visibility toggle (`showVisibilityToggle`,
`visibilityToggleState`, `onVisibilityToggleClicked`) as an eye icon button at the end of the input
instead of in the form row header, and only once the input has a value. The toggle invokes the
supplied callback; the caller remains responsible for updating the visibility state and visual
transformation. The other labeled inputs don't offer a visibility toggle.

The label, optional indication and help text are announced on the input's own semantics node.
Their separate visual nodes, and the visual error message, are excluded from accessibility to
avoid repeated announcements. Editing, selection and focus actions remain on the field.
Interactive clear, trailing and visibility buttons remain separate accessibility actions.

## Colour Tokens mapping

The mappings have changed. If you are using the colour tokens directly, you will need to update the
tokens in your application. The [migration mapping can be found here](https://design.ns.nl/4a05a30ad/p/3248ef-migration-mapping).

Instead of using `NesTheme.colors` you should now either use `NesTokens.colors` or
`NesTokens.applied` to be able to use the new tokens.

## Typography

All of `NesTypography` is deprecated. You should now use `NesTokens.typography` instead which map
to the new typography tokens used in Figma designs. The new tokens also automatically add the
correct bounding box which makes implementation from Figma designs easier. The currently used
`NesTypography` tokens are still available but marked as deprecated for the linters and do **not**
have the correct bounding box. This means that if you migrate from NesTypography tokens to the new
NesTokens typography tokens, you will need to adjust (or remove) the bounding box in your screen.

There is a [typography token matching table](https://design.ns.nl/4a05a30ad/p/244621-typography/b/41ad6c)
available to help you choose the right token for the right context.
