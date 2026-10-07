#### Title and back navigation

![Title and back navigation preview](./images/nl.ns.nessie.components.appbar.samples.NesTextTopAppBar_TitleAndBack_Sample.png)

```kotlin
NesTextTopAppBar(
    title = "Title",
    showBackNavigationIcon = true,
)
```

#### Modal style and force show divider

![Modal style and force show divider preview](./images/nl.ns.nessie.components.appbar.samples.NesTextTopAppBar_ModalStyleAndDivider_Sample.png)

```kotlin
NesTextTopAppBar(
    style = NesTopAppBarStyle.Modal,
    title = "Title",
    showDivider = true
)
```

#### Modal style and show divider when scrolled

If the divider needs to be only showing when the content is scrolled.

![Modal style and show divider when scrolled preview](./images/nl.ns.nessie.components.appbar.samples.NesTextTopAppBar_ModalStyleScrollableDivider_Sample.png)

```kotlin
val state = rememberLazyListState()
val isScrolled by remember {
    derivedStateOf {
        state.firstVisibleItemIndex > 0 || state.firstVisibleItemScrollOffset > 0
    }
}

NesScaffold(
    topBar = {
        NesTextTopAppBar(
            style = NesTopAppBarStyle.Modal,
            title = "Title",
            showDivider = isScrolled
        )
    },
    content = { paddingValues ->
        LazyColumn(
            modifier = Modifier.padding(paddingValues),
            state = state // make sure to use the same state
        ) {
            items(25) {
                NesText(
                    text = "Item $it",
                    modifier = Modifier.minimumInteractiveComponentSize().fillMaxWidth()
                )
            }
        }
    },
    backgroundColor = NesTokens.colors.contentBackgroundDefault
)
```

