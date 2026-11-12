#### Single, contained, has option(s)

Text below the label will be displayed as option (interactive colour)

![Single, contained, has option(s) preview](./images/nl.ns.nessie.components.list.prefab.samples.NesListItemMenu_SingleContainedOptions_Sample.png)

```kotlin
NesListItemMenu(
    label = "Title",
    subtext = "Subtitle",
    type = NesListItemType.Single,
    onClick = { println("Item clicked") }
)
```

#### Single, contained, as subtext

Text below the label will be rendered as subtext (help text colour)

![Single, contained, as subtext preview](./images/nl.ns.nessie.components.list.prefab.samples.NesListItemMenu_SingleContainedSubtext_Sample.png)

```kotlin
NesListItemMenu(
    label = "Title",
    subtext = "Subtitle",
    hasOptions = false,
    type = NesListItemType.Single,
    onClick = { println("Item clicked") }
)
```

