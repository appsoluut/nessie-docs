#### Single, contained, with trailing text

Showing a list item with a train icon, label and trailing text.

![Single, contained, with trailing text preview](./images/nl.ns.nessie.components.list.prefab.samples.NesListItemNavigation_SingleContainedTrailing_Sample.png)

```kotlin
NesListItemNavigation(
    label = "Label",
    trailingText = "Trailing Text",
    type = NesListItemType.Single,
    icon = R.drawable.ic_nes_cropped_train_ic_alt,
    onClick = { println("Item clicked") }
)
```

#### Single, contained, with subtext

Showing a list item with a train icon, label and subtext

![Single, contained, with subtext preview](./images/nl.ns.nessie.components.list.prefab.samples.NesListItemNavigation_SingleContainedDefaultSubtext_Sample.png)

```kotlin
NesListItemNavigation(
    label = "Label",
    subtext = "Subtext",
    type = NesListItemType.Single,
    icon = R.drawable.ic_nes_cropped_train_ic_alt,
    onClick = { println("Item clicked") }
)
```

#### Single, uncontained, with options

Showing a list item with a train icon, label and subtext (as options).

![Single, uncontained, with options preview](./images/nl.ns.nessie.components.list.prefab.samples.NesListItemNavigation_SingleUncontainedOptionsSubtext_Sample.png)

```kotlin
NesListItemNavigation(
    label = "Label",
    subtext = "Options",
    hasOptions = true,
    contained = false,
    type = NesListItemType.Single,
    icon = R.drawable.ic_nes_cropped_train_ic_alt,
    onClick = { println("Item clicked") }
)
```

#### List of three contained navigation items.

![List of three contained navigation items. preview](./images/nl.ns.nessie.components.list.prefab.samples.NesListItemNavigation_ListOfThreeItems_Sample.png)

```kotlin
val numberOfItems = 3
LazyColumn {
    items((0 until numberOfItems).toList()) { index ->
        val type = NesListItemType.fromIndex(index = index, count = numberOfItems)
        NesListItemNavigation(
            type = type,
            icon = R.drawable.ic_nes_cropped_train_ic_alt,
            label = "Label",
            subtext = type.name,
            onClick = { /* No-op */ }
        )
    }
}
```

