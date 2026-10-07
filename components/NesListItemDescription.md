#### Single, contained, with trailing text

Showing a list item with only a label and trailing text.

![Single, contained, with trailing text preview](./images/nl.ns.nessie.components.list.prefab.samples.NesListItemDescription_SingleContainedTrailing_Sample.png)

```kotlin
NesListItemDescription(
    label = "Title",
    trailingText = "Trailing text",
    type = NesListItemType.Single,
    onClick = { println("Item clicked") }
)
```

#### Single, uncontained, non-clickable

Showing a list item with only a label as uncontained and non-clickable

![Single, uncontained, non-clickable preview](./images/nl.ns.nessie.components.list.prefab.samples.NesListItemDescription_SingleUncontainedNonClickable_Sample.png)

```kotlin
NesListItemDescription(
    label = "Title",
    trailingText = "Trailing text",
    type = NesListItemType.Single
)
```

