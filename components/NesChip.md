#### Action Chip with only a label

![Action Chip with only a label preview](./images/nl.ns.nessie.components.chip.samples.NesChipAction_Label_Sample.png)

```kotlin
NesChipAction(
    text = "Chip Action",
    onClick = { /* Handle click */ }
)
```

#### Action Chip with both an icon and label

![Action Chip with both an icon and label preview](./images/nl.ns.nessie.components.chip.samples.NesChipAction_IconAndLabel_Sample.png)

```kotlin
NesChipAction(
    text = "Chip Action",
    leadingIcon = R.drawable.ic_nes_cropped_bike,
    onClick = { /* Handle click */ }
)
```

#### Dismissible Chip with a label and dismiss action

This sample demonstrates how to create a dismissible chip that includes a label and a dismiss button, which can be used to remove the chip from the UI.

![Dismissible Chip with a label and dismiss action preview](./images/nl.ns.nessie.components.chip.samples.NesChipDismissible_Default_Sample.png)

```kotlin
NesChipDismissible(
    text = "Dismissible Chip",
    onDismissClick = { /* Handle dismiss */ },
)
```

#### Dismissible Chip with a filled style, label, and dismiss action

![Dismissible Chip with a filled style, label, and dismiss action preview](./images/nl.ns.nessie.components.chip.samples.NesChipDismissible_Filled_Sample.png)

```kotlin
NesChipDismissible(
    text = "Dismissible Chip",
    filled = true,
    onDismissClick = { /* Handle dismiss */ },
)
```

#### Checked Filter Chip with a label and a badge

This sample demonstrates how to create a filter chip that is checked, includes a label, and displays a badge with a count. The badge can be used to indicate the number of items filtered by this chip.

![Checked Filter Chip with a label and a badge preview](./images/nl.ns.nessie.components.chip.samples.NesChipFilter_CheckedWithLabelAndBadge_Sample.png)

```kotlin
var checked by remember { mutableStateOf(true) }
NesChipFilter(
    text = "Modalities",
    checked = checked,
    onCheckedChange = { newState ->
        checked = newState
    },
    badge = {
        NesBadge(
            count = 2,
            contentDescription = "2 filtered modalities",
        )
    }
)
```

#### Filled Filter Chip with a label and the multi option

This sample demonstrates how to create a filter chip that is filled, includes a label, and allows for multiple selections.

![Filled Filter Chip with a label and the multi option preview](./images/nl.ns.nessie.components.chip.samples.NesChipFilter_FilledWithLabelAndMulti_Sample.png)

```kotlin
var checked by remember { mutableStateOf(false) }
NesChipFilter(
    text = "Modalities",
    filled = true,
    multi = true,
    checked = checked,
    onCheckedChange = { newState ->
        checked = newState
    },
)
```

