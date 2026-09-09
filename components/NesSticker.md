#### Default

![Default preview](./images/nl.ns.nessie.components.sticker.samples.NesSticker_Default_Sample.png)

```kotlin
NesSticker(text = "Sticker")
```

#### Compact, with attention style

![Compact, with attention style preview](./images/nl.ns.nessie.components.sticker.samples.NesSticker_Compact_Sample.png)

```kotlin
NesSticker(
    text = "Compact",
    type = NesStickerType.Attention,
    size = NesStickerSize.Compact
)
```

#### Bordered, brand styling

![Bordered, brand styling preview](./images/nl.ns.nessie.components.sticker.samples.NesSticker_BorderedBrand_Sample.png)

```kotlin
NesSticker(
    text = "Bordered",
    type = NesStickerType.Brand,
    size = NesStickerSize.Compact,
    filled = false
)
```

#### Icon, bordered and with info styling

Behaviour: - size: only the 'xs' size is supported. Other sizes are ignored/unsupported. - compact variant: when sticker size 'compact' is used, the icon will not be shown.

![Icon, bordered and with info styling preview](./images/nl.ns.nessie.components.sticker.samples.NesSticker_Icon_Sample.png)

```kotlin
NesSticker(
    icon = IconSize.Xs.Transfer,
    text = "Transfer",
    type = NesStickerType.Info,
    filled = false
)
```

