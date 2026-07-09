# Rate Drift

A tiny, live currency-movement tool built for the five-day build challenge.

**Option chosen:** Option 1 : API Tool + Chat/Form (weight ×1.00)

**Live link:** (https://johannjames25.github.io/rate-drift/)
## What it does
We enter an amount and pick a "from" and "to" currency. The tool:
1. Looks up today's exchange rate (Frankfurter v1 API, which serves European Central Bank data).
2. Looks up the rate from 7/30/90 days ago (your choice) for the same pair.
3. Computes the converted amount and the percentage change between the two dates.
4. Returns one plain-language sentence stating whether the currency strengthened, weakened, or held steady — not a raw JSON blob.
5. For any pair not involving EUR, makes one more lookup and shows the actual cross-rate arithmetic: the ECB only publishes rates against the euro, so a pair like USD→INR is derived by dividing one euro rate by another. The tool shows that math openly instead of hiding it behind a single number.

It also handles a couple of edge cases gracefully: picking the same currency twice, entering an invalid amount, and the API being briefly unreachable or missing data for a date.

## What I cut and why
- **No historical chart.** A line chart would make the trend easier to see at a glance, but it adds a charting dependency and more edge cases (missing days, axis scaling) than I could finish cleanly in the time budget. A single stated percentage change gets the same core insight across reliably.
- **Fixed currency list (13 currencies) instead of the full ~30 Frankfurter supports.** I kept the dropdown to the currencies most people would actually ask about, to keep the UI simple rather than exhaustive.
- **No MCP tool wrapper (the optional stretch goal).** Given the time budget, I prioritized finishing the core interactive tool and the full submission bundle (citations, one-pager, recording) over the optional stretch.

## Files in this repo
- `index.html` — the artifact + live front-end (open directly, or serve via GitHub Pages)
- `CITATIONS.md` — the Citation Ledger
- `ONE_PAGER.md` — the one-pager for a non-technical reader
- `README.md` — this file
