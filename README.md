# 🌊 FloodReady

FloodReady alerts residents of **Yeronga, Brisbane** when the Brisbane River reaches a dangerous level.

## What it does (this sprint)

One feature: it checks the water level and shows an alert when the level reaches the danger level.

## How to run it

1. Download `index.html`.
2. Double-click it to open it in your web browser.

That's it. There's nothing to install.

## How it works

The code is in `index.html`, inside the `<script>` tag. It runs one function, `checkWaterLevel()`, which:

1. **Gets the data** from the API, or from sample data if no API is set yet
2. **Reads the water level** from the JSON reply
3. **Shows** the level on the page
4. **Decides** whether it's safe or dangerous, and pops up an alert if it's dangerous

The function runs when the page opens and then every 10 minutes.

## Where to add the BOM API

Look for the 👉 markers in `index.html`:

- `const BOM_API_URL = "";` – put the live data address between the quotes.
- `data.observations.data[0].water_level_m` – change this if the real JSON uses different field names.

## Testing the alert

Change the number in `SAMPLE_DATA` (currently `2.1`):

- Below `1.7` → shows **Safe**
- `1.7` or above → shows **DANGER** and pops up an alert

## Known limitation

BOM publishes river heights as web pages, not as JSON, and browsers block websites from reading BOM's data directly (this is called CORS). Live data will need either a browser-friendly source, such as Brisbane City Council's open data API, or a small proxy server. That's planned for a future sprint.

## Data source

Flood level for the Brisbane River City Gauge (BOM station 540198). Data © Bureau of Meteorology.
