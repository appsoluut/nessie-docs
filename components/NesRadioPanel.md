#### Panel with label and 2 items

![Panel with label and 2 items preview](./images/nl.ns.nessie.components.radiopanel.samples.NesRadioPanel_Items_Sample.png)

```kotlin
var state by remember { mutableIntStateOf(0) }
val titles = listOf("Label", "Longer label")
NesFormRow(
    label = "Label"
) {
    NesRadioPanel(selectedRadioIndex = state) {
        titles.forEachIndexed { index, title ->
            NesRadioPanelItem(
                selected = state == index,
                text = title,
                onClick = {
                    state = index
                }
            )
        }
    }
}
```

