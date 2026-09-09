#### Anonymous with card number

![Anonymous with card number preview](./images/nl.ns.nessie.components.card.samples.NesTravelCardInline_AnonymousWithCardNumber.png)

```kotlin
NesTravelCardInline(
    type = NesTravelCardInlineType.Anonymous,
    size = NesTravelCardInlineSize.Default,
    cardNumber = NesState.Success("4210")
)
```

#### Business without card number

![Business without card number preview](./images/nl.ns.nessie.components.card.samples.NesTravelCardInline_BusinessNoNumber.png)

```kotlin
NesTravelCardInline(
    type = NesTravelCardInlineType.NSBusiness,
    size = NesTravelCardInlineSize.Default,
    cardNumber = NesState.None
)
```

#### Compact single ticket

![Compact single ticket preview](./images/nl.ns.nessie.components.card.samples.NesTravelCardInline_SingleTicketCompact.png)

```kotlin
NesTravelCardInline(
    type = NesTravelCardInlineType.SingleTicket,
    size = NesTravelCardInlineSize.Compact,
)
```

