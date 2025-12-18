---
layout: home
title: Wall Street's Secret Calendar
subtitle: Analyzing the Seven Calendar-Effect Anomalies in NASDAQ Since 1962
---

# Have you ever heard these phrases?

“Mondays are cursed.” “January is magic.” “Santa always shows up.” “Sell in May and go away.”
If you’ve ever heard those lines (or traded like you believed them), you’re not alone … but you might be trading a myth.

Welcome to NASDAQ’s secret calendar: where timing is everything, and the market may (or may not) have habits it can’t shake.

**So… what are we doing here?**
Think of us as your mythbusting team for stock market folklore. We’re putting seven famous “calendar effects” on trial using daily NASDAQ stock data since 1962:

- Monday effect
- January effect
- Santa Claus Rally
- Turn-of-the-Month
- Half-Month
- Halloween effect (“Sell in May”)
- Holiday effect

## How?

By digging into patterns across millions of trading days, we’ll compare returns inside each calendar window versus outside it to spot the patterns, then we’ll check if it is real by stronger statistical tests, then we will turn up the difficulty and use regressions that account for the fact that many stocks move together on the same trading day, and test robustness with controls like volatility, interest rates (Fed Funds), and inflation (CPI). Finally we want to see where they live by breaking the results down by decade and exchange to see what’s stable (and what fades).

In other words:
We start with the folklore… and keep only what survives the data.

## What we want to find?

**Do calendar effects show up in NASDAQ stocks? and which ones survive strickter checks?**

We will explore this question by answering these subquestions:

1. Which of the seven calendar effects appear in NASDAQ returns since 1962?
2. Which effects remain after stricter inference (e.g., regressions with clustered standard errors)?
3. Are these effects consistent across decades, or do they weaken/flip over time?
4. Do these effects differ across exchanges (e.g., NASDAQ vs NYSE listings in your dataset metadata)?
5. Do volatility and macro conditions (Fed Funds, CPI) meaningfully change the estimated effects?

## Where does our data come from?

If we’re going to put market folklore on trial, we’d better bring serious evidence.

All of our analysis is built on a **large-scale historical dataset of NASDAQ-traded securities**, compiled from Yahoo Finance and distributed on Kaggle. It covers **daily price data from January 1962 to April 1st, 2020**, spanning nearly six decades of market history.

In concrete terms, the dataset includes **5,879 unique tickers** and more than **24 million daily observations**, with each stock observed for an average of **over 4,000 trading days**. This isn’t a hand-picked collection of “interesting” names or a short window chosen to make patterns look good — it’s the market, day after day, through booms, crashes, bubbles, and recoveries.

---

## Why this dataset works for calendar effects

Calendar anomalies are subtle by nature. If they exist at all, they tend to be **small, noisy, and easy to overstate**.

That’s exactly why scale matters:

- **Long time span** → lets us test whether effects persist or fade over time
- **Large cross-section** → reduces the risk that results are driven by a few unusual stocks
- **Daily frequency** → aligns precisely with calendar-based trading rules

Together, these dimensions give us enough statistical power to separate **real patterns** from **lucky coincidences**.

<!-- ---

## A quick reality check

Of course, no dataset is perfect. Prices are observed at daily frequency, and the sample ends in 2020 — meaning the most recent market episodes fall outside our scope.

But for a project focused on **historical regularities and their robustness**, this dataset is more than sufficient. If calendar effects truly shaped market behavior, they should leave footprints here.

And if they don’t?

That’s a result too.

--- -->

From here on, we stop talking about data and start asking the uncomfortable question:

**Which of these famous market “rules” actually survive contact with the numbers?**

➡️ _Let’s find out._
