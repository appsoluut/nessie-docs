#### Labeled OV-Pas input in a form row

![Labeled OV-Pas input in a form row preview](./images/nl.ns.nessie.components.form.samples.NesOVPas_Labeled_Sample.png)

```kotlin
var value by remember { mutableStateOf("") }
NesOVPasInput(
    label = "OV-Pas number",
    value = value,
    helpText = "Enter the number printed on your pass",
    onValueChange = { value = it }
)
```

