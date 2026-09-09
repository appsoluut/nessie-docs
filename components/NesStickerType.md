#### Use a type from the API.

To provide a `NesStickerType` from an API perspective, you can use the `toNesStickerType()` String extension function. This example converts "offer" to `NesStickerType.Offer`. Unknown types will default to `NesStickerType.Default`.

![Use a type from the API. preview](./images/nl.ns.nessie.components.sticker.samples.NesStickerType_toNesStickerType_Sample.png)

```kotlin
NesSticker(
    text = "Offer from API",
    type = "offer".toNesStickerType()
)
```

