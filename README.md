# Excel Stopping Distance Curve Fit

Interactive HTML version of an Excel measurement-analysis worksheet for vehicle stopping distances. The project uses measurement data, charting, polynomial curve fitting, and extrapolation to estimate vehicle stopping distance at higher speeds.

## Project purpose

This project demonstrates how spreadsheet-based measurement analysis can be converted into a small interactive browser tool. The original task focused on using Excel charts and curve fitting to estimate the stopping distance of a car on a wet road surface at 150 km/h.

The repository presents the work as an independent data-analysis project rather than as a school worksheet. The original spreadsheet file is not included; the public project contains the interpreted dataset, documentation, and an interactive HTML implementation.

## Interactive tool

The main interactive version is in [`index.html`](index.html).

The tool allows the user to:

- select a road surface: dry, wet, snowy, or icy
- inspect the measured reaction, braking, and stopping distances
- view a chart of stopping distance against speed
- fit a second-degree polynomial trendline to the selected surface
- estimate stopping distance at a custom speed such as 150 km/h

## Primary analysis

The original assignment focused on wet road conditions. For the wet-road dataset, the stopping distance is calculated from:

```text
stopping distance = reaction distance + braking distance
```

Wet-road measurement data:

| Speed (km/h) | Reaction distance (m) | Braking distance (m) | Stopping distance (m) |
|---:|---:|---:|---:|
| 30 | 8 | 6 | 14 |
| 40 | 11 | 10 | 21 |
| 50 | 14 | 16 | 30 |
| 60 | 17 | 23 | 40 |
| 80 | 22 | 41 | 63 |
| 100 | 28 | 64 | 92 |
| 120 | 33 | 93 | 126 |

The 150 km/h value is an extrapolated estimate because it is outside the original 30–120 km/h measurement range.

## Calculation method

The browser version performs the following steps:

1. Stores the measurement table as structured JavaScript data.
2. Calculates stopping distance from reaction and braking distances.
3. Filters the dataset by selected road surface.
4. Fits a second-degree polynomial curve to the selected points.
5. Uses the fitted curve to estimate stopping distance at the selected speed.
6. Draws both measurement points and fitted trendline on a canvas chart.

## Why polynomial curve fitting is used

Stopping distance does not grow linearly with speed. Reaction distance grows approximately with speed, while braking distance grows much faster. A polynomial trendline gives a practical spreadsheet-style way to model this relationship and continue the curve beyond the measured values.

## Files

| File | Description |
|---|---|
| [`index.html`](index.html) | Interactive stopping-distance analysis tool |
| [`README.md`](README.md) | Project documentation |
| [`LICENSE`](LICENSE) | MIT License |

## Source material policy

The original spreadsheet was used as working material only and is intentionally not included in this repository. The public repository keeps the project focused on the cleaned dataset, the analysis method, and the interactive implementation.

## Skills demonstrated

- Excel-style measurement analysis
- Data cleaning and interpretation
- Chart-based analysis
- Polynomial curve fitting
- Extrapolation from measured data
- HTML/CSS/JavaScript implementation
- Canvas-based chart drawing
- Technical documentation

## License

MIT License
