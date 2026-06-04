# cosmos

> Pure astrometry + astrology engine — ephemeris, sky, sundial, tides, transits — in Rust, with a [Llimphi](https://gitea.gioser.net/sergio/llimphi) UI.

`cosmos` computes the sky. Around a core astrology engine sit independent astrometric extracts — `cosmos-ephemeris`, `cosmos-sky`, `cosmos-sundial`, `cosmos-tides`, `cosmos-transits`, `cosmos-pointing` — that serve sundial / tides / navigation / planning without touching the chart machinery. A GPU UI (`cosmos-app-llimphi`, `cosmos-canvas-llimphi`) renders charts, sky maps and a dense starfield.

## Run

```sh
cargo run --release -p cosmos-app-llimphi              # the chart/sky desktop app
cargo run --release -p cosmos-canvas-llimphi --example dense_starfield
```

## How dependencies work

cosmos is a full app: its UI integrates notebooks, panels and content-addressed sources. Llimphi and every foundational dependency are pulled as git dependencies from the [`gioser`](https://gitea.gioser.net/sergio/gioser) monorepo — the suite's source of truth. The astrometric core crates (`cosmos-ephemeris`, `-coords`, `-time`, …) are pure compute with no UI deps.

## License

MIT. Builds on [Llimphi](https://gitea.gioser.net/sergio/llimphi) and the [gioser](https://gitea.gioser.net/sergio/gioser) suite.
