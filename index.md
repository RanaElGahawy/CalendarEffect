---
layout: home
title:  Market Detectives - Investigating Calendar Effects 
subtitle: Analyzing Seven Calendar-Effect Anomalies in NASDAQ Since 1962
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

Reinforced by rigorous statistical tools, the detectives conduct an in-depth investigation into each calendar effect. 

<p align="center">
  <img src="assets/img/perry_regression.png" width="500">
</p>

Every suspected calendar anomaly is subjected to rigorous evaluation through formal hypothesis testing. In particular, t-tests are employed to determine whether average returns during specific calendar periods differ significantly from those observed in the rest of the sample. t-tests are employed to determine whether average returns during specific calendar periods differ significantly from those observed in the rest of the sample.
For these tests to be valid, several underlying assumptions must be satisfied, most notably the normality and independence of the data. To ensure the validity of the statistical tests, the investigation begins with a careful assessment of these assumptions. In particular, the normality of returns is examined prior to conducting the hypothesis tests.

// Plots of normality check//

<details>
  <summary><strong>📈 Monday Effect</strong></summary
<!-- ---
  <p>
    Mondays are often said to deliver negative returns.
    Let’s see what the data actually says.
  </p>
--- -->
  <div id="monday-plot" style="height:450px;"></div>
</details>
<iframe src="assets/img/plot_monday_effect_dec.html"
        width="100%" 
        height="550"
        frameborder="0">
</iframe>
<details>
  <summary><strong>📉 January Effect</strong></summary>
<!-- ---
  <p>
    Mondays are often said to deliver negative returns.
    Let’s see what the data actually says.
  </p>
--- -->
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


<div style="margin:20px 0;">
  <a href="{{ site.baseurl }}/test_santa.md/"
     style="
       display:inline-block;
       padding:12px 18px;
       border-radius:12px;
       background:#2563eb;
       color:white;
       font-weight:600;
       text-decoration:none;
     ">
    Explore Santa Claus Effect
  </a>
</div>


<div id="calendar-effects">

  <p>
    Select a calendar effect to see its corresponding plot.
  </p>

  <div class="effect-grid">
    <button class="effect-btn active"
            data-img="{{ site.baseurl }}/assets/img/january_company.png">
      January Effect
    </button>

    <button class="effect-btn"
            data-img="{{ site.baseurl }}/assets/effects/sell_in_may.png">
      Sell in May
    </button>

    <button class="effect-btn"
            data-img="{{ site.baseurl }}/assets/effects/tom_company.png">
      Turn-of-Month
    </button>

    <button class="effect-btn"
            data-img="{{ site.baseurl }}/assets/effects/monday_company.png">
      Monday Effect
    </button>

    <button class="effect-btn"
            data-img="{{ site.baseurl }}/assets/effects/holiday.png">
      Holiday Effect
    </button>

    <button class="effect-btn"
            data-img="{{ site.baseurl }}/assets/effects/santa_claus_rally_company.png">
      Santa Rally
    </button>
  </div>

  <div class="effect-view">
    <img id="effectImage"
         src="{{ site.baseurl }}/assets/effects/january.png"
         alt="Calendar effect plot">
  </div>

</div>

<script>
  (function () {
    const buttons = document.querySelectorAll("#calendar-effects .effect-btn");
    const img = document.getElementById("effectImage");

    buttons.forEach(btn => {
      btn.addEventListener("click", () => {
        img.src = btn.dataset.img;

        buttons.forEach(b => b.classList.remove("active"));
        btn.classList.add("active");

        // sayfa içinde yumuşak kayma (sayfa içi sayfa hissi)
        img.scrollIntoView({ behavior: "smooth", block: "nearest" });
      });
    });
  })();
</script>

<style>
  #calendar-effects{
    margin-top:2rem;
  }

  .effect-grid{
    display:grid;
    grid-template-columns:repeat(3, 1fr);
    gap:12px;
    margin:1rem 0;
  }
  @media(max-width:900px){ .effect-grid{grid-template-columns:repeat(2,1fr)} }
  @media(max-width:520px){ .effect-grid{grid-template-columns:1fr} }

  .effect-btn{
    padding:12px 14px;
    border-radius:14px;
    cursor:pointer;
    border:1px solid rgba(0,0,0,.15);
    background:rgba(255,255,255,.05);
    transition:.15s;
  }
  .effect-btn:hover{
    transform:translateY(-2px);
  }
  .effect-btn.active{
    outline:2px solid #6aa9ff;
    background:rgba(106,169,255,.12);
  }

  .effect-view{
    margin-top:1.5rem;
    border-radius:16px;
    overflow:hidden;
    border:1px solid rgba(0,0,0,.15);
  }
  .effect-view img{
    width:100%;
    display:block;
  }
</style>




