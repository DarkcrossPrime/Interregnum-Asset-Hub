# Contributing

## Picking up an asset

1. Pick a ticket in [CATALOG.md](CATALOG.md) with status "Not started" and agree it with the owner.
2. Create a branch named after the asset folder, for example `asset/ak-74-family`.
3. Set the status to "In progress" in the catalog, in `catalog.csv` and in the asset's README.

## What to deliver

Put the replacement in the asset's `new/` folder, one subfolder per variant:

```
new/<variant>/models/<variant>.obj
new/<variant>/models/<variant>.mtl
new/<variant>/textures/<variant>.png
new/source/            optional: .blend, .fbx, .psd and similar
```

- **Formats:** the game reads OBJ + MTL + PNG only. Working files go in `source/`, never next to the OBJ.
- **Names:** lowercase with underscores. Keep the variant names from `old/` unless the owner agrees to a change.
- **MTL:** it must have the same file name as its OBJ (`ak74.obj` → `ak74.mtl`). Point textures at a relative path: `map_Kd ../textures/<variant>.png`.
- **Textures:** PNG with power-of-two sides (16, 32, 64 … 1024). Variants that only differ by colour or skin should share one model and get one texture each.
- **Scale and pivot:** match the model in `old/` so the replacement drops in without code changes. Open both in the same scene to compare.
- **Guns and attachments:** the mod's weapon and animation pipeline is being replaced, so nothing here needs to fit the old one. The animations in `old/<variant>/animations/` are reference only. A studio with its own weapon pipeline (attachments, aiming, animations) can deliver in that pipeline's format: agree the format with the owner before starting, and the rules in this list then apply only where that pipeline doesn't set its own.
- **Style:** match the reference asset in `assets/block/military-ammo-can/new/`.
- **Preview:** add `new/preview.png`, a render of all variants on a transparent or plain background.
- **Third-party sources:** list any texture or photo source in the asset's README, with its licence (see [NOTICE.md](NOTICE.md)).

Never edit or delete anything in `old/`.

## Review

1. Open a pull request into `main`. The template lists the checks.
2. The owner reviews it in game. Set the status to "In review" while it is open.
3. Once merged, the status becomes "Done", and the new render goes on the Miro board.

## Repository settings (owner)

Suggested settings for the GitHub repository:

- Protect `main`: require a pull request and one approving review, and block force pushes and deletions.
- Keep the repository private, and give collaborators "Write" access rather than "Admin".
