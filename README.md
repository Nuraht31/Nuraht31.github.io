<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Tharun — Supply Chain Data Analyst</title>
<meta name="description" content="Tharun — Data Analyst specializing in supply chain analytics: network optimization, SQL, Python, Power BI, and Tableau.">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Archivo:wght@600;700;800;900&family=Inter:wght@400;500;600;700&family=IBM+Plex+Mono:wght@400;500;600&display=swap" rel="stylesheet">
<style>
:root{
  --bg:#F1F3F0;
  --surface:#FFFFFF;
  --ink:#14201E;
  --ink-muted:#56685F;
  --ink-faint:#8A988F;
  --teal:#1C6E5C;
  --teal-dim:#E4EEEB;
  --rust:#C24914;
  --line:#DBE1D9;
  --radius:8px;
  --maxw:1120px;
}
*{box-sizing:border-box;}
html{scroll-behavior:smooth;}
body{
  margin:0; background:var(--bg); color:var(--ink);
  font-family:'Inter',sans-serif; line-height:1.55; font-size:16px;
  -webkit-font-smoothing:antialiased;
}
h1,h2,h3,h4{font-family:'Archivo',sans-serif; font-weight:800; letter-spacing:-0.015em; margin:0;}
.mono{font-family:'IBM Plex Mono',monospace;}
.wrap{max-width:var(--maxw); margin:0 auto; padding:0 28px;}
a{color:inherit;}
img,svg{max-width:100%;}
::selection{background:var(--teal); color:white;}

/* ---------- utility ---------- */
.eyebrow{
  display:inline-flex; align-items:center; gap:8px;
  font-family:'IBM Plex Mono',monospace; font-size:0.74rem; letter-spacing:0.08em;
  color:var(--teal); text-transform:uppercase; margin-bottom:14px;
}
.eyebrow::before{content:""; width:18px; height:1.5px; background:var(--teal); display:inline-block;}
.section{padding:88px 0;}
.section-head{margin-bottom:44px; max-width:640px;}
.section-head h2{font-size:2rem;}
.section-head p{color:var(--ink-muted); margin-top:10px; font-size:1.02rem;}
.reveal{opacity:0; transform:translateY(18px); transition:opacity 0.6s ease, transform 0.6s ease;}
.reveal.visible{opacity:1; transform:translateY(0);}
@media (prefers-reduced-motion: reduce){
  .reveal{opacity:1; transform:none; transition:none;}
  *{animation-duration:0.01ms !important; animation-iteration-count:1 !important;}
}

/* ---------- header ---------- */
header{
  position:sticky; top:0; z-index:50; background:rgba(241,243,240,0.88);
  backdrop-filter:blur(10px); border-bottom:1px solid transparent; transition:border-color 0.3s;
}
header.scrolled{border-bottom-color:var(--line);}
.nav{display:flex; align-items:center; justify-content:space-between; padding:18px 0;}
.brand{font-family:'Archivo',sans-serif; font-weight:800; font-size:1.05rem; text-decoration:none; display:flex; align-items:center; gap:8px;}
.brand .dot{width:9px; height:9px; background:var(--rust); border-radius:50%; display:inline-block;}
nav.links{display:flex; gap:28px; font-size:0.9rem; font-weight:500;}
nav.links a{text-decoration:none; color:var(--ink-muted); transition:color 0.2s;}
nav.links a:hover{color:var(--ink);}
.btn{
  display:inline-flex; align-items:center; gap:8px; font-family:'Inter',sans-serif; font-weight:600;
  font-size:0.88rem; padding:11px 20px; border-radius:5px; text-decoration:none; border:1.5px solid transparent;
  cursor:pointer; transition:transform 0.15s ease, box-shadow 0.15s ease;
}
.btn:hover{transform:translateY(-1px);}
.btn-primary{background:var(--ink); color:white;}
.btn-primary:hover{box-shadow:0 6px 16px rgba(20,32,30,0.25);}
.btn-outline{border-color:var(--ink); color:var(--ink);}
.btn-outline:hover{background:var(--ink); color:white;}

/* ---------- hero ---------- */
.hero{padding:60px 0 40px;}
.hero-grid{display:grid; grid-template-columns:1.05fr 0.95fr; gap:40px; align-items:center;}
.hero h1{font-size:3.4rem; line-height:1.03;}
.hero h1 span{color:var(--teal);}
.hero .lede{font-size:1.12rem; color:var(--ink-muted); margin:20px 0 30px; max-width:480px;}
.hero .cta-row{display:flex; gap:14px; flex-wrap:wrap;}
.stat-strip{display:flex; gap:36px; margin-top:52px; flex-wrap:wrap;}
.stat-strip .stat b{display:block; font-family:'Archivo',sans-serif; font-weight:800; font-size:1.7rem;}
.stat-strip .stat span{font-size:0.78rem; color:var(--ink-muted); font-family:'IBM Plex Mono',monospace;}

.network-card{background:var(--surface); border:1px solid var(--line); border-radius:12px; padding:18px; position:relative;}
.network-card .cap{display:flex; justify-content:space-between; align-items:center; margin-bottom:6px; padding:0 4px;}
.network-card .cap .tag{font-family:'IBM Plex Mono',monospace; font-size:0.68rem; color:var(--ink-faint); letter-spacing:0.04em;}
.network-card .cap .live{font-family:'IBM Plex Mono',monospace; font-size:0.68rem; color:var(--teal); display:flex; align-items:center; gap:5px;}
.network-card .cap .live::before{content:""; width:6px; height:6px; border-radius:50%; background:var(--teal); animation:blink 1.6s infinite;}
@keyframes blink{50%{opacity:0.25;}}

.edge{stroke:var(--teal); stroke-width:1.6; fill:none; opacity:0.55; stroke-dasharray:640; stroke-dashoffset:640; animation:draw 1.6s ease forwards;}
.node-dot{fill:var(--rust); stroke:var(--surface); stroke-width:2.5; opacity:0; animation:popin 0.35s ease forwards;}
.node-label{font-family:'IBM Plex Mono',monospace; font-size:9.5px; fill:var(--ink-muted); opacity:0; animation:popin 0.35s ease forwards;}
.node-featured{fill:var(--ink);}
@keyframes draw{to{stroke-dashoffset:0;}}
@keyframes popin{to{opacity:1;}}

/* ---------- about ---------- */
.about-grid{display:grid; grid-template-columns:1.3fr 1fr; gap:56px;}
.about-grid p{color:var(--ink-muted); margin:0 0 16px; font-size:1.02rem;}
.about-grid p strong{color:var(--ink); font-weight:600;}
.fact-list{border-top:1px solid var(--line);}
.fact-list .row{display:flex; justify-content:space-between; padding:14px 0; border-bottom:1px solid var(--line); font-size:0.92rem; gap:12px;}
.fact-list .row .k{color:var(--ink-faint); font-family:'IBM Plex Mono',monospace; font-size:0.76rem; text-transform:uppercase; letter-spacing:0.04em; white-space:nowrap;}
.fact-list .row .v{font-weight:600; text-align:right;}

/* ---------- skills ---------- */
.skills-grid{display:grid; grid-template-columns:repeat(4,1fr); gap:16px;}
.skill-card{background:var(--surface); border:1px solid var(--line); border-radius:var(--radius); padding:22px 20px;}
.skill-card .icon{font-family:'IBM Plex Mono',monospace; font-size:0.7rem; color:var(--teal); margin-bottom:10px;}
.skill-card h4{font-size:1rem; margin-bottom:12px;}
.skill-card ul{list-style:none; margin:0; padding:0; font-size:0.87rem; color:var(--ink-muted);}
.skill-card li{padding:4px 0; border-top:1px dashed var(--line);}
.skill-card li:first-child{border-top:none;}

/* ---------- projects ---------- */
.project{
  background:var(--surface); border:1px solid var(--line); border-radius:12px;
  margin-bottom:22px; overflow:hidden;
}
.project-head{
  display:flex; justify-content:space-between; align-items:flex-start; gap:20px;
  padding:26px 28px 0;
}
.project-code{font-family:'IBM Plex Mono',monospace; font-size:0.72rem; color:var(--ink-faint); letter-spacing:0.05em; margin-bottom:8px; display:block;}
.project h3{font-size:1.3rem; margin-bottom:8px;}
.project .desc{color:var(--ink-muted); font-size:0.95rem; max-width:640px;}
.status-badge{
  font-family:'IBM Plex Mono',monospace; font-size:0.68rem; letter-spacing:0.05em; padding:4px 10px;
  border-radius:20px; white-space:nowrap; height:fit-content; border:1px solid var(--teal); color:var(--teal);
}
.project-body{padding:18px 28px 26px; display:flex; justify-content:space-between; align-items:flex-end; flex-wrap:wrap; gap:16px;}
.tag-row{display:flex; gap:7px; flex-wrap:wrap;}
.tech-tag{
  font-family:'IBM Plex Mono',monospace; font-size:0.7rem; background:var(--teal-dim); color:var(--teal);
  padding:4px 9px; border-radius:4px;
}
.metric-block{text-align:right;}
.metric-block .num{font-family:'Archivo',sans-serif; font-weight:800; font-size:1.5rem; color:var(--rust); line-height:1;}
.metric-block .lbl{font-size:0.72rem; color:var(--ink-faint); font-family:'IBM Plex Mono',monospace; margin-top:3px;}
.project-links{padding:14px 28px; border-top:1px solid var(--line); display:flex; gap:22px; background:#FAFBF9;}
.project-links a{font-size:0.85rem; font-weight:600; text-decoration:none; color:var(--ink); display:flex; align-items:center; gap:6px;}
.project-links a:hover{color:var(--teal);}
.project-links a .arrow{transition:transform 0.15s;}
.project-links a:hover .arrow{transform:translateX(3px);}

/* ---------- education ---------- */
.edu-grid{display:grid; grid-template-columns:1fr 1fr; gap:20px;}
.edu-card{background:var(--surface); border:1px solid var(--line); border-radius:var(--radius); padding:22px 24px;}
.edu-card .tag{font-family:'IBM Plex Mono',monospace; font-size:0.7rem; color:var(--teal); text-transform:uppercase; letter-spacing:0.05em;}
.edu-card h4{margin-top:8px; font-size:1.05rem;}
.edu-card p{margin:6px 0 0; color:var(--ink-muted); font-size:0.9rem;}
.cert-list{display:flex; flex-direction:column; gap:0;}
.cert-list .cert{display:flex; justify-content:space-between; padding:13px 0; border-bottom:1px solid var(--line); font-size:0.92rem;}
.cert-list .cert:last-child{border-bottom:none;}
.cert-list .cert .name{font-weight:600;}
.cert-list .cert .meta{color:var(--ink-faint); font-size:0.78rem; font-family:'IBM Plex Mono',monospace;}

/* ---------- contact ---------- */
.contact-box{
  background:var(--ink); color:var(--bg); border-radius:16px; padding:56px; text-align:center;
  position:relative; overflow:hidden;
}
.contact-box h2{color:white; font-size:2.1rem;}
.contact-box p{color:#B9C4BE; margin:14px auto 30px; max-width:460px;}
.contact-links{display:flex; gap:16px; justify-content:center; flex-wrap:wrap;}
.contact-box .btn-primary{background:var(--rust);}
.contact-box .btn-outline{border-color:#4A584F; color:white;}
.contact-box .btn-outline:hover{background:white; color:var(--ink); border-color:white;}

footer{padding:34px 0; text-align:center; color:var(--ink-faint); font-size:0.82rem; font-family:'IBM Plex Mono',monospace;}
footer a{color:var(--ink-faint);}

@media (max-width:880px){
  .hero-grid{grid-template-columns:1fr;}
  .hero h1{font-size:2.5rem;}
  .about-grid{grid-template-columns:1fr;}
  .skills-grid{grid-template-columns:repeat(2,1fr);}
  .edu-grid{grid-template-columns:1fr;}
  nav.links{display:none;}
  .contact-box{padding:36px 22px;}
  .project-head{flex-direction:column;}
  .project-body{align-items:flex-start;}
  .metric-block{text-align:left;}
}
</style>
</head>
<body>

<header id="siteHeader">
  <div class="wrap nav">
    <a href="#top" class="brand"><span class="dot"></span>THARUN</a>
    <nav class="links">
      <a href="#about">Overview</a>
      <a href="#skills">Skills</a>
      <a href="#projects">Projects</a>
      <a href="#education">Education</a>
    </nav>
    <a href="#contact" class="btn btn-primary">Get in touch</a>
  </div>
</header>

<main id="top">

<!-- ============ HERO ============ -->
<section class="hero">
  <div class="wrap hero-grid">
    <div>
      <div class="eyebrow">Supply Chain Data Analytics</div>
      <h1>Tharun</h1>
      <h1><span>Turning shipment data<br>into network decisions</span></h1>
      <p class="lede">Data Analyst with a background running an actual hub floor before moving into analytics — now building network models, SQL pipelines, and BI dashboards for supply chain decisions, in Python, SQL, Power BI, and Tableau.</p>
      <div class="cta-row">
        <a href="#projects" class="btn btn-primary">View case studies →</a>
        <a href="#contact" class="btn btn-outline">Get in touch</a>
      </div>
      <div class="stat-strip">
        <div class="stat"><b>4</b><span>CASE STUDIES</span></div>
        <div class="stat"><b>190K+</b><span>RECORDS ANALYZED</span></div>
        <div class="stat"><b>8.9%</b><span>COST REDUCTION MODELED</span></div>
      </div>
    </div>

    <div class="network-card reveal">
      <div class="cap">
        <span class="tag">FIG. 01 — OPTIMIZED HUB NETWORK</span>
        <span class="live">LIVE MODEL</span>
      </div>
      <svg viewBox="0 0 480 500" style="width:100%;height:auto;">
        <path class="edge" style="animation-delay:.1s" d="M129.6,85.3 L122.8,40"/>
        <path class="edge" style="animation-delay:.2s" d="M129.6,85.3 L211.1,126.7"/>
        <path class="edge" style="animation-delay:.3s" d="M40,300.1 L171.7,254"/>
        <path class="edge" style="animation-delay:.4s" d="M40,300.1 L159,337.9"/>
        <path class="edge" style="animation-delay:.5s" d="M140,436.4 L126.5,480"/>
        <path class="edge" style="animation-delay:.6s" d="M140,436.4 L159,337.9"/>
        <path class="edge" style="animation-delay:.7s" d="M368.5,222.1 L440,142.4"/>
        <path class="edge" style="animation-delay:.8s" d="M368.5,222.1 L171.7,254"/>
        <path class="edge" style="animation-delay:.9s" d="M159,337.9 L171.7,254"/>
        <path class="edge" style="animation-delay:1s" d="M211.1,126.7 L122.8,40"/>

        <g>
          <circle class="node-dot node-featured" style="animation-delay:1.2s" cx="129.6" cy="85.3" r="7"/>
          <text class="node-label" style="animation-delay:1.3s" x="139.6" y="82">DELHI</text>

          <circle class="node-dot" style="animation-delay:1.25s" cx="40" cy="300.1" r="6"/>
          <text class="node-label" style="animation-delay:1.35s" x="10" y="317">MUMBAI</text>

          <circle class="node-dot node-featured" style="animation-delay:1.3s" cx="140" cy="436.4" r="7"/>
          <text class="node-label" style="animation-delay:1.4s" x="150" y="433">BANGALORE</text>

          <circle class="node-dot" style="animation-delay:1.35s" cx="368.5" cy="222.1" r="6"/>
          <text class="node-label" style="animation-delay:1.45s" x="378.5" y="219">KOLKATA</text>

          <circle class="node-dot" style="animation-delay:1.4s" cx="159" cy="337.9" r="6"/>
          <text class="node-label" style="animation-delay:1.5s" x="169" y="335">HYDERABAD</text>

          <circle class="node-dot" style="animation-delay:1.45s" cx="211.1" cy="126.7" r="6"/>
          <text class="node-label" style="animation-delay:1.55s" x="221.1" y="124">LUCKNOW</text>

          <circle class="node-dot" style="animation-delay:1.5s" cx="171.7" cy="254" r="6"/>
          <text class="node-label" style="animation-delay:1.6s" x="181.7" y="251">NAGPUR</text>

          <circle class="node-dot" style="animation-delay:1.55s" cx="126.5" cy="480" r="6"/>
          <text class="node-label" style="animation-delay:1.65s" x="90" y="478">COIMBATORE</text>

          <circle class="node-dot" style="animation-delay:1.6s" cx="440" cy="142.4" r="6"/>
          <text class="node-label" style="animation-delay:1.7s" x="410" y="130">GUWAHATI</text>

          <circle class="node-dot" style="animation-delay:1.65s" cx="122.8" cy="40" r="6"/>
          <text class="node-label" style="animation-delay:1.75s" x="132.8" y="37">CHANDIGARH</text>
        </g>
      </svg>
      <div class="cap" style="margin-top:2px;">
        <span class="tag">10 HUBS · 50 DEMAND POINTS · MILP-SOLVED</span>
      </div>
    </div>
  </div>
</section>

<!-- ============ ABOUT ============ -->
<section class="section" id="about">
  <div class="wrap about-grid">
    <div class="reveal">
      <div class="eyebrow">Overview</div>
      <h2>From the hub floor to the data model</h2>
      <p style="margin-top:20px;">Tharun works in Supply Chain Solutions at <strong>Delhivery</strong>, India's logistics network, as a Data Analyst — a role he moved into after first running one as a <strong>Hub Operations Manager</strong>. That sequence matters: the network models and dashboards below aren't built from the outside looking in, they're built by someone who has stood on the hub floor the data is describing.</p>
      <p>He designs supply chain network architectures for a living — <strong>30+ built to date</strong> — including a geo-clustering model that cut a client's transportation costs by roughly <strong>10%</strong> in production. The four case studies on this page apply the same toolkit — MILP optimization, SQL, Python forecasting, BI dashboards — to a fictional company end-to-end, so the full method is visible, not just the result.</p>
      <p>His academic background is Metallurgical and Materials Engineering (NIT Tiruchirappalli), including research applying a CNN-based Variational Autoencoder to generate synthetic polycrystalline microstructures — an early, unusual rep in the same muscle these projects use now: modeling messy real-world systems computationally.</p>
    </div>
    <div class="reveal">
      <div class="fact-list mono">
        <div class="row"><span class="k">Current Role</span><span class="v">Data Analyst, Supply Chain Solutions</span></div>
        <div class="row"><span class="k">Company</span><span class="v">Delhivery Ltd.</span></div>
        <div class="row"><span class="k">Prior Role</span><span class="v">Hub Operations Manager</span></div>
        <div class="row"><span class="k">Core Stack</span><span class="v">Python · SQL · Power BI · Tableau</span></div>
        <div class="row"><span class="k">Optimization</span><span class="v">PuLP (LP/MILP) · Excel Solver</span></div>
        <div class="row"><span class="k">Education</span><span class="v">B.Tech, NIT Tiruchirappalli</span></div>
      </div>
    </div>
  </div>
</section>

<!-- ============ SKILLS ============ -->
<section class="section" id="skills" style="background:var(--surface); border-top:1px solid var(--line); border-bottom:1px solid var(--line);">
  <div class="wrap">
    <div class="section-head reveal">
      <div class="eyebrow">Capabilities</div>
      <h2>The toolkit behind every case study</h2>
      <p>Every skill listed here is used in at least one of the projects below — nothing here is a resume keyword without a working example attached to it.</p>
    </div>
    <div class="skills-grid">
      <div class="skill-card reveal">
        <div class="icon">01 · LANGUAGES</div>
        <h4>Python & Statistical Tooling</h4>
        <ul>
          <li>Pandas, NumPy</li>
          <li>Matplotlib</li>
          <li>PuLP (LP / MILP)</li>
          <li>Forecasting libraries</li>
          <li>RStudio</li>
        </ul>
      </div>
      <div class="skill-card reveal">
        <div class="icon">02 · DATA</div>
        <h4>SQL & Databases</h4>
        <ul>
          <li>Joins & subqueries</li>
          <li>Window functions</li>
          <li>CTEs</li>
          <li>Schema design</li>
          <li>SQLite / relational DBs</li>
        </ul>
      </div>
      <div class="skill-card reveal">
        <div class="icon">03 · BI & VISUALIZATION</div>
        <h4>Dashboards & Reporting</h4>
        <ul>
          <li>Power BI (DAX, data modeling)</li>
          <li>Tableau (calculated fields)</li>
          <li>Looker Studio</li>
          <li>Advanced Excel</li>
        </ul>
      </div>
      <div class="skill-card reveal">
        <div class="icon">04 · OPERATIONS RESEARCH</div>
        <h4>Optimization & Modeling</h4>
        <ul>
          <li>Facility location (MILP)</li>
          <li>Geo-clustering</li>
          <li>Safety stock modeling</li>
          <li>ABC / XYZ classification</li>
          <li>Excel Solver</li>
        </ul>
      </div>
    </div>
  </div>
</section>

<!-- ============ PROJECTS ============ -->
<section class="section" id="projects">
  <div class="wrap">
    <div class="section-head reveal">
      <div class="eyebrow">Case Files</div>
      <h2>Four projects, one fictional network</h2>
      <p>The first three case studies analyze <strong>Vayu Logistics</strong>, a fictional Indian logistics company built for this portfolio — synthetic data, genuinely computed results, real methodology. The fourth is a standalone forecasting project on public e-commerce data. Every repo ships with its full source, SQL, and a README written for someone who wants to actually read the approach.</p>
    </div>

    <div class="project reveal">
      <div class="project-head">
        <div>
          <span class="project-code">CASE-01 · NETWORK DESIGN</span>
          <h3>Distribution Network & Facility Location Optimization</h3>
          <p class="desc">A MILP model (PuLP) decides which of 15 candidate hubs to open and how to route 50 demand points between them — then proves the "obvious" 6-hub answer is actually infeasible once capacity is respected.</p>
        </div>
        <span class="status-badge">SOLVED · MILP</span>
      </div>
      <div class="project-body">
        <div class="tag-row">
          <span class="tech-tag">Python</span><span class="tech-tag">PuLP</span><span class="tech-tag">SQL</span><span class="tech-tag">Matplotlib</span>
        </div>
        <div class="metric-block">
          <div class="num">8.9%</div>
          <div class="lbl">COST REDUCTION VS. REALISTIC BASELINE</div>
        </div>
      </div>
      <div class="project-links">
        <a href="https://github.com/yourusername/vayu-network-optimization" target="_blank" rel="noopener">GitHub Repo <span class="arrow">→</span></a>
      </div>
    </div>

    <div class="project reveal">
      <div class="project-head">
        <div>
          <span class="project-code">CASE-02 · OPERATIONS ANALYTICS</span>
          <h3>Last-Mile Delivery SLA & Performance Analytics</h3>
          <p class="desc">179K shipments across 10 hubs and 12 months, analyzed in SQL to find that two hubs aren't having a bad month — they're chronically missing target, one of them for all 12 months straight.</p>
        </div>
        <span class="status-badge">LIVE DASHBOARD</span>
      </div>
      <div class="project-body">
        <div class="tag-row">
          <span class="tech-tag">SQL</span><span class="tech-tag">Power BI</span><span class="tech-tag">Window Functions</span><span class="tech-tag">Plotly</span>
        </div>
        <div class="metric-block">
          <div class="num">86.5%</div>
          <div class="lbl">OTIF ACROSS 179,197 SHIPMENTS</div>
        </div>
      </div>
      <div class="project-links">
        <a href="https://github.com/yourusername/vayu-lastmile-sla-analytics" target="_blank" rel="noopener">GitHub Repo <span class="arrow">→</span></a>
        <a href="https://yourusername.github.io/vayu-lastmile-sla-analytics/dashboard/" target="_blank" rel="noopener">Live Dashboard <span class="arrow">→</span></a>
      </div>
    </div>

    <div class="project reveal">
      <div class="project-head">
        <div>
          <span class="project-code">CASE-03 · COST ANALYTICS</span>
          <h3>Freight & Carrier Performance Analytics</h3>
          <p class="desc">Scorecards 8 carriers across road, rail, and air on cost-per-kg vs. reliability, then simulates same-mode carrier swaps to find real, low-risk savings — deliberately excluding unfair cross-mode comparisons.</p>
        </div>
        <span class="status-badge">LIVE DASHBOARD</span>
      </div>
      <div class="project-body">
        <div class="tag-row">
          <span class="tech-tag">Python</span><span class="tech-tag">Tableau</span><span class="tech-tag">SQL</span><span class="tech-tag">Pandas</span>
        </div>
        <div class="metric-block">
          <div class="num">₹14.3L</div>
          <div class="lbl">ANNUAL SAVINGS IDENTIFIED</div>
        </div>
      </div>
      <div class="project-links">
        <a href="https://github.com/yourusername/vayu-freight-carrier-analytics" target="_blank" rel="noopener">GitHub Repo <span class="arrow">→</span></a>
        <a href="https://yourusername.github.io/vayu-freight-carrier-analytics/dashboard/" target="_blank" rel="noopener">Live Dashboard <span class="arrow">→</span></a>
      </div>
    </div>

    <div class="project reveal">
      <div class="project-head">
        <div>
          <span class="project-code">CASE-04 · DEMAND PLANNING</span>
          <h3>Demand Forecasting & Safety Stock Engine</h3>
          <p class="desc">A five-model forecasting ensemble (Moving Average, Holt-Winters, ARIMA, Prophet, and a blended ensemble) on the Brazilian Olist e-commerce dataset, paired with ABC/XYZ classification and safety stock modeling.</p>
        </div>
        <span class="status-badge">EARLIER PROJECT</span>
      </div>
      <div class="project-body">
        <div class="tag-row">
          <span class="tech-tag">Python</span><span class="tech-tag">Prophet</span><span class="tech-tag">ARIMA</span><span class="tech-tag">Holt-Winters</span>
        </div>
        <div class="metric-block">
          <div class="num">5</div>
          <div class="lbl">FORECASTING MODELS ENSEMBLED</div>
        </div>
      </div>
      <div class="project-links">
        <a href="https://github.com/yourusername/demand-planning-olist" target="_blank" rel="noopener">GitHub Repo <span class="arrow">→</span></a>
      </div>
    </div>

  </div>
</section>

<!-- ============ EDUCATION ============ -->
<section class="section" id="education" style="background:var(--surface); border-top:1px solid var(--line); border-bottom:1px solid var(--line);">
  <div class="wrap">
    <div class="section-head reveal">
      <div class="eyebrow">Education & Certifications</div>
      <h2>Formal training, kept current</h2>
    </div>
    <div class="edu-grid">
      <div class="edu-card reveal">
        <span class="tag">DEGREE</span>
        <h4>B.Tech, Metallurgical and Materials Engineering</h4>
        <p>National Institute of Technology, Tiruchirappalli</p>
        <p>Research: CNN-based Variational Autoencoder for synthetic polycrystalline microstructure generation</p>
      </div>
      <div class="edu-card reveal">
        <span class="tag">CERTIFICATIONS</span>
        <div class="cert-list" style="margin-top:10px;">
          <div class="cert"><span class="name">CSCMP Supply Chain Foundations</span><span class="meta">DEMAND PLANNING</span></div>
          <div class="cert"><span class="name">Google Business Intelligence</span><span class="meta">CERTIFICATE</span></div>
          <div class="cert"><span class="name">SQL (Intermediate)</span><span class="meta">CERTIFICATE</span></div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ============ CONTACT ============ -->
<section class="section" id="contact">
  <div class="wrap">
    <div class="contact-box reveal">
      <div class="eyebrow" style="color:#8FBFB0;">Get in touch</div>
      <h2>Open to Data Analyst & Supply Chain Analyst roles</h2>
      <p>Looking for someone who's worked both sides of the supply chain — the floor and the model? Let's talk.</p>
      <div class="contact-links">
        <a href="mailto:your.email@example.com" class="btn btn-primary">Email me →</a>
        <a href="https://linkedin.com/in/yourusername" target="_blank" rel="noopener" class="btn btn-outline">LinkedIn</a>
        <a href="https://github.com/yourusername" target="_blank" rel="noopener" class="btn btn-outline">GitHub</a>
      </div>
    </div>
  </div>
</section>

</main>

<footer>
  <div class="wrap">Built and maintained by Tharun · © 2026 · <a href="#top">Back to top</a></div>
</footer>

<script>
const revealEls = document.querySelectorAll('.reveal');
const io = new IntersectionObserver((entries) => {
  entries.forEach(e => { if (e.isIntersecting) { e.target.classList.add('visible'); io.unobserve(e.target); } });
}, { threshold: 0.12 });
revealEls.forEach(el => io.observe(el));

const header = document.getElementById('siteHeader');
window.addEventListener('scroll', () => {
  header.classList.toggle('scrolled', window.scrollY > 8);
});
</script>
</body>
</html>
