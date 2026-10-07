#### Basic usage example

![Basic usage example preview](./images/nl.ns.nessie.components.section.samples.NesSectionHeadingDismissible_Usage_Sample.png)

```kotlin
NesSectionHeadingDismissible(
    title = "Section Heading",
    onDismiss = { /* Handle: Dismiss click */ }
) {
    Column {
        val count = 2
        repeat(count) { index ->
            NesListItemNavigation(
                type = NesListItemType.fromIndex(index, count),
                icon = R.drawable.ic_nes_cropped_train_ic_alt,
                label = "Label",
                onClick = { }
            )
        }
    }
}
```

#### Additional actions that belong to the section

![Additional actions that belong to the section preview](./images/nl.ns.nessie.components.section.samples.NesSectionHeadingDismissible_AdditionalActions_Sample.png)

```kotlin
NesSectionHeadingDismissible(
    title = "Section Heading",
    actions = {
        LabelButton(
            label = "Read more",
            onClick = { /* Handle: read more button clicked */ }
        )
    },
    onDismiss = { /* Handle: Dismiss click */ }
) {
    Column {
        val count = 2
        repeat(count) { index ->
            NesListItemNavigation(
                type = NesListItemType.fromIndex(index, count),
                icon = R.drawable.ic_nes_cropped_train_ic_alt,
                label = "Label",
                onClick = { }
            )
        }
    }
}
```

