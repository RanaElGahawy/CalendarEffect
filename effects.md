---
layout: page
title: Calendar Effects
permalink: /effects/
---

<div class="effect-grid">
  <button class="effect-btn active" data-img="{{ site.baseurl }}/assets/effects/january.png">January Effect</button>
  <button class="effect-btn" data-img="{{ site.baseurl }}/assets/effects/sell_in_may.png">Sell in May</button>
  <button class="effect-btn" data-img="{{ site.baseurl }}/assets/effects/turn_of_month.png">Turn-of-Month</button>
  <button class="effect-btn" data-img="{{ site.baseurl }}/assets/effects/monday.png">Monday Effect</button>
  <button class="effect-btn" data-img="{{ site.baseurl }}/assets/effects/holiday.png">Holiday Effect</button>
  <button class="effect-btn" data-img="{{ site.baseurl }}/assets/effects/santa_rally.png">Santa Rally</button>
  <button class="effect-btn" data-img="{{ site.baseurl }}/assets/effects/other.png">Other Effect</button>
</div>

<div class="effect-view">
  <img id="effectImage"
       src="{{ site.baseurl }}/assets/effects/january.png"
       alt="Effect plot"
       loading="lazy">
</div>

<script>
  (function () {
    const buttons = document.querySelectorAll(".effect-btn");
    const img = document.getElementById("effectImage");

    buttons.forEach(btn => {
      btn.addEventListener("click", () => {
        img.src = btn.getAttribute("data-img");

        buttons.forEach(b => b.classList.remove("active"));
        btn.classList.add("active");
      });
    });
  })();
</script>

<style>
  .effect-grid{
    display:grid;
    grid-template-columns:repeat(3, 1fr);
    gap:12px;
    margin:18px 0;
  }
  @media(max-width:900px){ .effect-grid{grid-template-columns:repeat(2,1fr)} }
  @media(max-width:520px){ .effect-grid{grid-template-columns:1fr} }

  .effect-btn{
    text-align:left;
    cursor:pointer;
    padding:12px 14px;
    border-radius:14px;
    border:1px solid rgba(255,255,255,.16);
    background:rgba(255,255,255,.06);
    color:inherit;
    box-shadow:0 10px 28px rgba(0,0,0,.20);
    transition:transform .12s ease, box-shadow .12s ease, background .12s ease;
  }
  .effect-btn:hover{
    transform:translateY(-2px);
    box-shadow:0 14px 34px rgba(0,0,0,.28);
    background:rgba(255,255,255,.10);
  }
  .effect-btn.active{
    outline:2px solid rgba(120,170,255,.75);
    background:rgba(120,170,255,.12);
  }

  .effect-view{
    margin-top:16px;
    border-radius:16px;
    overflow:hidden;
    border:1px solid rgba(255,255,255,.14);
    background:rgba(0,0,0,.12);
  }
  .effect-view img{
    width:100%;
    display:block;
  }
</style>
