# Interregnum Asset Hub

Working repository for the asset replacement collaboration. Every 3D asset in the current mod is being replaced, apart from the military ammo can, which is the reference for the new standard.

This repository is private and proprietary. Read [LICENSE.md](LICENSE.md) and [NOTICE.md](NOTICE.md) before using anything in it.

## Layout

```
assets/<category>/<asset>/
  README.md     what the asset is, its variants, its status
  preview.png   render of the old asset (all variants on one sheet)
  old/          the current asset, for reference only
    <variant>/models/   .obj + .mtl
    <variant>/textures/ .png
    <variant>/animations/ .danim.json (guns only, reference)
  new/          the replacement goes here
    <variant>/models/
    <variant>/textures/
    source/     optional working files (.blend, .fbx, .psd)
```

- One folder per ticket on the Miro board. Variants of the same asset share a ticket and a folder (for example `assets/gun/rifle/ak-74-family` holds the AK-74, AKS-74, AKS-74U and RPK-74).
- Guns are grouped by class: `gun/pistol`, `gun/rifle`, `gun/smg`, `gun/shotgun`, `gun/mg`, `gun/rocket`, `gun/revolver`, `gun/crossbow`.
- [`assets/block/military-ammo-can`](assets/block/military-ammo-can/) is the reference asset. It only has a `new/` folder.

## Tracking

- [CATALOG.md](CATALOG.md) lists every ticket with its status. [catalog.csv](catalog.csv) holds the same data for spreadsheets.
- The Miro board "Interregnum - Zombie Apocalypse Asset Hub" mirrors this list with old and new renders side by side.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for the delivery format, naming rules and review steps.

## Setup

Large source files go through Git LFS. Install it once before cloning or committing:

```bash
git lfs install
```
