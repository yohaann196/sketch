# sketch

a generative art thing i built to mess around with flow fields and canvas. particles follow a noise-based vector field and get pulled toward your mouse.

## try it

just open `index.html` in a browser. no build step or dependencies. or just go to my github pages linked.

## controls

| key / input | what it does |
|---|---|
| mouse | particles follow your cursor |
| click | burst 80 particles at cursor |
| `space` | pause / resume |
| `r` | randomize color palette |
| `c` | clear the canvas |

## how it works

the flow field is built from a fake noise function — a few sine waves mashed together with irrational multipliers. it's not real perlin noise but it looks smooth enough and is way simpler to understand. each particle samples the field at its position to get a direction angle, then moves that way. the trail effect is just a transparent black rectangle painted over the canvas every frame instead of clearing it — old dots fade out slowly.

particle count scales automatically to your screen size so it should fill out on any display.

## things to tweak

all the interesting numbers are at the top of the script:

```js
const COUNT = ...      // particles per screen area
const SPEED = 1.8      // how fast particles move
const TRAIL_ALPHA = 0.008  // lower = longer trails
const NOISE_SCALE = 0.003  // lower = wider, lazier curves
const TIME_SPEED = 0.0004  // how fast the field evolves
```

## i have another repository, Canvas, which has all my HTML/digital coding artwork in seperate files.
