#### List, expanded

![List, expanded preview](./images/nl.ns.nessie.components.expandable.samples.NesExpandable_List_Sample.png)

```kotlin
var expanded by rememberSaveable { mutableStateOf(NesExpandableState.Expanded) }
NesExpandable(
    header = "Header",
    type = NesExpandableType.List,
    expanded = expanded,
    onExpand = { expanded = NesExpandableState.Expanded },
    onCollapse = { expanded = NesExpandableState.Collapsed }
) {
    NesText("Content")
}
```

#### Stand-alone, expanded with tinted content

![Stand-alone, expanded with tinted content preview](./images/nl.ns.nessie.components.expandable.samples.NesExpandable_StandAlone_Sample.png)

```kotlin
var expanded by rememberSaveable { mutableStateOf(NesExpandableState.Expanded) }
NesExpandable(
    header = "Header",
    type = NesExpandableType.StandAlone,
    contentTint = true,
    expanded = expanded,
    onExpand = { expanded = NesExpandableState.Expanded },
    onCollapse = { expanded = NesExpandableState.Collapsed }
) {
    NesText("Content")
}
```

#### Stand-alone, collapsed with a long, multiline header

![Stand-alone, collapsed with a long, multiline header preview](./images/nl.ns.nessie.components.expandable.samples.NesExpandable_StandAloneMultiline_Sample.png)

```kotlin
var expanded by rememberSaveable { mutableStateOf(NesExpandableState.Collapsed) }
NesExpandable(
    header = "A very long header text that should span over multiple lines",
    type = NesExpandableType.StandAlone,
    contentTint = true,
    expanded = expanded,
    onExpand = { expanded = NesExpandableState.Expanded },
    onCollapse = { expanded = NesExpandableState.Collapsed }
) {
    NesText("Content")
}
```

