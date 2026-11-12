#### Show a price with leading text

![Show a price with leading text preview](./images/nl.ns.nessie.components.price.samples.NesPrice_Default_Sample.png)

```kotlin
NesPrice(
    priceInCents = 99900,
    leadingText = "Leading"
)
```

#### Price with discount and trailing text

![Price with discount and trailing text preview](./images/nl.ns.nessie.components.price.samples.NesPrice_Discount_Sample.png)

```kotlin
NesPrice(
    priceInCents = 2000,
    previousPriceInCents = 4995,
    trailingText = "Trailing"
)
```

#### Price with alternate colour

![Price with alternate colour preview](./images/nl.ns.nessie.components.price.samples.NesPrice_AlternateColour_Sample.png)

```kotlin
NesPrice(
    priceInCents = 2000,
    previousPriceInCents = 4995,
    color = NesTokens.colors.systemHighlightDefault
)
```

#### Unknown price with leading text

![Unknown price with leading text preview](./images/nl.ns.nessie.components.price.samples.NesPrice_Unknown_Sample.png)

```kotlin
NesPrice(
    priceInCents = null,
    leadingText = "Balance:"
)
```

#### Stacked price with leading and trailing text

![Stacked price with leading and trailing text preview](./images/nl.ns.nessie.components.price.samples.NesPrice_Stacked_Sample.png)

```kotlin
NesPrice(
    leadingText = "Leading",
    trailingText = "Trailing",
    priceInCents = 99900,
    stacked = true
)
```

#### Always show decimals

Forces the price to be formatted with two decimal places even for round amounts. Example: `priceInCents = 1000` -> "€ 10.00" (instead of "€ 10"). Useful for consistent column alignment or when you want to emphasize cents.

![Always show decimals preview](./images/nl.ns.nessie.components.price.samples.NesPrice_Decimals_Sample.png)

```kotlin
NesPrice(
    priceInCents = 1000,
    alwaysShowDecimals = true
)
```

