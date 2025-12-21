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








<section id="calendar-effects" class="fx-wrap">

  <!-- HERO -->
  <div class="fx-hero">
    <div class="fx-hero-left">
      <div class="fx-eyebrow">NASDAQ • Calendar Anomalies</div>
      <h2 class="fx-h1">Explore Seasonal Patterns, One Click at a Time</h2>
      <p class="fx-lead">
        Select a calendar effect and instantly see how many companies show the pattern.
        This is designed as a single-page exploration (no page breaks, no distraction).
      </p>

      <div class="fx-cta-row">
        <a class="fx-cta"
           href="{{ site.baseurl }}/test_santa/"
           aria-label="Open Santa effect page">
          Explore Santa Rally Deep Dive →
        </a>
        <span class="fx-note">Tip: Hover the effect cards.</span>
      </div>
    </div>

    <div class="fx-hero-right">
      <div class="fx-stat">
        <div class="fx-stat-num">7</div>
        <div class="fx-stat-lbl">Effects</div>
      </div>
      <div class="fx-stat">
        <div class="fx-stat-num">1</div>
        <div class="fx-stat-lbl">Plot at a time</div>
      </div>
      <div class="fx-stat">
        <div class="fx-stat-num">Fast</div>
        <div class="fx-stat-lbl">Switching</div>
      </div>
    </div>
  </div>

  <!-- LAYOUT -->
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
          data-img="{{ site.baseurl }}/assets/img/sell_in_may.png">
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
