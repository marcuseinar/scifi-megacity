# Texture credits

All materials are **CC0 1.0** scans from [ambientCG](https://ambientcg.com) —
public domain, no attribution required (credited here anyway). Each was resized
from the original 2K release and channel-packed for the web; the four packs
together are ~900 KB rather than the ~120 MB they ship as.

Every `*_orm.webp` packs several greyscale maps into one file: **R = ambient
occlusion, G = roughness, B = metalness**. Those are the exact channels three.js
reads for `aoMap`, `roughnessMap` and `metalnessMap`, so one texture feeds up to
three slots. `NormalGL` is always used over `NormalDX` — three.js expects the
OpenGL convention, and the DirectX variant renders relief inverted.

| Pack | Source | Used for | Tile |
|---|---|---|---|
| `tarmac_*` | Asphalt014 | Roadway | 14 m |
| `concrete_*` | Concrete016 | Cornices, ribs, skyway decks, pylon caps | 6 m |
| `rustplate_*` | Metal022 | Rooftop machinery, masts, tanks, pylons | 9 m |
| `paving_*` | PavingStones038 | Sidewalks | 3 m |


## Sidewalk paving — `paving_color.webp`, `paving_normal.webp`, `paving_orm.webp`

**Source:** PavingStones038 from [ambientCG](https://ambientcg.com), 2K JPG release
**Licence:** [CC0 1.0 Universal](https://creativecommons.org/publicdomain/zero/1.0/) — public domain, no attribution required (credited here anyway)

Processed for the web from the original 2K set:

| File | Source map | Size | Format |
|---|---|---|---|
| `paving_color.webp` | `Color` | 1024² | WebP q82 |
| `paving_normal.webp` | `NormalGL` | 768² | WebP q88 |
| `paving_orm.webp` | `AmbientOcclusion` + `Roughness` | 512² | WebP q90 |

`paving_orm.webp` packs two maps into one file: **R = ambient occlusion,
G = roughness**, which is exactly what three.js reads from `aoMap` and
`roughnessMap`, so a single texture feeds both slots. Blue is unused — stone
is not metallic.

`NormalGL` is the OpenGL-convention normal (+Y up), which is what three.js
expects. The `NormalDX` variant in the original download would render with
inverted relief.

The original 29 MB download reduces to ~340 KB this way. `Displacement` is
unused — it needs geometry tessellation the pavement doesn't have.
