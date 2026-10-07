# V3 Migration Guide

## Breaking Changes to Components

All components will fail snapshot tests as palette colours have been altered.

**Chips**

1. `NesChipAction` and `NesChipDismissible` don't not support `NesBadge` anymore. This property has been removed.
2. Deprecated components overloads removed for `NesChipAction` and `NesChipFilter`. 

**Divider**

1. `NesDividerType.Strong` and `NesDividerType.Alpha` have been removed.

**Error Message**

1. `NesError` has now been removed. Use `NesErrorMessage` instead.

**Sticker**

1. `Informative` Sticker type has now been removed. Use `Default` instead.

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
