#### Default Neutral

Show location (Track / Platform) "8" in the Neutral colour set

![Default Neutral preview](./images/nl.ns.nessie.components.tag.samples.NesTagLocation_NeutralDefault_Sample.png)

```kotlin
NesTagLocation(
    variant = NesTagLocationVariant.Neutral,
    location = "8",
    state = NesTagLocationState.Default,
    contentDescription = "Platform",
)
```

#### Default Blue

Show location (Track / Platform) "8" in the Blue colour set

![Default Blue preview](./images/nl.ns.nessie.components.tag.samples.NesTagLocation_BlueDefault_Sample.png)

```kotlin
NesTagLocation(
    variant = NesTagLocationVariant.Blue,
    location = "8",
    state = NesTagLocationState.Default,
    contentDescription = "Platform",
)
```

#### Cancelled Neutral

Show cancelled location (Track / Platform) "8" in the Neutral colour set

![Cancelled Neutral preview](./images/nl.ns.nessie.components.tag.samples.NesTagLocation_CancelledNeutralDefault_Sample.png)

```kotlin
NesTagLocation(
    variant = NesTagLocationVariant.Neutral,
    location = "8",
    state = NesTagLocationState.Cancelled,
    contentDescription = "Platform",
)
```

#### Cancelled Blue

Show cancelled location (Track / Platform) "8" in the Blue colour set

![Cancelled Blue preview](./images/nl.ns.nessie.components.tag.samples.NesTagLocation_CancelledBlueDefault_Sample.png)

```kotlin
NesTagLocation(
    variant = NesTagLocationVariant.Blue,
    location = "8",
    state = NesTagLocationState.Cancelled,
    contentDescription = "Platform",
)
```

#### Changed Neutral

Show changed location (Track / Platform) "7a" from Track "18a" in the Neutral colour set

![Changed Neutral preview](./images/nl.ns.nessie.components.tag.samples.NesTagLocation_ChangedNeutralDefault_Sample.png)

```kotlin
// Show a changed location from track 18a to 7a
NesTagLocation(
    variant = NesTagLocationVariant.Neutral,
    location = "18a",
    state = NesTagLocationState.Changed("7a"),
    contentDescription = "Platform",
)
```

#### Changed Blue

Show changed location (Track / Platform) "7a" from Track "8" in the Blue colour set

![Changed Blue preview](./images/nl.ns.nessie.components.tag.samples.NesTagLocation_ChangedBlueDefault_Sample.png)

```kotlin
// Show a changed location from track 8 to 7a
NesTagLocation(
    variant = NesTagLocationVariant.Blue,
    location = "8",
    state = NesTagLocationState.Changed("7a"),
    contentDescription = "Platform",
)
```

#### Changed and Cancelled Blue

Show changed and cancelled location (Track / Platform) "7a" from Track "8" in the Blue colour set

![Changed and Cancelled Blue preview](./images/nl.ns.nessie.components.tag.samples.NesTagLocation_ChangedAndCancelledBlueDefault_Sample.png)

```kotlin
// Show a changed and cancelled location from track 8 to 7a
NesTagLocation(
    variant = NesTagLocationVariant.Blue,
    location = "8",
    state = NesTagLocationState.Changed("7a", state = NesTagLocationState.Cancelled),
    contentDescription = "Platform",
)
```

