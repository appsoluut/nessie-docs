#### Unchecked checkbox

![Unchecked checkbox preview](./images/nl.ns.nessie.components.checkbox.samples.NesCheckbox_Unchecked_Sample.png)

```kotlin
var checked by remember { mutableStateOf(false) }
NesCheckbox(
    text = "Label",
    checked = checked,
    onCheckedChange = { checked = it }
)
```

#### Checked checkbox

![Checked checkbox preview](./images/nl.ns.nessie.components.checkbox.samples.NesCheckbox_Checked_Sample.png)

```kotlin
var checked by remember { mutableStateOf(true) }
NesCheckbox(
    text = "Label",
    checked = checked,
    onCheckedChange = { checked = it }
)
```

#### Checkbox with help text shown underneath the label

![Checkbox with help text shown underneath the label preview](./images/nl.ns.nessie.components.checkbox.samples.NesCheckbox_HelpText_Sample.png)

```kotlin
var checked by remember { mutableStateOf(false) }
NesCheckbox(
    text = "Label",
    helpText = "Help text",
    checked = checked,
    onCheckedChange = { checked = it }
)
```

#### Checkbox in an error state

![Checkbox in an error state preview](./images/nl.ns.nessie.components.checkbox.samples.NesCheckbox_Error_Sample.png)

```kotlin
var checked by remember { mutableStateOf(false) }
NesCheckbox(
    text = "Label",
    checked = checked,
    error = true,
    onCheckedChange = { checked = it }
)
```

#### Disabled checkbox

![Disabled checkbox preview](./images/nl.ns.nessie.components.checkbox.samples.NesCheckbox_Disabled_Sample.png)

```kotlin
var checked by remember { mutableStateOf(false) }
NesCheckbox(
    text = "Label",
    checked = checked,
    enabled = false,
    onCheckedChange = { checked = it }
)
```

#### Checkbox with the border hidden

![Checkbox with the border hidden preview](./images/nl.ns.nessie.components.checkbox.samples.NesCheckbox_Borderless_Sample.png)

```kotlin
var checked by remember { mutableStateOf(false) }
NesCheckbox(
    text = "Label",
    checked = checked,
    border = false,
    onCheckedChange = { checked = it }
)
```

#### Tri-state checkbox in an indeterminate state, used for parent checkboxes that

represent a partially checked group of child checkboxes

![Tri-state checkbox in an indeterminate state, used for parent checkboxes that preview](./images/nl.ns.nessie.components.checkbox.samples.NesTriStateCheckbox_Indeterminate_Sample.png)

```kotlin
NesTriStateCheckbox(
    text = "Label",
    state = ToggleableState.Indeterminate,
    onClick = {}
)
```

