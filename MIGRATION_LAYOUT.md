# Layout migration

When migrating from old layout tokens, do not only match the old numeric value.

Instead, choose the new token based on context.

## Example: spacing used as padding

Before:

```kotlin
Modifier.padding(NesTheme.dimens.spacing_4)
```

After:

```kotlin
Modifier.padding(NesTokens.layout.spaceAppInsetDefault)
```

Or, if no specific app inset meaning applies:

```kotlin
Modifier.padding(NesTokens.layout.spaceMd)
```

## Example: spacing used as icon size

Before:

```kotlin
NesIcon(
    modifier = Modifier.size(NesTheme.dimens.spacing_8),
    icon = icon,
    contentDescription = null
)
```

After:

```kotlin
NesIcon(
    modifier = Modifier.size(NesTokens.layout.sizeComponentIconMd),
    icon = icon,
    contentDescription = null
)
```

Do not migrate this to `space2xl`, because the value is not spacing. It describes an icon size.

## Example: hardcoded border width

Before:

```kotlin
BorderStroke(
    width = 1.dp,
    color = color
)
```

After, static:

```kotlin
BorderStroke(
    width = NesBorderWidth.W1,
    color = color
)
```

After, dynamic:

```kotlin
BorderStroke(
    width = NesTokens.layout.borderWidthDefault,
    color = color
)
```

## Example: hardcoded border radius

Before:

```kotlin
RoundedCornerShape(12.dp)
```

After, static:

```kotlin
RoundedCornerShape(NesBorderRadius.R300)
```

After, dynamic:

```kotlin
RoundedCornerShape(NesTokens.layout.borderRadiusContainer)
```
# Mapping tables

## Static tokens

### Spacing

| **Deprecated Token**  | **Matching Token(s)** |
|-----------------------|-----------------------|
| `NesLayout.Spacing1`  | `NesDimension.D100`   |
| `NesLayout.Spacing2`  | `NesDimension.D200`   |
| `NesLayout.Spacing3`  | `NesDimension.D300`   |
| `NesLayout.Spacing4`  | `NesDimension.D400`   |
| `NesLayout.Spacing5`  | `NesDimension.D500`   |
| `NesLayout.Spacing6`  | `NesDimension.D600`   |
| `NesLayout.Spacing8`  | `NesDimension.D800`   |
| `NesLayout.Spacing10` | `NesDimension.D1000`  |
| `NesLayout.Spacing12` | `NesDimension.D1200`  |
| `NesLayout.Spacing14` | `NesDimension.D1400`  |
| `NesLayout.Spacing16` | `NesDimension.D1600`  |
| `NesLayout.Spacing20` | `NesDimension.D2000`  |
| `NesLayout.Spacing24` | `NesDimension.D2400`  |
| `NesLayout.Spacing32` | `NesDimension.D3200`  |

### Elevation

| **Deprecated Token**    | **Matching Token(s)** |
|-------------------------|-----------------------|
| `NesLayout.ElevationSm` | None                  |
| `NesLayout.ElevationMd` | None                  |
| `NesLayout.ElevationLg` | None                  |

## Dynamic tokens

Choose the appropriate matching token based on the context it is used in.

For example, use `NesTokens.layout.sizeComponentIconMd` when it is describing the size of an icon
instead of `NesTokens.layout.space2xl`.

| **Deprecated Token**                   | **Matching Token(s)**                                                                                                                                                                                                                                                                                                                         |
|----------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `NesTheme.dimens.spacing_1`            | `NesTokens.layout.space2xs`                                                                                                                                                                                                                                                                                                                   |
| `NesTheme.dimens.spacing_2`            | `NesTokens.layout.spaceXs`, `NesTokens.layout.spaceAppInsetTight`, `NesTokens.layout.spaceAppStackTiny`, `NesTokens.layout.spaceAppInlineDense`, `NesTokens.layout.spaceBoxXs`                                                                                                                                                                |
| `NesTheme.dimens.spacing_3`            | `NesTokens.layout.spaceSm`, `NesTokens.layout.spaceAppInsetDense`, `NesTokens.layout.spaceAppStackTight`, `NesTokens.layout.spaceAppInlineDefault`, `NesTokens.layout.spaceWebGutterDense`, `NesTokens.layout.spaceBoxSm`                                                                                                                     |
| `NesTheme.dimens.spacing_4`            | `NesTokens.layout.spaceMd`, `NesTokens.layout.spaceAppInsetDefault`, `NesTokens.layout.spaceAppStackDense`, `NesTokens.layout.spaceAppInlineComfy`, `NesTokens.layout.spaceBoxMd`, `NesTokens.layout.sizeComponentIconXs`                                                                                                                     |
| `NesTheme.dimens.spacing_5`            | `NesTokens.layout.spaceLg`                                                                                                                                                                                                                                                                                                                    |
| `NesTheme.dimens.spacing_6`            | `NesTokens.layout.spaceXl`, `NesTokens.layout.spaceAppInsetComfy`, `NesTokens.layout.spaceAppStackDefault`, `NesTokens.layout.spaceWebContainerInsetDefault`, `NesTokens.layout.spaceWebContainerInsetFull`, `NesTokens.layout.spaceWebWrapperStackDefault`, `NesTokens.layout.spaceWebGutterDefault`, `NesTokens.layout.sizeComponentIconSm` |
| `NesTheme.dimens.spacing_8`            | `NesTokens.layout.space2xl`, `NesTokens.layout.spaceAppInsetRelaxed`, `NesTokens.layout.spaceAppStackComfy`, `NesTokens.layout.spaceWebSectionInsetTight`, `NesTokens.layout.spaceWebGutterComfy`, `NesTokens.layout.spaceWebGutterRelaxed`, `NesTokens.layout.sizeComponentControlHeightTiny`, `NesTokens.layout.sizeComponentIconMd`        |
| `NesTheme.dimens.spacing_12`           | `NesTokens.layout.space3xl`, `NesTokens.layout.sizeComponentControlHeightDefault`, `NesTokens.layout.sizeComponentIconLg`                                                                                                                                                                                                                     |
| `NesTheme.dimens.spacing_14`           | `NesTokens.layout.sizeComponentControlHeightComfy`, `NesTokens.layout.sizeComponentIconXl`                                                                                                                                                                                                                                                    |
| `NesTheme.dimens.spacing_16`           | `NesTokens.layout.space4xl`, `NesTokens.layout.sizeComponentControlHeightRelaxed`                                                                                                                                                                                                                                                             |
| `NesTheme.dimens.spacing_20`           | None                                                                                                                                                                                                                                                                                                                                          |
| `NesTheme.dimens.spacing_24`           | None                                                                                                                                                                                                                                                                                                                                          |
| `NesTheme.dimens.spacing_32`           | None                                                                                                                                                                                                                                                                                                                                          |
| `NesTheme.dimens.minimum_touch_target` | None                                                                                                                                                                                                                                                                                                                                          |

## Borders

### Width

| **Width** | **Static**          | **Dynamic**                           |
|-----------|---------------------|---------------------------------------|
| `0.dp`    | `NesBorderWidth.W0` | `NesTokens.layout.borderWidthNone`    |
| `1.dp`    | `NesBorderWidth.W1` | `NesTokens.layout.borderWidthDefault` |
| `2.dp`    | `NesBorderWidth.W2` | `NesTokens.layout.borderWidthActive`  |

### Radius

| **Radius** | **Static**             | **Dynamic**                                |
|------------|------------------------|--------------------------------------------|
| `0.dp`     | `NesBorderRadius.R0`   | `NesTokens.layout.borderRadiusKeen`        |
| `1.dp`     | `NesBorderRadius.R25`  | `NesTokens.layout.borderRadiusEdge`        |
| `3.dp`     | `NesBorderRadius.R75`  | `NesTokens.layout.borderRadiusParticle`    |
| `6.dp`     | `NesBorderRadius.R150` | `NesTokens.layout.borderRadiusDefault`     |
| `12.dp`    | `NesBorderRadius.R300` | `NesTokens.layout.borderRadiusContainer`   |
| `16.dp`    | `NesBorderRadius.R400` | `NesTokens.layout.borderRadiusInteraction` |
| `24.dp`    | `NesBorderRadius.R600` | `NesTokens.layout.borderRadiusPanel`       |
| `32.dp`    | `NesBorderRadius.R800` | `NesTokens.layout.borderRadiusArea`        |
| `9999.dp`  | `NesBorderRadius.Full` | `NesTokens.layout.borderRadiusEntire`      |
