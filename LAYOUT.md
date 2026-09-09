# Layout

Nessie layout tokens are split into two main categories:

- **Static tokens**: fixed `dp` values that never change based on screen size or density mode.
- **Dynamic tokens**: semantic layout tokens that should be used when spacing, sizing, or layout
  behaviour depends on context and may vary between density modes.

Use static tokens when you need an exact value. Use dynamic tokens when the value represents a
design decision, such as app spacing, component sizing, container inset, icon size, or border
styling.

## Screen size breakpoints determination table

| Density mode | Evaluated dimension           | Android approx.    | Notes                   |
|:-------------|:------------------------------|:-------------------|:------------------------|
| Compact      | width or height below minimum | ≤ 360sw            | Smallest dimension wins |
| Default      | both dimensions above 2XS     | \> 360sw & ≤ 512sw | Standard design mode    |
| Expanded     | expanded width and height     | ≥ 512sw            | Tablets / panes         |

The active density mode determines which dynamic token values are used.

## Static layout tokens

Static layout tokens are fixed layout values expressed in `dp`.

They do not change with screen size, density mode, or layout breakpoint.

Use static tokens when you need a predictable fixed value, for example:

- a fixed spacing value;
- a fixed size;
- a fixed border width;
- a fixed border radius.

## Dimension tokens

The `NesDimension` tokens are static layout sizes expressed in `dp`.

A token like `NesDimension.D25` always equals `1.dp`.

### Scale rule

Every `25` units in the token name equals `1.dp`.

Formula:

```kotlin
Dn = (n / 25).dp
```

Examples:

```kotlin
NesDimension.D25   // 1.dp
NesDimension.D50   // 2.dp
NesDimension.D75   // 3.dp
NesDimension.D100  // 4.dp
NesDimension.D200  // 8.dp
NesDimension.D400  // 16.dp
```

### Intended use

Use `NesDimension` tokens when you want a fixed, predictable spacing or dimension that does not
adapt to screen-size breakpoints.

For responsive or semantic layout values, use the dynamic layout tokens from `NesTokens.layout`.

### Example

```kotlin
Modifier.padding(NesDimension.D400)
```

This always applies `16.dp` padding, regardless of the current screen size or density mode.

## Static border tokens

Nessie also provides static tokens for border width and border radius.

These tokens currently map directly to their `dp` values. They should be used instead of
hardcoded `dp` values to keep layout styling consistent and easier to migrate.

## Border width

| Width  | Static token         |
|--------|----------------------|
| `0.dp` | `NesBorderWidth.W0`  |
| `1.dp` | `NesBorderWidth.W1`  |
| `2.dp` | `NesBorderWidth.W2`  |

### Example

```kotlin
BorderStroke(
    width = NesBorderWidth.W1,
    color = color
)
```

---

## Border radius

| Radius    | Static token             |
|-----------|--------------------------|
| `0.dp`    | `NesBorderRadius.R0`     |
| `1.dp`    | `NesBorderRadius.R25`    |
| `3.dp`    | `NesBorderRadius.R75`    |
| `6.dp`    | `NesBorderRadius.R150`   |
| `12.dp`   | `NesBorderRadius.R300`   |
| `16.dp`   | `NesBorderRadius.R400`   |
| `24.dp`   | `NesBorderRadius.R600`   |
| `32.dp`   | `NesBorderRadius.R800`   |
| `9999.dp` | `NesBorderRadius.Full`   |

### Scale rule

Border radius tokens follow the same `25` units equals `1.dp` scale as `NesDimension`.

Examples:

```kotlin
NesBorderRadius.R25   // 1.dp
NesBorderRadius.R75   // 3.dp
NesBorderRadius.R150  // 6.dp
NesBorderRadius.R300  // 12.dp
```

`NesBorderRadius.Full` is used for fully rounded shapes, such as pills or circles.

### Example

```kotlin
RoundedCornerShape(NesBorderRadius.R300)
```

## Dynamic layout tokens

Dynamic layout tokens are semantic tokens available through:

```kotlin
NesTokens.layout
```

Unlike static tokens, dynamic tokens describe the purpose of a value instead of only describing the
raw `dp` size.

For example:

```kotlin
NesTokens.layout.spaceAppInsetDefault
NesTokens.layout.spaceAppStackDense
NesTokens.layout.sizeComponentIconMd
NesTokens.layout.borderRadiusContainer
```

These names describe how the value should be used:

- `space...` tokens are used for spacing.
- `size...` tokens are used for component dimensions.
- `borderWidth...` tokens are used for border widths.
- `borderRadius...` tokens are used for corner radii.

Dynamic tokens should be preferred when the value is part of the design system and may depend on
the active density mode.

## Why dynamic tokens are semantic

A dynamic token is not just a replacement for an old spacing value.

For example, an old spacing value such as: `NesTheme.dimens.spacing_8` can map to multiple new
tokens depending on how it is used:

```kotlin
NesTokens.layout.space2xl
NesTokens.layout.spaceAppInsetRelaxed
NesTokens.layout.spaceAppStackComfy
NesTokens.layout.spaceWebSectionInsetTight
NesTokens.layout.spaceWebGutterComfy
NesTokens.layout.sizeComponentControlHeightTiny
NesTokens.layout.sizeComponentIconMd
```

The correct replacement depends on the context.

- If the value is used as spacing between layout elements, use a spacing token.
- If the value is used as the size of an icon, use an icon size token.
- If the value is used as the height of a component, use a component size token.

## Choosing the right dynamic token

When replacing an old layout value, choose the new token based on intent.

## Generic spacing

Use generic spacing tokens when no more specific layout context applies.

Examples:

```kotlin
NesTokens.layout.space2xs
NesTokens.layout.spaceXs
NesTokens.layout.spaceSm
NesTokens.layout.spaceMd
NesTokens.layout.spaceLg
NesTokens.layout.spaceXl
NesTokens.layout.space2xl
NesTokens.layout.space3xl
NesTokens.layout.space4xl
```

Example:

```kotlin
Modifier.padding(NesTokens.layout.spaceMd)
```

## App spacing

Use app-specific spacing tokens for app layouts.

Examples:

```kotlin
NesTokens.layout.spaceAppInsetDefault
NesTokens.layout.spaceAppInsetDense
NesTokens.layout.spaceAppInsetComfy
NesTokens.layout.spaceAppStackDefault
NesTokens.layout.spaceAppInlineDefault
```

Use these when the spacing describes layout behavior inside an app screen.

Examples:

```kotlin
Modifier.padding(NesTokens.layout.spaceAppInsetDefault)
```

```kotlin
Column(
    verticalArrangement = Arrangement.spacedBy(
        NesTokens.layout.spaceAppStackDefault
    )
)
```

## Web spacing

Use web-specific spacing tokens for web layouts, containers, wrappers, sections, and gutters.

Examples:

```kotlin
NesTokens.layout.spaceWebContainerInsetDefault
NesTokens.layout.spaceWebContainerInsetFull
NesTokens.layout.spaceWebWrapperStackDefault
NesTokens.layout.spaceWebSectionInsetTight
NesTokens.layout.spaceWebGutterDefault
NesTokens.layout.spaceWebGutterComfy
NesTokens.layout.spaceWebGutterRelaxed
```

## Box spacing

Use box spacing tokens for spacing inside boxed UI elements.

Examples:

```kotlin
NesTokens.layout.spaceBoxXs
NesTokens.layout.spaceBoxSm
NesTokens.layout.spaceBoxMd
```

## Component sizes

Use component size tokens when the value defines the size of a component or part of a component.

Examples:

```kotlin
NesTokens.layout.sizeComponentIconXs
NesTokens.layout.sizeComponentIconSm
NesTokens.layout.sizeComponentIconMd
NesTokens.layout.sizeComponentIconLg
NesTokens.layout.sizeComponentIconXl
```

```kotlin
NesTokens.layout.sizeComponentControlHeightTiny
NesTokens.layout.sizeComponentControlHeightDefault
NesTokens.layout.sizeComponentControlHeightComfy
NesTokens.layout.sizeComponentControlHeightRelaxed
```

Example:

```kotlin
NesIcon(
    modifier = Modifier.size(NesTokens.layout.sizeComponentIconMd),
    icon = icon,
    contentDescription = null
)
```

Do not use a spacing token to size an icon or control when a component size token exists.

## Dynamic border tokens

Dynamic border tokens are also available through `NesTokens.layout`.

Use these when the border value is part of the design system and should be selected semantically.

## Dynamic border width

| Width  | Static token         | Dynamic token                         |
|--------|----------------------|---------------------------------------|
| `0.dp` | `NesBorderWidth.W0`  | `NesTokens.layout.borderWidthNone`    |
| `1.dp` | `NesBorderWidth.W1`  | `NesTokens.layout.borderWidthDefault` |
| `2.dp` | `NesBorderWidth.W2`  | `NesTokens.layout.borderWidthActive`  |

### Example

```kotlin
BorderStroke(
    width = NesTokens.layout.borderWidthDefault,
    color = color
)
```

Use `borderWidthActive` for active, selected, focused, or emphasized states when applicable.

## Dynamic border radius

| Radius    | Static token             | Dynamic token                              |
|-----------|--------------------------|--------------------------------------------|
| `0.dp`    | `NesBorderRadius.R0`     | `NesTokens.layout.borderRadiusKeen`        |
| `1.dp`    | `NesBorderRadius.R25`    | `NesTokens.layout.borderRadiusEdge`        |
| `3.dp`    | `NesBorderRadius.R75`    | `NesTokens.layout.borderRadiusParticle`    |
| `6.dp`    | `NesBorderRadius.R150`   | `NesTokens.layout.borderRadiusDefault`     |
| `12.dp`   | `NesBorderRadius.R300`   | `NesTokens.layout.borderRadiusContainer`   |
| `16.dp`   | `NesBorderRadius.R400`   | `NesTokens.layout.borderRadiusInteraction` |
| `24.dp`   | `NesBorderRadius.R600`   | `NesTokens.layout.borderRadiusPanel`       |
| `32.dp`   | `NesBorderRadius.R800`   | `NesTokens.layout.borderRadiusArea`        |
| `9999.dp` | `NesBorderRadius.Full`   | `NesTokens.layout.borderRadiusEntire`      |

### Example

```kotlin
RoundedCornerShape(NesTokens.layout.borderRadiusContainer)
```

Use dynamic border radius tokens when the radius describes the role of the element, such as a container, panel, interaction element, or fully rounded element.

---

## Static vs dynamic tokens

### Use static tokens when

Use static tokens when the value should always stay the same.

Examples:

```kotlin
NesDimension.D400
NesBorderWidth.W1
NesBorderRadius.R300
```

Good use cases:

- fixed spacing;
- fixed dimensions;
- low-level drawing values;
- values that should not respond to layout density.

---

### Use dynamic tokens when

Use dynamic tokens when the value has semantic meaning in the design system.

Examples:

```kotlin
NesTokens.layout.spaceAppInsetDefault
NesTokens.layout.spaceAppStackDense
NesTokens.layout.sizeComponentIconMd
NesTokens.layout.borderRadiusContainer
```

Good use cases:

- screen or container insets;
- spacing between components;
- component sizes;
- icon sizes;
- control heights;
- border widths;
- border radii;
- values that should follow the current layout density mode.

## Summary

- `NesDimension` tokens are static `dp` values.
- `NesBorderWidth` and `NesBorderRadius` are static border tokens.
- `NesTokens.layout` contains dynamic, semantic layout tokens.
- Static tokens describe exact values.
- Dynamic tokens describe intent.
- When migrating, choose the replacement token based on how the value is used, not only by 
  matching the old `dp` value. See [migration guidance](https://design.ns.nl/4a05a30ad/p/558802-layout/b/23d7bf) for more details.
