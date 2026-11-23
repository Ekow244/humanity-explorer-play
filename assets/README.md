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
  The manifest lists neutral.png for everyone and all 25 Chapter 1 expressions; add a line for any other.
audio/music/   home-warm  market-day  tender  road-quiet  tense  sorrow  sea  night   (.ogg, looped)
audio/sfx/     select  rooster  rustle  thud  waves  creak                          (.ogg)
fonts/         add a pixel font and point --font at it in src/ui/styles.css
```

## Pixel or illustrated (art test)

The 2D stage can draw at two sizes. Pixel is the default; illustrated is a test, switched on with
`?art=hd` in the address or Settings > "Art style (test)". Compare them at `/art-compare.html`.

```
pixel         480x270 backgrounds, portraits up to 176px tall, hard edges      (folders above)
illustrated   1920x1080 backgrounds, portraits up to 704px tall, smooth scaling
  backgrounds-hd/<id>.png                     ("hd" on the background in the manifest)
  portraits-hd/<character>/<expression>.png   ("portraitsHd" in the manifest)
```

The manifest already lists illustrated files for the five Chapter 1 backgrounds and the 25
Chapter 1 expressions. On the illustrated stage a missing file falls back to the pixel file, then
to the placeholder, each enlarged four times.

`art-test/` holds STAND-IN pictures for that test only (Unreal screenshots and Ama v2 renders).
They are not final art. `node scripts/make-art-test.mjs` rebuilds them, they are listed in
`src/content/assets.art-test.json`, and the normal game never loads them.
