# Assets

Drop files here and the game picks them up — no code changes. Anything missing
is replaced at runtime by a generated placeholder (or a synthesised sound).

Ids, filenames and fallbacks are declared in `src/content/assets.manifest.json`.
To rename a file or add an expression, edit the manifest.

```
backgrounds/   480x270 PNG (or any 16:9 multiple; drawn with nearest-neighbour scaling)
  home-morning.png  market.png  family-home.png  forest-path.png
  confinement.png   coast-dusk.png  ship-night.png
portraits/<character>/<expression>.png
  characters:  ama  adwoa  kofi  kojo  efua  abla
  expressions: neutral  happy  amused  concerned  sad  surprised
  Transparent PNG, up to 176px tall at stage scale (taller art is scaled down).
  A missing expression falls back to neutral.png, then to a placeholder.
  Only neutral.png is listed in the manifest to start with; add a line per extra expression.
audio/music/   home-warm  market-day  tender  road-quiet  tense  sorrow  sea  night   (.ogg, looped)
audio/sfx/     select  rooster  rustle  thud  waves  creak                          (.ogg)
fonts/         add a pixel font and point --font at it in src/ui/styles.css
```
