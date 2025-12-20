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

Profile of each suspect pattern

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


## Calendar effect during crises ?

The detectives turn their attention to the darkest moments in market history: Black Monday in 1987, the dot-com crash of 2000–2002, and the global financial crisis of 2008–2009. As they examine the data, familiar calendar patterns begin to fade.
Market crises are special periods. Volatility is high. Uncertainty dominates. 

// PLots //

Visual evidence suggests that many patterns become weaker. Large price swings dominate returns, leaving little space for predictable calendar behavior. T This is confirmed by low OLS coefficients, showing that volatility weakens average return patterns.

## Calendar effects through exchanges 
<!-- ---

## A quick reality check

Of course, no dataset is perfect. Prices are observed at daily frequency, and the sample ends in 2020 — meaning the most recent market episodes fall outside our scope.

But for a project focused on **historical regularities and their robustness**, this dataset is more than sufficient. If calendar effects truly shaped market behavior, they should leave footprints here.

And if they don’t?

That’s a result too.

--- -->

## Do calendar effects survive through the years?

Now that we have detected and analyzed several calendar effects, a natural question arises: **do these patterns remain stable over time, or do they evolve as markets change?**

Calendar anomalies are often presented as timeless rules — but real financial markets rarely stay constant. Trading technology evolves, regulations shift, investor composition changes, and macroeconomic regimes come and go. Any of these forces can influence whether an anomaly strengthens, weakens, or disappears entirely.

In this section, we investigate the **temporal stability** of each calendar effect. More precisely, we ask:

- Do the effects behave similarly in the 1970s, 1980s, 1990s, and 2000s?  
- Do some grow stronger or weaker across decades?    
- And crucially: **which calendar effects survive consistently over time, and which ones vanish once they become widely known?**






