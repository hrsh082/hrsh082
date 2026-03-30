<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Harsh Gajjar — GitHub Profile</title>
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@300;400;500;700&family=Syne:wght@400;700;800&display=swap" rel="stylesheet"/>
<style>
  :root {
    --bg: #080808;
    --surface: #0f0f0f;
    --surface2: #161616;
    --border: rgba(255,255,255,0.07);
    --border-hover: rgba(255,255,255,0.15);
    --text: #e8e8e8;
    --muted: #555;
    --muted2: #888;
    --accent: #e8e8e8;
    --green: #4ade80;
    --dim-green: rgba(74,222,128,0.15);
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'JetBrains Mono', monospace;
    font-size: 13px;
    line-height: 1.7;
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* Subtle grid bg */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(255,255,255,0.015) 1px, transparent 1px),
      linear-gradient(90deg, rgba(255,255,255,0.015) 1px, transparent 1px);
    background-size: 40px 40px;
    pointer-events: none;
    z-index: 0;
  }

  .wrap {
    max-width: 780px;
    margin: 0 auto;
    padding: 60px 32px 100px;
    position: relative;
    z-index: 1;
  }

  /* ── HEADER ── */
  .header {
    border: 1px solid var(--border);
    background: var(--surface);
    padding: 40px;
    margin-bottom: 20px;
    position: relative;
    overflow: hidden;
  }

  .header::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 1px;
    background: linear-gradient(90deg, transparent, rgba(255,255,255,0.2), transparent);
  }

  .header-top {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    margin-bottom: 28px;
  }

  .name {
    font-family: 'Syne', sans-serif;
    font-size: 42px;
    font-weight: 800;
    letter-spacing: -1.5px;
    color: #fff;
    line-height: 1;
  }

  .name span {
    color: var(--muted2);
    font-weight: 400;
  }

  .status-dot {
    display: flex;
    align-items: center;
    gap: 8px;
    font-size: 11px;
    color: var(--green);
    background: var(--dim-green);
    border: 1px solid rgba(74,222,128,0.2);
    padding: 6px 12px;
    letter-spacing: 0.05em;
  }

  .dot {
    width: 6px; height: 6px;
    background: var(--green);
    border-radius: 50%;
    animation: pulse 2s ease-in-out infinite;
  }

  @keyframes pulse {
    0%, 100% { opacity: 1; }
    50% { opacity: 0.3; }
  }

  .tagline {
    color: var(--muted2);
    font-size: 12px;
    letter-spacing: 0.03em;
    margin-bottom: 28px;
    max-width: 500px;
    line-height: 1.8;
  }

  .links {
    display: flex;
    gap: 6px;
    flex-wrap: wrap;
  }

  .link-chip {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    font-size: 11px;
    padding: 6px 14px;
    border: 1px solid var(--border);
    color: var(--muted2);
    text-decoration: none;
    transition: all 0.2s;
    letter-spacing: 0.04em;
  }

  .link-chip:hover {
    border-color: var(--border-hover);
    color: var(--text);
    background: var(--surface2);
  }

  .corner-tag {
    position: absolute;
    bottom: 14px; right: 16px;
    font-size: 10px;
    color: var(--muted);
    letter-spacing: 0.1em;
  }

  /* ── GRID ── */
  .grid-2 {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 20px;
    margin-bottom: 20px;
  }

  /* ── CARDS ── */
  .card {
    border: 1px solid var(--border);
    background: var(--surface);
    padding: 28px;
    position: relative;
  }

  .card-label {
    font-size: 10px;
    letter-spacing: 0.14em;
    color: var(--muted);
    text-transform: uppercase;
    margin-bottom: 18px;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .card-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  /* ── STACK ── */
  .stack-list {
    list-style: none;
    display: flex;
    flex-direction: column;
    gap: 10px;
  }

  .stack-item {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 8px 12px;
    border: 1px solid var(--border);
    background: var(--surface2);
    transition: border-color 0.2s;
  }

  .stack-item:hover { border-color: var(--border-hover); }

  .stack-name { color: var(--text); font-size: 12px; }
  .stack-bar-wrap { width: 80px; height: 2px; background: rgba(255,255,255,0.07); }
  .stack-bar { height: 100%; background: rgba(255,255,255,0.35); }

  /* ── PROJECTS ── */
  .project-list { display: flex; flex-direction: column; gap: 10px; }

  .project-item {
    padding: 14px 16px;
    border: 1px solid var(--border);
    background: var(--surface2);
    display: flex;
    align-items: center;
    justify-content: space-between;
    transition: border-color 0.2s, background 0.2s;
    cursor: pointer;
    text-decoration: none;
  }

  .project-item:hover {
    border-color: var(--border-hover);
    background: rgba(255,255,255,0.03);
  }

  .project-name {
    font-size: 13px;
    color: #fff;
    font-weight: 500;
    margin-bottom: 2px;
  }

  .project-desc {
    font-size: 11px;
    color: var(--muted2);
  }

  .project-arrow {
    font-size: 16px;
    color: var(--muted);
    transition: transform 0.2s, color 0.2s;
  }

  .project-item:hover .project-arrow {
    transform: translateX(3px);
    color: var(--text);
  }

  /* ── CURRENTLY ── */
  .doing-list { display: flex; flex-direction: column; gap: 8px; }

  .doing-item {
    display: flex;
    align-items: flex-start;
    gap: 10px;
    font-size: 12px;
    color: var(--muted2);
    padding: 6px 0;
    border-bottom: 1px solid var(--border);
  }

  .doing-item:last-child { border-bottom: none; }

  .doing-num {
    color: var(--muted);
    font-size: 10px;
    min-width: 18px;
    padding-top: 2px;
  }

  /* ── STATS ROW ── */
  .stats-row {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
    margin-bottom: 20px;
  }

  .stat-card {
    border: 1px solid var(--border);
    background: var(--surface);
    padding: 22px 24px;
    text-align: center;
  }

  .stat-img {
    width: 100%;
    filter: brightness(0.9) contrast(1.1);
    display: block;
  }

  /* ── QUOTE ── */
  .quote-block {
    border: 1px solid var(--border);
    background: var(--surface);
    padding: 32px 40px;
    position: relative;
    text-align: center;
  }

  .quote-mark {
    font-family: 'Syne', sans-serif;
    font-size: 72px;
    font-weight: 800;
    color: rgba(255,255,255,0.04);
    position: absolute;
    top: 0; left: 24px;
    line-height: 1;
  }

  .quote-text {
    font-size: 14px;
    color: var(--muted2);
    font-style: italic;
    letter-spacing: 0.02em;
    position: relative;
    z-index: 1;
  }

  .quote-text em { color: var(--text); font-style: normal; }

  /* ── GSOC BADGE ── */
  .gsoc-badge {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    font-size: 10px;
    letter-spacing: 0.1em;
    color: #fbbf24;
    background: rgba(251,191,36,0.08);
    border: 1px solid rgba(251,191,36,0.2);
    padding: 5px 12px;
    margin-top: 14px;
  }

  .gsoc-dot { width: 5px; height: 5px; background: #fbbf24; border-radius: 50%; }

  /* ── FADE IN ── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(16px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  .header    { animation: fadeUp 0.5s ease both 0.05s; }
  .grid-2    { animation: fadeUp 0.5s ease both 0.15s; }
  .stats-row { animation: fadeUp 0.5s ease both 0.25s; }
  .quote-block { animation: fadeUp 0.5s ease both 0.35s; }

  /* full-width card variant */
  .card-full {
    border: 1px solid var(--border);
    background: var(--surface);
    padding: 28px;
    margin-bottom: 20px;
    position: relative;
  }

  .card-full::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 1px;
    background: linear-gradient(90deg, transparent, rgba(255,255,255,0.1), transparent);
  }
</style>
</head>
<body>
<div class="wrap">

  <!-- HEADER -->
  <div class="header">
    <div class="header-top">
      <div>
        <div class="name">Harsh<span>.</span>Gajjar</div>
      </div>
      <div style="display:flex;flex-direction:column;align-items:flex-end;gap:8px;">
        <div class="status-dot"><span class="dot"></span>OPEN TO COLLABORATE</div>
        <div class="gsoc-badge"><span class="gsoc-dot"></span>GSoC 2026 CANDIDATE</div>
      </div>
    </div>

    <p class="tagline">
      Engineering student building clean, fast, and modern web apps.<br/>
      Focused on MERN, TypeScript, and open-source.
    </p>

    <div class="links">
      <a class="link-chip" href="https://www.linkedin.com/in/harsh-082-gajjar">↗ linkedin</a>
      <a class="link-chip" href="https://x.com/_hrsh_082">↗ twitter / x</a>
      <a class="link-chip" href="mailto:harshgajjar280@gmail.com">↗ email</a>
      <a class="link-chip" href="https://github.com/hrsh082">↗ github</a>
    </div>

    <div class="corner-tag">hrsh082</div>
  </div>

  <!-- STACK + PROJECTS -->
  <div class="grid-2">

    <!-- Stack -->
    <div class="card">
      <div class="card-label">tech stack</div>
      <ul class="stack-list">
        <li class="stack-item">
          <span class="stack-name">TypeScript</span>
          <div class="stack-bar-wrap"><div class="stack-bar" style="width:90%"></div></div>
        </li>
        <li class="stack-item">
          <span class="stack-name">React / Next.js</span>
          <div class="stack-bar-wrap"><div class="stack-bar" style="width:85%"></div></div>
        </li>
        <li class="stack-item">
          <span class="stack-name">Node.js</span>
          <div class="stack-bar-wrap"><div class="stack-bar" style="width:80%"></div></div>
        </li>
        <li class="stack-item">
          <span class="stack-name">MongoDB</span>
          <div class="stack-bar-wrap"><div class="stack-bar" style="width:75%"></div></div>
        </li>
        <li class="stack-item">
          <span class="stack-name">Tailwind CSS</span>
          <div class="stack-bar-wrap"><div class="stack-bar" style="width:88%"></div></div>
        </li>
        <li class="stack-item">
          <span class="stack-name">Express.js</span>
          <div class="stack-bar-wrap"><div class="stack-bar" style="width:78%"></div></div>
        </li>
      </ul>
    </div>

    <!-- Projects -->
    <div class="card">
      <div class="card-label">projects</div>
      <div class="project-list">
        <a class="project-item" href="#">
          <div>
            <div class="project-name">Helper</div>
            <div class="project-desc">on-demand service provider platform</div>
          </div>
          <span class="project-arrow">→</span>
        </a>
        <a class="project-item" href="#">
          <div>
            <div class="project-name">Plant-Pro</div>
            <div class="project-desc">MERN-based plant-care & tracking</div>
          </div>
          <span class="project-arrow">→</span>
        </a>
        <a class="project-item" href="#">
          <div>
            <div class="project-name">Portfolio</div>
            <div class="project-desc">modern personal site with clean UI</div>
          </div>
          <span class="project-arrow">→</span>
        </a>
      </div>
    </div>

  </div>

  <!-- CURRENTLY -->
  <div class="card-full">
    <div class="card-label">currently working on</div>
    <div class="doing-list">
      <div class="doing-item">
        <span class="doing-num">01</span>
        <span>Contributing to open-source projects and building meaningful PRs</span>
      </div>
      <div class="doing-item">
        <span class="doing-num">02</span>
        <span>Learning system design fundamentals and distributed systems</span>
      </div>
      <div class="doing-item">
        <span class="doing-num">03</span>
        <span>Improving full-stack architecture and backend performance patterns</span>
      </div>
      <div class="doing-item">
        <span class="doing-num">04</span>
        <span>Preparing codebase contributions for GSoC 2026</span>
      </div>
    </div>
  </div>

  <!-- STATS -->
  <div class="stats-row">
    <div class="stat-card">
      <img class="stat-img" src="https://github-readme-stats.vercel.app/api?username=hrsh082&show_icons=true&theme=dark&bg_color=0f0f0f&border_color=222&title_color=e8e8e8&text_color=666&icon_color=e8e8e8&hide_border=false" alt="stats"/>
    </div>
    <div class="stat-card">
      <img class="stat-img" src="https://github-readme-streak-stats.herokuapp.com/?user=hrsh082&theme=dark&background=0f0f0f&border=222&ring=e8e8e8&fire=e8e8e8&currStreakLabel=e8e8e8&sideLabels=666&currStreakNum=e8e8e8&sideNums=e8e8e8" alt="streak"/>
    </div>
    <div class="stat-card">
      <img class="stat-img" src="https://github-readme-stats.vercel.app/api/top-langs/?username=hrsh082&layout=compact&theme=dark&bg_color=0f0f0f&border_color=222&title_color=e8e8e8&text_color=666" alt="langs"/>
    </div>
  </div>

  <!-- QUOTE -->
  <div class="quote-block">
    <div class="quote-mark">"</div>
    <p class="quote-text">
      Keep pushing boundaries and <em>build what you'd love to use.</em>
    </p>
  </div>

</div>
</body>
</html>
