#### Heading with heading1 style

![Heading with heading1 style preview](./images/nl.ns.nessie.components.text.samples.NesHeading_StringSample.png)

```kotlin
NesHeading(
    text = "Heading text",
    style = NesTokens.typography.heading1
)
```

#### Heading with heading2 non-bold style

An example showing how to use a heading with different styles. The "is off" part is bold, but the "Combined Travel Discount" part is not.

![Heading with heading2 non-bold style preview](./images/nl.ns.nessie.components.text.samples.NesHeading_AnnotatedStringSample.png)

```kotlin
NesHeading(
    text = buildAnnotatedString {
        append("Combined Travel Discount")
        pushStyle(style = NesTokens.typography.heading2.toTextStyle().toSpanStyle())
        append(" is off")
    },
    style = NesTokens.typography.heading2.copy(
        fontWeight = NesFontStyle.bodyWeight
    )
)
```

