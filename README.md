# A day on the fire & medical radio — NYC FDNY explorer

Pick any New York City police precinct and any day, and this pulls every FDNY run there that
day — ambulances and fire units — from the city's own dispatch records, and rebuilds the hourly
timeline, the call mix and the response-time breakdown. The companion to the
[police 911 explorer](https://joshgreenman1973.github.io/nyc-precinct-day/).

**Live:** https://joshgreenman1973.github.io/nyc-fire-medical-day/

## Data

- **EMS (medical):** FDNY [EMS Incident Dispatch Data](https://data.cityofnewyork.us/Public-Safety/EMS-Incident-Dispatch-Data/76xm-jjuj) (`76xm-jjuj`).
- **Fire:** FDNY [Fire Incident Dispatch Data](https://data.cityofnewyork.us/Public-Safety/Fire-Incident-Dispatch-Data/8m42-w767) (`8m42-w767`).
- Both carry a `policeprecinct` field, so runs filter to the same precincts as the police version.
- Queried live in the browser for the precinct, date and service you choose.
- **Coverage:** through March 31, 2026 — fresher than the police calls feed (which ends Dec 2025).

## Method & limits

- **No map.** FDNY dispatch records are **not geocoded to a point** (medical privacy); location is
  ZIP + precinct only. So this companion leads with time and response, not a dot map.
- **Response time** = incident-created to first-unit-on-scene, using FDNY's own response-second
  fields, for runs FDNY flags as having a valid response time.
- **EMS urgency (severity 1–8):** 1 is most life-threatening, 8 least — FDNY's own scale, and the
  data bears it out (severity 1–3 reach the scene fastest; 4+ can wait far longer). "Life-threatening"
  here means severity 1–3.
- **EMS call types** use FDNY's initial call-type codes; plain-language labels are shown for the
  common ones, the raw code otherwise.
- **Medians, not means** — a long tail of low-acuity runs skews the averages.
- **No outcomes**, and **not linked** to the police calls at the record level — a same-day, same-place
  companion, not a matched one.

Map tiles: none. A single day is a snapshot, not a typical pattern.
