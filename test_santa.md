---
layout: page
title: Santa Test
permalink: /santa-test/
---

<div style="display:grid; grid-template-columns: 1fr 1fr; gap:12px; align-items:start;">
  <div style="border:1px solid rgba(0,0,0,.12); border-radius:14px; padding:12px;">
    <div id="pieDiv" style="height:520px;"></div>
  </div>

  <div style="border:1px solid rgba(0,0,0,.12); border-radius:14px; padding:12px;">
    <div id="sliceTitle" style="font-weight:700; margin-bottom:10px;">Click a slice</div>
    <input id="tickerSearch" placeholder="Search ticker..."
      style="width:100%; padding:10px; border-radius:10px; border:1px solid rgba(0,0,0,.18); margin-bottom:10px;">
    <div id="tickerList"
      style="max-height:440px; overflow:auto; border:1px solid rgba(0,0,0,.12); border-radius:10px; padding:10px;">
      <em>Select a slice to list tickers.</em>
    </div>
  </div>
</div>

<div style="margin-top:12px; border:1px solid rgba(0,0,0,.12); border-radius:14px; padding:12px;">
  <div id="histDiv" style="height:320px;"></div>
</div>

<div style="margin-top:12px; border:1px solid rgba(0,0,0,.12); border-radius:14px; padding:12px;">
  <div id="tickerPlot" style="height:720px;"></div>
</div>

<script src="https://cdn.plot.ly/plotly-2.30.0.min.js"></script>
<script>
(async function () {
  const url = "{{ site.baseurl }}/assets/data/santa.json";
  const payload = await (await fetch(url)).json();

  const pieLabels = payload.pie.labels;
  const pieCounts = payload.pie.counts;
  const tickersBySlice = payload.pie.tickersBySlice;
  const histCounts = payload.hist.counts;
  const histEdges = payload.hist.edges;
  const seriesByTicker = payload.seriesByTicker;

  const pieDiv = document.getElementById("pieDiv");
  const sliceTitle = document.getElementById("sliceTitle");
  const tickerSearch = document.getElementById("tickerSearch");
  const tickerList = document.getElementById("tickerList");
  const tickerPlot = document.getElementById("tickerPlot");
  const histDiv = document.getElementById("histDiv");

  let currentTickers = [];

  function drawPie() {
    const data = [{
      type: "pie",
      labels: pieLabels,
      values: pieCounts,
      textinfo: "percent+value",
      hovertemplate: "<b>%{label}</b><br>Companies: %{value}<extra></extra>",
      pull: pieLabels.map(() => 0.04),
      sort: false
    }];

    const layout = {
      title: "Santa Claus Effect — Company Distribution",
      height: 520,
      margin: {l: 10, r: 10, t: 60, b: 10},
      showlegend: true,
      uniformtext: {minsize: 11, mode: "hide"}
    };

    Plotly.newPlot(pieDiv, data, layout, {responsive: true, displayModeBar: true});
  }

  function drawHistogram() {
    const x = [];
    for (let i = 0; i < histCounts.length; i++) {
      x.push((histEdges[i] + histEdges[i + 1]) / 2);
    }

    const data = [{
      type: "bar",
      x: x,
      y: histCounts,
      name: "Companies",
      hovertemplate: "Bin center=%{x:.1f}<br>Count=%{y}<extra></extra>"
    }];

    const layout = {
      title: "Santa Claus Effect — Histogram",
      height: 320,
      margin: {l: 40, r: 10, t: 60, b: 40},
      xaxis: {title: "Win rate (%)"},
      yaxis: {title: "Company count"}
    };

    Plotly.newPlot(histDiv, data, layout, {responsive: true, displayModeBar: false});
  }

  function renderTickerList(query = "") {
    const q = query.trim().toUpperCase();
    const arr = q ? currentTickers.filter(t => t.toUpperCase().includes(q)) : currentTickers;

    if (!arr.length) {
      tickerList.innerHTML = "<em>No matches.</em>";
      return;
    }

    tickerList.innerHTML = arr.slice(0, 2000).map(t => `
      <button
        style="width:100%; text-align:left; margin-bottom:8px; padding:10px; border-radius:12px;
               border:1px solid rgba(0,0,0,.12); background:#fff; cursor:pointer;"
        data-ticker="${t}">
        ${t}
      </button>
    `).join("");

    tickerList.querySelectorAll("[data-ticker]").forEach(btn => {
      btn.addEventListener("click", () => drawTickerPlot(btn.getAttribute("data-ticker")));
    });

    if (arr.length > 2000) {
      const note = document.createElement("div");
      note.style.marginTop = "8px";
      note.innerHTML = `<em>Showing the first 2000 tickers. Use search to find the rest.</em>`;
      tickerList.appendChild(note);
    }
  }

  function drawTickerPlot(ticker) {
    const s = seriesByTicker[ticker];
    if (!s) return;

    const years = s.Year;
    const scr = s.scr_avg;
    const non = s.non_scr_avg;
    const diff = s.diff;
    const win = s.scr_win;
    const winRate = (s.win_rate ?? 0).toFixed(1);

    const shapes = [];
    for (let i = 0; i < years.length; i++) {
      if (win[i]) {
        const y = years[i];
        shapes.push({
          type: "rect",
          xref: "x", yref: "paper",
          x0: y - 0.5, x1: y + 0.5,
          y0: 0.42, y1: 1.0,
          fillcolor: "rgba(0,0,0,0.06)",
          line: {width: 0}
        });
      }
    }

    const traces = [
      {
        type: "scatter",
        mode: "lines+markers",
        x: years,
        y: scr,
        name: "SCR avg",
        hovertemplate: "Year=%{x}<br>SCR=%{y:.5f}<extra></extra>"
      },
      {
        type: "scatter",
        mode: "lines+markers",
        x: years,
        y: non,
        name: "non-SCR avg",
        line: {dash: "dash"},
        hovertemplate: "Year=%{x}<br>non-SCR=%{y:.5f}<extra></extra>"
      },
      {
        type: "bar",
        x: years,
        y: diff,
        name: "Diff (SCR - non-SCR)",
        xaxis: "x2",
        yaxis: "y2",
        hovertemplate: "Year=%{x}<br>Diff=%{y:.5f}<extra></extra>"
      }
    ];

    const layout = {
      title: `Santa Claus Effect — ${ticker} (win rate ${winRate}%)`,
      height: 720,
      margin: {l: 50, r: 20, t: 70, b: 40},
      hovermode: "x unified",
      legend: {orientation: "h", y: 1.06, x: 0},
      xaxis: {domain: [0, 1], anchor: "y"},
      yaxis: {domain: [0.42, 1], title: "Avg return"},
      xaxis2: {domain: [0, 1], anchor: "y2", title: "Year"},
      yaxis2: {domain: [0, 0.33], title: "Diff"},
      shapes: shapes
    };

    Plotly.react(tickerPlot, traces, layout, {responsive: true, displayModeBar: true});
  }

  tickerSearch.addEventListener("input", e => renderTickerList(e.target.value));

  pieDiv.on("plotly_click", evt => {
    const idx = evt.points[0].pointNumber;
    currentTickers = tickersBySlice[idx] || [];
    sliceTitle.textContent = `${pieLabels[idx]} — ${currentTickers.length} companies`;
    tickerSearch.value = "";
    renderTickerList("");

    if (currentTickers.length) drawTickerPlot(currentTickers[0]);
  });

  drawPie();
  drawHistogram();

  const maxIdx = pieCounts.indexOf(Math.max(...pieCounts));
  currentTickers = tickersBySlice[maxIdx] || [];
  sliceTitle.textContent = `${pieLabels[maxIdx]} — ${currentTickers.length} companies`;
  renderTickerList("");
  if (currentTickers.length) drawTickerPlot(currentTickers[0]);
})();
</script>
