#### Single, contained, whole item is toggleable

![Single, contained, whole item is toggleable preview](./images/nl.ns.nessie.components.list.prefab.samples.NesListItemToggle_SingleContainedRow_Sample.png)

```kotlin
NesListItemToggle(
    label = "Label",
    state = NesToggleableState.Off,
    type = NesListItemType.Single,
    onClick = { newState ->
        println("Toggle item clicked: $newState")
    }
)
```

#### Single, contained, toggle is separately toggleable from the list item

![Single, contained, toggle is separately toggleable from the list item preview](./images/nl.ns.nessie.components.list.prefab.samples.NesListItemToggle_SingleContainedToggle_Sample.png)

```kotlin
NesListItemToggle(
    label = "Label",
    state = NesToggleableState.On,
    type = NesListItemType.Single,
    toggleContentDescription = "Optional toggle content description",
    onCheckedChange = { newState ->
        println("Toggle item clicked: $newState")
    },
    onClick = { println("Item clicked") }
)
```

