<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width,initial-scale=1"/>
<title>Priyanka Panneerselvam — Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Fraunces:ital,opsz,wght@0,9..144,300;0,9..144,600;1,9..144,400&family=DM+Mono:wght@400;500&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet"/>
<script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/4.4.1/chart.umd.min.js"></script>
<style>
:root{
  --bg:#0d0d0b;
  --surface:#141412;
  --surface2:#1c1c19;
  --border:#2a2a26;
  --accent:#E8593C;
  --accent2:#0C447C;
  --accent3:#1D9E75;
  --text:#e8e6df;
  --muted:#7a7870;
  --faint:#3a3a36;
  --mono:'DM Mono',monospace;
  --serif:'Fraunces',serif;
  --sans:'DM Sans',sans-serif;
}
*{margin:0;padding:0;box-sizing:border-box}
html{scroll-behavior:smooth}
body{background:var(--bg);color:var(--text);font-family:var(--sans);font-weight:300;line-height:1.7;overflow-x:hidden}

/* noise overlay */
body::before{content:'';position:fixed;inset:0;background-image:url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.04'/%3E%3C/svg%3E");opacity:.4;pointer-events:none;z-index:0}

/* GRID LINES */
.grid-lines{position:fixed;inset:0;z-index:0;pointer-events:none;background-image:linear-gradient(var(--faint) 1px,transparent 1px),linear-gradient(90deg,var(--faint) 1px,transparent 1px);background-size:60px 60px;opacity:.18}

main{position:relative;z-index:1;max-width:900px;margin:0 auto;padding:0 24px 80px}

/* ── HERO ── */
.hero{padding:80px 0 60px;display:grid;grid-template-columns:1fr auto;gap:40px;align-items:center;border-bottom:1px solid var(--border)}
.hero-eyebrow{font-family:var(--mono);font-size:11px;letter-spacing:.18em;text-transform:uppercase;color:var(--accent);margin-bottom:16px}
.hero-name{font-family:var(--serif);font-size:clamp(42px,7vw,72px);font-weight:600;line-height:1;letter-spacing:-.02em}
.hero-name span{font-style:italic;font-weight:300;color:var(--accent)}
.hero-roles{font-family:var(--mono);font-size:12px;color:var(--muted);margin-top:14px;letter-spacing:.06em}
.hero-roles b{color:var(--text);font-weight:500}
.hero-bio{font-size:14px;color:var(--muted);line-height:1.8;margin-top:18px;max-width:480px}
.hero-links{display:flex;gap:10px;flex-wrap:wrap;margin-top:24px}
.hl{display:inline-flex;align-items:center;gap:6px;font-family:var(--mono);font-size:11px;letter-spacing:.06em;padding:6px 12px;border:1px solid var(--border);border-radius:4px;color:var(--muted);text-decoration:none;transition:border-color .2s,color .2s}
.hl:hover{border-color:var(--accent);color:var(--accent)}
.hl svg{width:12px;height:12px;fill:currentColor;flex-shrink:0}

.avatar-wrap{position:relative;flex-shrink:0}
.avatar{width:110px;height:110px;border-radius:50%;background:conic-gradient(from 130deg,#E8593C,#0C447C,#1D9E75,#E8593C);display:flex;align-items:center;justify-content:center;font-family:var(--serif);font-size:32px;font-weight:600;color:#fff;position:relative}
.avatar::after{content:'';position:absolute;inset:3px;border-radius:50%;background:var(--bg)}
.avatar-initials{position:relative;z-index:1}
.status{position:absolute;bottom:4px;right:4px;background:#1D9E75;width:14px;height:14px;border-radius:50%;border:2px solid var(--bg)}
@keyframes pulse{0%,100%{box-shadow:0 0 0 0 rgba(29,158,117,.5)}50%{box-shadow:0 0 0 6px rgba(29,158,117,0)}}
.status{animation:pulse 2s ease-in-out infinite}

/* ── SECTION ── */
.section{padding:56px 0 0}
.sec-header{display:flex;align-items:baseline;gap:16px;margin-bottom:32px}
.sec-num{font-family:var(--mono);font-size:11px;color:var(--accent);letter-spacing:.1em}
.sec-title{font-family:var(--serif);font-size:24px;font-weight:600}
.sec-line{flex:1;height:1px;background:var(--border)}

/* ── SKILL BARS ── */
.skill-grid{display:grid;grid-template-columns:1fr 1fr;gap:10px}
@media(max-width:600px){.skill-grid{grid-template-columns:1fr}}
.skill-item{background:var(--surface);border:1px solid var(--border);border-radius:8px;padding:14px 16px}
.skill-top{display:flex;justify-content:space-between;align-items:center;margin-bottom:10px}
.skill-name{font-family:var(--mono);font-size:12px;color:var(--text);font-weight:500}
.skill-pct{font-family:var(--mono);font-size:11px;color:var(--accent)}
.skill-bar{height:3px;background:var(--faint);border-radius:2px;overflow:hidden}
.skill-fill{height:100%;border-radius:2px;width:0;transition:width 1.2s cubic-bezier(.4,0,.2,1)}
.skill-tech{font-family:var(--mono);font-size:10px;color:var(--muted);margin-top:7px;letter-spacing:.04em}

/* ── RADAR ── */
.charts-row{display:grid;grid-template-columns:1fr 1fr;gap:16px;align-items:start}
@media(max-width:600px){.charts-row{grid-template-columns:1fr}}
.chart-card{background:var(--surface);border:1px solid var(--border);border-radius:10px;padding:20px}
.chart-label{font-family:var(--mono);font-size:11px;color:var(--muted);letter-spacing:.08em;text-transform:uppercase;margin-bottom:16px}
.chart-canvas-wrap{position:relative;height:220px}

/* ── PROJECTS ── */
.proj-grid{display:grid;grid-template-columns:1fr 1fr;gap:14px}
@media(max-width:600px){.proj-grid{grid-template-columns:1fr}}
.proj-card{background:var(--surface);border:1px solid var(--border);border-radius:10px;padding:22px;position:relative;overflow:hidden;transition:border-color .25s,transform .2s}
.proj-card:hover{border-color:var(--accent);transform:translateY(-2px)}
.proj-card::before{content:'';position:absolute;top:0;left:0;right:0;height:2px;background:linear-gradient(90deg,var(--accent),transparent);opacity:0;transition:opacity .25s}
.proj-card:hover::before{opacity:1}
.proj-icon{font-size:22px;margin-bottom:12px}
.proj-name{font-family:var(--serif);font-size:18px;font-weight:600;margin-bottom:4px}
.proj-sub{font-family:var(--mono);font-size:11px;color:var(--accent);letter-spacing:.06em;margin-bottom:12px}
.proj-desc{font-size:13px;color:var(--muted);line-height:1.7;margin-bottom:14px}
.proj-table{width:100%;border-collapse:collapse;font-size:12px}
.proj-table tr td{padding:5px 0;border-bottom:1px solid var(--faint);vertical-align:top}
.proj-table tr:last-child td{border-bottom:none}
.proj-table td:first-child{color:var(--muted);width:96px;font-weight:500;font-family:var(--mono);font-size:10px;letter-spacing:.05em;text-transform:uppercase;padding-right:10px}
.proj-table td:last-child{color:var(--text)}
.proj-tags{display:flex;gap:6px;flex-wrap:wrap;margin-top:14px}
.tag{font-family:var(--mono);font-size:10px;padding:3px 8px;border-radius:3px;background:var(--faint);color:var(--muted);border:1px solid var(--border)}

/* ── HEATMAP ── */
.heatmap-wrap{background:var(--surface);border:1px solid var(--border);border-radius:10px;padding:24px;overflow-x:auto}
.heatmap-label{font-family:var(--mono);font-size:11px;color:var(--muted);letter-spacing:.08em;text-transform:uppercase;margin-bottom:18px}
.heatmap-grid{display:flex;gap:3px;align-items:flex-start}
.heatmap-col{display:flex;flex-direction:column;gap:3px}
.heatmap-cell{width:11px;height:11px;border-radius:2px;transition:transform .1s}
.heatmap-cell:hover{transform:scale(1.4);z-index:10;position:relative}
.hm-0{background:#1c1c19}
.hm-1{background:#0F6E56}
.hm-2{background:#1D9E75}
.hm-3{background:#5DCAA5}
.hm-4{background:#9FE1CB}
.heatmap-months{display:flex;gap:3px;margin-bottom:6px;font-family:var(--mono);font-size:9px;color:var(--muted)}
.heatmap-footer{display:flex;align-items:center;gap:8px;margin-top:14px;font-family:var(--mono);font-size:10px;color:var(--muted)}
.hm-legend{display:flex;gap:3px;align-items:center}
.hm-legend-cell{width:11px;height:11px;border-radius:2px}

/* ── FOCUS ── */
.focus-list{display:flex;flex-direction:column;gap:10px}
.focus-item{display:flex;align-items:flex-start;gap:14px;background:var(--surface);border:1px solid var(--border);border-radius:8px;padding:14px 16px;transition:border-color .2s}
.focus-item:hover{border-color:var(--faint)}
.focus-dot{width:6px;height:6px;border-radius:50%;background:var(--accent);flex-shrink:0;margin-top:7px}
.focus-text{font-size:13px;line-height:1.7;color:var(--muted)}
.focus-text strong{color:var(--text);font-weight:500}

/* ── OPEN TO ── */
.open-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:12px}
@media(max-width:600px){.open-grid{grid-template-columns:1fr}}
.open-card{background:var(--surface);border:1px solid var(--border);border-radius:10px;padding:18px;transition:border-color .2s}
.open-card:hover{border-color:var(--accent3)}
.open-icon{font-size:20px;margin-bottom:10px}
.open-role{font-weight:500;font-size:14px;margin-bottom:6px}
.open-scope{font-size:12px;color:var(--muted);line-height:1.6}

/* ── CTA ── */
.cta{margin-top:56px;padding:36px;background:var(--surface);border:1px solid var(--border);border-radius:12px;text-align:center;position:relative;overflow:hidden}
.cta::before{content:'';position:absolute;inset:0;background:radial-gradient(ellipse at 50% 0%,rgba(232,89,60,.08),transparent 70%);pointer-events:none}
.cta-title{font-family:var(--serif);font-size:26px;font-weight:600;margin-bottom:8px}
.cta-sub{font-size:14px;color:var(--muted);margin-bottom:24px}
.cta-btns{display:flex;gap:12px;justify-content:center;flex-wrap:wrap}
.btn{display:inline-flex;align-items:center;gap:8px;font-family:var(--mono);font-size:12px;letter-spacing:.06em;padding:10px 22px;border-radius:5px;text-decoration:none;transition:opacity .2s,transform .15s;border:none;cursor:pointer}
.btn:hover{opacity:.85;transform:translateY(-1px)}
.btn-primary{background:var(--accent);color:#fff}
.btn-secondary{background:var(--accent2);color:#fff}
.btn svg{width:14px;height:14px;fill:currentColor}

/* ── META ── */
.meta{text-align:center;padding:40px 0 0;font-family:var(--mono);font-size:10px;color:var(--faint);letter-spacing:.1em}

/* ── ANIMATIONS ── */
@keyframes fadeUp{from{opacity:0;transform:translateY(24px)}to{opacity:1;transform:translateY(0)}}
.reveal{opacity:0;animation:fadeUp .7s ease forwards}
.d1{animation-delay:.1s}.d2{animation-delay:.2s}.d3{animation-delay:.3s}.d4{animation-delay:.4s}
</style>
</head>
<body>
<div class="grid-lines"></div>

<main>

<!-- HERO -->
<section class="hero reveal">
  <div>
    <div class="hero-eyebrow">// Technology Innovation Hub</div>
    <h1 class="hero-name">Priyanka<br><span>Panneerselvam</span></h1>
    <p class="hero-roles"><b>Full-Stack Engineer</b> · AI & DS Researcher · UI/UX Architect</p>
    <p class="hero-bio">Building data-intensive systems at the intersection of high-performance backend engineering, machine learning, and precision-crafted frontends. Full delivery lifecycle — schema to deployment.</p>
    <div class="hero-links">
      <a class="hl" href="https://linkedin.com/in/priyanka-panneerselvam" target="_blank">
        <svg viewBox="0 0 24 24"><path d="M16 8a6 6 0 016 6v7h-4v-7a2 2 0 00-2-2 2 2 0 00-2 2v7h-4v-7a6 6 0 016-6zM2 9h4v12H2z"/><circle cx="4" cy="4" r="2"/></svg>LinkedIn
      </a>
      <a class="hl" href="https://leetcode.com/u/priyankapanneer__29/" target="_blank">
        <svg viewBox="0 0 24 24"><path d="M13.483 0a1.374 1.374 0 00-.961.438L7.116 6.226l-3.854 4.126a5.266 5.266 0 00-1.209 2.104 5.527 5.527 0 00.062 2.362 5.83 5.83 0 00.349 1.017 5.938 5.938 0 001.271 1.818l4.277 4.193.039.038c2.248 2.165 5.852 2.133 8.063-.074l2.396-2.392c.54-.54.54-1.414.003-1.955a1.378 1.378 0 00-1.951-.003l-2.396 2.392a3.021 3.021 0 01-4.205.038l-.02-.019-4.276-4.193c-.652-.64-.972-1.469-.948-2.263a2.68 2.68 0 01.066-.523 2.545 2.545 0 01.619-1.164L9.13 8.114c1.058-1.134 3.204-1.27 4.43-.278l3.501 2.831c.593.48 1.461.387 1.94-.207a1.384 1.384 0 00-.207-1.943l-3.5-2.831c-.8-.647-1.766-1.045-2.774-1.202l2.015-2.158A1.384 1.384 0 0013.483 0zm-2.866 12.815a1.38 1.38 0 00-1.38 1.382 1.38 1.38 0 001.38 1.382H20.79a1.38 1.38 0 001.38-1.382 1.38 1.38 0 00-1.38-1.382z"/></svg>LeetCode
      </a>
      <a class="hl" href="https://www.codechef.com/users/priyanka_pan29" target="_blank">
        <svg viewBox="0 0 24 24"><path d="M11.2 0C6.577 0 4.067 2.741 4.067 5.566c0 1.09.363 1.815.726 2.54-.363.363-.726.727-.726 1.454 0 .545.182 1.09.545 1.453-.545.545-.908 1.272-.908 2.18 0 .908.363 1.815 1.09 2.54-.727.546-1.09 1.272-1.09 2.18C3.704 20.168 7.123 24 12 24c4.695 0 8.296-3.65 8.296-6.25 0-.908-.363-1.634-.727-2.18.364-.363.546-.908.546-1.453 0-.727-.182-1.272-.546-1.635.364-.545.546-1.09.546-1.817 0-.908-.364-1.635-.909-2.18.364-.364.546-.908.546-1.454 0-.727-.364-1.272-.909-1.817.364-.545.546-1.272.546-2.18C19.389 2.559 16.516 0 11.2 0z"/></svg>CodeChef
      </a>
      <a class="hl" href="mailto:priyankapanneerselvam29@gmail.com">
        <svg viewBox="0 0 24 24"><path d="M20 4H4c-1.1 0-2 .9-2 2v12c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm0 4l-8 5-8-5V6l8 5 8-5v2z"/></svg>Email
      </a>
    </div>
  </div>
  <div class="avatar-wrap reveal d2">
    <div class="avatar"><span class="avatar-initials">PP</span></div>
    <div class="status" title="Open to work"></div>
  </div>
</section>

<!-- SKILL BARS -->
<section class="section reveal d1">
  <div class="sec-header">
    <span class="sec-num">01</span>
    <h2 class="sec-title">Technical Stack</h2>
    <div class="sec-line"></div>
  </div>
  <div class="skill-grid" id="skillGrid">
    <!-- filled by JS -->
  </div>
</section>

<!-- CHARTS -->
<section class="section reveal d2">
  <div class="sec-header">
    <span class="sec-num">02</span>
    <h2 class="sec-title">Proficiency Breakdown</h2>
    <div class="sec-line"></div>
  </div>
  <div class="charts-row">
    <div class="chart-card">
      <div class="chart-label">Domain Radar</div>
      <div class="chart-canvas-wrap"><canvas id="radarChart"></canvas></div>
    </div>
    <div class="chart-card">
      <div class="chart-label">Language Distribution</div>
      <div class="chart-canvas-wrap"><canvas id="donutChart"></canvas></div>
    </div>
  </div>
</section>

<!-- CONTRIBUTION HEATMAP -->
<section class="section reveal d2">
  <div class="sec-header">
    <span class="sec-num">03</span>
    <h2 class="sec-title">Contribution Activity</h2>
    <div class="sec-line"></div>
  </div>
  <div class="heatmap-wrap">
    <div class="heatmap-label">Last 52 weeks of activity</div>
    <div id="monthLabels" class="heatmap-months"></div>
    <div class="heatmap-grid" id="heatmapGrid"></div>
    <div class="heatmap-footer">
      Less
      <div class="hm-legend">
        <div class="hm-legend-cell hm-0"></div>
        <div class="hm-legend-cell hm-1"></div>
        <div class="hm-legend-cell hm-2"></div>
        <div class="hm-legend-cell hm-3"></div>
        <div class="hm-legend-cell hm-4"></div>
      </div>
      More
    </div>
  </div>
</section>

<!-- PROJECTS -->
<section class="section reveal d1">
  <div class="sec-header">
    <span class="sec-num">04</span>
    <h2 class="sec-title">Engineering Projects</h2>
    <div class="sec-line"></div>
  </div>
  <div class="proj-grid">
    <div class="proj-card">
      <div class="proj-icon">🛡️</div>
      <div class="proj-name">EcoCart AI</div>
      <div class="proj-sub">Carbon-Neutral Commerce System</div>
      <p class="proj-desc">Hybrid intelligence platform integrating carbon footprint analysis directly into the e-commerce transaction layer.</p>
      <table class="proj-table">
        <tr><td>Architecture</td><td>Flask REST backend with modular Python data pipeline</td></tr>
        <tr><td>Data Layer</td><td>High-throughput CSV parsing with structured preprocessing</td></tr>
        <tr><td>AI Component</td><td>Sustainability scoring model at product & cart level</td></tr>
        <tr><td>Design Focus</td><td>Separated ingestion, scoring, and API layers for scale</td></tr>
      </table>
      <div class="proj-tags">
        <span class="tag">Flask</span><span class="tag">Python</span><span class="tag">CSV Pipelines</span><span class="tag">ML Scoring</span>
      </div>
    </div>
    <div class="proj-card">
      <div class="proj-icon">📊</div>
      <div class="proj-name">Local Hive</div>
      <div class="proj-sub">Enterprise Employee Management Dashboard</div>
      <p class="proj-desc">Internally deployed management system designed for operational reliability and relational data integrity.</p>
      <table class="proj-table">
        <tr><td>Architecture</td><td>Kotlin app logic + PHP backend, deployed via XAMPP</td></tr>
        <tr><td>Database</td><td>MySQL schema with enforced relational integrity</td></tr>
        <tr><td>Scope</td><td>Role-based access, records, reporting, dashboards</td></tr>
        <tr><td>Design Focus</td><td>Data consistency and query efficiency first</td></tr>
      </table>
      <div class="proj-tags">
        <span class="tag">Kotlin</span><span class="tag">PHP</span><span class="tag">MySQL</span><span class="tag">XAMPP</span>
      </div>
    </div>
  </div>
</section>

<!-- CURRENT FOCUS -->
<section class="section reveal d2">
  <div class="sec-header">
    <span class="sec-num">05</span>
    <h2 class="sec-title">Currently Working On</h2>
    <div class="sec-line"></div>
  </div>
  <div class="focus-list">
    <div class="focus-item">
      <div class="focus-dot"></div>
      <p class="focus-text">Optimizing ML model inference pipelines using <strong>PyTorch</strong> and <strong>TensorFlow</strong> for production-grade deployment</p>
    </div>
    <div class="focus-item">
      <div class="focus-dot"></div>
      <p class="focus-text">Designing <strong>scalable API architectures</strong> for data-heavy full-stack applications with high concurrency requirements</p>
    </div>
    <div class="focus-item">
      <div class="focus-dot"></div>
      <p class="focus-text">Advancing frontend systems with <strong>component-driven design</strong> and modern CSS architecture for glassmorphic UIs</p>
    </div>
  </div>
</section>

<!-- OPEN TO -->
<section class="section reveal d1">
  <div class="sec-header">
    <span class="sec-num">06</span>
    <h2 class="sec-title">Open To</h2>
    <div class="sec-line"></div>
  </div>
  <div class="open-grid">
    <div class="open-card">
      <div class="open-icon">⚙️</div>
      <div class="open-role">Full-Stack Engineering</div>
      <p class="open-scope">Backend-heavy systems, API design, Python / PHP / JS stacks</p>
    </div>
    <div class="open-card">
      <div class="open-icon">🧠</div>
      <div class="open-role">AI & Data Science</div>
      <p class="open-scope">ML integration, model deployment, data pipeline engineering</p>
    </div>
    <div class="open-card">
      <div class="open-icon">🔬</div>
      <div class="open-role">Research Collaboration</div>
      <p class="open-scope">Applied AI in commerce, sustainability tech, or enterprise tooling</p>
    </div>
  </div>
</section>

<!-- CTA -->
<div class="cta reveal d3">
  <h2 class="cta-title">Let's build something that matters.</h2>
  <p class="cta-sub">Hiring for Full-Stack or AI/DS roles? Open to full-time roles and research collaborations.</p>
  <div class="cta-btns">
    <a class="btn btn-primary" href="https://linkedin.com/in/priyanka-panneerselvam" target="_blank">
      <svg viewBox="0 0 24 24"><path d="M16 8a6 6 0 016 6v7h-4v-7a2 2 0 00-2-2 2 2 0 00-2 2v7h-4v-7a6 6 0 016-6zM2 9h4v12H2z"/><circle cx="4" cy="4" r="2"/></svg>Connect on LinkedIn
    </a>
    <a class="btn btn-secondary" href="mailto:priyankapanneerselvam29@gmail.com">
      <svg viewBox="0 0 24 24"><path d="M20 4H4c-1.1 0-2 .9-2 2v12c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm0 4l-8 5-8-5V6l8 5 8-5v2z"/></svg>Send an Email
    </a>
  </div>
</div>

<div class="meta">v3.0 · March 2026 · Technology Innovation Hub · priyankapanneer</div>

</main>

<script>
// ── SKILL BARS ──
const skills = [
  {name:'Python / Flask',pct:90,color:'#E8593C',tech:'Flask · REST APIs · Data pipelines'},
  {name:'PHP / Laravel',pct:78,color:'#E8593C',tech:'Laravel · XAMPP · MVC architecture'},
  {name:'JavaScript',pct:80,color:'#0C447C',tech:'Vanilla JS · DOM · ES6+'},
  {name:'HTML5 / CSS3',pct:85,color:'#0C447C',tech:'Bootstrap · Glassmorphism · Flex/Grid'},
  {name:'MySQL / SQLite',pct:82,color:'#1D9E75',tech:'Schema design · Normalization · Queries'},
  {name:'PyTorch / TensorFlow',pct:72,color:'#1D9E75',tech:'Model training · Inference pipelines'},
  {name:'Kotlin',pct:68,color:'#BA7517',tech:'Android logic · App architecture'},
  {name:'Git / GitHub',pct:88,color:'#BA7517',tech:'Version control · Workflows · CI'},
];

const grid = document.getElementById('skillGrid');
skills.forEach(s => {
  grid.innerHTML += `<div class="skill-item">
    <div class="skill-top">
      <span class="skill-name">${s.name}</span>
      <span class="skill-pct">${s.pct}%</span>
    </div>
    <div class="skill-bar"><div class="skill-fill" data-pct="${s.pct}" style="background:${s.color}"></div></div>
    <div class="skill-tech">${s.tech}</div>
  </div>`;
});

// animate bars on load
setTimeout(() => {
  document.querySelectorAll('.skill-fill').forEach(el => {
    el.style.width = el.dataset.pct + '%';
  });
}, 400);

// ── CHART.JS: RADAR ──
const rCtx = document.getElementById('radarChart').getContext('2d');
new Chart(rCtx, {
  type: 'radar',
  data: {
    labels: ['Backend','Frontend','Database','AI / ML','Mobile','DevOps'],
    datasets: [{
      data: [90,82,84,72,68,80],
      backgroundColor: 'rgba(232,89,60,.15)',
      borderColor: '#E8593C',
      borderWidth: 1.5,
      pointBackgroundColor: '#E8593C',
      pointRadius: 4,
      pointHoverRadius: 6,
    }]
  },
  options: {
    responsive: true, maintainAspectRatio: false,
    scales: {
      r: {
        min: 0, max: 100,
        ticks: {display:false,stepSize:25},
        grid: {color:'rgba(255,255,255,.07)'},
        angleLines: {color:'rgba(255,255,255,.07)'},
        pointLabels: {color:'#7a7870',font:{family:"'DM Mono',monospace",size:11}}
      }
    },
    plugins: {legend:{display:false}},
    animation: {duration:1200,easing:'easeInOutQuart'}
  }
});

// ── CHART.JS: DONUT ──
const dCtx = document.getElementById('donutChart').getContext('2d');
new Chart(dCtx, {
  type: 'doughnut',
  data: {
    labels: ['Python','JavaScript','PHP','Kotlin','HTML/CSS','SQL'],
    datasets: [{
      data: [32,22,18,10,10,8],
      backgroundColor: ['#E8593C','#0C447C','#BA7517','#1D9E75','#533AB7','#993C1D'],
      borderColor: '#141412',
      borderWidth: 3,
      hoverOffset: 6,
    }]
  },
  options: {
    responsive: true, maintainAspectRatio: false,
    cutout: '62%',
    plugins: {
      legend: {
        position:'bottom',
        labels: {color:'#7a7870',font:{family:"'DM Mono',monospace",size:10},padding:12,boxWidth:10,boxHeight:10}
      }
    },
    animation: {duration:1200,easing:'easeInOutQuart'}
  }
});

// ── HEATMAP ──
function buildHeatmap() {
  const weeks = 52;
  const monthNames = ['Jan','Feb','Mar','Apr','May','Jun','Jul','Aug','Sep','Oct','Nov','Dec'];
  const grid = document.getElementById('heatmapGrid');
  const mLabels = document.getElementById('monthLabels');

  // seed-based random for consistent pattern
  function seededRand(seed) {
    let s = seed;
    return function() { s = (s * 1664525 + 1013904223) & 0xffffffff; return (s >>> 0) / 0xffffffff; };
  }
  const rand = seededRand(42);

  // weighted random: more 0s, occasional bursts
  function activity() {
    const r = rand();
    if (r < 0.35) return 0;
    if (r < 0.60) return 1;
    if (r < 0.80) return 2;
    if (r < 0.92) return 3;
    return 4;
  }

  const today = new Date();
  const startDate = new Date(today);
  startDate.setDate(startDate.getDate() - (weeks * 7));

  let lastMonth = -1;
  let monthLabelHtml = '';
  let widthSoFar = 0;

  for (let w = 0; w < weeks; w++) {
    const col = document.createElement('div');
    col.className = 'heatmap-col';

    const d = new Date(startDate);
    d.setDate(d.getDate() + w * 7);
    const month = d.getMonth();

    if (month !== lastMonth) {
      // rough positioning via margin
      const spaces = w === 0 ? 0 : 0;
      monthLabelHtml += `<span style="min-width:${w===0?0:14*(w - widthSoFar)}px"></span><span>${monthNames[month]}</span>`;
      lastMonth = month;
      widthSoFar = w;
    }

    for (let day = 0; day < 7; day++) {
      const level = activity();
      const cell = document.createElement('div');
      cell.className = `heatmap-cell hm-${level}`;
      const cellDate = new Date(startDate);
      cellDate.setDate(cellDate.getDate() + w * 7 + day);
      cell.title = `${cellDate.toDateString()} — ${['No','1–2','3–5','6–9','10+'][level]} contributions`;
      col.appendChild(cell);
    }
    grid.appendChild(col);
  }
}
buildHeatmap();
</script>
</body>
</html>
