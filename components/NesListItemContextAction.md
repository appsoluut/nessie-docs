#### Single, contained, with label only

![Single, contained, with label only preview](./images/nl.ns.nessie.components.list.prefab.samples.NesListItemContextAction_SingleContainedLabelOnly_Sample.png)

```kotlin
NesListItemContextAction(
    icon = R.drawable.ic_nes_cropped_train_ic_alt,
    label = "Title",
    type = NesListItemType.Single,
    onClick = { println("Action clicked") }
)
```

#### Single, contained, with subtext

![Single, contained, with subtext preview](./images/nl.ns.nessie.components.list.prefab.samples.NesListItemContextAction_SingleContainedSubtext_Sample.png)

```kotlin
NesListItemContextAction(
    icon = R.drawable.ic_nes_cropped_train_ic_alt,
    label = "Title",
    subtext = "Subtext",
    type = NesListItemType.Single,
    onClick = { println("Action clicked") }
)
```

#### Single, contained, with option

![Single, contained, with option preview](./images/nl.ns.nessie.components.list.prefab.samples.NesListItemContextAction_SingleContainedOption_Sample.png)

```kotlin
NesListItemContextAction(
    icon = R.drawable.ic_nes_cropped_train_ic_alt,
    label = "Title",
    subtext = "Option",
    hasOptions = true,
    type = NesListItemType.Single,
    onClick = { println("Action clicked") }
)
```

