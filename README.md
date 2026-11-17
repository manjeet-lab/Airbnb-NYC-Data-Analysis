# Airbnb NYC Data Analysis | Market, Pricing, Host & Availability Insights

**Python · Power BI · Excel (dataset viewing only)**

---

## Executive Snapshot (3-Minute Read)

**Business Context:** Airbnb's NYC market is large (102K listings) and spread across five boroughs, hundreds of neighbourhoods and four room types. This project analyses the listing data to understand **where supply is concentrated, how listings are priced, who the hosts are, and how availability differs across room types.**

**Approach:** The dataset was cleaned and prepared in Python, and the findings were presented in an interactive three-page Power BI dashboard.

> **Important:** This analysis is based on *listing* data. Price is listing price (not revenue), availability is open days (not occupancy), and number of reviews is not bookings. See [Limitations](#-assumptions--limitations).

---

## Dashboard Walkthrough

| Page | Purpose |
|---|---|
| **Overview** | Landing page and navigation |
| **NYC Airbnb Market Overview** | Supply by borough, neighbourhood and room type; average prices |
| **Pricing, Host & Availability Insights** | Price, host activity, ratings, reviews and availability by room type |

**Dashboard Preview**

![Dashboard Overview](images/dashboard_overview.png)

**Page 1: Overview**

![Overview Page](images/overview.png)

**Page 2: NYC Airbnb Market Overview**

![NYC Airbnb Market Overview](images/market_overview.png)

**Page 3: Pricing, Host & Availability Insights**

![Pricing, Host & Availability Insights](images/pricing_host_availability.png)

---

## Key Findings

- **Supply is concentrated in two boroughs.** Manhattan (44K, 42.69%) and Brooklyn (42K, 40.8%) hold about **83.5%** of the 102K listings.
- **Brooklyn has the two largest neighbourhoods.** Bedford-Stuyvesant (7,899) and Williamsburg (7,733) lead, while Manhattan's supply is spread across many neighbourhoods.
- **Two room types dominate.** Entire Home/Apt (53K) and Private Room (46K) make up roughly **97%** of listings.
- **Listing prices are almost identical across boroughs.** The average is $625.35, and the spread between boroughs is only about $5–7 (under 1%).
- **Guests pay about 20% above listing price.** Average total price is $750.39, and the $125.04 gap equals the average service fee.
- **The host base looks commercially operated.** 13K hosts manage 102K listings (about 8 per host), and the largest host has roughly 870 listings.
- **Hotel and shared rooms are open for far more days.** Hotel Room averages 220 available days versus 130 for Private Room.
- **The most-reviewed listings are not the most expensive.** The 501–1000 review band has the lowest average price (about $535).

### Why This Matters

The NYC Airbnb market depends on a small number of boroughs, neighbourhoods and large hosts. Price differences between boroughs and between room types are much smaller than expected, and the real cost to guests is about one-fifth higher than the listing price shows.

---

## Project Overview

This project analyses the **NYC Airbnb listings dataset** to answer one question:

> *What does the NYC Airbnb market look like in terms of supply, pricing, hosts and availability, and what can listing data tell us about it?*

The analysis covers three areas:

1. **Market structure:** listings by borough, neighbourhood and room type
2. **Pricing:** listing price, service fee and total price
3. **Hosts & availability:** host concentration, verification, ratings, reviews and available days

---

## Executive Summary

### Dashboard KPIs

| Metric | Value |
|---|---|
| Total Listings | 102K |
| Total Hosts | 13K |
| Avg Listing Price | $625.35 |
| Avg Total Price | $750.39 |
| Avg Service Fee | $125.04 |
| Highest Listing Price | $1.2K |
| Avg Availability | 133 days |
| Verified Host % | 49.80% |
| Avg Reviews (as labelled on the dashboard) | 2.77 |

### Market Structure


![Market Structure](images/market_structure.png)
- Manhattan 44K (42.69%), Brooklyn 42K (40.8%), Queens 13K (12.93%), Bronx 3K, Staten Island 1K
- Top 10 neighbourhoods hold **47,566 listings** (about 47% of the market)
- Top neighbourhoods: Bedford-Stuyvesant 7,899, Williamsburg 7,733, Harlem 5,441, Bushwick 4,956, Hell's Kitchen 3,950

**Implication:** Almost half of all listings sit in 10 neighbourhoods, so the market is geographically concentrated.

### Pricing


![Pricing](images/pricing.png)
- Average listing price by borough ranges only from just under $625 (Manhattan) to about $630 (Queens)
- Room type averages (approximate, from chart): Hotel Room about $666, Shared Room about $635, Entire Home/Apt and Private Room about $625

**Implication:** Location and room type do not create large price gaps in this dataset.

### Hosts & Availability


![Hosts and Availability](images/hosts_availability.png)
- 13K hosts for 102K listings (about 8 listings per host)
- Average availability by room type: Hotel Room 220, Shared Room 167, Entire Home/Apt 134, Private Room 130 days
- Verified Host %: 49.80%

---

## Insights Deep Dive

### Supply


![Supply by Borough](images/supply_by_borough.png)

- Manhattan and Brooklyn together are about 83.5% of listings. Changes in demand, regulation or host behaviour there would move the whole market.
- The Bronx and Staten Island are under 4% combined.

### Room Types


![Room Types](images/room_types.png)

- Entire Home/Apt is about 52% and Private Room about 45% of listings.
- Hotel Room has the highest price, rating (about 3.5) and availability, but is a very small segment, so its averages may not be stable.
- Shared rooms are priced above entire homes and private rooms, which does not follow the usual product hierarchy.

### Pricing
- Guests pay about 20% above listing price once the service fee is added.
- Listings with very high review counts are priced below average, but this is an association, not a cause.

### Hosts


![Top Hosts](images/top_hosts.png)

- Multi-listing and professional operators (for example, "Sonder (Nyc)" appears in the top 10) account for a large share of supply.
- About half of hosts are verified (49.80%).

---

## Key Analytical Decisions

- **Missing neighbourhoods:** Some missing neighbourhood values were identified using **GeoPandas** (with ChatGPT's guidance) based on coordinates. These are **estimated values**, not exact matches from the original data.
- **Imputed coordinates:** Some coordinates were estimated during cleaning.
- **Business-first framing:** Findings are described as listing-level observations, never as revenue or demand performance.

> Add here: number of rows before and after cleaning, duplicate handling, and any other cleaning steps you applied.

---

## Tools Used

- **Python:** data cleaning and preparation (including GeoPandas for neighbourhood identification)
- **Power BI:** interactive three-page dashboard
- **Excel:** dataset viewing only

---

## ⚠ Assumptions & Limitations

- **Price is listing price,** not revenue. Actual host earnings and Airbnb revenue are not available.
- **Availability is open days,** not occupancy. A high value does not mean a listing was unbooked.
- **Number of reviews is not bookings.**
- **Cancellation policy** does not show actual cancellations.
- **Top 10 neighbourhood totals** represent only those 10 neighbourhoods.
- **Some neighbourhood names and coordinates were estimated** or imputed during cleaning. Neighbourhood-level counts could shift if estimated assignments are wrong.
- **Small segments:** Hotel Room (0K–very few listings) averages may be unstable.
- **Host names:** if hosts were grouped by name, common names may combine several people, and "Unknown" is a data-quality gap rather than a real host.
- Several dashboard charts have truncated axes, so visual gaps look larger than the actual differences.

---

## Repository Structure

```
├── dataset/              # Airbnb NYC dataset
├── notebooks/            # Python cleaning and analysis notebook
├── dashboard/            # Power BI file (.pbix)
├── images/               # Dashboard screenshots
└── README.md
```

> Update this to match your actual folders.

---

## Contact & Feedback

This project was developed as part of a portfolio demonstrating data analysis skills across Python and Power BI.

**Data Analyst:** *Your Name*
**LinkedIn:** *Your LinkedIn link*
**Email:** *Your email*

*Data Source: Airbnb NYC listings dataset (add source link) · Tools: Python · Power BI*
