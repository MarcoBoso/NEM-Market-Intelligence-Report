# Price Formation and Risk in the NEM

A reproducible R Markdown report that analyses wholesale electricity prices across the five
regions of Australia's National Electricity Market (NSW1, QLD1, SA1, TAS1, VIC1) using AEMO's
public dispatch data. The current version covers 1 May to 4 October 2026
(157 days, about 226,000 five-minute observations).

## What it covers

- Price behaviour: monthly averages, share of negative-price intervals, hourly "duck curve"
  and the largest price spikes
- Forecasting: hourly price forecast with an 80% uncertainty band using quantile regression,
  compared against a same-hour-last-week baseline
- Demand: typical daily demand shapes by region using k-means clustering
- Market analytics: price duration curves, regional price premium by hour, solar shape
  discount (stylised profile), price response to demand and the historical payoff of a cap

## How to run

1. Install the R packages listed in the setup chunk
2. Set `FIRST_DATE` and `LAST_DATE` in the settings section
3. Knit `nem_dashboard.Rmd`

The first run downloads AEMO's daily archive files and caches each day in `data/raw`,
so later runs only fetch new days.

## Notes

- The solar shape discount uses a stylised solar profile and not actual plant output
- Results are historical and descriptive, not market quotes or investment advice
- Data source: AEMO NEMweb (public)
