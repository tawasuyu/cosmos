# cosmos

> Pure astrometry + astrology engine — ephemeris, sky, sundial, tides, transits — in Rust, with a [Llimphi](https://github.com/tawasuyu/llimphi) UI.

`cosmos` computes the sky. Around a core astrology engine sit independent astrometric extracts — `cosmos-ephemeris`, `cosmos-sky`, `cosmos-sundial`, `cosmos-tides`, `cosmos-transits`, `cosmos-pointing` — that serve sundial / tides / navigation / planning without touching the chart machinery. A GPU UI (`cosmos-app-llimphi`, `cosmos-canvas-llimphi`) renders charts, sky maps and a dense starfield.

<p align="center">
  <img src="docs/cosmos_showreel.gif" alt="cosmos showreel — a natal chart wheel drawing in with zodiac ring, planets and aspect lines, then a data panel of positions and aspects" width="900">
  <br>
  <sub>the real natal wheel (zodiac ring, planets, aspect lines) computed by the VSOP2013 engine, with live positions &amp; aspects</sub>
</p>

## Run

```sh
cargo run --release -p cosmos-app-llimphi              # the chart/sky desktop app
cargo run --release -p cosmos-canvas-llimphi --example dense_starfield
```

## How dependencies work

cosmos is a full app: its UI integrates notebooks, panels and content-addressed sources. Llimphi and every foundational dependency are pulled as git dependencies from the [`tawasuyu`](https://github.com/tawasuyu/tawasuyu) monorepo — the suite's source of truth. The astrometric core crates (`cosmos-ephemeris`, `-coords`, `-time`, …) are pure compute with no UI deps.

## License

MIT. Builds on [Llimphi](https://github.com/tawasuyu/llimphi) and the [tawasuyu](https://github.com/tawasuyu/tawasuyu) suite.
