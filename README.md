# Finnair Network Performance, November 2024 to August 2026

A one-page Power BI analysis of Finnair's public monthly traffic data. It looks at what happened to capacity, load factor and revenue per RPK after Finnair suspended its flights to Doha and Dubai on 28 February 2026.

![Dashboard preview]()

**Full report:** [Finnair_Network_Performance.pdf]()

## What the analysis shows

- In March 2026, the first month after the suspension, Asia load factor reached **93.8%**, up 18.4 points year on year.
- Network traffic (RPK) grew 15.7% in March. Asia contributed 14.9 points of that growth, Europe 5.7, and the Middle East took away 4.7.
- Implied revenue grew 24.2% in March, or 21.7 log points: capacity explains 2.3, load factor 12.2 and revenue per RPK 7.1. So fuller aircraft drove the increase.
- From April to August, revenue per RPK became the main driver, up about 7% to 11% a year, while capacity moved between roughly −5% and +5%.
- Passenger volumes in January to August 2026 were 86% of the same months in 2019.

## Next step

In my bachelor's thesis I used Monte Carlo simulation and Simulation Decomposition (SimDec) to find which uncertain assumptions drive an investment decision ([interactive walkthrough](https://karina-kovtun-thesis.netlify.app/), [Python replication](https://github.com/kovkarina9-blip/recruitment-decision-under-uncertainty)). The natural extension of this report is to model uncertainty in capacity, load factor and revenue per RPK, and show which of them drives the risk in a revenue forecast.

## Method

- **Data.** Finnair's monthly traffic performance releases, 2019 to 2026, collected from the public release archive on mfn.se. Regional detail covers November 2024 to August 2026; earlier releases give network passengers and load factor only.
- **Revenue decomposition.** Finnair defines RASK as revenue per available seat kilometre, so implied revenue = ASK × RASK. Revenue growth is split into capacity (ASK), load factor (RPK / ASK) and revenue per RPK. The split uses log changes, so the three effects add up exactly to the total.
- **Load factor** is always computed as total RPK divided by total ASK, so a small region carries its true weight.
- **Limitations.** ASK and RPK use great-circle distances, so longer routings around closed airspace are missing from both. RASK covers all revenue, so revenue per RPK is a proxy for yield. July 2026 RASK is unavailable. August 2019 passengers are derived from the August 2020 release.
## Files

- `Finnair_Network_Performance.pdf`: the report

## How it was built

Data collection and method guidance were assisted by Claude. The Power BI data model, measures and report are my own work.

This is an independent analysis of public data. 

Karina Kovtun · [LinkedIn](https://www.linkedin.com/in/karina-kovtun) · November 2026
