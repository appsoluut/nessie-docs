#### Single, contained, with label only

![Single, contained, with label only preview](./images/nl.ns.nessie.components.list.prefab.samples.NesListItemDataAction_SingleContainedLabelOnly_Sample.png)

```kotlin
NesListItemDataAction(
    icon = R.drawable.ic_nes_cropped_train_ic_alt,
    iconVariant = ListItemChildIconColorVariant.Info,
    label = "Title",
    type = NesListItemType.Single,
    onClick = { println("Action clicked") }
)
```

#### Single, contained, with trailing text

![Single, contained, with trailing text preview](./images/nl.ns.nessie.components.list.prefab.samples.NesListItemDataAction_SingleContainedTrailingText_Sample.png)

```kotlin
NesListItemDataAction(
    icon = R.drawable.ic_nes_cropped_train_ic_alt,
    iconVariant = ListItemChildIconColorVariant.Brand,
    label = "Title",
    trailingText = "Trailing text",
    type = NesListItemType.Single,
    onClick = { println("Action clicked") }
)
```

#### Single, contained, with trailing text and importance badge

![Single, contained, with trailing text and importance badge preview](./images/nl.ns.nessie.components.list.prefab.samples.NesListItemDataAction_SingleContainedTrailingTextBadge_Sample.png)

```kotlin
NesListItemDataAction(
    icon = R.drawable.ic_nes_cropped_train_ic_alt,
    iconVariant = ListItemChildIconColorVariant.Orange,
    label = "Title",
    trailingText = "Trailing text",
    badgeVariant = NesBadgeVariant.Important,
    type = NesListItemType.Single,
    onClick = { println("Action clicked") }
)
```

#### Single, contained, with trailing text and importance badge

![Single, contained, with trailing text and importance badge preview](./images/nl.ns.nessie.components.list.prefab.samples.NesListItemDataAction_SingleContainedBadge_Sample.png)

```kotlin
NesListItemDataAction(
    icon = R.drawable.ic_nes_cropped_train_ic_alt,
    iconVariant = ListItemChildIconColorVariant.Gray,
    label = "Title",
    badgeVariant = NesBadgeVariant.Default,
    type = NesListItemType.Single,
    onClick = { println("Action clicked") }
)
```

