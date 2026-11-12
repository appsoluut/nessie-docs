#### Text area with placeholder

![Text area with placeholder preview](./images/nl.ns.nessie.components.form.samples.NesTextArea_Placeholder_Sample.png)

```kotlin
var value by remember { mutableStateOf("") }
NesTextArea(
    label = "Comments",
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
    label = "Comments",
    value = value,
    onValueChange = { value = it },
    readOnly = true
)
```

#### Text area in error state

![Text area in error state preview](./images/nl.ns.nessie.components.form.samples.NesTextArea_Error_Sample.png)

```kotlin
var value by remember { mutableStateOf("Text") }
NesTextArea(
    label = "Comments",
    errorMessage = "Enter a description of your journey",
    value = value,
    onValueChange = { value = it },
    isError = true,
)
```

#### Borderless text area

![Borderless text area preview](./images/nl.ns.nessie.components.form.samples.NesTextArea_Borderless_Sample.png)

```kotlin
var value by remember { mutableStateOf("Text") }
NesTextArea(
    label = "Comments",
    value = value,
    onValueChange = { value = it },
    border = false,
)
```

#### Default text area

Sample showing how to use a TextFieldValue in combination with the Text Area

![Default text area preview](./images/nl.ns.nessie.components.form.samples.NesTextArea_Default_Sample.png)

```kotlin
var value by remember { mutableStateOf(TextFieldValue("Text")) }
NesTextArea(
    label = "Comments",
    helpText = "Tell us about your journey",
    optional = true,
    value = value,
    onValueChange = { value = it }
)
```

