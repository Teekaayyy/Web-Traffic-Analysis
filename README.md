# Project 09: Website Traffic Analysis
### Understanding How Users Find, Navigate, and Leave a Website

---

## Business Brief

A website generates data on every visit, every page, every source, and every exit. Most businesses look at total session counts and call it analytics. That is not analytics. That is counting.

Real website analysis answers questions that drive product and marketing decisions:

1. Which traffic sources bring the most valuable visitors, not just the most visitors?
2. Where do users drop off in the funnel?
3. Which sources have engagement problems hidden behind good volume numbers?
4. What is the actual quality of traffic from each channel?

---

## Dataset

| Property | Detail |
|----------|--------|
| **Name** | Website Traffic and Engagement Dataset |
| **Direct Link** | https://www.kaggle.com/datasets/anthonytherrien/website-traffic-and-engagement-metrics |
| **Records** | 2,000+ sessions with per-session engagement metrics |
| **Features** | Traffic source, pages visited, session duration, bounce, conversions |

---

## What Makes This Different

- Fully adaptive column detection, no hardcoded column names
- Builds a Traffic Quality Score combining four engagement signals
- Funnel analysis showing drop-off at each engagement stage
- Identifies the volume-quality mismatch, sources that inflate metrics without value
- All SQL queries are built dynamically based on which columns exist

---

## Project Structure

```
website-traffic-analysis/
├── project_09_web_traffic.ipynb
└── README.md
```

---

## Kaggle Setup

1. Search **"website-traffic-and-engagement-metrics"** by *anthonytherrien* on Kaggle and attach it
2. Upload `project_09_web_traffic.ipynb`
3. Run the path finder cell first
4. Update `DATA_PATH` in Cell 3 if needed
5. Run all cells

---

## Notebook Walkthrough

### Section 1: Setup
Libraries, colour system. Each traffic source type has a dedicated colour (organic = green, paid = indigo, social = amber, direct = blue, email = purple, referral = pink).

### Section 2: Load Data
Auto-detects CSV files. Tries multiple encodings.

### Section 3: Prepare and Standardise
Standardises column names. Auto-detects source, session, bounce, duration, pages, and conversion columns by keyword search. Converts numeric columns. Cleans and title-cases source names.

### Section 4: SQL Traffic Analysis
Two SQL queries built dynamically based on detected columns:
- Source performance (sessions, bounce rate, avg duration, avg pages, conversion rate)
- Engagement depth ranking by session duration

### Section 5: Traffic Analysis Charts
Three visualisations:
- Sessions and bounce rate side-by-side horizontal bar charts (bounce bars colour-coded green/amber/red)
- Session duration box plot by source with notched display
- Pages per session and conversion rate grouped bar charts

### Section 6: Traffic Quality Score
Composite score built from up to four signals with documented weights:
- Conversion rate (40%)
- Session duration (25%)
- Pages per session (20%)
- Bounce rate inverted (15%)

Weights are normalised automatically if some columns are missing. Interactive scatter plotting quality score vs volume share. Identifies volume-quality mismatches. Horizontal bar chart with colour-coded tiers.

### Section 7: Engagement Funnel
Builds a funnel from available columns: all sessions, not bounced, multi-page, above median duration, converted. Plotly funnel chart with percentage of total at each step.

### Section 8: Executive Summary Dashboard
Dark-theme KPI cards: total sessions, top volume source, best quality source, avg bounce rate, avg session duration, overall conversion rate.

### Section 9: Findings and Recommendations
Five findings with evidence. Four recommendations with specific actions.

---

## Key Findings

| Finding | Evidence |
|---------|----------|
| Volume and quality are not the same metric | Quality score vs volume scatter |
| Bounce rate varies significantly by source | Source performance chart |
| Some sources have above-average volume but below-average quality | Mismatch detection |
| Most session abandonment happens at the first funnel stage | Funnel analysis |
| A composite quality score surfaces underappreciated channels | Quality score ranking |

---

## Tools Used

| Tool | Purpose |
|------|---------|
| Python (Pandas, NumPy) | Data manipulation, adaptive column detection |
| SQLite3 | Dynamic source performance queries |
| Plotly | Funnel chart, scatter, dual-panel charts |
| Matplotlib | Quality score bar chart, overview panels |

---

*Built by Jessica Dan-Odhomo - [LinkedIn](https://www.linkedin.com/in/jessica-dan-odhomo) - [GitHub](https://github.com/Teekaayyy)*
