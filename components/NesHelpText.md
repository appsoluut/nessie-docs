#### Default indents

![Default indents preview](./images/nl.ns.nessie.components.form.samples.NesHelpText_IndentDefault_Sample.png)

```kotlin
NesHelpText(text = "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.")
```

#### No starting indent

![No starting indent preview](./images/nl.ns.nessie.components.form.samples.NesHelpText_IndentNone_Sample.png)

```kotlin
NesHelpText(
    text = "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
    indent = NesHelpTextIndent.None
)
```

#### Custom Indent

![Custom Indent preview](./images/nl.ns.nessie.components.form.samples.NesHelpText_IndentCustom_Sample.png)

```kotlin
NesHelpText(
    text = "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
    indent = NesHelpTextIndent.Custom(paddingValues = PaddingValues(
        start = 4.dp,
        end = 4.dp,
        top = 8.dp,
        bottom = 4.dp
    ))
)
```

