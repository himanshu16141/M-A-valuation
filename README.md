<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>M&A Valuation Case Study — Tata Motors × Nexon EV Expansion</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700;900&family=IBM+Plex+Mono:wght@300;400;600&family=IBM+Plex+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #0a0c0f;
    --surface: #111418;
    --surface2: #181d23;
    --border: #1e2530;
    --accent: #c8a96e;
    --accent2: #4fc97e;
    --accent3: #e05c5c;
    --accent4: #5b8de8;
    --text: #e8e4dc;
    --muted: #6b7280;
    --green: #4fc97e;
    --red: #e05c5c;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'IBM Plex Sans', sans-serif;
    font-size: 15px;
    line-height: 1.7;
    overflow-x: hidden;
  }

  /* ── HEADER ── */
  header {
    border-bottom: 1px solid var(--border);
    padding: 0 48px;
    position: sticky;
    top: 0;
    background: rgba(10,12,15,0.96);
    backdrop-filter: blur(12px);
    z-index: 100;
    display: flex;
    align-items: center;
    justify-content: space-between;
    height: 60px;
  }
  .logo {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 11px;
    letter-spacing: 3px;
    color: var(--accent);
    text-transform: uppercase;
  }
  nav {
    display: flex;
    gap: 32px;
  }
  nav a {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 10px;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: var(--muted);
    text-decoration: none;
    transition: color .2s;
  }
  nav a:hover { color: var(--accent); }

  /* ── HERO ── */
  .hero {
    padding: 100px 48px 80px;
    border-bottom: 1px solid var(--border);
    position: relative;
    overflow: hidden;
  }
  .hero::before {
    content: 'M&A';
    position: absolute;
    right: -20px;
    top: 20px;
    font-family: 'Playfair Display', serif;
    font-size: 280px;
    font-weight: 900;
    color: rgba(200,169,110,0.04);
    pointer-events: none;
    line-height: 1;
  }
  .tag {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 10px;
    letter-spacing: 3px;
    color: var(--accent);
    text-transform: uppercase;
    background: rgba(200,169,110,0.08);
    border: 1px solid rgba(200,169,110,0.2);
    padding: 4px 12px;
    display: inline-block;
    margin-bottom: 28px;
  }
  .hero h1 {
    font-family: 'Playfair Display', serif;
    font-size: clamp(38px, 5vw, 68px);
    font-weight: 900;
    line-height: 1.1;
    max-width: 820px;
    margin-bottom: 20px;
  }
  .hero h1 em {
    font-style: italic;
    color: var(--accent);
  }
  .hero-sub {
    color: var(--muted);
    font-size: 15px;
    max-width: 560px;
    margin-bottom: 48px;
  }
  .hero-kpis {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 1px;
    background: var(--border);
    border: 1px solid var(--border);
    max-width: 820px;
  }
  .kpi {
    background: var(--surface);
    padding: 24px 28px;
    transition: background .2s;
  }
  .kpi:hover { background: var(--surface2); }
  .kpi-val {
    font-family: 'Playfair Display', serif;
    font-size: 32px;
    font-weight: 700;
    line-height: 1;
    margin-bottom: 6px;
  }
  .kpi-lbl {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 9px;
    letter-spacing: 2px;
    color: var(--muted);
    text-transform: uppercase;
  }
  .up { color: var(--green); }
  .dn { color: var(--red); }
  .go { color: var(--accent); }
  .bl { color: var(--accent4); }

  /* ── SECTION LAYOUT ── */
  .container { padding: 72px 48px; border-bottom: 1px solid var(--border); }
  .section-label {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 9px;
    letter-spacing: 4px;
    color: var(--accent);
    text-transform: uppercase;
    margin-bottom: 12px;
  }
  .section-title {
    font-family: 'Playfair Display', serif;
    font-size: clamp(28px, 3vw, 44px);
    font-weight: 700;
    line-height: 1.15;
    margin-bottom: 48px;
  }

  /* ── GRID CARDS ── */
  .grid-2 { display: grid; grid-template-columns: 1fr 1fr; gap: 20px; }
  .grid-3 { display: grid; grid-template-columns: repeat(3, 1fr); gap: 20px; }
  .grid-4 { display: grid; grid-template-columns: repeat(4, 1fr); gap: 16px; }

  .card {
    background: var(--surface);
    border: 1px solid var(--border);
    padding: 28px;
    transition: border-color .2s, transform .2s;
  }
  .card:hover {
    border-color: rgba(200,169,110,0.3);
    transform: translateY(-2px);
  }
  .card h3 {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 10px;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 14px;
  }
  .card p { color: #9aa0ab; font-size: 14px; line-height: 1.7; }

  /* ── STRATEGIC RATIONALE ── */
  .rationale-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 1px; background: var(--border); border: 1px solid var(--border); }
  .rat-item {
    background: var(--surface);
    padding: 32px;
  }
  .rat-num {
    font-family: 'Playfair Display', serif;
    font-size: 48px;
    font-weight: 900;
    color: rgba(200,169,110,0.15);
    line-height: 1;
    margin-bottom: 8px;
  }
  .rat-title {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 11px;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 10px;
  }
  .rat-body { color: #9aa0ab; font-size: 13.5px; }

  /* ── SYNERGIES TABLE ── */
  .syn-table { width: 100%; border-collapse: collapse; margin-top: 8px; }
  .syn-table th {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 9px;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: var(--muted);
    padding: 12px 16px;
    text-align: left;
    border-bottom: 1px solid var(--border);
  }
  .syn-table td {
    padding: 14px 16px;
    font-size: 13px;
    border-bottom: 1px solid rgba(30,37,48,0.5);
    color: #c0c8d2;
  }
  .syn-table tr:hover td { background: var(--surface2); }
  .syn-table .num {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 13px;
    font-weight: 600;
  }
  .pill {
    display: inline-block;
    padding: 2px 10px;
    font-family: 'IBM Plex Mono', monospace;
    font-size: 9px;
    letter-spacing: 1px;
    text-transform: uppercase;
    border-radius: 2px;
  }
  .pill-cost { background: rgba(79,201,126,0.1); color: var(--green); border: 1px solid rgba(79,201,126,0.2); }
  .pill-rev { background: rgba(91,141,232,0.1); color: var(--accent4); border: 1px solid rgba(91,141,232,0.2); }
  .pill-total { background: rgba(200,169,110,0.1); color: var(--accent); border: 1px solid rgba(200,169,110,0.2); }

  /* ── VALUATION ── */
  .val-methods { display: grid; grid-template-columns: repeat(3, 1fr); gap: 1px; background: var(--border); border: 1px solid var(--border); }
  .val-m {
    background: var(--surface);
    padding: 32px 28px;
  }
  .val-m-tag {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 9px;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 16px;
  }
  .val-m-price {
    font-family: 'Playfair Display', serif;
    font-size: 42px;
    font-weight: 700;
    color: var(--accent);
    line-height: 1;
    margin-bottom: 4px;
  }
  .val-m-sub {
    font-size: 12px;
    color: var(--muted);
    margin-bottom: 20px;
  }
  .val-m-rows { display: flex; flex-direction: column; gap: 8px; }
  .val-row { display: flex; justify-content: space-between; font-size: 12.5px; }
  .val-row span:first-child { color: #7a8494; }
  .val-row span:last-child { font-family: 'IBM Plex Mono', monospace; color: var(--text); }

  /* ── FOOTBALL FIELD ── */
  .football-field {
    background: var(--surface);
    border: 1px solid var(--border);
    padding: 36px;
    margin-top: 32px;
  }
  .ff-title {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 10px;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 28px;
  }
  .ff-row { margin-bottom: 18px; }
  .ff-label {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 10px;
    color: var(--muted);
    width: 200px;
    display: inline-block;
    margin-bottom: 6px;
  }
  .ff-bar-wrap {
    position: relative;
    height: 28px;
    background: rgba(255,255,255,0.03);
    border: 1px solid var(--border);
  }
  .ff-bar {
    position: absolute;
    height: 100%;
    display: flex;
    align-items: center;
    padding: 0 10px;
    font-family: 'IBM Plex Mono', monospace;
    font-size: 10px;
    font-weight: 600;
    white-space: nowrap;
    transition: width 1s ease;
  }
  .ff-bar.dcf   { background: rgba(200,169,110,0.25); color: var(--accent); left: 10%; width: 40%; }
  .ff-bar.comps { background: rgba(91,141,232,0.2);   color: var(--accent4); left: 18%; width: 35%; }
  .ff-bar.prec  { background: rgba(79,201,126,0.18);  color: var(--green);   left: 22%; width: 38%; }
  .ff-bar.lbo   { background: rgba(224,92,92,0.18);   color: var(--red);     left: 8%;  width: 28%; }

  /* ── ACCRETION/DILUTION ── */
  .acc-scenarios { display: grid; grid-template-columns: repeat(3, 1fr); gap: 16px; }
  .acc-card {
    border: 1px solid var(--border);
    padding: 28px;
    text-align: center;
    position: relative;
    overflow: hidden;
  }
  .acc-card.base  { border-color: rgba(200,169,110,0.3); background: rgba(200,169,110,0.04); }
  .acc-card.bull  { border-color: rgba(79,201,126,0.3);  background: rgba(79,201,126,0.04); }
  .acc-card.bear  { border-color: rgba(224,92,92,0.3);   background: rgba(224,92,92,0.04); }
  .acc-tag {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 9px;
    letter-spacing: 3px;
    text-transform: uppercase;
    margin-bottom: 16px;
  }
  .acc-card.base  .acc-tag { color: var(--accent); }
  .acc-card.bull  .acc-tag { color: var(--green); }
  .acc-card.bear  .acc-tag { color: var(--red); }
  .acc-value {
    font-family: 'Playfair Display', serif;
    font-size: 52px;
    font-weight: 900;
    line-height: 1;
    margin-bottom: 4px;
  }
  .acc-card.base  .acc-value { color: var(--accent); }
  .acc-card.bull  .acc-value { color: var(--green); }
  .acc-card.bear  .acc-value { color: var(--red); }
  .acc-label { font-size: 12px; color: var(--muted); margin-bottom: 20px; }
  .acc-details { text-align: left; display: flex; flex-direction: column; gap: 10px; border-top: 1px solid var(--border); padding-top: 18px; }
  .acc-detail-row { display: flex; justify-content: space-between; font-size: 12px; }
  .acc-detail-row span:first-child { color: #7a8494; }
  .acc-detail-row span:last-child { font-family: 'IBM Plex Mono', monospace; }

  /* ── DCF ASSUMPTIONS ── */
  .dcf-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 28px; }
  .assumptions-table { width: 100%; border-collapse: collapse; }
  .assumptions-table th {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 9px;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: var(--muted);
    padding: 10px 14px;
    text-align: left;
    border-bottom: 1px solid var(--border);
    background: var(--surface2);
  }
  .assumptions-table td {
    padding: 11px 14px;
    font-size: 13px;
    border-bottom: 1px solid rgba(30,37,48,0.6);
    color: #b0b8c4;
  }
  .assumptions-table td:last-child {
    font-family: 'IBM Plex Mono', monospace;
    color: var(--accent);
  }

  /* ── DEAL STRUCTURE ── */
  .deal-flow {
    display: flex;
    align-items: stretch;
    gap: 0;
    margin-top: 8px;
  }
  .deal-step {
    flex: 1;
    background: var(--surface);
    border: 1px solid var(--border);
    padding: 24px;
    position: relative;
  }
  .deal-step::after {
    content: '▶';
    position: absolute;
    right: -14px;
    top: 50%;
    transform: translateY(-50%);
    color: var(--accent);
    font-size: 16px;
    z-index: 2;
  }
  .deal-step:last-child::after { display: none; }
  .step-num {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 9px;
    letter-spacing: 2px;
    color: var(--muted);
    margin-bottom: 8px;
  }
  .step-title {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 12px;
    color: var(--accent);
    font-weight: 600;
    margin-bottom: 8px;
  }
  .step-body { font-size: 12px; color: #8a929e; line-height: 1.6; }

  /* ── VERDICT ── */
  .verdict {
    background: linear-gradient(135deg, rgba(200,169,110,0.06), rgba(79,201,126,0.04));
    border: 1px solid rgba(200,169,110,0.2);
    padding: 48px;
    display: grid;
    grid-template-columns: 1fr auto;
    gap: 40px;
    align-items: center;
  }
  .verdict-stamp {
    font-family: 'Playfair Display', serif;
    font-size: 80px;
    font-weight: 900;
    color: rgba(79,201,126,0.15);
    letter-spacing: 4px;
    text-transform: uppercase;
    line-height: 1;
    border: 6px solid rgba(79,201,126,0.15);
    padding: 12px 24px;
    transform: rotate(-8deg);
    white-space: nowrap;
  }

  /* ── RISKS ── */
  .risk-grid { display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 16px; }
  .risk-card {
    border: 1px solid var(--border);
    padding: 22px;
    background: var(--surface);
  }
  .risk-sev {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 9px;
    letter-spacing: 2px;
    text-transform: uppercase;
    margin-bottom: 10px;
  }
  .sev-h { color: var(--red); }
  .sev-m { color: #f0a040; }
  .sev-l { color: var(--green); }
  .risk-title { font-size: 13px; font-weight: 500; margin-bottom: 6px; color: var(--text); }
  .risk-body { font-size: 12px; color: #7a8494; }

  /* ── FOOTER ── */
  footer {
    padding: 32px 48px;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  footer p {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 10px;
    color: var(--muted);
    letter-spacing: 1px;
  }

  /* ── SCROLLBAR ── */
  ::-webkit-scrollbar { width: 4px; }
  ::-webkit-scrollbar-track { background: var(--bg); }
  ::-webkit-scrollbar-thumb { background: var(--border); }

  /* ── RESPONSIVE ── */
  @media (max-width: 900px) {
    .hero { padding: 60px 24px 50px; }
    .container { padding: 48px 24px; }
    header { padding: 0 24px; }
    footer { padding: 24px; }
    .hero-kpis, .rationale-grid, .val-methods, .grid-2, .grid-3, .dcf-grid,
    .acc-scenarios, .risk-grid, .val-methods { grid-template-columns: 1fr; }
    .hero-kpis { max-width: 100%; }
    .deal-flow { flex-direction: column; }
    .deal-step::after { content: '▼'; right: 50%; bottom: -18px; top: auto; transform: translateX(50%); }
    nav { display: none; }
    .verdict { grid-template-columns: 1fr; }
  }
</style>
</head>
<body>

<!-- HEADER -->
<header>
  <div class="logo">M&amp;A Valuation · Case Study</div>
  <nav>
    <a href="#rationale">Rationale</a>
    <a href="#synergies">Synergies</a>
    <a href="#valuation">Valuation</a>
    <a href="#accretion">Accretion</a>
    <a href="#risks">Risks</a>
  </nav>
</header>

<!-- HERO -->
<section class="hero">
  <div class="tag">Deal Analysis · EV Sector · India 2024</div>
  <h1>Should Tata Motors<br>Acquire <em>EV Next Ltd.?</em></h1>
  <p class="hero-sub">A comprehensive buy-side M&amp;A valuation analysis exploring strategic fit, synergy value, and shareholder impact of a proposed acquisition in India's fast-growing electric vehicle market.</p>
  <div class="hero-kpis">
    <div class="kpi">
      <div class="kpi-val go">₹4,200Cr</div>
      <div class="kpi-lbl">Offer Price</div>
    </div>
    <div class="kpi">
      <div class="kpi-val up">₹850Cr</div>
      <div class="kpi-lbl">Synergy Value (NPV)</div>
    </div>
    <div class="kpi">
      <div class="kpi-val bl">+8.4%</div>
      <div class="kpi-lbl">EPS Accretion (Yr3)</div>
    </div>
    <div class="kpi">
      <div class="kpi-val go">2.3×</div>
      <div class="kpi-lbl">EV/Revenue Multiple</div>
    </div>
  </div>
</section>

<!-- DEAL OVERVIEW -->
<section class="container">
  <div class="section-label">01 — Deal Overview</div>
  <div class="section-title">Transaction Summary</div>
  <div class="deal-flow">
    <div class="deal-step">
      <div class="step-num">ACQUIRER</div>
      <div class="step-title">Tata Motors Ltd.</div>
      <div class="step-body">BSE: 500570 · Market Cap ~₹3.4L Cr · JLR + Commercial + Passenger EVs (Nexon, Tiago EV)</div>
    </div>
    <div class="deal-step">
      <div class="step-num">STRUCTURE</div>
      <div class="step-title">100% Share Acquisition</div>
      <div class="step-body">Cash + Stock deal (70/30 split) · Subject to CCI approval · 6–9 month timeline</div>
    </div>
    <div class="deal-step">
      <div class="step-num">TARGET</div>
      <div class="step-title">EV Next Ltd.</div>
      <div class="step-body">Unlisted EV startup · Revenue ₹1,820Cr FY24 · EBITDA –₹140Cr · 18% market share in 2W EVs</div>
    </div>
    <div class="deal-step">
      <div class="step-num">CONSIDERATION</div>
      <div class="step-title">₹4,200 Crore</div>
      <div class="step-body">2.3× EV/Revenue · 35% control premium · Includes earn-out of ₹300Cr on milestone delivery</div>
    </div>
  </div>
</section>

<!-- STRATEGIC RATIONALE -->
<section class="container" id="rationale">
  <div class="section-label">02 — Strategic Rationale</div>
  <div class="section-title">Why This Deal Makes Sense</div>
  <div class="rationale-grid">
    <div class="rat-item">
      <div class="rat-num">01</div>
      <div class="rat-title">Market Share Acceleration</div>
      <div class="rat-body">EV Next commands 18% of India's 2-wheeler EV market with 3.2 lakh units sold FY24. Tata Motors currently has zero presence in this segment. The acquisition instantly positions Tata as a multi-segment EV leader, countering Ola Electric and Bajaj Chetak's growing dominance.</div>
    </div>
    <div class="rat-item">
      <div class="rat-num">02</div>
      <div class="rat-title">Battery Technology IP</div>
      <div class="rat-body">EV Next holds 14 patents in solid-state cell management and fast-charging architecture. These are directly applicable to Tata's upcoming Avinya and Punch EV platforms, potentially reducing R&D capex by ₹400–600Cr over 5 years through IP reuse.</div>
    </div>
    <div class="rat-item">
      <div class="rat-num">03</div>
      <div class="rat-title">Distribution & Last-Mile Reach</div>
      <div class="rat-body">EV Next operates 640 exclusive service touchpoints in Tier 2/3 cities where Tata's EV service network is thin. Combined, the entity would have 1,400+ EV-dedicated service points — a moat hard to replicate organically within 3 years.</div>
    </div>
    <div class="rat-item">
      <div class="rat-num">04</div>
      <div class="rat-title">Government Policy Tailwind</div>
      <div class="rat-body">Under FAME-III and PLI Scheme for Advanced Chemistry Cells, Tata's expanded EV portfolio would qualify for incremental incentives of ~₹180–240Cr annually. Regulatory capital allocation favours vertically integrated, large-scale EV manufacturers.</div>
    </div>
  </div>
</section>

<!-- SYNERGIES -->
<section class="container" id="synergies">
  <div class="section-label">03 — Synergy Analysis</div>
  <div class="section-title">Cost &amp; Revenue Synergies</div>
  <div class="grid-2">
    <div>
      <p style="color:var(--muted); font-size:13px; margin-bottom:20px;">Estimated synergy realisation over 3-year integration period. Year 1 captures quick wins; full run-rate by Year 3.</p>
      <table class="syn-table">
        <thead>
          <tr>
            <th>Synergy Item</th>
            <th>Type</th>
            <th>FY26E</th>
            <th>FY27E</th>
            <th>FY28E (Run Rate)</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>Shared Battery Procurement</td>
            <td><span class="pill pill-cost">Cost</span></td>
            <td class="num up">₹80Cr</td>
            <td class="num up">₹140Cr</td>
            <td class="num up">₹200Cr</td>
          </tr>
          <tr>
            <td>Manufacturing Consolidation</td>
            <td><span class="pill pill-cost">Cost</span></td>
            <td class="num up">₹30Cr</td>
            <td class="num up">₹70Cr</td>
            <td class="num up">₹110Cr</td>
          </tr>
          <tr>
            <td>SG&amp;A / Headcount Overlap</td>
            <td><span class="pill pill-cost">Cost</span></td>
            <td class="num up">₹45Cr</td>
            <td class="num up">₹65Cr</td>
            <td class="num up">₹75Cr</td>
          </tr>
          <tr>
            <td>IT &amp; Platform Consolidation</td>
            <td><span class="pill pill-cost">Cost</span></td>
            <td class="num up">₹15Cr</td>
            <td class="num up">₹25Cr</td>
            <td class="num up">₹35Cr</td>
          </tr>
          <tr>
            <td>Cross-Sell Fleet / B2B Channels</td>
            <td><span class="pill pill-rev">Revenue</span></td>
            <td class="num bl">₹60Cr</td>
            <td class="num bl">₹120Cr</td>
            <td class="num bl">₹180Cr</td>
          </tr>
          <tr>
            <td>Tata Ecosystem (Finance, Insurance)</td>
            <td><span class="pill pill-rev">Revenue</span></td>
            <td class="num bl">₹25Cr</td>
            <td class="num bl">₹55Cr</td>
            <td class="num bl">₹90Cr</td>
          </tr>
          <tr>
            <td>Export Market (Africa, SE Asia)</td>
            <td><span class="pill pill-rev">Revenue</span></td>
            <td class="num bl">—</td>
            <td class="num bl">₹40Cr</td>
            <td class="num bl">₹90Cr</td>
          </tr>
          <tr style="background: rgba(200,169,110,0.05);">
            <td style="font-weight:600; color: var(--text);">Total Synergies</td>
            <td><span class="pill pill-total">Combined</span></td>
            <td class="num go" style="font-weight:700;">₹255Cr</td>
            <td class="num go" style="font-weight:700;">₹515Cr</td>
            <td class="num go" style="font-weight:700;">₹780Cr</td>
          </tr>
        </tbody>
      </table>
    </div>
    <div>
      <div class="card" style="margin-bottom:16px;">
        <h3>Synergy NPV Calculation</h3>
        <p>Discounted at Tata Motors' WACC of 11.2%, the 5-year synergy stream yields an NPV of <span style="color:var(--green); font-family:'IBM Plex Mono',monospace; font-weight:600;">₹850 Crore</span>. This equates to ~20% of the offer price, providing a meaningful margin of safety on deal economics.</p>
        <br>
        <div style="display:flex; flex-direction:column; gap:10px;">
          <div style="display:flex; justify-content:space-between; border-bottom:1px solid var(--border); padding-bottom:8px;">
            <span style="font-size:13px; color:var(--muted);">PV of Cost Synergies</span>
            <span style="font-family:'IBM Plex Mono',monospace; color:var(--green); font-size:13px;">₹520Cr</span>
          </div>
          <div style="display:flex; justify-content:space-between; border-bottom:1px solid var(--border); padding-bottom:8px;">
            <span style="font-size:13px; color:var(--muted);">PV of Revenue Synergies</span>
            <span style="font-family:'IBM Plex Mono',monospace; color:var(--accent4); font-size:13px;">₹390Cr</span>
          </div>
          <div style="display:flex; justify-content:space-between; border-bottom:1px solid var(--border); padding-bottom:8px;">
            <span style="font-size:13px; color:var(--muted);">Integration Costs (–)</span>
            <span style="font-family:'IBM Plex Mono',monospace; color:var(--red); font-size:13px;">–₹60Cr</span>
          </div>
          <div style="display:flex; justify-content:space-between;">
            <span style="font-size:14px; font-weight:600;">Net Synergy NPV</span>
            <span style="font-family:'IBM Plex Mono',monospace; color:var(--accent); font-size:15px; font-weight:700;">₹850Cr</span>
          </div>
        </div>
      </div>
      <div class="card">
        <h3>Integration Timeline</h3>
        <p>
          <strong style="color: var(--accent);">Phase 1 (0–6 months):</strong> Leadership alignment, IT integration planning, procurement renegotiation.<br><br>
          <strong style="color: var(--accent4);">Phase 2 (6–18 months):</strong> Manufacturing consolidation, brand portfolio rationalisation, channel merge.<br><br>
          <strong style="color: var(--green);">Phase 3 (18–36 months):</strong> Full IP integration, export market launch, cross-sell maturity.
        </p>
      </div>
    </div>
  </div>
</section>

<!-- VALUATION -->
<section class="container" id="valuation">
  <div class="section-label">04 — Target Valuation</div>
  <div class="section-title">Valuing EV Next Ltd.</div>

  <div class="val-methods">
    <div class="val-m">
      <div class="val-m-tag">Method 1 — DCF Analysis</div>
      <div class="val-m-price">₹3,800Cr</div>
      <div class="val-m-sub">Intrinsic Value Estimate</div>
      <div class="val-m-rows">
        <div class="val-row"><span>Revenue CAGR (5yr)</span><span>28%</span></div>
        <div class="val-row"><span>Terminal EBITDA Margin</span><span>14%</span></div>
        <div class="val-row"><span>WACC</span><span>13.5%</span></div>
        <div class="val-row"><span>Terminal Growth Rate</span><span>5.5%</span></div>
        <div class="val-row"><span>EV (DCF)</span><span>₹3,800Cr</span></div>
      </div>
    </div>
    <div class="val-m" style="border-left:1px solid var(--border);">
      <div class="val-m-tag">Method 2 — Comparable Co. (Comps)</div>
      <div class="val-m-price">₹3,640Cr</div>
      <div class="val-m-sub">Market-Based Value</div>
      <div class="val-m-rows">
        <div class="val-row"><span>Peer EV/Revenue (median)</span><span>2.0×</span></div>
        <div class="val-row"><span>EV Next Revenue FY24</span><span>₹1,820Cr</span></div>
        <div class="val-row"><span>Peer EV/EBITDA (NTM)</span><span>22×</span></div>
        <div class="val-row"><span>Implied Equity Value</span><span>₹3,640Cr</span></div>
        <div class="val-row"><span>Comps: Ola Electric, Ampere</span><span>—</span></div>
      </div>
    </div>
    <div class="val-m" style="border-left:1px solid var(--border);">
      <div class="val-m-tag">Method 3 — Precedent Transactions</div>
      <div class="val-m-price">₹4,050Cr</div>
      <div class="val-m-sub">Control Premium Included</div>
      <div class="val-m-rows">
        <div class="val-row"><span>Median Deal EV/Rev (India EV)</span><span>2.2×</span></div>
        <div class="val-row"><span>Control Premium Applied</span><span>30–35%</span></div>
        <div class="val-row"><span>Ref: Hero × Ather (partial)</span><span>—</span></div>
        <div class="val-row"><span>Ref: Greaves Electric stake deals</span><span>—</span></div>
        <div class="val-row"><span>Implied Value</span><span>₹4,050Cr</span></div>
      </div>
    </div>
  </div>

  <!-- Football Field -->
  <div class="football-field">
    <div class="ff-title">Football Field Chart — Valuation Range Summary</div>
    <div style="display:flex; gap:60px; margin-bottom: 8px;">
      <span style="font-family:'IBM Plex Mono',monospace; font-size:9px; color:var(--muted);">₹0</span>
      <span style="font-family:'IBM Plex Mono',monospace; font-size:9px; color:var(--muted); margin-left:auto;">₹5,500Cr</span>
    </div>
    <div class="ff-row">
      <div class="ff-label">DCF Analysis</div>
      <div class="ff-bar-wrap">
        <div class="ff-bar dcf">₹3,200 – ₹4,400Cr</div>
      </div>
    </div>
    <div class="ff-row">
      <div class="ff-label">Trading Comps</div>
      <div class="ff-bar-wrap">
        <div class="ff-bar comps">₹3,000 – ₹4,100Cr</div>
      </div>
    </div>
    <div class="ff-row">
      <div class="ff-label">Precedent Transactions</div>
      <div class="ff-bar-wrap">
        <div class="ff-bar prec">₹3,600 – ₹4,800Cr</div>
      </div>
    </div>
    <div class="ff-row">
      <div class="ff-label">LBO / Floor Value</div>
      <div class="ff-bar-wrap">
        <div class="ff-bar lbo">₹2,200 – ₹3,200Cr</div>
      </div>
    </div>
    <div style="margin-top:16px; padding-top:16px; border-top:1px solid var(--border); display:flex; align-items:center; gap:16px;">
      <div style="width:16px; height:3px; background:var(--accent);"></div>
      <span style="font-family:'IBM Plex Mono',monospace; font-size:10px; color:var(--accent);">Offer Price: ₹4,200Cr</span>
      <span style="font-size:12px; color:var(--muted);">— at 10.5% premium to DCF mid, within precedent range ✓</span>
    </div>
  </div>

  <!-- DCF Assumptions -->
  <div class="dcf-grid" style="margin-top:28px;">
    <div>
      <p class="ff-title" style="font-family:'IBM Plex Mono',monospace; font-size:10px; letter-spacing:3px; text-transform:uppercase; color:var(--accent); margin-bottom:16px;">DCF — Key Assumptions</p>
      <table class="assumptions-table">
        <thead><tr><th>Assumption</th><th>Value</th></tr></thead>
        <tbody>
          <tr><td>FY24 Revenue (Base)</td><td>₹1,820 Cr</td></tr>
          <tr><td>Revenue Growth — FY25–27</td><td>32% / 28% / 24%</td></tr>
          <tr><td>Revenue Growth — FY28–29</td><td>18% / 14%</td></tr>
          <tr><td>EBITDA Margin — FY29E</td><td>14.2%</td></tr>
          <tr><td>D&A (% of Revenue)</td><td>4.5%</td></tr>
          <tr><td>Capex (% of Revenue)</td><td>7.0%</td></tr>
          <tr><td>Working Capital Change</td><td>–2% Revenue/yr</td></tr>
          <tr><td>WACC (Target)</td><td>13.5%</td></tr>
          <tr><td>Terminal Growth Rate</td><td>5.5%</td></tr>
        </tbody>
      </table>
    </div>
    <div>
      <p class="ff-title" style="font-family:'IBM Plex Mono',monospace; font-size:10px; letter-spacing:3px; text-transform:uppercase; color:var(--accent4); margin-bottom:16px;">Sensitivity — EV/Implied Price (₹Cr)</p>
      <table class="assumptions-table">
        <thead><tr><th>WACC \ TGR</th><th>4.5%</th><th>5.5%</th><th>6.5%</th></tr></thead>
        <tbody>
          <tr><td>12.0%</td><td style="color:#9aa0ab;">4,480</td><td style="color:var(--green); font-weight:600;">4,890</td><td style="color:#9aa0ab;">5,360</td></tr>
          <tr><td>13.5%</td><td style="color:#9aa0ab;">3,520</td><td style="color:var(--accent); font-weight:600;">3,800</td><td style="color:#9aa0ab;">4,140</td></tr>
          <tr><td>15.0%</td><td style="color:#9aa0ab;">2,870</td><td style="color:var(--red); font-weight:600;">3,080</td><td style="color:#9aa0ab;">3,320</td></tr>
        </tbody>
      </table>
      <p style="font-size:11px; color:var(--muted); margin-top:12px;">Offer of ₹4,200Cr requires ~12.5% WACC / 5.5% TGR to be NPV-neutral. Achievable with synergies baked in.</p>
    </div>
  </div>
</section>

<!-- ACCRETION / DILUTION -->
<section class="container" id="accretion">
  <div class="section-label">05 — Accretion / Dilution Analysis</div>
  <div class="section-title">Impact on Tata Motors EPS</div>
  <p style="color:var(--muted); font-size:13px; max-width:640px; margin-bottom:36px;">Deal financed 70% cash (at 7.5% cost of debt) + 30% stock (1.8Cr new shares issued at ₹700). Analysis assumes full synergy realisation on the stated schedule.</p>

  <div class="acc-scenarios">
    <div class="acc-card base">
      <div class="acc-tag">Base Case</div>
      <div class="acc-value">+8.4%</div>
      <div class="acc-label">EPS Accretion by Year 3</div>
      <div class="acc-details">
        <div class="acc-detail-row"><span>Year 1 EPS Impact</span><span style="color:var(--red);">–2.1%</span></div>
        <div class="acc-detail-row"><span>Year 2 EPS Impact</span><span style="color:var(--accent);">+3.8%</span></div>
        <div class="acc-detail-row"><span>Year 3 EPS Impact</span><span style="color:var(--green);">+8.4%</span></div>
        <div class="acc-detail-row"><span>Breakeven</span><span>~18 months</span></div>
        <div class="acc-detail-row"><span>Synergy Realised</span><span>100%</span></div>
      </div>
    </div>
    <div class="acc-card bull">
      <div class="acc-tag">Bull Case</div>
      <div class="acc-value">+14.2%</div>
      <div class="acc-label">EPS Accretion by Year 3</div>
      <div class="acc-details">
        <div class="acc-detail-row"><span>Year 1 EPS Impact</span><span style="color:var(--accent);">+1.2%</span></div>
        <div class="acc-detail-row"><span>Year 2 EPS Impact</span><span style="color:var(--green);">+7.6%</span></div>
        <div class="acc-detail-row"><span>Year 3 EPS Impact</span><span style="color:var(--green);">+14.2%</span></div>
        <div class="acc-detail-row"><span>Breakeven</span><span>~8 months</span></div>
        <div class="acc-detail-row"><span>Synergy Realised</span><span>125%</span></div>
      </div>
    </div>
    <div class="acc-card bear">
      <div class="acc-tag">Bear Case</div>
      <div class="acc-value">–3.1%</div>
      <div class="acc-label">EPS Dilution by Year 3</div>
      <div class="acc-details">
        <div class="acc-detail-row"><span>Year 1 EPS Impact</span><span style="color:var(--red);">–5.8%</span></div>
        <div class="acc-detail-row"><span>Year 2 EPS Impact</span><span style="color:var(--red);">–4.2%</span></div>
        <div class="acc-detail-row"><span>Year 3 EPS Impact</span><span style="color:var(--red);">–3.1%</span></div>
        <div class="acc-detail-row"><span>Breakeven</span><span>Not in 5yr</span></div>
        <div class="acc-detail-row"><span>Synergy Realised</span><span>50%</span></div>
      </div>
    </div>
  </div>

  <div class="card" style="margin-top:24px; background: rgba(200,169,110,0.03);">
    <h3>Accretion Bridge — Base Case Year 3</h3>
    <div style="display:grid; grid-template-columns: repeat(5,1fr); gap:1px; background:var(--border); margin-top:12px;">
      <div style="background:var(--surface); padding:18px 14px; text-align:center;">
        <div style="font-family:'IBM Plex Mono',monospace; font-size:18px; color:var(--text);">₹42.6</div>
        <div style="font-size:10px; color:var(--muted); margin-top:4px;">Standalone EPS</div>
      </div>
      <div style="background:var(--surface); padding:18px 14px; text-align:center;">
        <div style="font-family:'IBM Plex Mono',monospace; font-size:18px; color:var(--red);">–₹4.2</div>
        <div style="font-size:10px; color:var(--muted); margin-top:4px;">Interest on Debt</div>
      </div>
      <div style="background:var(--surface); padding:18px 14px; text-align:center;">
        <div style="font-family:'IBM Plex Mono',monospace; font-size:18px; color:var(--red);">–₹1.8</div>
        <div style="font-size:10px; color:var(--muted); margin-top:4px;">Dilution (New Shares)</div>
      </div>
      <div style="background:var(--surface); padding:18px 14px; text-align:center;">
        <div style="font-family:'IBM Plex Mono',monospace; font-size:18px; color:var(--green);">+₹9.6</div>
        <div style="font-size:10px; color:var(--muted); margin-top:4px;">Target Earnings + Synergies</div>
      </div>
      <div style="background:rgba(200,169,110,0.06); padding:18px 14px; text-align:center; border-left:2px solid var(--accent);">
        <div style="font-family:'IBM Plex Mono',monospace; font-size:18px; color:var(--accent);">₹46.2</div>
        <div style="font-size:10px; color:var(--muted); margin-top:4px;">Pro Forma EPS (+8.4%)</div>
      </div>
    </div>
  </div>
</section>

<!-- RISKS -->
<section class="container" id="risks">
  <div class="section-label">06 — Key Risks</div>
  <div class="section-title">Risk Register</div>
  <div class="risk-grid">
    <div class="risk-card">
      <div class="risk-sev sev-h">● HIGH SEVERITY</div>
      <div class="risk-title">Synergy Execution Risk</div>
      <div class="risk-body">Integration of two distinct cultures, tech stacks, and distribution models is complex. Historical M&amp;A data shows 40–60% of deals fail to achieve Year 1 synergy targets. Bear case assumes only 50% realisation.</div>
    </div>
    <div class="risk-card">
      <div class="risk-sev sev-h">● HIGH SEVERITY</div>
      <div class="risk-title">Valuation Overpay Risk</div>
      <div class="risk-body">At ₹4,200Cr (35% premium), if EV Next's growth slows to 15% CAGR vs projected 28%, intrinsic value drops to ~₹2,600Cr. Earn-out structure partially mitigates this risk.</div>
    </div>
    <div class="risk-card">
      <div class="risk-sev sev-m">● MEDIUM</div>
      <div class="risk-title">Technology Disruption</div>
      <div class="risk-body">EV Next's battery patents may face obsolescence if solid-state batteries commercialise faster than expected. China-origin cell cost deflation could also erode the IP moat within 3–4 years.</div>
    </div>
    <div class="risk-card">
      <div class="risk-sev sev-m">● MEDIUM</div>
      <div class="risk-title">Regulatory / CCI Risk</div>
      <div class="risk-body">Competition Commission of India may impose conditions given combined EV market share exceeding 30% in passenger + 2W segment. Could require divesting specific charging network assets.</div>
    </div>
    <div class="risk-card">
      <div class="risk-sev sev-m">● MEDIUM</div>
      <div class="risk-title">Key Person Dependency</div>
      <div class="risk-body">EV Next's CTO and founding team hold critical battery IP knowledge. Post-acquisition talent retention is essential. Recommend 3-year retention bonus pool of ₹60–80Cr for top 25 engineers.</div>
    </div>
    <div class="risk-card">
      <div class="risk-sev sev-l">● LOW</div>
      <div class="risk-title">Tata Balance Sheet Stretch</div>
      <div class="risk-body">70% cash portion adds ~₹2,940Cr debt to Tata Motors. Pro forma Net Debt/EBITDA moves from 1.8× to 2.4× — elevated but manageable. JLR FCF provides deleveraging runway.</div>
    </div>
  </div>
</section>

<!-- VERDICT -->
<section class="container" style="border-bottom:none;">
  <div class="section-label">07 — Investment Conclusion</div>
  <div class="section-title">Deal Recommendation</div>
  <div class="verdict">
    <div>
      <p style="font-size:15px; color:var(--text); max-width:600px; margin-bottom:20px;">
        The proposed acquisition of EV Next Ltd. at ₹4,200 Crore is <strong style="color:var(--green);">strategically compelling and financially accretive</strong> under Base and Bull scenarios. The offer price sits within the upper range of DCF and precedent transaction analysis, with the 35% control premium justified by:
      </p>
      <ul style="list-style:none; display:flex; flex-direction:column; gap:10px; max-width:560px;">
        <li style="font-size:13.5px; color:#9aa0ab; padding-left:20px; position:relative;"><span style="position:absolute; left:0; color:var(--green);">✓</span> Immediate entry into 2-wheeler EV — Tata's biggest segment gap</li>
        <li style="font-size:13.5px; color:#9aa0ab; padding-left:20px; position:relative;"><span style="position:absolute; left:0; color:var(--green);">✓</span> ₹850Cr NPV synergy cushion effectively reduces real cost to ₹3,350Cr</li>
        <li style="font-size:13.5px; color:#9aa0ab; padding-left:20px; position:relative;"><span style="position:absolute; left:0; color:var(--green);">✓</span> +8.4% EPS accretion by Year 3 with full synergies — value-creating for shareholders</li>
        <li style="font-size:13.5px; color:#9aa0ab; padding-left:20px; position:relative;"><span style="position:absolute; left:0; color:var(--green);">✓</span> 14 battery patents accelerate Avinya &amp; next-gen platform R&amp;D</li>
        <li style="font-size:13.5px; color:#9aa0ab; padding-left:20px; position:relative;"><span style="position:absolute; left:0; color:var(--accent);">!</span> Bear case risk (50% synergy miss) results in EPS dilution — integration governance critical</li>
      </ul>
      <p style="margin-top:24px; font-family:'IBM Plex Mono',monospace; font-size:11px; color:var(--muted);">Prepared for illustrative purposes · All figures hypothetical · March 2025</p>
    </div>
    <div class="verdict-stamp">PROCEED</div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <p>M&amp;A Valuation Case Study · Tata Motors × EV Next Ltd.</p>
  <p>Illustrative Analysis · FY2024–2028 Projections · ₹ Crore unless stated</p>
</footer>

</body>
</html>
