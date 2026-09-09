#### Toggle Row simple example with only 2 states

![Toggle Row simple example with only 2 states preview](./images/nl.ns.nessie.components.form.samples.NesToggleRow_Simple_Sample.png)

```kotlin
var checked by remember { mutableStateOf(true) }
NesToggleRow(
    label = "Label",
    checked = checked,
    onCheckedChange = { checked = it }
)
```

#### Toggle row in loading state

![Toggle row in loading state preview](./images/nl.ns.nessie.components.form.samples.NesToggleRow_Loading_Sample.png)

```kotlin
var checked by remember { mutableStateOf(false) }
NesToggleRow(
    label = "Label",
    state = NesToggleableState.Loading,
    onCheckedChange = { checked = it }
)

// Helper to get the checked boolean based on NesToggleableState
val isOn = NesToggleableState(checked)
```

#### Only toggle based on Boolean

![Only toggle based on Boolean preview](./images/nl.ns.nessie.components.form.samples.NesToggle_Boolean_Sample.png)

```kotlin
var checked by remember { mutableStateOf(true) }
NesToggle(
    checked = checked,
    onCheckedChange = { checked = it }
)
```

