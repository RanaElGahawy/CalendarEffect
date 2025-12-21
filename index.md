---
layout: home
title:  Market Detectives - Investigating Calendar Effects 
subtitle: Analyzing Seven Calendar-Effect Anomalies in NASDAQ Since 1962

use-site-title: true
mathjax: true
---
{% include budget_chart.html %}

# Market detectives

Over the past decades, academic studies and market commentary have documented recurring patterns in stock returns linked to the calendar. These so-called calendar effects have sparked long-standing debates about their existence, persistence, and economic relevance
Despite the large body of literature, there is still no clear consensus on whether these effects represent genuine market inefficiencies or merely statistical artifacts that fade once widely known. Some studies argue that calendar effects reflect behavioral biases and institutional trading practices, while others suggest that they weaken over time as markets become more efficient. This is when our team of market detectives Furkan, Aitor, Rana, Zouhair and Melvyn appear, also called the FARZM.  

<style>
.team5{max-width:1100px;margin:2.5rem auto;padding:0 1rem;font-family:system-ui}
.team5-grid{display:grid;grid-template-columns:repeat(5,1fr);gap:14px}
@media(max-width:1100px){.team5-grid{grid-template-columns:repeat(3,1fr)}}
@media(max-width:760px){.team5-grid{grid-template-columns:repeat(2,1fr)}}
@media(max-width:520px){.team5-grid{grid-template-columns:1fr}}

.team5-card{background:#fff;border:1px solid rgba(0,0,0,.1);border-radius:16px;overflow:hidden;cursor:pointer}
.team5-card img{width:100%;height:180px;object-fit:cover;display:block}
.team5-body{padding:10px 12px}
.team5-name{margin:0;font-weight:700;font-size:.98rem}
.team5-role{margin:6px 0 0;font-size:.85rem;opacity:.7}

.team5-backdrop{position:fixed;inset:0;background:rgba(0,0,0,.55);display:none;align-items:center;justify-content:center;z-index:9999}
.team5-backdrop.open{display:flex}
.team5-modal{background:#fff;border-radius:16px;max-width:720px;width:100%;overflow:hidden}
.team5-modalTop{display:grid;grid-template-columns:140px 1fr;gap:14px;padding:14px;background:#fafafa}
.team5-modalTop img{width:100%;aspect-ratio:1/1;object-fit:cover;border-radius:12px}
.team5-story{padding:14px;font-size:.98rem;line-height:1.5}
.team5-actions{text-align:right;padding:12px}
.team5-btn{border:1px solid rgba(0,0,0,.15);background:#fff;border-radius:12px;padding:8px 12px;cursor:pointer}
</style>

<div class="team5">
<div class="team5-grid">

<div class="team5-card" data-name="Zouhair" data-role="Investigation Lead"
data-img="assets/img/littlezouhair.png"
data-story="Zouhair works on.">
<img src="assets/img/littlezouhair.png">
<div class="team5-body"><p class="team5-name">Zouhair</p><p class="team5-role">Investigation Lead</p></div>
</div>

<div class="team5-card" data-name="Melvyn" data-role="Paris"
data-img="assets/img/littlemelvyn.png"
data-story="Melvyn builds .">
<img src="assets/img/littlemelvyn.png">
<div class="team5-body"><p class="team5-name">Melvyn</p><p class="team5-role">Paris</p></div>
</div>

<div class="team5-card" data-name="Furkan" data-role="Paris"
data-img="assets/img/littlefurkan.png"
data-story="Furkan works on ">
<img src="assets/img/littlefurkan.png">
<div class="team5-body"><p class="team5-name">Furkan</p><p class="team5-role">Paris</p></div>
</div>

</div>
</div>

<div class="team5-backdrop" id="m">
<div class="team5-modal">
<div class="team5-modalTop">
<img id="mi"><div><strong id="mt"></strong><br><span id="mr"></span></div>
</div>
<div class="team5-story" id="ms"></div>
<div class="team5-actions"><button class="team5-btn" onclick="c()">Close</button></div>
</div>
</div>

<script>
const q=s=>document.querySelector(s),
cards=[...document.querySelectorAll('.team5-card')],
m=q('#m'),mi=q('#mi'),mt=q('#mt'),mr=q('#mr'),ms=q('#ms');
cards.forEach(c=>c.onclick=()=>{mt.textContent=c.dataset.name;
mr.textContent=c.dataset.role;ms.textContent=c.dataset.story;
mi.src=c.dataset.img;m.classList.add('open')});
const c=()=>m.classList.remove('open');
m.onclick=e=>e.target===m&&c();
</script>





The FARZM set out to investigate these calendar effects. Armed with data and a passion for uncovering hidden market truths, FARZM are on a mission: to determine whether calendar effects still hold power in modern and if they exist.
- Monday effect
- January effect
- Santa Claus Rally
- Turn-of-the-Month
- Half-Month
- Halloween effect (“Sell in May”)
- Holiday effect


{% include research_questions.html %}


## Investigating the dataset

The investigation begins with the dataset itself. Diving into the NASDAQ data allows us to demystify the alleged calendar effects by first understanding the underlying market dynamics.


<iframe src="assets/img/plot_number_of_companies_per_year.html"
        width="100%"
        height="550"
        frameborder="0">
</iframe>

The graph illustrates a strong long-term increase in the number of distinct companies appearing in the NASDAQ historical dataset. While the exchange hosted only a handful of small technology firms in the early 1970s, the number of listed companies expanded rapidly across the decades, especially during the early 1980s, the dot-com period, and the post-2010 tech boom—reaching over 5,000 firms by 2020. This evolution reflects major structural changes in the U.S. equity market, including sector diversification, higher listing activity, and increases in trading volume and liquidity.

This trend is especially relevant when looking at calendar effects as these anomalies are known to depend on market structure, liquidity conditions, and the composition of traded firms. A small, low-liquidity NASDAQ dominated by volatile growth stocks (1970s–1980s) may exhibit very different calendar anomalies than the modern, highly liquid and institutionally traded NASDAQ of the 2010s. As the number of listed firms grows, the distribution of returns, the prevalence of small caps, and the level of arbitrage activity all change, which can amplify, weaken, or eliminate calendar effects.

<iframe src="assets/img/plot_volume_per_year.html"
        width="100%"
        height="550"
        frameborder="0">
</iframe>

<iframe src="assets/img/plot_return_avg_per_year.html"
        width="100%"
        height="550"
        frameborder="0">
</iframe>


<p>The plot shows the evolution of annual trading volume from 1962 to 2020. Overall, trading activity exhibits a strong upward long-term trend, indicating a substantial increase in market participation and liquidity over time. Since calendar effects are often linked to investor behavior and trading activity, failing to account for volume dynamics may confound calendar effect estimate. So incorporating volume as a control variable or analyzing calendar effects within homogeneous sub-periods becomes essential. <br>
The plot shows the average annual return from 1962 to 2020. Overall, returns are predominantly positive, fluctuating around a small positive mean. It means that returns are positive on average over the long run, despite year-to-year volatility. There are occasional negative returns (for example mid-1970s, late 2000s). Since the unconditional mean return is small, any calendar effects are expected to be weak relative to overall volatility. Moreover, the absence of a strong time trend in average returns supports a key assumption of calendar effect studies: return stationarity over time. This makes the dataset appropriate for isolating return differences attributable to calendar variables rather than structural change. It allows calendar-related differences to be analyzed without being confounded by structural market changes. </p>


## Getting an initial sense of the calendar effects

The detectives begin with an initial exploratory analysis aimed at visualizing potential calendar effects. 

Profile of each suspect pattern


<div class="flourish-embed flourish-cards" data-src="visualisation/26917943"><script src="https://public.flourish.studio/resources/embed.js"></script><noscript><img src="https://public.flourish.studio/visualisation/26917943/thumbnail" width="100%" alt="cards visualization" /></noscript></div>




The visual evidence reveals several intriguing regularities. Returns appear to differ depending on the timing within the trading week, with certain days consistently exhibiting weaker performance than others. Seasonal variations also emerge, as returns during the early part of the year seem marginally higher compared to the remainder of the sample. These patterns are consistent with what the literature commonly refers to as calendar effects.

( //Interpretation //) Indeed, plots demonstrate ____ .
 For each calendar effect, average returns are computed and compared across relevant time periods. By examining these averages, the team aims to determine whether any of the proposed calendar effects already appear detectable at the mean level.

Of course, simply looking at mean returns is not sufficient to conclude whether a calendar effect is real or statistically valid. Average differences may offer intuition, but they do not prove significance. These preliminary comparisons serve only as an initial diagnostic.  

  <img src="assets/img/perry_mean.png" width="500">
</p>


The crucial question of whether these calendar effects are statistically significant needs to be investigated. This requires moving beyond visual evidence to formal statistical testing.

## Are the Calendar effects real ? 

<style>
  .content-block{
    display: flex;
    align-items: flex-start;
    gap: 24px;
  }

  .content-image{
    width: 500px;
    height: auto;
    flex-shrink: 0;
  }

  .content-text{
    flex: 1;
  }

  .content-text p{
    margin-top: 0;
    line-height: 1.6;
  }
</style>


<div class="content-block">
  <img src="assets/img/perrymeme.png" alt="Image" class="content-image">

  <div class="content-text">
    <p>
      Reinforced by rigorous statistical tools, the detectives conduct an in-depth investigation into each calendar effect.
      Every suspected calendar anomaly is subjected to rigorous evaluation through formal hypothesis testing.
    </p>

    <p>
      In particular, welch's test, mann-whitney u test and regression are employed to determine whether statistically significant differences in returns exist between calendar and non-calendar effect period
    </p>
  </div>
</div>

For these tests to be valid, several underlying assumptions must be satisfied, most notably the normality and independence of the data. To ensure the validity of the statistical tests, the investigation begins with a careful assessment of these assumptions. In particular, the normality of returns is examined prior to conducting the hypothesis tests.

### Normality Test

Before drawing any statistical conclusions, the detectives examine a crucial assumption that underlays many of the classical hypothesis tests: **the normality of returns**.

Many standard tests used in finance rely on the idea that returns follow a normal distribution. However, daily stock returns are often characterized by **heavy tails, skewness, and occasional extreme events**, especially during periods of market stress or crisis.

To verify these assumption, we formally test the normality of returns for each calendar-effect window using the D’Agostino–Pearson omnibus test, which jointly evaluates skewness and kurtosis. The resulting statistic follows a chi-squared distribution with two degrees of freedom and its corresponding control period. In other words, we ask a simple but fundamental question:

> **Do stock returns within these calendar periods have a bell shaped battern?**

This would help the detectives choose the appropriate test for their investigations, because if returns deviate strongly from normality, mean-based tests alone may be misleading, as a small number of extreme observations can dominate the results.

<details markdown="1">
  <summary><strong>Hypotheses</strong></summary>

$$
H_0:\ \text{the data are normally distributed}
\qquad
H_1:\ \text{the data are not normally distributed}
$$

</details>

<details>
  <summary><strong>Equations for the normality test</strong></summary>

  <div markdown="1">

#### Sample moments

Given observations $$ x_1, \dots, x_n $$, the central moments is defined as:
$$
m_k = \frac{1}{n} \sum_{i=1}^n (x_i - \bar{x})^k
$$
From these, we compute:

- **Sample skewness**

$$
g_1 = \frac{m_3}{m_2^{3/2}}
$$

- **Sample excess kurtosis**

$$
g_2 = \frac{m_4}{m_2^2} - 3
$$

---

#### Standardize skewness and kurtosis

The skewness and kurtosis statistics are transformed into approximately
standard normal variables:

$$
Z_1 = \text{skewtest}(g_1, n)
$$

$$
Z_2 = \text{kurtosistest}(g_2, n)
$$

---

#### Omnibus test statistic

$$
K^2 = Z_1^2 + Z_2^2
$$

  </div>
</details>


Across all calendar effects considered being investigated we got a $P-value = 0.000$. Thus, the normality hypothesis is consistently rejected which aligns with well-established evidence in financial economics: stock returns are not normally distributed.

Rather than being a setback, this result plays an important role in the investigation. It urges the detectives to **go beyond a single testing framework**. While mean-based tests can still provide useful insights in large samples, they must be complemented with **distribution-free methods** that remain valid even when normality fails.

With this in mind, the investigation proceeds using two different approaches:
- a **mean-comparison approach** (Welch’s *t*-test), and  
- a **rank-based, non-parametric approach** (Mann–Whitney U test),

allowing us to distinguish between calendar effects driven by **systematic shifts in typical returns** and those driven by **rare but extreme market movements (in other words outliers in the dataset)**.

### Welch's Test
<style>
  .content-block{
    display: flex;
    align-items: flex-start;
    gap: 32px;
    margin: 30px 0;
  }

  .content-image{
    width: 250px;
    height: auto;
    flex-shrink: 0;
  }

  .content-text{
    flex: 1;
    line-height: 1.6;
  }

  .content-text p{
    margin: 0;   /* aucun espace vertical */
  }
</style>

<div class="content-block">
  <img src="assets/img/perry_welchtest.jpg" alt="Welch Test Meme" class="content-image">

  <div class="content-text">
    <p>
      The detectives specifically chose the Welch’s Test because, unlike the standard <em>t</em>-test, it can accommodate
      data with unequal variances and unequal sample sizes, making it a more appropriate and conservative choice for
      financial return data. When investigating a calendar-effect window, returns are typically compared with those
      observed during the remainder of the year. Although daily stock returns are not normally distributed, the large
      sample size of daily NASDAQ data (~24 million records) ensures that sample means are approximately normal by the
      Central Limit Theorem, making mean-based tests valid. As a result, Welch’s <em>t</em>-test provides a robust benchmark
      for evaluating whether calendar-effect average returns are statistically significant, directly addressing the core
      economic claims behind calendar effects while minimizing false positives driven by volatility differences or
      sample imbalance.
    </p>
  </div>
</div>
<details markdown="1">
  <summary><strong>Hypotheses</strong></summary>

$$
H_0:\ \mu_1 = \mu_2
\qquad
H_1:\ \mu_1 \neq \mu_2
$$

</details>

<details markdown="1">
  <summary><strong>Equations of Welch's Test</strong></summary>
Given:
- $$ \bar{x}_1, \bar{x}_2 $$ = sample means  
- $$ s_1^2, s_2^2 $$ = sample variances  
- $$ n_1, n_2 $$ = sample sizes  

The Welch *t*-statistic is defined as:

$$
t
=
\frac{\bar{x}_1 - \bar{x}_2}
{\sqrt{\dfrac{s_1^2}{n_1} + \dfrac{s_2^2}{n_2}}}
$$
</details>


<!-- <div style="border-left: 4px solid #432750; padding-left: 20px; font-size: 18px; margin-top: 2;">
  <details> 
    <summary style = "font-size: 18px; cursor: pointer;"><b>Central Limit Theorem</b></summary>     
      <p>The Central Limit Theorem (CLT) is a cornerstone of statistics, stating that the distribution of sample means from any population will approach a normal distribution as the sample size gets large, regardless of the original population's shape. This convergence to normality, usually with samples of 30 or more ($$ n \geq 30$$).
      </p> 
  </details>
</div> -->

<details markdown="1">
  <summary><strong>Central Limit Theorem</strong></summary>
        The Central Limit Theorem (CLT) is a cornerstone of statistics, stating that the distribution of sample means from any population will approach a normal distribution as the sample size gets large, regardless of the original population's shape. This convergence to normality, usually with samples of 30 or more ($$ n \geq 30$$).
</details>

After investigating all the calendar effect's windows using the Welch’s t-test, the detectives found an interesting lead in their story. The test rejects the null hypothesis of equal mean returns for all calendar effects, with reported *p-values* effectively equal to zero. This outcome reflects overwhelming statistical evidence that average returns differ between calendar and non-calendar periods; however it still doesn't prove casuality. The investigators also had to keep i mind that, given the extremely large sample size of daily NASDAQ data, even very small mean differences become statistically detectable causing this high signifigance result. As a result, they interperet these findings as evidence of statistical significance rather than economic magnitude. The detectives decides that the presence of the highly significant *p-values* does not imply that calendar effects are large, stable, or economically meaningful, which motivates them to go for another independent witness as well. 

### Mann–Whitney U Test

To determine whether calendar effects reflect a systematic shift in the distribution of returns, rather than the effect of rare outliers, the detectives call in a second independent witness: the Mann–Whitney U test. Unlike Welch’s test, Mann–Whitney does not rely on normality distribution assumptions and does not compare averages. Instead, it evaluates whether returns from one calendar period tend to be consistently higher or lower than those from another period across the entire distribution. They hope that by interviewing a mean-based witness and a rank-based one, it would help them distinguish between calendar effects driven by behavioral patterns and those driven by a few rare market events.


<details markdown="1">
  <summary><strong>Hypotheses</strong></summary>
When investigating the calendar effects for most of the suspects, the investigators have the hypothesis that the returns during the calendar windows are higher than the rest of the data; however in the Middle of the month effect they assume the opposite acording to it's definition. Finally, when testing the Monday effect, the make a pair-wise test between the 5 trading daysof the week.
$$
H_0:\ \mu_1 = \mu_2
\qquad
H_1:\ \mu_1 \neq \mu_2
$$

</details>

<details markdown="1">
  <summary><strong>Equations of Mann–Whitney U Test</strong></summary>
When both samples are large (typically $n_1, n_2 \gtrsim 20$), the Mann–Whitney $U$ statistic is approximately normally distributed.

$$
\mu_U = \frac{n_1 n_2}{2}
$$

$$
\sigma_U = \sqrt{\frac{n_1 n_2 (n_1 + n_2 + 1)}{12}}
$$

$$
Z = \frac{U - \mu_U}{\sigma_U}
$$
</details>

Again like the Welch's test the investigators got *p-values* that were almost zero in most of the calendar effects, which as they already knew is because of the very large number of samples  which makes the tiny and economically negligible differences between return distributions become statistically detectable. In other words, the test provides overwhelming statistical evidence that returns inside those calendar windows are not drawn from the same distribution as returns outside the window, but it does not tell us whether the effect is meaningful in practice. 

On the other hand, the Middle of The Month window got a *p-value* of 1, which indicated that there is no significant difference between the returns during the middle of th emonths compared with the rest of the days. This was their first interesting lead that *Middle of The Month* might not be a criminal after all.

Finally, the test between Wednesday and Thursday got a *p-value* of 0.25, which also rejects the null hypothesis and indicates that there is not significant difference between the returns of both days. However, to recall the Monday effect; the investigaros assumes that the difference would only be beween Monday, Friday, and the rest of the days. Since, the original crime is that returns of Fridays are the highest, Mondays are the lowest, and the rest of the week are almost similar. This is still an interesting lead as it showed that a huge part of the assumption is correct which is the similarity between Wednesday and Thursday.

Finally, after investigating these two witnesses and having almost a *p-value* equal to zero in most of the calendar effect windows, the investogators reached a conclusion: with massive datasets, statistical significance is cheap and not enough. So to have more clues that can help them tighten their analysis, they decided to interview another witness and ask him about the effect sizes.

### Probability of Superiority
Since the investigators began to doubt that the clues and samples they have might be directing them in the wrong direction or can be misleading, they decide to bring the *Probability of Superiority* to the case, and ask him about the effect sizes of the previous witnesses. They believe that this would help them support the previously exagerated conclusioned they had.

<details markdown="1">
  <summary><strong>Equation</strong></summary>
The probability that previous witnesses ranked a randomly chosen sample from the calendar window higher than another randomly chosen one from the rest of the data
$$
\text{PS} = \frac{U}{n_1 n_2}
$$
        
</details>

After a thorough examination of this witness, the investigators uncover a revealing pattern. First, most of the calendar effects yielded a probability of superiority ranging between 45% to 55%, indicating that returns inside these windows are only marginally bigger than the returns from outside the window. This also imply an overlap between distributions, which suggest that while these effects can be statistically detectable, their practical impact is most likely weak.

One exception clearly to that though. The Halloween effect displays a probability of superiority of 73%, in other words in nearly three out of four pairwise comparisons, returns during the Halloween window are begger than those outside it. This represents a large and systematic distributional shift, that can be only due to sampling noise or rare tail events.

This contrast reveals an important distinction: while most calendar effects have statistical significance which is amplified by large sample sizes, the Halloween effect so far is a genuine and economically meaningful anomaly.

In the graph below you can choose a calendar effect to see the results of each of the tests. :)

/////////////////////////////////////////

FURKAN, PLEASE TRY TO ADD THESE IN 
AN INTERACTIVE GRAPH

///////////////////////////////////////
[January Effect] T-test: 29.7588, P-value: 0.0000
[Santa Claus Rally Effect] T-test: 62.5301, P-value: 0.0000
[Holiday Effect] T-test: 45.4908, P-value: 0.0000
[Sell in May effect] T-test: -4.0670, P-value: 0.0001
[Turn of the month effect] T-test: 38.2926, P-value: 0.0000
[Middle of the month effect] T-test: 2.8484, P-value: 0.0044
[Day 0 vs day 1] T-test: -5.1272, P-value: 0.0000
[Day 0 vs day 2] T-test: -7.1175, P-value: 0.0000
[Day 0 vs day 3] T-test: -6.3706, P-value: 0.0000
[Day 0 vs day 4] T-test: -9.0762, P-value: 0.0000
[Day 1 vs day 2] T-test: -2.3667, P-value: 0.0180
[Day 1 vs day 3] T-test: -1.5279, P-value: 0.1266
[Day 1 vs day 4] T-test: -4.3898, P-value: 0.0000
[Day 2 vs day 3] T-test: 0.8144, P-value: 0.4154
[Day 2 vs day 4] T-test: -1.8308, P-value: 0.0672
[Day 3 vs day 4] T-test: -2.6877, P-value: 0.0072


mannwhitneyu
[January Effect] mannwhitneyu-test: 22095602484142.5000, P-value: 0.0000
probability_superiority: 0.5042, cliffs_delta: 0.008313
[Santa Claus Rally Effect] mannwhitneyu-test: 8282136107953.0000, P-value: 0.0000
probability_superiority: 0.5209, cliffs_delta: 0.041847
[Holiday Effect] mannwhitneyu-test: 6211308568991.5000, P-value: 0.0000
probability_superiority: 0.5187, cliffs_delta: 0.037399
[Sell in May effect] mannwhitneyu-test: 2442.0000, P-value: 0.0000
probability_superiority: 0.7259, cliffs_delta: 0.451843
[Turn of the month effect] mannwhitneyu-test: 28118639813802.0000, P-value: 0.0000
probability_superiority: 0.5098, cliffs_delta: 0.019593
[Middle of the month effect] mannwhitneyu-test: 28301799364045.5000, P-value: 1.0000
probability_superiority: 0.5039, cliffs_delta: 0.007811
[Day 0 vs day 1] mannwhitneyu-test: 3890012.0000, P-value: 0.0000
probability_superiority: 0.4647, cliffs_delta: -0.070623
[Day 0 vs day 2] mannwhitneyu-test: 3631521.0000, P-value: 0.0000
probability_superiority: 0.4357, cliffs_delta: -0.128596
[Day 0 vs day 3] mannwhitneyu-test: 3652316.0000, P-value: 0.0000
probability_superiority: 0.4437, cliffs_delta: -0.112592
[Day 0 vs day 4] mannwhitneyu-test: 3422377.0000, P-value: 0.0000
probability_superiority: 0.4180, cliffs_delta: -0.163917
[Day 1 vs day 2] mannwhitneyu-test: 4200482.0000, P-value: 0.0001
probability_superiority: 0.4706, cliffs_delta: -0.058728
[Day 1 vs day 3] mannwhitneyu-test: 4220330.0000, P-value: 0.0047
probability_superiority: 0.4788, cliffs_delta: -0.042394
[Day 1 vs day 4] mannwhitneyu-test: 3972846.0000, P-value: 0.0000
probability_superiority: 0.4532, cliffs_delta: -0.093623
[Day 2 vs day 3] mannwhitneyu-test: 4462502.0000, P-value: 0.2580
probability_superiority: 0.5085, cliffs_delta: 0.016971
[Day 2 vs day 4] mannwhitneyu-test: 4216530.0000, P-value: 0.0243
probability_superiority: 0.4831, cliffs_delta: -0.033833
[Day 3 vs day 4] mannwhitneyu-test: 4086882.0000, P-value: 0.0006
probability_superiority: 0.4741, cliffs_delta: -0.051771

//////////////////////////////////////////////////////////////////////////////////////////


<details markdown="1">
  <summary><strong>Equation</strong></summary>
The probability that previous witnesses ranked a randomly chosen sample from the calendar window higher than another randomly chosen one from the rest of the data
$$
\text{PS} = \frac{U}{n_1 n_2}
$$
   <details markdown="1">
  <summary><strong>Equation</strong></summary>
The probability that previous witnesses ranked a randomly chosen sample from the calendar window higher than another randomly chosen one from the rest of the data
$$
\text{PS} = \frac{U}{n_1 n_2}
$$
        
</details>      
</details>

<details>
  <summary><strong>📈 Monday Effect</strong></summary>
---
  <p>
    Mondays are often said to deliver negative returns.
    Let’s see what the data actually says.
  </p>
        <iframe src="assets/img/plot_monday_effect_dec.html"
        width="100%" 
        height="550"
        frameborder="0">
</iframe>
---
  <div id="monday-plot" style="height:450px;"></div>
</details>

<details>
  <summary><strong>📉 January Effect</strong></summary>
---
  <p>
                            OLS Regression Results                            
==============================================================================
Dep. Variable:                 Return   R-squared:                       0.001
Model:                            OLS   Adj. R-squared:                  0.001
Method:                 Least Squares   F-statistic:                     6.562
Date:                Sat, 20 Dec 2025   Prob (F-statistic):            0.00142
Time:                        17:14:58   Log-Likelihood:                 48895.
No. Observations:               14643   AIC:                        -9.778e+04
Df Residuals:                   14640   BIC:                        -9.776e+04
Df Model:                           2                                         
Covariance Type:                  HAC                                         
==============================================================================
                 coef    std err          z      P>|z|      [0.025      0.975]
------------------------------------------------------------------------------
const          0.0006   8.64e-05      6.406      0.000       0.000       0.001
is_january     0.0011      0.000      3.563      0.000       0.000       0.002
fed_funds  -5.469e-05   9.16e-05     -0.597      0.550      -0.000       0.000
==============================================================================
Omnibus:                     5141.886   Durbin-Watson:                   1.750
Prob(Omnibus):                  0.000   Jarque-Bera (JB):           227707.381
Skew:                          -0.960   Prob(JB):                         0.00
Kurtosis:                      22.223   Cond. No.                         3.65
==============================================================================
  </p>
---
  <div id="january-plot" style="height:450px;"></div>
</details>

<details>
  <summary><strong>🎅 Santa Claus Rally Effect</strong></summary>
<!-- ---
  <p>
    Mondays are often said to deliver negative returns.
    Let’s see what the data actually says.
  </p>
--- -->
  <div id="santa_claus_rally-plot" style="height:450px;"></div>
</details>


<details>
  <summary><strong>📉 Turn-of-the-Month Effect</strong></summary>
<!-- ---
  <p>
    Mondays are often said to deliver negative returns.
    Let’s see what the data actually says.
  </p>
--- -->
  <div id="turn-of-the-Month-plot" style="height:450px;"></div>
</details>

<details>
  <summary><strong>📆 Half-Month Effect</strong></summary>
<!-- ---
  <p>
    Mondays are often said to deliver negative returns.
    Let’s see what the data actually says.
  </p>
--- -->
  <div id="half-Month-plot" style="height:450px;"></div>
</details>

<details>
  <summary><strong>🎃 Halloween Effect</strong></summary>
<!-- ---
  <p>
    Mondays are often said to deliver negative returns.
    Let’s see what the data actually says.
  </p>
--- -->
  <div id="halloween-plot" style="height:450px;"></div>
</details>

<details>
  <summary><strong>🎉 Holiday Effect</strong></summary>
<!-- ---
  <p>
    Mondays are often said to deliver negative returns.
    Let’s see what the data actually says.
  </p>
--- -->
  <div id="holiday-plot" style="height:450px;"></div>
</details>

Interpretation of the normality check

// Results of t-tests //             

Interpretation of t-tests

When the assumption of normality is violated, the Mann–Whitney U test, a non-parametric alternative, is employed to compare return distributions across calendar periods. This approach allows the investigation to remain robust to deviations from normality.

  // Results of Mann-Whitney test //

  Interpretation of Mann-Whitney test


To further strengthen the analysis, these tests are complemented by regression models that isolate the calendar component while controlling for other market dynamics (volume, volatility, fed funds rate).

<p align="center">
  <img src="assets/img/perry_regression.png" width="500">
</p>


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
<details open>
  <summary><strong>📉 Monday Effect — Myth or Reality?</strong></summary>

  <p>
    Mondays are often said to deliver negative returns.
    Let’s see what the data actually says.
  </p>

  <div id="monday-plot" style="height:450px;"></div>
</details>


## Do calendar effects survive through the years?

Now that we have detected and analyzed several calendar effects, a natural question arises: **do these patterns remain stable over time, or do they evolve as markets change?**

Calendar anomalies are often presented as timeless rules — but real financial markets rarely stay constant. Trading technology evolves, regulations shift, investor composition changes, and macroeconomic regimes come and go. Any of these forces can influence whether an anomaly strengthens, weakens, or disappears entirely.

In this section, we investigate the **temporal stability** of each calendar effect. More precisely, we ask:

- Do the effects behave similarly in the 1970s, 1980s, 1990s, and 2000s?  
- Do some grow stronger or weaker across decades?    
- And crucially: **which calendar effects survive consistently over time, and which ones vanish once they become widely known?**


{% include outer_effects_ui.html %}







<section id="calendar-effects" class="fx-wrap">
  <div class="fx-layout">

    <!-- LEFT: Effect cards -->
    <aside class="fx-panel">
      <div class="fx-panel-top">
        <div class="fx-panel-title">Effects</div>
        <input id="fxSearch" class="fx-search" placeholder="Search (jan, may, tom...)" />
      </div>

      <div class="fx-grid" id="fxGrid">

        <button class="fx-card active"
          data-key="january"
          data-title="January Effect"
          data-desc="January average return is higher than the average of Feb–Dec."
          data-img="{{ site.baseurl }}/assets/img/january_company.png">
          <div class="fx-icon">JAN</div>
          <div class="fx-card-main">
            <div class="fx-card-title">January Effect</div>
            <div class="fx-card-sub">Month seasonality</div>
          </div>
          <div class="fx-chip">classic</div>
        </button>

        <button class="fx-card"
          data-key="sell"
          data-title="Sell in May"
          data-desc="Winter (Nov–Apr) vs Summer (May–Oct) return gap."
          data-img="{{ site.baseurl }}/assets/img/sell_in_may_company.png">
          <div class="fx-icon">MAY</div>
          <div class="fx-card-main">
            <div class="fx-card-title">Sell in May</div>
            <div class="fx-card-sub">Season regime</div>
          </div>
          <div class="fx-chip">macro</div>
        </button>

        <button class="fx-card"
          data-key="tom"
          data-title="Turn-of-Month"
          data-desc="Returns around the month switch (end/beginning) are stronger."
          data-img="{{ site.baseurl }}/assets/img/tom_company.png">
          <div class="fx-icon">ToM</div>
          <div class="fx-card-main">
            <div class="fx-card-title">Turn-of-Month</div>
            <div class="fx-card-sub">Window effect</div>
          </div>
          <div class="fx-chip">timing</div>
        </button>

        <button class="fx-card"
          data-key="monday"
          data-title="Monday Effect"
          data-desc="Monday average return is lower than the other weekdays."
          data-img="{{ site.baseurl }}/assets/img/monday_company.png">
          <div class="fx-icon">MON</div>
          <div class="fx-card-main">
            <div class="fx-card-title">Monday Effect</div>
            <div class="fx-card-sub">Weekday bias</div>
          </div>
          <div class="fx-chip">week</div>
        </button>

        <button class="fx-card"
          data-key="holiday"
          data-title="Holiday Effect"
          data-desc="Pre/post-holiday behavior: abnormal returns around holidays."
          data-img="{{ site.baseurl }}/assets/img/holiday.png">
          <div class="fx-icon">HOL</div>
          <div class="fx-card-main">
            <div class="fx-card-title">Holiday Effect</div>
            <div class="fx-card-sub">Event timing</div>
          </div>
          <div class="fx-chip">event</div>
        </button>

        <button class="fx-card"
          data-key="santa"
          data-title="Santa Rally"
          data-desc="End-of-year rally window: late Dec to early Jan pattern."
          data-img="{{ site.baseurl }}/assets/img/santa_claus_rally_company.png">
          <div class="fx-icon">🎅</div>
          <div class="fx-card-main">
            <div class="fx-card-title">Santa Rally</div>
            <div class="fx-card-sub">Year-end</div>
          </div>
          <div class="fx-chip">fun</div>
        </button>

      </div>
    </aside>

    <!-- RIGHT: Plot viewer -->
    <main class="fx-viewer">
      <div class="fx-view-card">
        <div class="fx-view-head">
          <div>
            <div class="fx-kicker">Selected effect</div>
            <div id="fxTitle" class="fx-title">January Effect</div>
            <div id="fxDesc" class="fx-desc">January average return is higher than the average of Feb–Dec.</div>
          </div>

          <div class="fx-actions">
            <a id="fxOpenImg" class="fx-open" target="_blank" rel="noopener">Open image</a>
          </div>
        </div>

        <div class="fx-img-wrap">
          <div id="fxShimmer" class="fx-shimmer"></div>
          <img id="effectImage"
               src="{{ site.baseurl }}/assets/img/january_company.png"
               alt="Calendar effect plot"
               loading="lazy">
        </div>
      </div>
    </main>

  </div>
</section>

<script>
  (function () {
    const root = document.getElementById("calendar-effects");
    const cards = root.querySelectorAll(".fx-card");
    const img   = root.querySelector("#effectImage");
    const ttl   = root.querySelector("#fxTitle");
    const dsc   = root.querySelector("#fxDesc");
    const open  = root.querySelector("#fxOpenImg");
    const shim  = root.querySelector("#fxShimmer");
    const srch  = root.querySelector("#fxSearch");

    function setLoading(on){
      shim.style.display = on ? "block" : "none";
      img.style.opacity = on ? "0.65" : "1";
    }

    function activate(btn){
      cards.forEach(c => c.classList.remove("active"));
      btn.classList.add("active");

      ttl.textContent = btn.dataset.title || "Effect";
      dsc.textContent = btn.dataset.desc || "";
      const src = btn.dataset.img;

      setLoading(true);
      img.onload = () => setLoading(false);
      img.src = src;
      open.href = src;

      // smooth focus
      img.scrollIntoView({ behavior: "smooth", block: "nearest" });
    }

    cards.forEach(btn => btn.addEventListener("click", () => activate(btn)));

    srch.addEventListener("input", () => {
      const q = srch.value.trim().toLowerCase();
      cards.forEach(btn => {
        const hay = (btn.innerText + " " + (btn.dataset.key || "")).toLowerCase();
        btn.style.display = hay.includes(q) ? "" : "none";
      });
    });

    // init open link
    open.href = img.src;
  })();
</script>

<style>
  /* ===== overall vibe ===== */
  .fx-wrap{ margin-top:2rem; }
  .fx-hero{
    display:flex; justify-content:space-between; gap:18px;
    padding:18px 18px;
    border-radius:22px;
    border:1px solid rgba(255,255,255,.12);
    background: radial-gradient(1200px 500px at 20% 0%,
      rgba(120,170,255,.20), rgba(255,255,255,.03));
    box-shadow: 0 20px 70px rgba(0,0,0,.28);
  }
  .fx-eyebrow{ opacity:.75; font-weight:650; letter-spacing:.3px; }
  .fx-h1{ margin:.35rem 0 .3rem; font-size:1.7rem; line-height:1.15; }
  .fx-lead{ margin:0; opacity:.78; max-width:62ch; }

  .fx-cta-row{ margin-top:12px; display:flex; gap:12px; align-items:center; flex-wrap:wrap; }
  .fx-cta{
    display:inline-flex; align-items:center; gap:8px;
    padding:10px 14px;
    border-radius:999px;
    border:1px solid rgba(120,170,255,.55);
    background:rgba(120,170,255,.16);
    text-decoration:none;
    font-weight:750;
  }
  .fx-cta:hover{ transform:translateY(-1px); }
  .fx-note{ opacity:.7; font-size:.92rem; }

  .fx-hero-right{ display:flex; gap:10px; align-items:stretch; }
  .fx-stat{
    min-width:110px;
    padding:10px 12px;
    border-radius:18px;
    border:1px solid rgba(255,255,255,.12);
    background:rgba(0,0,0,.10);
    text-align:center;
  }
  .fx-stat-num{ font-size:1.25rem; font-weight:900; }
  .fx-stat-lbl{ opacity:.7; font-size:.9rem; margin-top:2px; }

  .fx-layout{
    display:grid;
    grid-template-columns: 360px 1fr;
    gap:16px;
    margin-top:14px;
    align-items:start;
  }
  @media(max-width:1000px){
    .fx-hero{ flex-direction:column; }
    .fx-hero-right{ justify-content:flex-start; }
    .fx-layout{ grid-template-columns: 1fr; }
  }

  /* ===== left panel ===== */
  .fx-panel{
    position:sticky; top:14px;
    padding:12px;
    border-radius:20px;
    border:1px solid rgba(255,255,255,.12);
    background:rgba(255,255,255,.04);
    box-shadow: 0 18px 60px rgba(0,0,0,.25);
  }
  .fx-panel-top{ display:flex; align-items:center; justify-content:space-between; gap:10px; margin-bottom:10px; }
  .fx-panel-title{ font-weight:850; letter-spacing:.2px; }
  .fx-search{
    width:170px;
    padding:9px 10px;
    border-radius:12px;
    border:1px solid rgba(255,255,255,.12);
    background:rgba(255,255,255,.06);
    color:inherit;
    outline:none;
  }
  .fx-search:focus{ border-color: rgba(120,170,255,.60); }

  .fx-grid{ display:flex; flex-direction:column; gap:10px; }

  .fx-card{
    display:grid;
    grid-template-columns: 52px 1fr auto;
    gap:10px;
    align-items:center;
    padding:12px 12px;
    border-radius:18px;
    border:1px solid rgba(255,255,255,.10);
    background:rgba(0,0,0,.10);
    cursor:pointer;
    text-align:left;
    transition: transform .12s ease, box-shadow .12s ease, border-color .12s ease, background .12s ease;
  }
  .fx-card:hover{
    transform:translateY(-2px);
    box-shadow: 0 16px 40px rgba(0,0,0,.32);
    border-color: rgba(255,255,255,.18);
    background:rgba(255,255,255,.06);
  }
  .fx-card.active{
    border-color: rgba(120,170,255,.75);
    background: linear-gradient(180deg, rgba(120,170,255,.18), rgba(0,0,0,.08));
    box-shadow: 0 20px 55px rgba(0,0,0,.40);
  }

  .fx-icon{
    width:52px; height:52px;
    display:flex; align-items:center; justify-content:center;
    border-radius:16px;
    border:1px solid rgba(255,255,255,.14);
    background:rgba(255,255,255,.08);
    font-weight:900;
    letter-spacing:.4px;
  }
  .fx-card-title{ font-weight:900; }
  .fx-card-sub{ opacity:.7; margin-top:2px; font-size:.92rem; }
  .fx-chip{
    padding:6px 10px;
    border-radius:999px;
    border:1px solid rgba(255,255,255,.14);
    background:rgba(255,255,255,.06);
    font-size:.85rem;
    opacity:.9;
  }

  /* ===== viewer ===== */
  .fx-view-card{
    border-radius:22px;
    border:1px solid rgba(255,255,255,.12);
    background:rgba(255,255,255,.04);
    box-shadow: 0 20px 70px rgba(0,0,0,.28);
    overflow:hidden;
  }
  .fx-view-head{
    display:flex; justify-content:space-between; gap:12px;
    padding:14px 16px;
    border-bottom:1px solid rgba(255,255,255,.10);
    background:rgba(0,0,0,.10);
  }
  .fx-kicker{ opacity:.7; font-size:.9rem; }
  .fx-title{ font-size:1.25rem; font-weight:950; margin-top:2px; }
  .fx-desc{ opacity:.78; margin-top:3px; max-width:75ch; }
  .fx-actions{ display:flex; align-items:flex-start; }
  .fx-open{
    padding:8px 12px;
    border-radius:999px;
    border:1px solid rgba(120,170,255,.55);
    background:rgba(120,170,255,.14);
    text-decoration:none;
    font-weight:800;
  }

  .fx-img-wrap{ position:relative; padding:10px; }
  .fx-img-wrap img{
    width:100%;
    display:block;
    border-radius:16px;
    border:1px solid rgba(255,255,255,.10);
    background:rgba(0,0,0,.12);
  }

  /* shimmer loading */
  .fx-shimmer{
    position:absolute;
    inset:10px;
    border-radius:16px;
    border:1px solid rgba(255,255,255,.10);
    background:
      linear-gradient(90deg,
        rgba(255,255,255,.04) 0%,
        rgba(255,255,255,.12) 45%,
        rgba(255,255,255,.04) 100%);
    background-size: 220% 100%;
    animation: fxsh 1.1s infinite linear;
    display:none;
  }
  @keyframes fxsh{
    0%{ background-position: 0% 0%; }
    100%{ background-position: -220% 0%; }
  }
</style>





<script src="https://cdn.plot.ly/plotly-2.30.0.min.js"></script>
<div class="santa-ui">
  <div class="santa-top">
    <div>
      <div style="font-weight:800; font-size:1.15rem;">Santa Claus Effect (per ticker)</div>
      <div style="opacity:.75;">Type a ticker and the plot updates instantly.</div>
    </div>

    <div>
      <input id="santaTicker" list="santaTickers" placeholder="Type ticker (e.g., TAPR)" />
      <datalist id="santaTickers"></datalist>
    </div>
  </div>

  <div id="santaPlot" style="margin-top:12px;"></div>
</div>

<script>
(async function(){
  const url = "{{ site.baseurl }}/assets/data/santa_comp_all.json";
  const res = await fetch(url);
  const ALL = await res.json();

  const input = document.getElementById("santaTicker");
  const dl = document.getElementById("santaTickers");
  const plotDiv = document.getElementById("santaPlot");

  // datalist doldur
  const tickers = Object.keys(ALL).sort();
  tickers.forEach(t => {
    const opt = document.createElement("option");
    opt.value = t;
    dl.appendChild(opt);
  });

  function buildWinYearShapes(winYears){
    // Python’daki add_vrect (x0=y-0.5, x1=y+0.5) karşılığı:
    return (winYears || []).map(y => ({
      type: "rect",
      xref: "x",
      yref: "y",
      x0: y - 0.5,
      x1: y + 0.5,
      y0: 0,
      y1: 1,
      yref: "paper",     // tüm üst subplot yüksekliği
      fillcolor: "rgba(0,0,0,0.06)",
      line: { width: 0 },
      layer: "below"
    }));
  }

  function draw(tkr){
    tkr = (tkr || "").trim().toUpperCase();
    const d = ALL[tkr];

    if(!d){
      Plotly.newPlot(plotDiv, [], {title: "Ticker not found"}, {responsive:true});
      return;
    }

    const years = d.years;

    const trace1 = {
      x: years, y: d.scr_avg,
      type: "scatter",
      mode: "lines+markers",
      name: "SCR avg",
      hovertemplate: "Year=%{x}<br>SCR avg=%{y:.5f}<extra></extra>",
      xaxis: "x",
      yaxis: "y"
    };

    const trace2 = {
      x: years, y: d.non_scr_avg,
      type: "scatter",
      mode: "lines+markers",
      name: "non-SCR avg",
      line: { dash: "dash" },
      hovertemplate: "Year=%{x}<br>non-SCR avg=%{y:.5f}<extra></extra>",
      xaxis: "x",
      yaxis: "y"
    };

    const trace3 = {
      x: years, y: d.diff,
      type: "bar",
      name: "Diff (SCR - non-SCR)",
      hovertemplate: "Year=%{x}<br>Diff=%{y:.5f}<extra></extra>",
      xaxis: "x2",
      yaxis: "y2"
    };

    // 2-row subplot layout (shared x gibi)
    const layout = {
      title: `Santa Claus Effect — ${tkr} (win rate ${d.win_rate.toFixed(1)}%)`,
      height: 720,
      margin: {l: 50, r: 20, t: 70, b: 50},
      hovermode: "x unified",
      legend: {orientation: "h", y: 1.06, x: 0},

      // üst subplot eksenleri
      xaxis: {domain: [0, 1], anchor: "y", title: ""}, 
      yaxis: {domain: [0.42, 1], title: "Avg return"},

      // alt subplot eksenleri
      xaxis2: {domain: [0, 1], anchor: "y2", title: "Year"},
      yaxis2: {domain: [0, 0.34], title: "Diff"},

      // win-year shading (üst panelin altına)
      shapes: buildWinYearShapes(d.win_years).concat([
        // y=0 line (alt subplot için)
        {
          type: "line",
          xref: "x2",
          yref: "y2",
          x0: Math.min(...years),
          x1: Math.max(...years),
          y0: 0,
          y1: 0,
          line: { dash: "dot", width: 1 }
        }
      ])
    };

    Plotly.newPlot(plotDiv, [trace1, trace2, trace3], layout, {responsive:true});
  }

  // default ticker
  const defaultT = "TAPR";
  input.value = ALL[defaultT] ? defaultT : tickers[0];
  draw(input.value);

  input.addEventListener("change", () => draw(input.value));
})();
</script>

<style>
  .santa-ui{
    margin-top:16px;
    padding:14px;
    border-radius:18px;
    border:1px solid rgba(255,255,255,.12);
    background:rgba(255,255,255,.04);
    box-shadow:0 18px 60px rgba(0,0,0,.25);
  }
  .santa-top{
    display:flex;
    justify-content:space-between;
    align-items:flex-end;
    gap:12px;
    flex-wrap:wrap;
  }
  #santaTicker{
    width:min(320px, 80vw);
    padding:10px 12px;
    border-radius:12px;
    border:1px solid rgba(255,255,255,.12);
    background:rgba(255,255,255,.06);
    color:inherit;
    outline:none;
  }
  #santaTicker:focus{ border-color: rgba(120,170,255,.6); }
</style>

<script src="https://cdn.plot.ly/plotly-2.30.0.min.js"></script>
<div class="sim-ui">
  <div class="sim-top">
    <div>
      <div class="sim-h">Sell in May (per ticker)</div>
      <div class="sim-sub">Type a ticker to update the two-panel plot.</div>
    </div>

    <div>
      <input id="simTicker" list="simTickers" placeholder="Type ticker (e.g., AAPL)" />
      <datalist id="simTickers"></datalist>
    </div>
  </div>

  <div class="sim-grid">
    <div class="sim-card">
      <div class="sim-card-title">Ticker view</div>
      <div id="simPlot"></div>
    </div>

    <div class="sim-card">
      <div class="sim-card-title">Company distribution</div>
      <div id="simPie"></div>
      <div id="simSliceInfo" class="sim-slice"></div>
    </div>
  </div>
</div>

<script>
(async function(){
  const compUrl = "{{ site.baseurl }}/assets/data/sell_in_may_comp_all.json";
  const pieUrl  = "{{ site.baseurl }}/assets/data/sell_in_may_pie.json";

  const [compRes, pieRes] = await Promise.all([fetch(compUrl), fetch(pieUrl)]);
  const ALL = await compRes.json();
  const PIE = await pieRes.json();

  const input = document.getElementById("simTicker");
  const dl = document.getElementById("simTickers");
  const plotDiv = document.getElementById("simPlot");
  const pieDiv = document.getElementById("simPie");
  const sliceInfo = document.getElementById("simSliceInfo");

  // datalist
  const tickers = Object.keys(ALL).sort();
  tickers.forEach(t => {
    const opt = document.createElement("option");
    opt.value = t;
    dl.appendChild(opt);
  });

  function buildWinYearShapes(winYears){
    return (winYears || []).map(y => ({
      type: "rect",
      xref: "x",
      yref: "paper",
      x0: y - 0.5,
      x1: y + 0.5,
      y0: 0.42,   // üst panel domain start
      y1: 1.00,   // üst panel domain end
      fillcolor: "rgba(0,0,0,0.06)",
      line: { width: 0 },
      layer: "below"
    }));
  }

  function drawTicker(tkr){
    tkr = (tkr || "").trim().toUpperCase();
    const d = ALL[tkr];
    if(!d){
      Plotly.newPlot(plotDiv, [], {title: "Ticker not found"}, {responsive:true});
      return;
    }

    const years = d.years;

    const trace1 = {
      x: years, y: d.winter_avg,
      type: "scatter", mode: "lines+markers",
      name: "Winter avg (Nov–Apr)",
      hovertemplate: "Year=%{x}<br>Winter avg=%{y:.5f}<extra></extra>",
      xaxis: "x", yaxis: "y"
    };

    const trace2 = {
      x: years, y: d.summer_avg,
      type: "scatter", mode: "lines+markers",
      name: "Summer avg (May–Oct)",
      line: { dash: "dash" },
      hovertemplate: "Year=%{x}<br>Summer avg=%{y:.5f}<extra></extra>",
      xaxis: "x", yaxis: "y"
    };

    const trace3 = {
      x: years, y: d.diff,
      type: "bar",
      name: "Diff (Winter - Summer)",
      hovertemplate: "Year=%{x}<br>Diff=%{y:.5f}<extra></extra>",
      xaxis: "x2", yaxis: "y2"
    };

    const layout = {
      title: `Sell in May — ${tkr} (win rate ${d.win_rate.toFixed(1)}%)`,
      height: 680,
      margin: {l: 55, r: 20, t: 70, b: 50},
      hovermode: "x unified",
      legend: {orientation:"h", y:1.07, x:0},

      xaxis:  {domain:[0,1], anchor:"y"},
      yaxis:  {domain:[0.42,1], title:"Avg return"},
      xaxis2: {domain:[0,1], anchor:"y2", title:"Year"},
      yaxis2: {domain:[0,0.34], title:"Diff"},

      shapes: buildWinYearShapes(d.win_years).concat([{
        type:"line",
        xref:"x2", yref:"y2",
        x0: Math.min(...years), x1: Math.max(...years),
        y0: 0, y1: 0,
        line: {dash:"dot", width:1}
      }])
    };

    Plotly.newPlot(plotDiv, [trace1, trace2, trace3], layout, {responsive:true});
  }

  function drawPie(){
    const labels = PIE.labels;
    const values = PIE.counts;

    const trace = {
      type: "pie",
      labels: labels,
      values: values,
      textinfo: "label+percent+value",
      hovertemplate: "<b>%{label}</b><br>Companies: %{value}<extra></extra>",
      pull: labels.map(() => 0.04)
    };

    const layout = {
      title: "Sell in May — Company Distribution",
      height: 520,
      margin: {l: 10, r: 10, t: 60, b: 10},
      showlegend: true
    };

    Plotly.newPlot(pieDiv, [trace], layout, {responsive:true});

    pieDiv.on("plotly_click", (ev) => {
      const idx = ev.points[0].pointNumber;
      const sliceLabel = labels[idx];
      const tickList = PIE.tickersBySlice[idx] || [];
      const preview = tickList.slice(0, 40).join(", ") + (tickList.length > 40 ? `, ... (+${tickList.length-40} more)` : "");
      sliceInfo.innerHTML = `<b>${sliceLabel}</b>: ${tickList.length} tickers<br><span style="opacity:.8">${preview}</span>`;
    });
  }

  // init
  drawPie();
  const defaultT = "TAPR";
  input.value = ALL[defaultT] ? defaultT : tickers[0];
  drawTicker(input.value);

  input.addEventListener("change", () => drawTicker(input.value));
})();
</script>

<style>
  .sim-ui{
    margin-top:16px;
    padding:14px;
    border-radius:18px;
    border:1px solid rgba(255,255,255,.12);
    background:rgba(255,255,255,.04);
    box-shadow:0 18px 60px rgba(0,0,0,.25);
  }
  .sim-top{
    display:flex; justify-content:space-between; align-items:flex-end;
    gap:12px; flex-wrap:wrap;
    margin-bottom:10px;
  }
  .sim-h{ font-weight:900; font-size:1.15rem; }
  .sim-sub{ opacity:.75; }

  #simTicker{
    width:min(320px, 80vw);
    padding:10px 12px;
    border-radius:12px;
    border:1px solid rgba(255,255,255,.12);
    background:rgba(255,255,255,.06);
    color:inherit;
    outline:none;
  }
  #simTicker:focus{ border-color: rgba(120,170,255,.6); }

  .sim-grid{
    display:grid;
    grid-template-columns: 1fr;
    gap:16px;
    align-items:start;
  }
  @media(max-width:980px){
    .sim-grid{ grid-template-columns: 1fr; }
  }
  .sim-card{
    border-radius:16px;
    border:1px solid rgba(255,255,255,.12);
    background:rgba(0,0,0,.10);
    padding:10px;
  }
  .sim-card-title{ font-weight:850; margin:4px 6px 10px; opacity:.9; }
  .sim-slice{
    margin-top:10px;
    padding:10px;
    border-radius:12px;
    border:1px solid rgba(255,255,255,.10);
    background:rgba(255,255,255,.04);
  }
</style>







<!-- ============== MONDAY EFFECT (per ticker + pie) ============== -->

<div class="mon-ui">
  <div class="mon-top">
    <div>
      <div class="mon-h">Monday Effect (per ticker)</div>
      <div class="mon-sub">Type a ticker to update the two-panel plot. Pie shows distribution across companies.</div>
    </div>

    <div>
      <input id="monTicker" list="monTickers" placeholder="Type ticker (e.g., AAPL)" />
      <datalist id="monTickers"></datalist>
    </div>
  </div>

  <div class="mon-grid">
    <div class="mon-card">
      <div class="mon-card-title">Ticker view</div>
      <div id="monPlot"></div>
    </div>

    <div class="mon-card">
      <div class="mon-card-title">Company distribution</div>
      <div id="monPie"></div>
      <div id="monSliceInfo" class="mon-slice"></div>
    </div>
  </div>
</div>

<script>
(async function(){
  const compUrl = "{{ site.baseurl }}/assets/data/monday_comp_all.json";
  const pieUrl  = "{{ site.baseurl }}/assets/data/monday_pie.json";

  const [compRes, pieRes] = await Promise.all([fetch(compUrl), fetch(pieUrl)]);
  const ALL = await compRes.json();
  const PIE = await pieRes.json();

  const input = document.getElementById("monTicker");
  const dl = document.getElementById("monTickers");
  const plotDiv = document.getElementById("monPlot");
  const pieDiv = document.getElementById("monPie");
  const sliceInfo = document.getElementById("monSliceInfo");

  // datalist
  const tickers = Object.keys(ALL).sort();
  tickers.forEach(t => {
    const opt = document.createElement("option");
    opt.value = t;
    dl.appendChild(opt);
  });

  function buildWinYearShapes(winYears){
    // add_vrect karşılığı: x0=y-0.5, x1=y+0.5
    return (winYears || []).map(y => ({
      type: "rect",
      xref: "x",
      yref: "paper",
      x0: y - 0.5,
      x1: y + 0.5,
      y0: 0.42,
      y1: 1.00,
      fillcolor: "rgba(0,0,0,0.06)",
      line: { width: 0 },
      layer: "below"
    }));
  }

  function drawTicker(tkr){
    tkr = (tkr || "").trim().toUpperCase();
    const d = ALL[tkr];
    if(!d){
      Plotly.newPlot(plotDiv, [], {title: "Ticker not found"}, {responsive:true});
      return;
    }

    const years = d.years;

    const trace1 = {
      x: years, y: d.monday_avg,
      type: "scatter", mode: "lines+markers",
      name: "Monday avg",
      hovertemplate: "Year=%{x}<br>Monday avg=%{y:.5f}<extra></extra>",
      xaxis: "x", yaxis: "y"
    };

    const trace2 = {
      x: years, y: d.non_monday_avg,
      type: "scatter", mode: "lines+markers",
      name: "Non-Monday avg",
      line: { dash: "dash" },
      hovertemplate: "Year=%{x}<br>Non-Monday avg=%{y:.5f}<extra></extra>",
      xaxis: "x", yaxis: "y"
    };

    const trace3 = {
      x: years, y: d.diff,
      type: "bar",
      name: "Diff (Mon - NonMon)",
      hovertemplate: "Year=%{x}<br>Diff=%{y:.5f}<extra></extra>",
      xaxis: "x2", yaxis: "y2"
    };

    const layout = {
      title: `Monday Effect — ${tkr} (win rate ${d.win_rate.toFixed(1)}%)`,
      height: 680,
      margin: {l: 55, r: 20, t: 70, b: 50},
      hovermode: "x unified",
      legend: {orientation:"h", y:1.07, x:0},

      xaxis:  {domain:[0,1], anchor:"y"},
      yaxis:  {domain:[0.42,1], title:"Avg return"},
      xaxis2: {domain:[0,1], anchor:"y2", title:"Year"},
      yaxis2: {domain:[0,0.34], title:"Diff"},

      shapes: buildWinYearShapes(d.win_years).concat([{
        type:"line",
        xref:"x2", yref:"y2",
        x0: Math.min(...years), x1: Math.max(...years),
        y0: 0, y1: 0,
        line: {dash:"dot", width:1}
      }])
    };

    Plotly.newPlot(plotDiv, [trace1, trace2, trace3], layout, {responsive:true});
  }

  function drawPie(){
    const labels = PIE.labels;
    const values = PIE.counts;

    const trace = {
      type: "pie",
      labels: labels,
      values: values,
      textinfo: "label+percent+value",
      hovertemplate: "<b>%{label}</b><br>Companies: %{value}<extra></extra>",
      pull: labels.map(() => 0.04)
    };

    const layout = {
      title: "Monday Effect — Company Distribution",
      height: 520,
      margin: {l: 10, r: 10, t: 60, b: 10},
      showlegend: true
    };

    Plotly.newPlot(pieDiv, [trace], layout, {responsive:true});

    pieDiv.on("plotly_click", (ev) => {
      const idx = ev.points[0].pointNumber;
      const sliceLabel = labels[idx];
      const tickList = PIE.tickersBySlice[idx] || [];
      const preview = tickList.slice(0, 40).join(", ")
        + (tickList.length > 40 ? `, ... (+${tickList.length-40} more)` : "");
      sliceInfo.innerHTML =
        `<b>${sliceLabel}</b>: ${tickList.length} tickers<br><span style="opacity:.8">${preview}</span>`;
    });
  }

  // init
  drawPie();
  const defaultT = "TAPR";
  input.value = ALL[defaultT] ? defaultT : tickers[0];
  drawTicker(input.value);

  input.addEventListener("change", () => drawTicker(input.value));
})();
</script>

<style>
  .mon-ui{
    margin-top:16px;
    padding:14px;
    border-radius:18px;
    border:1px solid rgba(255,255,255,.12);
    background:rgba(255,255,255,.04);
    box-shadow:0 18px 60px rgba(0,0,0,.25);
  }
  .mon-top{
    display:flex; justify-content:space-between; align-items:flex-end;
    gap:12px; flex-wrap:wrap;
    margin-bottom:10px;
  }
  .mon-h{ font-weight:900; font-size:1.15rem; }
  .mon-sub{ opacity:.75; }

  #monTicker{
    width:min(320px, 80vw);
    padding:10px 12px;
    border-radius:12px;
    border:1px solid rgba(255,255,255,.12);
    background:rgba(255,255,255,.06);
    color:inherit;
    outline:none;
  }
  #monTicker:focus{ border-color: rgba(120,170,255,.6); }

  .mon-grid{
    display:grid;
    grid-template-columns: 1fr; /* alt alta */
    gap:16px;
    align-items:start;
  }
  .mon-card{
    border-radius:16px;
    border:1px solid rgba(255,255,255,.12);
    background:rgba(0,0,0,.10);
    padding:10px;
  }
  .mon-card-title{ font-weight:850; margin:4px 6px 10px; opacity:.9; }
  .mon-slice{
    margin-top:10px;
    padding:10px;
    border-radius:12px;
    border:1px solid rgba(255,255,255,.10);
    background:rgba(255,255,255,.04);
  }
</style>
