# Writing your own NesListItem prefab

Use `NesListItem` directly when none of the ready-made prefabs match your use case.

The component is slot-based:

- `leading` uses `NesListItemLeadingScope`
- `content` uses `NesListItemContentScope`
- `trailing` uses `NesListItemTrailingScope`

## Recommended approach

1. Create a small wrapper composable for your specific use case.
2. Expose only the parameters that matter to that use case.
3. Keep stable defaults in the wrapper (for example `type`, `contained`, `size`).
4. Compose the slots with the scope helpers.
5. Reuse that wrapper anywhere you need the same layout.

## Scope helpers

### Leading scope (`NesListItemLeadingScope`)

- `Date(...)`
- `Icon(...)`
- `IconLarge(...)`
- `IconColor(...)`

### Content scope (`NesListItemContentScope`)

- `Label(...)`
- `Subtext(...)`
- `Option(...)`
- `SubtextOrOption(...)`
- `HelpText(...)`
- `Button(...)`
- `Column(...)`

### Trailing scope (`NesListItemTrailingScope`)

- `TrailingText(...)`
- `Icon(...)`
- `IconButton(...)`
- `Toggle(...)`
- `Row(...)`
