#### Text area with placeholder

![Text area with placeholder preview](./images/nl.ns.nessie.components.form.samples.NesTextArea_Placeholder_Sample.png)

```kotlin
var value by remember { mutableStateOf("") }
NesTextArea(
    value = value,
    onValueChange = { value = it },
    placeholder = "Placeholder"
)
```

#### Read-Only text area

![Read-Only text area preview](./images/nl.ns.nessie.components.form.samples.NesTextArea_ReadOnly_Sample.png)

```kotlin
var value by remember {
    mutableStateOf("This is a Text Area that is read-only, and can't be changed")
}
NesTextArea(
    value = value,
    onValueChange = { value = it },
    readOnly = true
)
```

#### Default text area

Sample showing how to use a TextFieldValue in combination with the Text Area

![Default text area preview](./images/nl.ns.nessie.components.form.samples.NesTextArea_Default_Sample.png)

```kotlin
var value by remember { mutableStateOf(TextFieldValue("Text")) }
NesTextArea(
    value = value,
    onValueChange = { value = it }
)
```

