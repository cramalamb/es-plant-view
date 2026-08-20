# Real telemetry drop-in

`plant-view.html` runs on synthesized telemetry anchored to each sample's
design point. To swap in real data (e.g. the OneDrive dataset), put a
`plant-data.js` file in this folder — the page loads it automatically
(a missing file is harmless; the 404 in the console can be ignored).

Format — arrays are oldest→newest, one value per 10-minute step, 4,320
points (30 days). Shorter arrays work; the page charts what it gets.

```js
window.PLANT_DATA = {
  A: {
    series: {
      cwIn:   [...],  // CW inlet, °F
      cwOut:  [...],  // CW outlet mean, °F (used for Tsat/TTD)
      cwOutW: [...],  // CW outlet West nozzle, °F
      cwOutE: [...],  // CW outlet East nozzle, °F
      bp:     [...],  // back pressure, inHgA
      ttd:    [...],  // terminal temperature difference, °F
      air:    [...],  // air off-take, SCFM
      b01: [...], /* … */ b08: [...]  // bundle ΔP, inH₂O
    }
  },
  B: {
    series: {
      cwIn: [...], cwMid: [...], cwOut: [...],
      bpLP: [...], bpHP: [...], ttd: [...], air: [...]
    }
  }
};
```

Only plants/keys you provide are overridden; anything missing falls back
to the synthesized series. Raw exports (CSV/XLSX) can be converted to this
file with a small script — ask Claude to do the conversion once the
download from OneDrive lands in this folder.
