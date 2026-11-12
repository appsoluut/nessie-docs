#### Labeled chipcard input in a form row

![Labeled chipcard input in a form row preview](./images/nl.ns.nessie.components.form.samples.NesChipcard_Labeled_Sample.png)

```kotlin
var value by remember { mutableStateOf("") }
NesChipcard(
    label = "Chipcard number",
    value = value,
    helpText = "Enter the 16-digit number on your card",
    onValueChange = { value = it }
)
```

