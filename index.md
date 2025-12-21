---
layout: home
title: ""
subtitle: ""
use-site-title: false
mathjax: true
---

<style>
.hero-header{
  position: relative;
  width: 100%;
  min-height: 420px;
  display: flex;
  align-items: center;
  justify-content: center;
  background-image: url("{{ site.baseurl }}/assets/img/market_detectives.jpeg");
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  border-radius: 16px;
  overflow: hidden;
  margin-top: 8px;
  box-shadow: 0 14px 35px rgba(0,0,0,.12);
}

.hero-overlay{
  position: absolute;
  inset: 0;
  background: rgba(0,0,0,0.45);
}

.hero-content{
  position: relative;
  z-index: 2;
  text-align: center;
  color: #fff;
  max-width: 980px;
  padding: 28px 18px;
}

.hero-content h1{
  font-size: 2.8rem;
  font-weight: 850;
  margin: 0 0 10px 0;
  line-height: 1.1;
}

.hero-content p{
  font-size: 1.25rem;
  margin: 0;
  opacity: 0.92;
}

@media (max-width: 768px){
  .hero-header{ min-height: 300px; }
  .hero-content h1{ font-size: 2.0rem; }
  .hero-content p{ font-size: 1.05rem; }
}
</style>

<section class="hero-header">
  <div class="hero-overlay"></div>
  <div class="hero-content">
    <h1>Market Detectives – Investigating Calendar Effects</h1>
    <p>Analyzing Seven Calendar-Effect Anomalies in NASDAQ Since 1962</p>
  </div>
</section>

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
data-story="Zouhair conducts interviews, interrogations, and on-site investigations. He also gathers first-hand testimonies and observations">
<img src="assets/img/littlezouhair.png">
<div class="team5-body"><p class="team5-name">Zouhair</p><p class="team5-role"></p>Field investigator </div>
</div>

<div class="team5-card" data-name="Melvyn" data-role="Paris"
data-img="assets/img/littlemelvyn.png"
data-story="Melvyn connects clues, timelines, and behaviors. He identifies inconsistencies, motives, and hidden patterns">
<img src="assets/img/littlemelvyn.png">
<div class="team5-body"><p class="team5-name">Melvyn</p><p class="team5-role">Analyst & Pattern Specialist</p></div>
</div>

<div class="team5-card" data-name="Furkan" data-role="Paris"
data-img="assets/img/littlefurkan.png"
data-story="Furkan analyzes physical evidence, documents, photos, and forensic clues. He ensures accuracy, consistency, and traceability of findings ">
<img src="assets/img/littlefurkan.png">
<div class="team5-body"><p class="team5-name">Furkan</p><p class="team5-role">Evidence & Forensics Specialist</p></div>
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

<style>
  .content-block{
    display: flex;
    align-items: flex-start;
    gap: 32px;
    margin: 30px 0;
  }

  .content-image{
  height: 350px;   /* ajuste selon ton besoin */
  width: auto;
  max-width: none;
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
  <img src="assets/img/perrynasdaq.jpg" alt="perry nasdaq Meme" class="content-image">

  <div class="content-text">
    <p>
    The investigation begins with the dataset itself: NASDAQ, a technology-heavy stock market index. Diving into the NASDAQ data allows us to demystify the alleged calendar effects by first understanding the underlying market dynamics.
    </p>
  </div>
</div>



<iframe src="assets/img/plot_number_of_companies_per_year.html"
        width="100%"
        height="550"
        frameborder="0">
</iframe>

NASDAQ has transformed dramatically over time, with the number of listed companies climbing from a handful to thousands. While the exchange hosted only a handful of small technology firms in the early 1970s, the number of listed companies expanded rapidly across the decades, especially during the early 1980s, the dot-com period, and the post-2010 tech boom reaching over 5,000 firms by 2020. This evolution reflects major structural changes in the U.S. equity market, including sector diversification, higher listing activity, and increases in trading volume and liquidity.

This trend is especially relevant when looking at calendar effects as these anomalies are known to depend on market structure, liquidity conditions, and the composition of traded firms. A small, low-liquidity NASDAQ dominated by volatile growth stocks (1970s–1980s) may exhibit very different calendar anomalies than the modern, highly liquid and institutionally traded NASDAQ of the 2010s. As the number of listed firms grows, the distribution of returns, the prevalence of small caps, and the level of arbitrage activity all change, which can amplify, weaken, or eliminate calendar effects.

<iframe src="assets/img/plot_volume_per_year.html"
        width="100%"
        height="550"
        frameborder="0">
</iframe>
<p> What started as modest trading activity in the 1960s has grown into a torrent of market volume by 2020. Overall, trading activity exhibits a strong upward long-term trend, indicating a substantial increase in market participation and liquidity over time. Since calendar effects are often linked to investor behavior and trading activity, failing to account for volume dynamics may confound calendar effect estimate. So incorporating volume as a control variable or analyzing calendar effects within homogeneous sub-periods becomes essential. <br>
  
<iframe src="assets/img/plot_return_avg_per_year.html"
        width="100%"
        height="550"
        frameborder="0">
</iframe>


Over the 1962–2020 period, annual returns consistently lean positive. It means that returns are positive on average over the long run, despite year-to-year volatility. There are occasional negative returns (for example mid-1970s, late 2000s). Since the unconditional mean return is small, any calendar effects are expected to be weak relative to overall volatility. Moreover, the absence of a strong time trend in average returns supports a key assumption of calendar effect studies: return stationarity over time. This makes the dataset appropriate for isolating return differences attributable to calendar variables rather than structural change. It allows calendar-related differences to be analyzed without being confounded by structural market changes. </p>


## Getting an initial sense of the calendar effects

The detectives begin with an initial exploratory analysis aimed at visualizing potential calendar effects. 

Profile of each suspect pattern

<div class="flourish-embed flourish-cards" data-src="visualisation/26917943"><script src="https://public.flourish.studio/resources/embed.js"></script><noscript><img src="https://public.flourish.studio/visualisation/26917943/thumbnail" width="100%" alt="cards visualization" /></noscript></div>



The visual evidence reveals several intriguing regularities. Returns appear to differ depending on the timing within the trading week, with certain days consistently exhibiting weaker performance than others. Seasonal variations also emerge, as returns during the early part of the year seem marginally higher compared to the remainder of the sample. These patterns are consistent with what the literature commonly refers to as calendar effects.

( //Interpretation //) Indeed, plots demonstrate ____ .
 For each calendar effect, average returns are computed and compared across relevant time periods. By examining these averages, the team aims to determine whether any of the proposed calendar effects already appear detectable at the mean level.

Of course, simply looking at mean returns is not sufficient to conclude whether a calendar effect is real or statistically valid. Average differences may offer intuition, but they do not prove significance. These preliminary comparisons serve only as an initial diagnostic.  
The crucial question of whether these calendar effects are statistically significant needs to be investigated. This requires moving beyond visual evidence to formal statistical testing.

## Are the Calendar effects real ? 


<style>
  .content-block{
    display: flex;
    align-items: flex-start;
    gap: 32px;
    margin: 30px 0;
  }

  .content-image{
    width: 5000px;
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
  <img src="assets/img/perrymeme.png" alt="Image" class="content-image">

  <div class="content-text">
    <p>
      Reinforced by rigorous statistical tools, the detectives conduct an in-depth investigation into each calendar effect. Every suspected calendar anomaly is subjected to rigorous evaluation through formal          hypothesis testing. In particular, welch's test, mann-whitney u test and regression are employed to determine whether statistically significant differences in returns exist between calendar and non-calendar effect period.
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
    width: 350px;
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

<div class="content-block">
  <img src="assets/img/mwutest.jpg" alt="Mann-Whitney Test Image" class="content-image">

  <div class="content-text">
    <p>
      To determine whether calendar effects reflect a systematic shift in the distribution of returns, rather than the effect of rare outliers, the detectives call in a second independent witness: the Mann–Whitney U test. Unlike Welch’s test, Mann–Whitney does not rely on normality distribution assumptions and does not compare averages. Instead, it evaluates whether returns from one calendar period tend to be consistently higher or lower than those from another period across the entire distribution.
    </p>

    <p>
      They hope that by interviewing a mean-based witness and a rank-based one, it would help them distinguish between calendar effects driven by behavioral patterns and those driven by a few rare market events.
    </p>
  </div>
</div>



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

---
layout: page
title: Calendar Effects – Metric Explorer
permalink: /effects/
---

<div class="efx">
  <div class="efx-head">
    <div class="efx-title">Calendar Effects</div>
    <div class="efx-sub">X = effect, Y = seçtiğin değer. Önce test seç, sonra metric seç.</div>
  </div>

  <div class="efx-card">
    <div class="efx-row">
      <div class="efx-field">
        <label>Test</label>
        <select id="testSelect">
          <option value="ttest">t-test</option>
          <option value="mwu">Mann–Whitney U</option>
        </select>
      </div>

      <div class="efx-field">
        <label>Metric</label>
        <select id="metricSelect"></select>
      </div>

      <div class="efx-field">
        <label>Group</label>
        <select id="groupSelect">
          <option value="Main effects">Main effects</option>
          <option value="Holiday window day comparisons">Holiday window day comparisons</option>
          <option value="ALL">All</option>
        </select>
      </div>
    </div>

    <div id="plot" class="efx-plot"></div>
    <div class="efx-foot" id="foot"></div>
  </div>
</div>

<script src="https://cdn.plot.ly/plotly-2.30.0.min.js"></script>

<style>
  .efx{max-width:980px;margin:1.2rem auto;padding:0 1rem;font-family:system-ui,-apple-system,Segoe UI,Roboto,Arial}
  .efx-head{margin-bottom:10px}
  .efx-title{font-size:1.45rem;font-weight:900}
  .efx-sub{color:rgba(0,0,0,.65);margin-top:4px}

  .efx-card{
    background:#fff;border:1px solid rgba(0,0,0,.10);
    border-radius:16px;padding:14px;
    box-shadow:0 12px 36px rgba(0,0,0,.06);
  }

  .efx-row{display:grid;grid-template-columns:1fr 1fr 1fr;gap:10px;margin-bottom:10px}
  @media(max-width:900px){.efx-row{grid-template-columns:1fr}}
  .efx-field label{display:block;font-size:.86rem;color:rgba(0,0,0,.65);margin:2px 0 6px}
  .efx-field select{
    width:100%;
    padding:10px 12px;border-radius:12px;
    border:1px solid rgba(0,0,0,.14);background:#fff;outline:none;
  }

  .efx-plot{height:560px}
  .efx-foot{margin-top:8px;color:rgba(0,0,0,.62);font-size:.92rem;line-height:1.4}
</style>

<script>
(async function(){
  const url = "{{ '/assets/data/effects_tests.json' | relative_url }}";
  const res = await fetch(url);
  const data = await res.json();
  const rowsAll = data.rows || [];

  const testSelect   = document.getElementById("testSelect");
  const metricSelect = document.getElementById("metricSelect");
  const groupSelect  = document.getElementById("groupSelect");
  const foot         = document.getElementById("foot");

  // Senin istediğin metric listeleri:
  const METRICS = {
    ttest: [
      { key: "p",    label: "p-value" },
      { key: "stat", label: "t-test value (t-stat)" }
    ],
    mwu: [
      { key: "u",               label: "mannwhitneyu-test (U)" },
      { key: "p",               label: "p-value" },
      { key: "prob_superiority",label: "probability superiority" },
      { key: "cliffs_delta",    label: "Cliff’s delta" }
    ]
  };

  function populateMetricOptions(){
    const test = testSelect.value;
    metricSelect.innerHTML = "";

    METRICS[test].forEach(m => {
      const opt = document.createElement("option");
      opt.value = m.key;
      opt.textContent = m.label;
      metricSelect.appendChild(opt);
    });

    // default seçim:
    metricSelect.value = (test === "ttest") ? "stat" : "cliffs_delta";
  }

  function getY(row, metricKey){
    // JSON'da ttest için "stat", mwu için "u" var. p zaten var.
    // Bazı satırlarda metric olmayabilir -> null dönelim
    const v = row[metricKey];
    if (v === undefined || v === null || Number.isNaN(v)) return null;
    return v;
  }

  function buildHover(row, test){
    if (test === "ttest"){
      return `Effect: <b>${row.effect}</b><br>` +
             `t-stat: <b>${(row.stat ?? 0).toFixed(4)}</b><br>` +
             `p: <b>${row.p}</b>`;
    }
    return `Effect: <b>${row.effect}</b><br>` +
           `U: <b>${(row.u ?? 0).toFixed(2)}</b><br>` +
           `p: <b>${row.p}</b><br>` +
           `prob superiority: <b>${(row.prob_superiority ?? 0).toFixed(4)}</b><br>` +
           `Cliff's delta: <b>${(row.cliffs_delta ?? 0).toFixed(4)}</b>`;
  }

  function render(){
    const test = testSelect.value;        // ttest | mwu
    const metricKey = metricSelect.value; // dynamic
    const grp = groupSelect.value;

    let rows = rowsAll.filter(r => r.test === test);
    if (grp !== "ALL") rows = rows.filter(r => r.group === grp);

    // X = effect (senin istediğin ana tema)
    const x = rows.map(r => r.effect);
    const y = rows.map(r => getY(r, metricKey));
    const hover = rows.map(r => buildHover(r, test));

    // title
    const metricLabel = (METRICS[test].find(m => m.key === metricKey) || {}).label || metricKey;

    const trace = {
      type: "scatter",
      mode: "markers",
      x, y,
      text: hover,
      hoverinfo: "text",
      marker: {size: 14, opacity: 0.9, line: {width: 1}}
    };

    const layout = {
      title: {text: `${test} · ${metricLabel}`, x: 0.02, xanchor: "left"},
      margin: {l: 70, r: 20, t: 60, b: 140},
      xaxis: {title: "Effect", tickangle: -25, automargin: true},
      yaxis: {title: metricLabel, zeroline: true},
      paper_bgcolor: "rgba(0,0,0,0)",
      plot_bgcolor: "rgba(0,0,0,0)",
      height: 560,
      showlegend: false
    };

    Plotly.react("plot", [trace], layout, {displayModeBar: true, responsive: true});

    // küçük açıklama
    if (test === "mwu" && metricKey === "u"){
      foot.innerHTML = `Not: U istatistiği ölçek olarak çok büyük olabilir; görsel olarak daha anlamlı metric genelde <b>Cliff’s delta</b>.`;
    } else {
      foot.innerHTML = `X = effect, Y = <b>${metricLabel}</b>. Test değiştirince metric seçenekleri otomatik değişiyor.`;
    }
  }

  // events
  testSelect.addEventListener("change", () => {
    populateMetricOptions();
    render();
  });

  metricSelect.addEventListener("change", render);
  groupSelect.addEventListener("change", render);

  // init
  populateMetricOptions();
  render();
})();
</script>

<div class="efx">
  <div class="efx-head">
    <div class="efx-title">Calendar Effects</div>
    <div class="efx-sub">
      Halkadan bir effect seç. Ortadaki kutu seçtiğin testin sonuçlarını gösterecek.
    </div>
  </div>

  <div class="efx-card">
    <div class="efx-row">
      <div class="efx-field">
        <label>Test</label>
        <select id="testSelect">
          <option value="ttest">t-test</option>
          <option value="mwu">Mann–Whitney U</option>
        </select>
      </div>

      <div class="efx-field">
        <label>Group</label>
        <select id="groupSelect">
          <option value="Main effects">Main effects</option>
          <option value="Holiday window day comparisons">Holiday window day comparisons</option>
          <option value="ALL">All</option>
        </select>
      </div>

      <div class="efx-field">
        <label>Auto</label>
        <select id="modeSelect">
          <option value="keep">Seçimi koru</option>
          <option value="first">Filtre değişince ilk effect</option>
        </select>
      </div>
    </div>

    <div id="ringPlot" class="efx-plot"></div>
    <div class="efx-foot" id="foot"></div>
  </div>
</div>

<script src="https://cdn.plot.ly/plotly-2.30.0.min.js"></script>

<div class="efx">
  <div class="efx-head">
    <div class="efx-title">Calendar Effects — Significance Ring</div>
    <div class="efx-sub">Sadece test seç. Halkadan effect’e tıkla.</div>
  </div>

  <div class="efx-card">
    <div class="efx-row">
      <div class="efx-field">
        <label for="testSelect">Test</label>
        <select id="testSelect">
          <option value="ttest">t-test</option>
          <option value="mwu">Mann–Whitney U</option>
        </select>
      </div>
    </div>

    <div id="ringPlot" class="efx-plot"></div>
    <div id="foot" class="efx-foot"></div>
  </div>
</div>

<style>
  .efx{max-width:980px;margin:1.2rem auto;padding:0 1rem;font-family:system-ui,-apple-system,Segoe UI,Roboto,Arial}
  .efx-head{margin-bottom:10px}
  .efx-title{font-size:1.45rem;font-weight:900}
  .efx-sub{color:rgba(0,0,0,.65);margin-top:4px}

  .efx-card{
    background:#fff;border:1px solid rgba(0,0,0,.10);
    border-radius:16px;padding:14px;
    box-shadow:0 12px 36px rgba(0,0,0,.06);
  }

  .efx-row{display:grid;grid-template-columns:1fr;gap:10px;margin-bottom:10px}
  .efx-field label{display:block;font-size:.86rem;color:rgba(0,0,0,.65);margin:2px 0 6px}
  .efx-field select{
    width:100%;
    padding:10px 12px;border-radius:12px;
    border:1px solid rgba(0,0,0,.14);background:#fff;outline:none;
  }

  .efx-plot{height:560px}
  .efx-foot{margin-top:8px;color:rgba(0,0,0,.62);font-size:.92rem;line-height:1.4}
</style>

<script>
(async function(){
  const url = "{{ '/assets/data/effects_tests.json' | relative_url }}";
  const res = await fetch(url);
  const data = await res.json();
  const rowsAll = (data.rows || []).map(r => ({
    ...r,
    // güvenli string normalize
    effect: (r.effect ?? "").toString().trim(),
    group: (r.group ?? "").toString().trim(),
    test:  (r.test  ?? "").toString().trim()
  }));

  const testSelect  = document.getElementById("testSelect");
  const foot        = document.getElementById("foot");

  let selectedEffect = null;

  function fmtNum(x, digits=4){
    if (x === undefined || x === null || Number.isNaN(x)) return "—";
    const n = Number(x);
    if (!Number.isFinite(n)) return "—";
    return n.toFixed(digits);
  }

  function fmtP(x){
    if (x === undefined || x === null || Number.isNaN(x)) return "—";
    const n = Number(x);
    if (!Number.isFinite(n)) return "—";
    if (Math.abs(n) > 0 && Math.abs(n) < 1e-4) return n.toExponential(2);
    return n.toFixed(6);
  }

  // kritik fix: test adlarını normalize et (mwu gelmeme sorunu burada bitiyor)
  function normalizeTest(s){
    const t = (s ?? "").toString().trim().toLowerCase();
    if (t === "ttest" || t === "t-test" || t === "t_test") return "ttest";
    if (t === "mwu" || t === "mw" || t.includes("mann") || t.includes("whitney")) return "mwu";
    return t;
  }

  function filterRows(){
    const selectedTest = normalizeTest(testSelect.value);

    // sadece main effects (senin istediğin)
    let rows = rowsAll.filter(r => r.group === "Main effects");

    // test filtre (burada normalize ile garanti)
    rows = rows.filter(r => normalizeTest(r.test) === selectedTest);

    // effect adı boşsa at
    rows = rows.filter(r => r.effect.length > 0);

    return rows;
  }

  function centerTextFor(row){
    if (!row){
      return "<b>Bir effect seç</b><br><span style='opacity:.75'>Halkadan tıkla</span>";
    }

    const eff = row.effect;
    const test = normalizeTest(testSelect.value);

    if (test === "ttest"){
      return `<b>${eff}</b><br>` +
             `<span style="font-size:13px;opacity:.75">t-test</span><br>` +
             `<span style="font-size:14px">t-stat: <b>${fmtNum(row.stat, 4)}</b></span><br>` +
             `<span style="font-size:14px">p-value: <b>${fmtP(row.p)}</b></span>`;
    }

    // MWU
    return `<b>${eff}</b><br>` +
           `<span style="font-size:13px;opacity:.75">Mann–Whitney U</span><br>` +
           `<span style="font-size:14px">U: <b>${fmtNum(row.u, 2)}</b></span><br>` +
           `<span style="font-size:14px">p-value: <b>${fmtP(row.p)}</b></span><br>` +
           `<span style="font-size:14px">prob sup.: <b>${fmtNum(row.prob_superiority, 4)}</b></span><br>` +
           `<span style="font-size:14px">Cliff’s δ: <b>${fmtNum(row.cliffs_delta, 4)}</b></span>`;
  }

  function buildPie(rows){
    const labels = rows.map(r => r.effect);
    const values = rows.map(_ => 1);

    const test = normalizeTest(testSelect.value);
    const hovertext = rows.map(r => {
      if (test === "ttest"){
        return `Effect: <b>${r.effect}</b><br>` +
               `t-stat: <b>${fmtNum(r.stat, 4)}</b><br>` +
               `p: <b>${fmtP(r.p)}</b>`;
      }
      return `Effect: <b>${r.effect}</b><br>` +
             `U: <b>${fmtNum(r.u, 2)}</b><br>` +
             `p: <b>${fmtP(r.p)}</b><br>` +
             `prob superiority: <b>${fmtNum(r.prob_superiority, 4)}</b><br>` +
             `Cliff's delta: <b>${fmtNum(r.cliffs_delta, 4)}</b>`;
    });

    return {
      type: "pie",
      labels,
      values,
      hole: 0.62,
      sort: false,
      direction: "clockwise",
      textinfo: "label",
      textposition: "outside",
      automargin: true,
      hoverinfo: "text",
      hovertext
    };
  }

  function render(){
    const rows = filterRows();

    if (!rows.length){
      Plotly.react("ringPlot", [], {
        height: 560,
        margin: {l:20,r:20,t:20,b:20},
        annotations: [{
          xref:"paper", yref:"paper", x:0.5, y:0.5,
          text:"<b>Bu test için veri yok</b><br><span style='opacity:.75'>JSON test alanını kontrol et</span>",
          showarrow:false, align:"center"
        }]
      }, {displayModeBar:false, responsive:true});

      foot.innerHTML = `Seçilen test = <b>${normalizeTest(testSelect.value)}</b>. (Main effects filtresi açık)`;
      return;
    }

    // seçili effect yoksa ilkini seç
    const set = new Set(rows.map(r => r.effect));
    if (!selectedEffect || !set.has(selectedEffect)) selectedEffect = rows[0].effect;

    const selectedRow = rows.find(r => r.effect === selectedEffect) || null;
    const centerHTML = centerTextFor(selectedRow);

    const layout = {
      margin: {l: 20, r: 20, t: 20, b: 20},
      height: 560,
      showlegend: false,
      paper_bgcolor: "rgba(0,0,0,0)",
      plot_bgcolor: "rgba(0,0,0,0)",
      shapes: [{
        type: "circle",
        xref: "paper", yref: "paper",
        x0: 0.5 - 0.17, x1: 0.5 + 0.17,
        y0: 0.5 - 0.12, y1: 0.5 + 0.12,
        fillcolor: "white",
        line: {color: "rgba(0,0,0,.12)", width: 1}
      }],
      annotations: [{
        xref: "paper", yref: "paper",
        x: 0.5, y: 0.5,
        text: centerHTML,
        showarrow: false,
        align: "center",
        font: {size: 14, color: "rgba(0,0,0,.92)"}
      }]
    };

    Plotly.react("ringPlot", [buildPie(rows)], layout, {displayModeBar: true, responsive: true});

    foot.innerHTML = `Halka dilimleri = <b>effect</b>. Tıkla. Seçilen test = <b>${normalizeTest(testSelect.value)}</b>. (Sadece Main effects)`;

    const gd = document.getElementById("ringPlot");
    // eski handler'ları temizle (üst üste binmesin)
    gd.removeAllListeners?.("plotly_click");

    gd.on("plotly_click", (ev) => {
      const label = ev?.points?.[0]?.label;
      if (!label) return;
      selectedEffect = label;

      const row = filterRows().find(r => r.effect === selectedEffect);
      Plotly.relayout(gd, {"annotations[0].text": centerTextFor(row)});
    });
  }

  testSelect.addEventListener("change", render);
  render();
})();
</script>




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

### Linear Regression

<p align="center">
  <img src="assets/img/perry_regression.png" width="500">
</p>

After all these very inconclusive investigations, the detictives couldn't stop here, they had to find other accomplices that might have helped the suspects to further examine whether calendar effects leave a systematic imprint on market returns or not. For that they choose the linear regression framework, this approach helps them to quantify the average effect of each calendar indicator on daily returns while controlling the accomplices which in this case are market conditions (such as volatility and trading volume) and interest rates which they managed to get as a clue from the published fed funds dataset. By exploiting the full sample of available data, the regression provides both an estimate of the magnitude of each effect and a measure of its statistical significance.

<details markdown="1">
  <summary><strong>Linear Regression</strong></summary>
<p>
A supervised statistical model in which the expected value of the response variable is modeled as a linear combination of explanatory variables.
  
In our setting, the model relates daily stock returns to calendar-effect indicators and control variables such as volatility, interest rates and trading volume. The coefficients capture the average change in returns associated with each calendar effect, holding other factors constant.
</p>
</details>

These are the equations they are tryping to achieve using the linear regression:

$$
\text{Return}_t
=
\beta_0
+
\beta_1 \,\mathbb{1}_{\text{Calendar Effect}_t}
+
\beta_2 \,\text{Volatility}_t
+
\beta_3 \,\text{Volume}_t
+
\varepsilon_t
$$

and

$$
\text{Return}_t
=
\beta_0
+
\beta_1 \,\mathbb{1}_{\text{Calendar Effect}_t}
+
\beta_2 \,\text{Interest Rate}_t
+
\varepsilon_t
$$

Now you might ask why they have two different equations, this mainly depends on the clues they have as they don't behave the same way.

When studying trading volume and volatility, they found that the data have lots of dependencies. First, the stocks tend to move together on the same trading day, so they might affect each other. In addition to that, stock also exhibits persistence over time meaning the returns of the same stock from previous days can affect its daily return. Thus, treating these observations as independent would give us a false sense of certainty. To avoid more confusion, they decided to choose a regressions with standard errors clustered both by ticker and by date, this allows the model to account for big events that cann affect the whole market or stock specific events.

On the other hand, interest rates have a completely different behaviour. Unlike volume or volatility, they do not vary across stocks and evolve only over time. Applying the same clustering strategy here would add noise rather than controlling it. For this, they decide to use heteroskedasticity and autocorrelation consistent (HAC) standard errors instead, which are specifically designed to handle serial dependence in time series.

By tailoring their regression approach to the structure of each clue, they ensure that any remaining calendar effects they uncover are not caused by the data’s dependence, but genuine signals worthy of further tests and efforts.

Keep in mind that at this stage, the detectives are not trying to to forecast returns, but to measure whether calendar indicators leave a systematic average imprint on the data once market conditions and dependence structures are controlled. More complex models could capture nonlinear patterns or higher-order dynamics, but they would come at the cost of interpretability and would risk fitting noise rather than signal. That's why although they have a *R-Squared* value equal to zero in all the following models. they still believe it was the model that suited the the best.

<details class="outer-details">
  <summary><strong>Linear Regression Summaries</strong></summary>
  <p>Choose Time Series for interest rate regression, or Clustering for volume and volatility.</p>

  <!-- ================= TIME SERIES ================= -->
  <details class="mid-details">
    <summary><strong>Time Series</strong></summary>

    <div class="effect-block">
      <details>
        <summary><b>📉 January Effect</b></summary>
        <div class="image-box">
          <img src="{{ '/assets/img/jan_fed.png' | relative_url }}" alt="January Effect">
        </div>
        <p class="effect-description">
          The January effect becomes statistically significant once interest rates are controlled for and serial correlation is addressed using HAC standard errors which means that it managed to survive the serial correlation correction. On the other had, fed funds have a negative coffiecient and a p-value > 0.5 which makes it insignificant.That being said, the model still explains only a very small fraction of daily return variation it only suggets that January have a very faint yet persistent footprint in the data.
        </p>
      </details>
    </div>

    <div class="effect-block">
      <details>
        <summary><b>🎅 Santa Claus Rally Effect</b></summary>
        <div class="image-box">
          <img src="{{ '/assets/img/scr_fed.png' | relative_url }}" alt="Santa Claus Rally – Interest Rate">
        </div>
        <p class="effect-description">
           description
        </p>
      </details>
    </div>

    <div class="effect-block">
      <details>
        <summary><b>🎃 Halloween Effect</b></summary>
        <div class="image-box">
          <img src="{{ '/assets/img/may_fed.png' | relative_url }}" alt="Halloween Effect – Interest Rate">
        </div>
        <p class="effect-description">
           description
        </p>
      </details>
    </div>

    <div class="effect-block">
      <details>
        <summary><b>🎉 Holiday Effect</b></summary>
        <div class="image-box">
          <img src="{{ '/assets/img/hol_fed.png' | relative_url }}" alt="Holiday Effect – Interest Rate">
        </div>
        <p class="effect-description">
           description
        </p>
      </details>
    </div>

  </details>

  <!-- ================= CLUSTERING ================= -->
  <details class="mid-details">
    <summary><strong>Time Clustering</strong></summary>

    <div class="effect-block">
      <details>
        <summary><b>📉 January Effect</b></summary>
        <div class="image-box">
          <img src="{{ '/assets/img/jan_vol.png' | relative_url }}" alt="January Effect – Volume">
        </div>
        <p class="effect-description">
           description
        </p>
      </details>
    </div>

    <div class="effect-block">
      <details>
        <summary><b>🎅 Santa Claus Rally Effect</b></summary>
        <div class="image-box">
          <img src="{{ '/assets/img/scr_vol.png' | relative_url }}" alt="Santa Claus Rally – Volume">
        </div>
        <p class="effect-description">
           description
        </p>
      </details>
    </div>

    <div class="effect-block">
      <details>
        <summary><b>🎃 Halloween Effect</b></summary>
        <div class="image-box">
          <img src="{{ '/assets/img/may_vol.png' | relative_url }}" alt="Halloween Effect – Volume">
        </div>
        <p class="effect-description">
           description
        </p>
      </details>
    </div>

    <div class="effect-block">
      <details>
        <summary><b>🎉 Holiday Effect</b></summary>
        <div class="image-box">
          <img src="{{ '/assets/img/hol_vol.png' | relative_url }}" alt="Holiday Effect – Volume">
        </div>
        <p class="effect-description">
           description
        </p>
      </details>
    </div>

  </details>

</details>


## Monday effect
### Across decades
### Across exchanges
### Through the Dot Com Bubble
### Through Global Financial Crisis

---
## January effect
### Across decades
### Across exchanges
### Through the Dot Com Bubble
### Through Global Financial Crisis

---
## Santa Claus Rally
### Across decades
### Across exchanges
### Through the Dot Com Bubble
### Through Global Financial Crisis

---
## Turn-of-the-Month
### Across decades
### Across exchanges
### Through the Dot Com Bubble
### Through Global Financial Crisis

---
## Half-Month
### Across decades
### Across exchanges
### Through the Dot Com Bubble
### Through Global Financial Crisis

---
## Halloween effect (“Sell in May”)
### Across decades
### Across exchanges
### Through the Dot Com Bubble
### Through Global Financial Crisis

---
## Holiday effect
### Across decades
<iframe src="assets/img/plot_holiday_effect_by_decade.html"
        width="100%"
        height="550"
        frameborder="0">
</iframe>
Looking at the chart, a clear pattern stands out. Across all decades, returns tend to be higher on days before holidays than on normal trading days. However, what once looked like a strong and regular market behavior gradually becomes less pronounced, hinting that market may have adapted to this seasonal tendency.
### Across exchanges
<iframe src="assets/img/plot_holiday_effect_exchange.html"
        width="100%"
        height="550"
        frameborder="0">
</iframe>
Holiday-related return differences vary widely across exchanges. The effect appears strongest on NASDAQ and NYSE American, where returns tend to be higher before holidays, while the NYSE exhibits a more modest increase. In contrast, ETFs and BATS/Cboe show little to no noticeable holiday effect, suggesting that this pattern is mainly concentrated in traditional equity markets.

### Through the Dot Com Bubble and Global Financial Crisis
<iframe src="assets/img/plot_crisis_holiday_heatmap.html"
        width="100%"
        height="550"
        frameborder="0">
During the Dot-Com bubble, performance around holidays turns weak and often negative, especially in the days following the break: The effect weakens. In contrast, during the Global Financial Crisis, returns around holidays are mostly positive, with particularly strong gains just before the holiday, showing that holiday effect remains during this crisis.


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


## Calendar effect during crises ?

<div class="content-block">
  <img src="assets/img/perry_CNN.png" alt="Market Crisis Image" class="content-image">

  <div class="content-text">
    <p>
      The detectives turn their attention to the darkest moments in market history: Black Monday in 1987, the dot-com crash of 2000–2002, and the global financial crisis of 2008–2009. As they examine the data, familiar calendar patterns begin to fade.
    </p>

    <p>
      Market crises are special periods. Volatility is high. Uncertainty dominates.
    </p>
  </div>
</div>


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
           <div class="fx-icon">MAY</div> <div class="fx-card-main"> 
           <div class="fx-card-title">Sell in May</div> 
           <div class="fx-card-sub">Season regime</div> 
           </div> <div class="fx-chip">macro</div> 
        </button>

        <button class="fx-card"
          data-key="holiday"
          data-title="Holiday Effect"
          data-desc="Pre/post-holiday behavior: abnormal returns around holidays."
          data-img="{{ site.baseurl }}/assets/img/New_Year_1.png">
          <div class="fx-icon">HOL</div>
          <div class="fx-card-main">
            <div class="fx-card-title">Holiday Effect</div>
            <div class="fx-card-sub">Event timing</div>
          </div>
          <div class="fx-chip">event</div>
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
        
        <div class="fx-holiday-row" id="fxHolidayRow" style="display:none;">
          <div class="fx-holiday-label">Choose holiday</div>
          <select id="fxHolidaySelect" class="fx-holiday-select"></select>
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

    // Holiday UI
    const holidayRow = root.querySelector("#fxHolidayRow");
    const holidaySel = root.querySelector("#fxHolidaySelect");

    // ===== MANUAL MAPPING (18 seçenek) =====
    // Dosya yolu: {{site.baseurl}}/assets/img/holidays/<file>.png
    const HOLIDAY_BASE = "{{ site.baseurl }}/assets/img/";

    const holidayOptions = [
      // New Year
      { label: "New Year 1", file: "New_Year_1.png" },
      { label: "New Year 2", file: "New_Year_2.png" },
      { label: "New Year 3", file: "New_Year_3.png" },

      // Christmas
      { label: "Christmas 1", file: "Christmas_1.png" },
      { label: "Christmas 2", file: "Christmas_2.png" },
      { label: "Christmas 3", file: "Christmas_3.png" },

      // Thanksgiving
      { label: "Thanksgiving 1", file: "Thanksgiving_1.png" },
      { label: "Thanksgiving 2", file: "Thanksgiving_2.png" },
      { label: "Thanksgiving 3", file: "Thanksgiving_3.png" },

      // Independence Day
      { label: "Independence Day 1", file: "Independence_Day_1.png" },
      { label: "Independence Day 2", file: "Independence_Day_2.png" },
      { label: "Independence Day 3", file: "Independence_Day_3.png" },

      // Memorial Day
      { label: "Memorial Day 1", file: "Memorial_Day_1.png" },
      { label: "Memorial Day 2", file: "Memorial_Day_2.png" },
      { label: "Memorial Day 3", file: "Memorial_Day_3.png" },

      // Labor Day
      { label: "Labor Day 1", file: "Labor_Day_1.png" },
      { label: "Labor Day 2", file: "Labor_Day_2.png" },
      { label: "Labor Day 3", file: "Labor_Day_3.png" }
    ];

    function setLoading(on){
      shim.style.display = on ? "block" : "none";
      img.style.opacity = on ? "0.65" : "1";
    }

    function setImage(src){
      setLoading(true);
      img.onload = () => setLoading(false);
      img.onerror = () => {
        setLoading(false);
        // Eğer image path yanlışsa hiç değilse user anlasın
        img.alt = "Image not found: " + src;
      };
      img.src = src;
      open.href = src;
    }

    function buildHolidaySelect(){
      if (!holidaySel) return;
      holidaySel.innerHTML = "";
      holidayOptions.forEach((opt, idx) => {
        const o = document.createElement("option");
        o.value = opt.file;
        o.textContent = opt.label;
        holidaySel.appendChild(o);
        if (idx === 0) holidaySel.value = opt.file;
      });
    }

    function showHolidayUI(show){
      if (!holidayRow) return;
      holidayRow.style.display = show ? "flex" : "none";
    }

    function activate(btn){
      cards.forEach(c => c.classList.remove("active"));
      btn.classList.add("active");

      ttl.textContent = btn.dataset.title || "Effect";
      dsc.textContent = btn.dataset.desc || "";

      const key = btn.dataset.key || "";
      const src = btn.dataset.img;

      // Holiday ise: dropdown göster, seçilen holiday'e göre resmi bas
      if (key === "holiday") {
        showHolidayUI(true);

        // İlk kez geldiyse select'i kur
        if (!holidaySel.dataset.built) {
          buildHolidaySelect();
          holidaySel.dataset.built = "1";
        }

        // Seçili option'a göre src üret
        const chosen = holidaySel.value || "New_Year_1.png";
        const holidaySrc = HOLIDAY_BASE + chosen;
        setImage(holidaySrc);

      } else {
        showHolidayUI(false);
        setImage(src);
      }

      img.scrollIntoView({ behavior: "smooth", block: "nearest" });
    }

    // Holiday dropdown change
    if (holidaySel) {
      holidaySel.addEventListener("change", () => {
        // Sadece holiday aktifken çalışsın
        const active = root.querySelector(".fx-card.active");
        if (!active || active.dataset.key !== "holiday") return;

        const chosen = holidaySel.value;
        const holidaySrc = HOLIDAY_BASE + chosen;
        setImage(holidaySrc);
      });
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

    // optional: sayfa açılınca holiday select'i kur (zararı yok)
    buildHolidaySelect();

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


<!-- ============================================================
  ✅ ONE-PAGE EFFECTS HUB (PIE NAV + COLLAPSIBLE SECTIONS)
  - No analysis/plot logic changed
  - Only wrapped each effect in <section> and added hub + show/hide
============================================================ -->

<!-- Plotly (load once is enough; kept as you had it in places too) -->
<script src="https://cdn.plot.ly/plotly-2.30.0.min.js"></script>

<!-- ========== EFFECTS OVERVIEW (Pie Navigation) ========== -->
<div class="effects-hub">
  <div class="hub-head">
    <div>
      <div class="hub-title">Calendar Effects Explorer</div>
      <div class="hub-sub">Click a slice to open that effect below. (Others collapse.)</div>
    </div>
    <div class="hub-mini">
      <button class="hub-btn" data-open="all">Show all</button>
      <button class="hub-btn" data-open="none">Collapse</button>
    </div>
  </div>

  <div class="hub-grid">
    <div class="hub-card">
      <div class="hub-card-title">Effects</div>
      <div id="effectsPie"></div>
      <div class="hub-note" id="effectsHint"></div>
    </div>

    <div class="hub-card">
      <div class="hub-card-title">Opened effect</div>
      <div class="hub-opened" id="openedEffectName">None</div>
      <div class="hub-note">Tip: share links like <code>#santa</code>, <code>#sim</code>, <code>#monday</code>, <code>#january</code>, <code>#holiday</code></div>
    </div>
  </div>
</div>

<style>
  .effects-hub{
    margin: 18px 0 22px;
    padding: 14px;
    border-radius: 18px;
    border: 1px solid rgba(255,255,255,.12);
    background: rgba(255,255,255,.04);
    box-shadow: 0 18px 60px rgba(0,0,0,.25);
  }
  .hub-head{display:flex;justify-content:space-between;gap:12px;flex-wrap:wrap;align-items:flex-end;margin-bottom:10px}
  .hub-title{font-weight:950;font-size:1.25rem}
  .hub-sub{opacity:.75;max-width:85ch}
  .hub-mini{display:flex;gap:10px;flex-wrap:wrap}
  .hub-btn{
    cursor:pointer;
    padding:10px 12px;
    border-radius:12px;
    border:1px solid rgba(255,255,255,.12);
    background:rgba(255,255,255,.06);
    color:inherit;
  }
  .hub-btn:hover{border-color:rgba(120,170,255,.45)}
  .hub-grid{display:grid;grid-template-columns: 1.25fr .75fr;gap:14px}
  @media(max-width:980px){.hub-grid{grid-template-columns:1fr}}
  .hub-card{
    border-radius:16px;
    border:1px solid rgba(255,255,255,.12);
    background:rgba(0,0,0,.10);
    padding:10px;
  }
  .hub-card-title{font-weight:850;margin:4px 6px 10px;opacity:.9}
  .hub-note{margin-top:10px;padding:10px;border-radius:12px;border:1px solid rgba(255,255,255,.10);background:rgba(255,255,255,.04);opacity:.9}
  .hub-opened{font-weight:900;font-size:1.05rem;opacity:.95;margin:8px 6px 2px}

  /* Sections show/hide */
  .effect-section{ display:none; margin-top:16px; }
  .effect-section.active{ display:block; }

  /* Show-all mode */
  .effects-all .effect-section{ display:block; }
</style>


<!-- ============================================================
  ✅ SECTION 1: SANTA (your code unchanged; only wrapped)
============================================================ -->
<section class="effect-section" id="effect-santa" data-effect="santa" data-title="Santa Claus Effect">

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

</section>


<!-- ============================================================
  ✅ SECTION 2: SELL IN MAY (your code unchanged; only wrapped)
============================================================ -->
<section class="effect-section" id="effect-sim" data-effect="sim" data-title="Sell in May">

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

</section>


<!-- ============================================================
  ✅ SECTION 3: MONDAY (your code unchanged; only wrapped)
============================================================ -->
<section class="effect-section" id="effect-monday" data-effect="monday" data-title="Monday Effect">

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

</section>


<!-- ============================================================
  ✅ SECTION 4: JANUARY (your code unchanged; only wrapped)
============================================================ -->
<section class="effect-section" id="effect-january" data-effect="january" data-title="January Effect">

<div class="jan-ui">
  <div class="jan-top">
    <div>
      <div class="jan-h">January Effect (per ticker)</div>
      <div class="jan-sub">Type a ticker to update the two-panel plot. Pie shows distribution across companies.</div>
    </div>

    <div>
      <input id="janTicker" list="janTickers" placeholder="Type ticker (e.g., AAPL)" />
      <datalist id="janTickers"></datalist>
    </div>
  </div>

  <div class="jan-grid">
    <div class="jan-card">
      <div class="jan-card-title">Ticker view</div>
      <div id="janPlot"></div>
    </div>

    <div class="jan-card">
      <div class="jan-card-title">Company distribution</div>
      <div id="janPie"></div>
      <div id="janSliceInfo" class="jan-slice"></div>
    </div>
  </div>
</div>

<script>
(async function(){
  const compUrl = "{{ site.baseurl }}/assets/data/january_comp_all.json";
  const pieUrl  = "{{ site.baseurl }}/assets/data/january_pie.json";

  const [compRes, pieRes] = await Promise.all([fetch(compUrl), fetch(pieUrl)]);
  const ALL = await compRes.json();
  const PIE = await pieRes.json();

  const input = document.getElementById("janTicker");
  const dl = document.getElementById("janTickers");
  const plotDiv = document.getElementById("janPlot");
  const pieDiv = document.getElementById("janPie");
  const sliceInfo = document.getElementById("janSliceInfo");

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
      x: years, y: d.jan_avg,
      type: "scatter", mode: "lines+markers",
      name: "Jan avg",
      hovertemplate: "Year=%{x}<br>Jan avg=%{y:.5f}<extra></extra>",
      xaxis: "x", yaxis: "y"
    };

    const trace2 = {
      x: years, y: d.other_months_avg,
      type: "scatter", mode: "lines+markers",
      name: "Feb–Dec avg",
      line: { dash: "dash" },
      hovertemplate: "Year=%{x}<br>Feb–Dec avg=%{y:.5f}<extra></extra>",
      xaxis: "x", yaxis: "y"
    };

    const trace3 = {
      x: years, y: d.diff,
      type: "bar",
      name: "Diff (Jan - Feb–Dec)",
      hovertemplate: "Year=%{x}<br>Diff=%{y:.5f}<extra></extra>",
      xaxis: "x2", yaxis: "y2"
    };

    const layout = {
      title: `January Effect — ${tkr} (win rate ${d.win_rate.toFixed(1)}%)`,
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
      title: "January Effect — Company Distribution",
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

  drawPie();
  const defaultT = "TAPR";
  input.value = ALL[defaultT] ? defaultT : tickers[0];
  drawTicker(input.value);

  input.addEventListener("change", () => drawTicker(input.value));
})();
</script>

<style>
  .jan-ui{ margin-top:16px; padding:14px; border-radius:18px; border:1px solid rgba(255,255,255,.12);
    background:rgba(255,255,255,.04); box-shadow:0 18px 60px rgba(0,0,0,.25); }
  .jan-top{ display:flex; justify-content:space-between; align-items:flex-end; gap:12px; flex-wrap:wrap; margin-bottom:10px; }
  .jan-h{ font-weight:900; font-size:1.15rem; }
  .jan-sub{ opacity:.75; }

  #janTicker{ width:min(320px, 80vw); padding:10px 12px; border-radius:12px; border:1px solid rgba(255,255,255,.12);
    background:rgba(255,255,255,.06); color:inherit; outline:none; }
  #janTicker:focus{ border-color: rgba(120,170,255,.6); }

  .jan-grid{ display:grid; grid-template-columns: 1fr; gap:16px; align-items:start; } /* alt alta */
  .jan-card{ border-radius:16px; border:1px solid rgba(255,255,255,.12); background:rgba(0,0,0,.10); padding:10px; }
  .jan-card-title{ font-weight:850; margin:4px 6px 10px; opacity:.9; }
  .jan-slice{ margin-top:10px; padding:10px; border-radius:12px; border:1px solid rgba(255,255,255,.10); background:rgba(255,255,255,.04); }
</style>

</section>


<!-- ============================================================
  ✅ SECTION 5: HOLIDAY (your code unchanged; only wrapped)
============================================================ -->
<section class="effect-section" id="effect-holiday" data-effect="holiday" data-title="Holiday Effect">

<!-- Plotly -->
<script src="https://cdn.plot.ly/plotly-2.30.0.min.js"></script>

<!-- ========== HOLIDAY EFFECT UI ========== -->
<div class="hol-ui">

  <div class="hol-top">
    <div>
      <div class="hol-h">Holiday Effect</div>
      <div class="hol-sub">Select holiday and window size (k), then choose a ticker.</div>
    </div>

    <div class="hol-controls">
      <div class="hol-ctrl">
        <div class="hol-lbl">Holiday</div>
        <select id="holHoliday"></select>
      </div>

      <div class="hol-ctrl">
        <div class="hol-lbl">k (days)</div>
        <select id="holK">
          <option value="1">1</option>
          <option value="2" selected>2</option>
          <option value="3">3</option>
        </select>
      </div>

      <div class="hol-ctrl">
        <div class="hol-lbl">Ticker</div>
        <input id="holTicker" list="holTickers" placeholder="Type ticker (e.g., AAPL)">
        <datalist id="holTickers"></datalist>
      </div>
    </div>
  </div>

  <div class="hol-grid">
    <div class="hol-card">
      <div class="hol-card-title">Ticker view</div>
      <div id="holPlot"></div>
    </div>

    <div class="hol-card">
      <div class="hol-card-title">Company distribution</div>
      <div id="holPie"></div>
      <div id="holSliceInfo" class="hol-slice"></div>
    </div>
  </div>

</div>

<script>
(async function(){

  /* ============================================================
     ✅ MANUEL MAPPING (UNUTMA!)
     Dropdown adı  ->  dosya prefix
     Dosyaların: assets/data/<prefix>_k1.json (k2, k3)
     ============================================================ */
  const HOLIDAYS = {
    "Christmas": "christmas",
    "New Year": "new_year",
    "Independence Day": "independence_day",
    "Thanksgiving": "thanksgiving",
    "Memorial Day": "memorial_day",
    "Labor Day": "labor_day"
  };

  // ✅ SENDE JSONLAR assets/data/ içinde direkt duruyor
  const DATA_DIR = "{{ site.baseurl }}/assets/data";
  const PIE_URL  = `${DATA_DIR}/holiday_pie_all.json`;

  // DOM
  const selHoliday = document.getElementById("holHoliday");
  const selK = document.getElementById("holK");
  const input = document.getElementById("holTicker");
  const dl = document.getElementById("holTickers");

  const plotDiv = document.getElementById("holPlot");
  const pieDiv  = document.getElementById("holPie");
  const sliceInfo = document.getElementById("holSliceInfo");

  // 1) dropdown doldur
  Object.keys(HOLIDAYS).forEach(h => {
    const opt = document.createElement("option");
    opt.value = h;
    opt.textContent = h;
    selHoliday.appendChild(opt);
  });

  // 2) pie json yükle
  let PIE = {};
  try{
    const pieRes = await fetch(PIE_URL);
    if(!pieRes.ok) throw new Error(`PIE fetch failed: ${PIE_URL} (${pieRes.status})`);
    PIE = await pieRes.json();
  }catch(e){
    console.error(e);
    Plotly.newPlot(pieDiv, [], {title:"Pie JSON not found / failed to load"}, {responsive:true});
  }

  // cache
  const compCache = {}; // key: holiday__k -> comp obj | null

  function H(){ return selHoliday.value; }
  function K(){ return selK.value; }

  function setDatalist(tickers){
    dl.innerHTML = "";
    (tickers || []).forEach(t => {
      const opt = document.createElement("option");
      opt.value = t;
      dl.appendChild(opt);
    });
  }

  async function loadComp(){
    const key = `${H()}__${K()}`;
    if (compCache[key] !== undefined) return compCache[key];

    const prefix = HOLIDAYS[H()];
    const url = `${DATA_DIR}/${prefix}_k${K()}.json`; // ✅ doğru yol

    try{
      const res = await fetch(url);
      if(!res.ok) throw new Error(`COMP fetch failed: ${url} (${res.status})`);
      const data = await res.json(); // {TICKER: {...}, ...}
      compCache[key] = data;
      return data;
    }catch(e){
      console.error(e);
      compCache[key] = null;
      return null;
    }
  }

  function winRects(winYears){
    return (winYears || []).map(y => ({
      type: "rect",
      xref: "x",
      yref: "paper",
      x0: y - 0.5,
      x1: y + 0.5,
      y0: 0.42,
      y1: 1.0,
      fillcolor: "rgba(0,0,0,0.06)",
      line: { width: 0 },
      layer: "below"
    }));
  }

  function drawPie(){
    const payload = (PIE[H()] && PIE[H()][K()]) ? PIE[H()][K()] : null;

    if(!payload || !(payload.labels||[]).length){
      Plotly.newPlot(pieDiv, [], {title:`No pie data for ${H()} (k=${K()})`}, {responsive:true});
      sliceInfo.innerHTML = "";
      return;
    }

    const labels = payload.labels || [];
    const values = payload.counts || [];

    Plotly.newPlot(pieDiv, [{
      type:"pie",
      labels: labels,
      values: values,
      textinfo:"label+percent+value",
      hovertemplate:"<b>%{label}</b><br>Companies: %{value}<extra></extra>",
      pull: labels.map(()=>0.04)
    }], {
      title:`Distribution — ${H()} (k=${K()})`,
      height:520,
      margin:{l:10,r:10,t:60,b:10},
      showlegend:true
    }, {responsive:true});

    pieDiv.on("plotly_click", (e) => {
      const i = e.points[0].pointNumber;
      const list = payload.tickersBySlice?.[i] || [];
      const preview = list.slice(0,40).join(", ") + (list.length>40 ? `, ... (+${list.length-40} more)` : "");
      sliceInfo.innerHTML = `<b>${labels[i]}</b>: ${list.length} tickers<br><span style="opacity:.8">${preview}</span>`;
    });
  }

  async function drawTicker(){
    const comp = await loadComp();
    if(!comp){
      Plotly.newPlot(plotDiv, [], {title:`Missing JSON: ${HOLIDAYS[H()]}_k${K()}.json`}, {responsive:true});
      return;
    }

    const tkr = (input.value || "").trim().toUpperCase();
    const d = comp[tkr];

    if(!d){
      Plotly.newPlot(plotDiv, [], {title:`Ticker not found: ${tkr}`}, {responsive:true});
      return;
    }

    const years = d.years || [];
    const pre   = d.pre_cum || [];
    const post  = d.post_cum || [];
    const diff  = d.diff || [];
    const wr    = Number(d.win_rate || 0);

    Plotly.newPlot(plotDiv, [
      {
        x: years, y: pre,
        type:"scatter", mode:"lines+markers",
        name:`Pre (k=${K()})`,
        hovertemplate:"Year=%{x}<br>Pre=%{y:.5f}<extra></extra>"
      },
      {
        x: years, y: post,
        type:"scatter", mode:"lines+markers",
        name:`Post (k=${K()})`,
        line:{dash:"dash"},
        hovertemplate:"Year=%{x}<br>Post=%{y:.5f}<extra></extra>"
      },
      {
        x: years, y: diff,
        type:"bar",
        name:"Diff (Pre-Post)",
        xaxis:"x2", yaxis:"y2",
        hovertemplate:"Year=%{x}<br>Diff=%{y:.5f}<extra></extra>"
      }
    ], {
      title:`Holiday Effect — ${H()} (k=${K()}) — ${tkr} | win rate ${wr.toFixed(1)}%`,
      height:680,
      margin:{l:55,r:20,t:70,b:50},
      hovermode:"x unified",
      legend:{orientation:"h", y:1.07, x:0},

      xaxis:{domain:[0,1]},
      yaxis:{domain:[0.42,1], title:"Avg return"},
      xaxis2:{domain:[0,1], title:"Year"},
      yaxis2:{domain:[0,0.34], title:"Diff"},

      shapes: winRects(d.win_years).concat([{
        type:"line",
        xref:"x2", yref:"y2",
        x0: years.length ? Math.min(...years) : 0,
        x1: years.length ? Math.max(...years) : 1,
        y0: 0, y1: 0,
        line:{dash:"dot", width:1}
      }])
    }, {responsive:true});
  }

  async function refresh(){
    const comp = await loadComp();

    if(!comp){
      setDatalist([]);
      input.value = "";
      drawPie();
      Plotly.newPlot(plotDiv, [], {title:"Comp JSON failed to load (check filename/path)"}, {responsive:true});
      return;
    }

    const tickers = Object.keys(comp).sort();
    setDatalist(tickers);

    input.value = tickers.includes("TAPR") ? "TAPR" : (tickers[0] || "");
    drawPie();
    await drawTicker();
  }

  // events
  selHoliday.addEventListener("change", refresh);
  selK.addEventListener("change", refresh);
  input.addEventListener("change", drawTicker);

  // init (default Thanksgiving)
  selHoliday.value = "Thanksgiving";
  await refresh();

})();
</script>

<style>
  .hol-ui{
    margin-top:20px;
    padding:14px;
    border-radius:18px;
    border:1px solid rgba(255,255,255,.12);
    background:rgba(255,255,255,.04);
    box-shadow:0 18px 60px rgba(0,0,0,.25);
  }
  .hol-top{
    display:flex;
    justify-content:space-between;
    flex-wrap:wrap;
    gap:12px;
    margin-bottom:10px;
  }
  .hol-h{ font-weight:900; font-size:1.2rem; }
  .hol-sub{ opacity:.75; max-width:85ch; }

  .hol-controls{
    display:flex;
    gap:12px;
    flex-wrap:wrap;
    align-items:flex-end;
  }
  .hol-ctrl{ display:flex; flex-direction:column; gap:6px; }
  .hol-lbl{ font-size:.85rem; font-weight:700; opacity:.8; }

  select, #holTicker{
    padding:10px 12px;
    border-radius:12px;
    border:1px solid rgba(255,255,255,.12);
    background:rgba(255,255,255,.06);
    color:inherit;
    outline:none;
    width:min(260px,80vw);
  }
  select:focus, #holTicker:focus{ border-color:rgba(120,170,255,.6); }

  .hol-grid{
    display:grid;
    grid-template-columns:1fr; /* alt alta */
    gap:16px;
  }
  .hol-card{
    border-radius:16px;
    border:1px solid rgba(255,255,255,.12);
    background:rgba(0,0,0,.10);
    padding:10px;
  }
  .hol-card-title{
    font-weight:850;
    margin:4px 6px 10px;
    opacity:.9;
  }
  .hol-slice{
    margin-top:10px;
    padding:10px;
    border-radius:12px;
    border:1px solid rgba(255,255,255,.10);
    background:rgba(255,255,255,.04);
  }
</style>

</section>


<!-- ============================================================
  ✅ HUB CONTROLLER JS: pie nav + show/hide + resize plots when opened
============================================================ -->
<script>
(function(){
  const root = document.documentElement;
  const sections = Array.from(document.querySelectorAll(".effect-section"));

  const EFFECTS = sections.map(s => ({
    key: s.dataset.effect,
    title: s.dataset.title || s.dataset.effect,
    el: s
  }));

  const openedName = document.getElementById("openedEffectName");
  const hint = document.getElementById("effectsHint");
  const pieDiv = document.getElementById("effectsPie");

  function resizeVisiblePlots(container){
    if(!container) return;
    const plotDivs = container.querySelectorAll(".js-plotly-plot");
    plotDivs.forEach(d => {
      try{ Plotly.Plots.resize(d); }catch(e){}
    });
  }

  function setActive(key){
    if(key === "all"){
      root.classList.add("effects-all");
      sections.forEach(s => s.classList.remove("active"));
      openedName.textContent = "All effects";
      hint.innerHTML = "All effects are visible. Click a slice to focus on one.";
      // resize all
      setTimeout(() => {
        sections.forEach(s => resizeVisiblePlots(s));
      }, 50);
      return;
    }

    if(key === "none"){
      root.classList.remove("effects-all");
      sections.forEach(s => s.classList.remove("active"));
      openedName.textContent = "None";
      hint.innerHTML = "Collapsed. Click a slice to open an effect.";
      history.replaceState(null, "", window.location.pathname + window.location.search);
      return;
    }

    root.classList.remove("effects-all");
    sections.forEach(s => s.classList.toggle("active", s.dataset.effect === key));
    const eff = EFFECTS.find(e => e.key === key);
    openedName.textContent = eff ? eff.title : key;

    history.replaceState(null, "", "#" + key);

    if(eff && eff.el){
      eff.el.scrollIntoView({behavior:"smooth", block:"start"});
      // Plotly hidden->shown width fix
      setTimeout(() => resizeVisiblePlots(eff.el), 50);
    }
  }

  // Buttons
  document.querySelectorAll(".hub-btn").forEach(btn => {
    btn.addEventListener("click", () => setActive(btn.dataset.open));
  });

  // Pie: navigation only (equal weights)
  const labels = EFFECTS.map(e => e.title);
  const keys = EFFECTS.map(e => e.key);
  const values = EFFECTS.map(() => 1);

  Plotly.newPlot(pieDiv, [{
    type:"pie",
    labels,
    values,
    textinfo:"label",
    hovertemplate:"<b>%{label}</b><extra></extra>",
    pull: labels.map(()=>0.04)
  }], {
    title: "Click to open",
    height: 520,
    margin: {l: 10, r: 10, t: 60, b: 10},
    showlegend: false
  }, {responsive:true});

  pieDiv.on("plotly_click", (ev) => {
    const idx = ev.points[0].pointNumber;
    const key = keys[idx];
    setActive(key);
  });

  // Init: hash varsa onu aç
  const hash = (window.location.hash || "").replace("#","").trim();
  if(hash && keys.includes(hash)){
    setActive(hash);
    hint.innerHTML = `Opened from link: <code>#${hash}</code>`;
  }else{
    setActive("none");
  }
})();
</script>
