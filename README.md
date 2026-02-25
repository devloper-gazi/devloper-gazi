<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>devloper-gazi · GitHub Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=JetBrains+Mono:wght@300;400;500&family=Instrument+Serif:ital@0;1&display=swap" rel="stylesheet"/>
<style>
  :root {
    --bg: #080c10;
    --surface: #0d1117;
    --border: #1e2a38;
    --accent: #00d4ff;
    --accent2: #7b5ea7;
    --gold: #c9a84c;
    --text: #c9d1d9;
    --muted: #586069;
    --bright: #ffffff;
  }

  * { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'JetBrains Mono', monospace;
    min-height: 100vh;
    line-height: 1.6;
  }

  /* Noise grain overlay */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.04'/%3E%3C/svg%3E");
    pointer-events: none;
    z-index: 0;
    opacity: 0.6;
  }

  .container {
    max-width: 860px;
    margin: 0 auto;
    padding: 48px 24px;
    position: relative;
    z-index: 1;
  }

  /* ── HEADER ── */
  .header {
    border: 1px solid var(--border);
    background: linear-gradient(135deg, #0d1117 0%, #0f1923 100%);
    padding: 48px 48px 40px;
    margin-bottom: 2px;
    position: relative;
    overflow: hidden;
    animation: fadeUp 0.7s ease both;
  }

  .header::before {
    content: '';
    position: absolute;
    top: -80px; right: -80px;
    width: 320px; height: 320px;
    background: radial-gradient(circle, rgba(0,212,255,0.07) 0%, transparent 70%);
    pointer-events: none;
  }

  .header::after {
    content: '';
    position: absolute;
    bottom: 0; left: 0; right: 0;
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--accent), transparent);
  }

  .eyebrow {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    font-weight: 400;
    letter-spacing: 0.2em;
    color: var(--accent);
    text-transform: uppercase;
    margin-bottom: 16px;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .eyebrow::before {
    content: '';
    display: inline-block;
    width: 24px;
    height: 1px;
    background: var(--accent);
  }

  .name {
    font-family: 'Syne', sans-serif;
    font-size: clamp(2.4rem, 5vw, 3.8rem);
    font-weight: 800;
    line-height: 1;
    color: var(--bright);
    letter-spacing: -0.02em;
    margin-bottom: 8px;
  }

  .name span {
    color: var(--accent);
  }

  .tagline {
    font-family: 'Instrument Serif', serif;
    font-style: italic;
    font-size: 1.15rem;
    color: var(--muted);
    margin-bottom: 28px;
  }

  .badges {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
  }

  .badge {
    font-size: 10px;
    font-weight: 500;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    padding: 4px 12px;
    border: 1px solid;
    border-radius: 2px;
    transition: all 0.2s;
  }

  .badge-cyan { border-color: var(--accent); color: var(--accent); }
  .badge-purple { border-color: var(--accent2); color: var(--accent2); }
  .badge-gold { border-color: var(--gold); color: var(--gold); }
  .badge:hover { opacity: 0.7; }

  /* ── STATS GRID ── */
  .stats-row {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 2px;
    margin-bottom: 2px;
    animation: fadeUp 0.7s 0.15s ease both;
  }

  .stat-card {
    background: var(--surface);
    border: 1px solid var(--border);
    padding: 20px 16px;
    text-align: center;
    position: relative;
    overflow: hidden;
    transition: border-color 0.3s;
  }

  .stat-card:hover { border-color: var(--accent); }

  .stat-card::before {
    content: '';
    position: absolute;
    bottom: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--accent2), var(--accent));
    transform: scaleX(0);
    transform-origin: left;
    transition: transform 0.3s;
  }

  .stat-card:hover::before { transform: scaleX(1); }

  .stat-num {
    font-family: 'Syne', sans-serif;
    font-size: 2rem;
    font-weight: 700;
    color: var(--bright);
    display: block;
    line-height: 1;
    margin-bottom: 4px;
  }

  .stat-num span {
    font-size: 1rem;
    color: var(--accent);
  }

  .stat-label {
    font-size: 9px;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: var(--muted);
  }

  /* ── TWO COLUMN ── */
  .two-col {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 2px;
    margin-bottom: 2px;
    animation: fadeUp 0.7s 0.3s ease both;
  }

  /* ── SECTION CARD ── */
  .card {
    background: var(--surface);
    border: 1px solid var(--border);
    padding: 28px 28px;
  }

  .section-label {
    font-size: 9px;
    font-weight: 500;
    letter-spacing: 0.25em;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 16px;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .section-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  .section-title {
    font-family: 'Syne', sans-serif;
    font-size: 1rem;
    font-weight: 700;
    color: var(--bright);
    margin-bottom: 12px;
  }

  p {
    font-size: 12px;
    line-height: 1.8;
    color: var(--muted);
  }

  /* ── SKILLS ── */
  .skill-group { margin-bottom: 16px; }
  .skill-group:last-child { margin-bottom: 0; }

  .skill-group-label {
    font-size: 9px;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--accent2);
    margin-bottom: 8px;
  }

  .skill-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
  }

  .skill-tag {
    font-size: 10px;
    font-weight: 400;
    color: var(--text);
    background: #111823;
    border: 1px solid var(--border);
    padding: 3px 10px;
    border-radius: 2px;
    transition: all 0.2s;
  }

  .skill-tag:hover {
    border-color: var(--accent);
    color: var(--accent);
  }

  /* ── PROJECTS ── */
  .projects {
    animation: fadeUp 0.7s 0.45s ease both;
  }

  .project-row {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 2px;
    margin-bottom: 2px;
  }

  .project-card {
    background: var(--surface);
    border: 1px solid var(--border);
    padding: 20px 24px;
    position: relative;
    overflow: hidden;
    transition: border-color 0.3s, transform 0.2s;
    cursor: pointer;
    text-decoration: none;
    display: block;
  }

  .project-card:hover {
    border-color: rgba(0, 212, 255, 0.4);
    transform: translateY(-1px);
  }

  .project-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0;
    width: 3px;
    height: 100%;
    background: linear-gradient(180deg, var(--accent), var(--accent2));
    opacity: 0;
    transition: opacity 0.3s;
  }

  .project-card:hover::before { opacity: 1; }

  .project-title {
    font-family: 'Syne', sans-serif;
    font-size: 0.9rem;
    font-weight: 700;
    color: var(--bright);
    margin-bottom: 6px;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .project-title::after {
    content: '↗';
    font-size: 12px;
    color: var(--muted);
    margin-left: auto;
  }

  .project-desc {
    font-size: 11px;
    color: var(--muted);
    line-height: 1.6;
  }

  .project-tag {
    display: inline-block;
    font-size: 9px;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    padding: 2px 8px;
    border-radius: 2px;
    margin-top: 10px;
    border: 1px solid;
  }

  .tag-quantum { color: var(--accent); border-color: rgba(0,212,255,0.3); }
  .tag-ai { color: var(--accent2); border-color: rgba(123,94,167,0.3); }
  .tag-finance { color: var(--gold); border-color: rgba(201,168,76,0.3); }

  /* ── PUBLICATION ── */
  .publication {
    animation: fadeUp 0.7s 0.6s ease both;
  }

  .pub-card {
    background: var(--surface);
    border: 1px solid var(--border);
    padding: 28px;
    position: relative;
    overflow: hidden;
  }

  .pub-card::before {
    content: '';
    position: absolute;
    inset: 0;
    background: linear-gradient(135deg, rgba(0,212,255,0.03), transparent 60%);
  }

  .pub-year {
    font-size: 10px;
    letter-spacing: 0.2em;
    color: var(--gold);
    margin-bottom: 8px;
  }

  .pub-title {
    font-family: 'Instrument Serif', serif;
    font-style: italic;
    font-size: 1.3rem;
    color: var(--bright);
    line-height: 1.3;
    margin-bottom: 10px;
  }

  /* ── GITHUB STATS ── */
  .stats-section {
    animation: fadeUp 0.7s 0.75s ease both;
  }

  .github-stats-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 2px;
  }

  .github-stat-card {
    background: var(--surface);
    border: 1px solid var(--border);
    padding: 24px;
    text-align: center;
  }

  .lang-bars { width: 100%; }

  .lang-row {
    display: flex;
    align-items: center;
    gap: 10px;
    margin-bottom: 10px;
    font-size: 11px;
  }

  .lang-name { width: 80px; color: var(--text); text-align: right; }
  .lang-bar-wrap { flex: 1; height: 3px; background: var(--border); border-radius: 2px; overflow: hidden; }
  .lang-bar { height: 100%; border-radius: 2px; }
  .lang-pct { width: 36px; color: var(--muted); text-align: left; }

  /* ── FOOTER QUOTE ── */
  .footer {
    background: var(--surface);
    border: 1px solid var(--border);
    padding: 32px 40px;
    text-align: center;
    margin-top: 2px;
    animation: fadeUp 0.7s 0.9s ease both;
    position: relative;
    overflow: hidden;
  }

  .footer::before {
    content: '"';
    position: absolute;
    top: -20px; left: 20px;
    font-family: 'Instrument Serif', serif;
    font-size: 180px;
    color: rgba(0,212,255,0.04);
    line-height: 1;
    pointer-events: none;
  }

  .quote-text {
    font-family: 'Instrument Serif', serif;
    font-style: italic;
    font-size: 1.1rem;
    color: var(--text);
    max-width: 560px;
    margin: 0 auto 12px;
    line-height: 1.6;
  }

  .quote-attr {
    font-size: 10px;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--muted);
  }

  /* ── CONTRIBUTION HEAT ── */
  .heat-grid {
    display: grid;
    grid-template-columns: repeat(52, 1fr);
    gap: 2px;
  }

  .heat-cell {
    width: 100%;
    aspect-ratio: 1;
    border-radius: 2px;
  }

  /* ── ANIMATIONS ── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(16px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  @media (max-width: 640px) {
    .stats-row { grid-template-columns: repeat(2, 1fr); }
    .two-col, .project-row, .github-stats-grid { grid-template-columns: 1fr; }
    .header { padding: 28px; }
  }
</style>
</head>
<body>
<div class="container">

  <!-- HEADER -->
  <div class="header">
    <div class="eyebrow">Research Profile · 2025</div>
    <div class="name">devloper-<span>gazi</span></div>
    <div class="tagline">Building the future, one algorithm at a time.</div>
    <div class="badges">
      <span class="badge badge-cyan">AI Researcher</span>
      <span class="badge badge-purple">Quantum Computing</span>
      <span class="badge badge-gold">Published Author</span>
      <span class="badge badge-cyan">Algorithmic Trading</span>
    </div>
  </div>

  <!-- STATS -->
  <div class="stats-row">
    <div class="stat-card">
      <span class="stat-num">4<span>+</span></span>
      <div class="stat-label">Public Projects</div>
    </div>
    <div class="stat-card">
      <span class="stat-num">5</span>
      <div class="stat-label">Languages</div>
    </div>
    <div class="stat-card">
      <span class="stat-num">1</span>
      <div class="stat-label">Publication</div>
    </div>
    <div class="stat-card">
      <span class="stat-num">3</span>
      <div class="stat-label">Research Areas</div>
    </div>
  </div>

  <!-- ABOUT + SKILLS -->
  <div class="two-col">
    <div class="card">
      <div class="section-label">About</div>
      <p>Research student at the intersection of theoretical physics and applied artificial intelligence. My work spans quantum computing simulations, multi-agent AI systems, and ethical frameworks for algorithmic trading.</p>
    </div>
    <div class="card">
      <div class="section-label">Technical Stack</div>
      <div class="skill-group">
        <div class="skill-group-label">Languages</div>
        <div class="skill-tags">
          <span class="skill-tag">Python</span>
          <span class="skill-tag">Rust</span>
          <span class="skill-tag">TypeScript</span>
          <span class="skill-tag">Go</span>
          <span class="skill-tag">C++</span>
        </div>
      </div>
      <div class="skill-group">
        <div class="skill-group-label">AI / ML</div>
        <div class="skill-tags">
          <span class="skill-tag">PyTorch</span>
          <span class="skill-tag">TensorFlow</span>
          <span class="skill-tag">Scikit-learn</span>
        </div>
      </div>
      <div class="skill-group">
        <div class="skill-group-label">Infrastructure</div>
        <div class="skill-tags">
          <span class="skill-tag">Docker</span>
          <span class="skill-tag">PostgreSQL</span>
          <span class="skill-tag">MongoDB</span>
          <span class="skill-tag">Linux</span>
        </div>
      </div>
    </div>
  </div>

  <!-- PROJECTS -->
  <div class="projects">
    <div class="project-row">
      <a class="project-card" href="https://github.com/devloper-gazi/QuantumBreaths1D">
        <div class="project-title">QuantumBreaths1D</div>
        <div class="project-desc">BEC quantum simulation framework. Models Bose-Einstein condensates via 1D Gross-Pitaevskii equations.</div>
        <span class="project-tag tag-quantum">Quantum</span>
      </a>
      <a class="project-card" href="https://github.com/devloper-gazi/Decentralized-Knowledge-Guardian">
        <div class="project-title">Decentralized Knowledge Guardian</div>
        <div class="project-desc">Distributed knowledge management system with resilient, peer-to-peer architecture.</div>
        <span class="project-tag tag-ai">AI Systems</span>
      </a>
    </div>
    <div class="project-row">
      <a class="project-card" href="https://github.com/devloper-gazi/Ethical-Foundations-of-AI-Trading-Systems">
        <div class="project-title">Ethical AI Trading Foundations</div>
        <div class="project-desc">Framework for responsible algorithmic trading — bias detection, transparency, auditability.</div>
        <span class="project-tag tag-finance">Finance</span>
      </a>
      <a class="project-card" href="https://github.com/devloper-gazi/Fx_trading_bot_v0.1">
        <div class="project-title">Fx Trading Bot v0.1</div>
        <div class="project-desc">Automated forex trading system with real-time signal processing and risk management.</div>
        <span class="project-tag tag-finance">Trading</span>
      </a>
    </div>
  </div>

  <!-- PUBLICATION -->
  <div class="publication">
    <div class="pub-card">
      <div class="section-label">Publication</div>
      <div class="pub-year">2025</div>
      <div class="pub-title">From Ether to Algorithms: The Lightborne Future of Information Systems</div>
      <p>Exploring photonic supersolids and next-generation computation paradigms. A theoretical examination of optical computing as the successor architecture to silicon-based systems.</p>
    </div>
  </div>

  <!-- GITHUB STATS MOCK -->
  <div class="stats-section">
    <div class="github-stats-grid">
      <div class="github-stat-card">
        <div class="section-label">Language Avg</div>
        <div class="lang-bars">
          <div class="lang-row">
            <span class="lang-name">Python</span>
            <div class="lang-bar-wrap"><div class="lang-bar" style="width:68%;background:linear-gradient(90deg,#00d4ff,#3b8fd6)"></div></div>
            <span class="lang-pct">68%</span>
          </div>
          <div class="lang-row">
            <span class="lang-name">Rust</span>
            <div class="lang-bar-wrap"><div class="lang-bar" style="width:12%;background:#ce422b"></div></div>
            <span class="lang-pct">12%</span>
          </div>
          <div class="lang-row">
            <span class="lang-name">TypeScript</span>
            <div class="lang-bar-wrap"><div class="lang-bar" style="width:10%;background:#3178c6"></div></div>
            <span class="lang-pct">10%</span>
          </div>
          <div class="lang-row">
            <span class="lang-name">Go</span>
            <div class="lang-bar-wrap"><div class="lang-bar" style="width:6%;background:#00acd7"></div></div>
            <span class="lang-pct">6%</span>
          </div>
          <div class="lang-row">
            <span class="lang-name">C++</span>
            <div class="lang-bar-wrap"><div class="lang-bar" style="width:4%;background:#7b5ea7"></div></div>
            <span class="lang-pct">4%</span>
          </div>
        </div>
      </div>
      <div class="github-stat-card">
        <div class="section-label">Current Research</div>
        <div class="skill-group" style="margin-bottom:12px">
          <div style="font-size:11px;color:var(--text);margin-bottom:6px;">Multi-Agent AI Systems</div>
          <div style="height:3px;background:var(--border);border-radius:2px;overflow:hidden">
            <div style="width:75%;height:100%;background:linear-gradient(90deg,var(--accent2),var(--accent));border-radius:2px"></div>
          </div>
        </div>
        <div class="skill-group" style="margin-bottom:12px">
          <div style="font-size:11px;color:var(--text);margin-bottom:6px;">Photonic Computing</div>
          <div style="height:3px;background:var(--border);border-radius:2px;overflow:hidden">
            <div style="width:60%;height:100%;background:linear-gradient(90deg,var(--accent2),var(--accent));border-radius:2px"></div>
          </div>
        </div>
        <div class="skill-group">
          <div style="font-size:11px;color:var(--text);margin-bottom:6px;">Ethical AI Trading Frameworks</div>
          <div style="height:3px;background:var(--border);border-radius:2px;overflow:hidden">
            <div style="width:50%;height:100%;background:linear-gradient(90deg,var(--accent2),var(--accent));border-radius:2px"></div>
          </div>
        </div>
      </div>
    </div>
  </div>

  <!-- FOOTER QUOTE -->
  <div class="footer">
    <div class="quote-text">"Sometimes it is the people no one can imagine anything of who do the things no one can imagine."</div>
    <div class="quote-attr">— Alan Turing</div>
  </div>

</div>
</body>
</html>
