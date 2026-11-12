#### Default search input

![Default search input preview](./images/nl.ns.nessie.components.form.samples.NesSearchInput_Default_Sample.png)

```kotlin
var value by remember { mutableStateOf(TextFieldValue("")) }
NesSearchInput(
    label = "Station",
    helpText = "Search for a station by name",
    value = value,
    onValueChange = { value = it },
    placeholder = "Search",
)
```

#### Search input with a value

A clear button is shown when the search input has a value.

![Search input with a value preview](./images/nl.ns.nessie.components.form.samples.NesSearchInput_Value_Sample.png)

```kotlin
var value by remember { mutableStateOf(TextFieldValue("Utrecht Centraal")) }
NesSearchInput(
    label = "Station",
    value = value,
    onValueChange = { value = it },
    placeholder = "Search",
)
```

#### Search input in error state

![Search input in error state preview](./images/nl.ns.nessie.components.form.samples.NesSearchInput_Error_Sample.png)

```kotlin
var value by remember { mutableStateOf(TextFieldValue("Utrecht Centraal")) }
NesSearchInput(
    label = "Station",
    errorMessage = "Choose a station from the search results",
    value = value,
    onValueChange = { value = it },
    isError = true,
)
```

#### Borderless search input

![Borderless search input preview](./images/nl.ns.nessie.components.form.samples.NesSearchInput_Borderless_Sample.png)

```kotlin
var value by remember { mutableStateOf(TextFieldValue("")) }
NesSearchInput(
    label = "Station",
    value = value,
    onValueChange = { value = it },
    placeholder = "Search",
    border = false,
)
```

