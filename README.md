# Plant View

Live condenser plant view for two demonstration units — an interactive
schematic with per-area sensor readings and a time-series chart

**Open it:** https://cramalamb.github.io/es-plant-view/
(dark control-room version: https://cramalamb.github.io/es-plant-view/dark.html)

- **Sample A** — single-pressure, single-pass, twin-bank surface condenser
  with a divided West/East waterbox and eight metered steam-side bundles.
- **Sample B** — twin-shell, dual-pressure, single-pass condenser with the
  circulating water routed in series through the L.P. and H.P. shells

Click any sensor chip or bundle diamond to chart it; switch ranges
(24h / 7d / 30d), open the data table, or let the idle auto-tour drive.
Deep-linkable state: `?plant=B&preset=ttd&range=30d` or `?sensor=b03`

A single self-contained HTML file — no build, no server, no network.
All telemetry is synthesized from each specification's design point;
no plant-identifying data. To chart real data instead, see
[data/README.md](data/README.md)
