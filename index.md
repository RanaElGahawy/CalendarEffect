---
layout: home
title:  Market Detectives - Investigating Calendar Effects 
subtitle: Analyzing Seven Calendar-Effect Anomalies in NASDAQ Since 1962
---

# Market detectives

Over the past decades, academic studies and market commentary have documented recurring patterns in stock returns linked to the calendar. These so-called calendar effects have sparked long-standing debates about their existence, persistence, and economic relevance
Despite the large body of literature, there is still no clear consensus on whether these effects represent genuine market inefficiencies or merely statistical artifacts that fade once widely known. Some studies argue that calendar effects reflect behavioral biases and institutional trading practices, while others suggest that they weaken over time as markets become more efficient. This is when our team of market detectives Furkan, Aitor, Rana, Zouhair and Melvyn appear, also called the FARZM.  
<p align="center">
  <img src="assets/img/melvyln_detective.jpeg" width="250">
</p>
<p align="center">
  <img src="assets/img/detective_zouhair.jpeg" width="250">
</p>



The FARZM set out to investigate these calendar effects. Armed with data and a passion for uncovering hidden market truths, FARZM are on a mission: to determine whether calendar effects still hold power in modern and if they exist.
- Monday effect
- January effect
- Santa Claus Rally
- Turn-of-the-Month
- Half-Month
- Halloween effect (“Sell in May”)
- Holiday effect

## Getting an initial sense of the calendar effects

The detectives begin with an initial exploratory analysis aimed at visualizing potential calendar effects. 

// plots demonstrating each effect //

The visual evidence reveals several intriguing regularities. Returns appear to differ depending on the timing within the trading week, with certain days consistently exhibiting weaker performance than others. Seasonal variations also emerge, as returns during the early part of the year seem marginally higher compared to the remainder of the sample. These patterns are consistent with what the literature commonly refers to as calendar effects.

( //Interpretation //) Indeed, plots demonstrate ____ .
 For each calendar effect, average returns are computed and compared across relevant time periods. By examining these averages, the team aims to determine whether any of the proposed calendar effects already appear detectable at the mean level.

Of course, simply looking at mean returns is not sufficient to conclude whether a calendar effect is real or statistically valid. Average differences may offer intuition, but they do not prove significance. These preliminary comparisons serve only as an initial diagnostic.  

  <img src="assets/img/mean_interro.png" width="500">
</p>


The crucial question of whether these calendar effects are statistically significant needs to be investigated. This requires moving beyond visual evidence to formal statistical testing.

## Are the Calendar effects real ? 

Reinforced by rigorous statistical tools, the detectives conduct an in-depth investigation into each calendar effect. 

<p align="center">
  <img src="assets/img/regression_intero.jpeg" width="500">
</p>

Every suspected calendar anomaly is subjected to rigorous evaluation through formal hypothesis testing. In particular, t-tests are employed to determine whether average returns during specific calendar periods differ significantly from those observed in the rest of the sample. t-tests are employed to determine whether average returns during specific calendar periods differ significantly from those observed in the rest of the sample.
For these tests to be valid, several underlying assumptions must be satisfied, most notably the normality and independence of the data. To ensure the validity of the statistical tests, the investigation begins with a careful assessment of these assumptions. In particular, the normality of returns is examined prior to conducting the hypothesis tests.

// Plots of normality check//

Interpretation of the normality check

// Results of t-tests //             

Interpretation of t-tests

When the assumption of normality is violated, the Mann–Whitney U test, a non-parametric alternative, is employed to compare return distributions across calendar periods. This approach allows the investigation to remain robust to deviations from normality.

  // Results of Mann-Whitney test //

  Interpretation of Mann-Whitney test


To further strengthen the analysis, these tests are complemented by regression models that isolate the calendar component while controlling for other market dynamics (volume, volatility, fed funds rate).

// Results of regression //

By estimating the statistical significance and magnitude of each effect, the detectives discovered that____ (interpretation of regressions)

// Conclude on real effects, stated by FARMZ //


## Do the calendar effect survive in time ?


## Calendar effect during crises ?

## Calendar effects through excahnges 
<!-- ---

## A quick reality check

Of course, no dataset is perfect. Prices are observed at daily frequency, and the sample ends in 2020 — meaning the most recent market episodes fall outside our scope.

But for a project focused on **historical regularities and their robustness**, this dataset is more than sufficient. If calendar effects truly shaped market behavior, they should leave footprints here.

And if they don’t?

That’s a result too.

--- -->

From here on, we stop talking about data and start asking the uncomfortable question:

**Which of these famous market “rules” actually survive contact with the numbers?**
_Let’s find out._

## Before anything else: what do we mean by a “calendar effect”?

Before testing whether markets really have a favorite day, month, or holiday, we need to be clear about one thing:

**What exactly counts as a calendar effect?**

In finance folklore, calendar effects are often described in vague terms:
“Mondays are bad.”  
“January is special.”  
“Stocks go up before holidays.”

That’s a nice story — but stories don’t run regressions.

---

## From folklore to measurable objects

In our analysis, a calendar effect is defined as a **systematic difference in stock returns** that depends _only_ on where a trading day falls on the calendar.

Concretely, this means comparing:

- **Returns inside a specific calendar window**  
  (e.g., Mondays, January trading days, pre-holiday sessions)

versus

- **Returns outside that window**, over the same time period

If returns inside the window are consistently higher (or lower) than outside — _and this difference survives statistical scrutiny_ — then we say the calendar effect exists.

---

## Measuring returns

We focus on **daily stock returns**, computed from _adjusted closing prices_ to properly account for dividends and stock splits. For each stock, daily returns are defined as:

$$
R_{t} = \frac{\text{AdjClose}_{t} - \text{AdjClose}_{t-1}}{\text{AdjClose}_{t-1}}
$$

Using daily data allows us to:

- Match calendar rules precisely
- Avoid assumptions about intraday timing
- Stay consistent across decades and across thousands of stocks

Each trading day becomes one observation, labeled according to its calendar position (weekday, month, holiday proximity, etc.), which allows us to systematically compare returns **inside** and **outside** calendar windows.

---

## Why comparison matters

Markets move for many reasons — firm-specific news, macroeconomic shocks, changes in monetary policy.  
Looking at raw returns alone would be misleading.

That’s why calendar effects are always measured **relative to a baseline**:
how stocks behave _when the calendar rule does not apply_.

This comparison-based approach helps ensure that any detected effect is:

- Not driven by a handful of extreme days
- Not an artifact of overall market trends
- Not just randomness wearing a seasonal costume

---

## Accounting for the broader market environment

Calendar effects do not operate in a vacuum. Broader economic conditions evolve over time and can influence returns in systematic ways.

To separate calendar-based patterns from macroeconomic influences, we later extend our analysis by controlling for:

- **Inflation**, measured using U.S. consumer price inflation (CPI)
- **Monetary policy conditions**, proxied by the Federal Funds Effective Rate

These variables allow us to test whether calendar effects persist once we account for changing inflation and interest rate regimes. At this stage, they remain in the background — but they play a key role when we move from simple comparisons to regression-based analysis.

---

## From definition to testing

With definitions in place, we gradually raise the bar:

1. Start with simple comparisons of average returns
2. Move to formal statistical tests
3. Estimate regressions that account for cross-stock dependence
4. Test robustness across decades, exchanges, and market conditions

Only effects that survive all of these steps earn the right to be called “real”.

---

With definitions out of the way, we can finally ask the question that matters:

**Do calendar effects actually exist — or do they disappear once we measure them carefully?**

## Do calendar effects survive through the years?

Now that we have detected and analyzed several calendar effects, a natural question arises: **do these patterns remain stable over time, or do they evolve as markets change?**

Calendar anomalies are often presented as timeless rules — but real financial markets rarely stay constant. Trading technology evolves, regulations shift, investor composition changes, and macroeconomic regimes come and go. Any of these forces can influence whether an anomaly strengthens, weakens, or disappears entirely.

In this section, we investigate the **temporal stability** of each calendar effect. More precisely, we ask:

- Do the effects behave similarly in the 1970s, 1980s, 1990s, and 2000s?  
- Do some grow stronger or weaker across decades?    
- And crucially: **which calendar effects survive consistently over time, and which ones vanish once they become widely known?**






