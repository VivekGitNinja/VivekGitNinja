<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Vivek Kumar Verma — SDE · Full Stack · DevRel</title>
<link href="https://fonts.googleapis.com/css2?family=Outfit:wght@300;400;500;600;700;800;900&family=JetBrains+Mono:wght@300;400;500;700&family=Playfair+Display:ital,wght@1,400;1,700&display=swap" rel="stylesheet"/>
<style>
/* ── RESET & TOKENS ── */
*, *::before, *::after { margin:0; padding:0; box-sizing:border-box; }

:root {
  --bg:       #080b10;
  --surface:  #0d1117;
  --card:     #111820;
  --border:   #1e2d3d;
  --glow:     #00d4ff;
  --glow2:    #7c3aed;
  --amber:    #f59e0b;
  --green:    #10b981;
  --red:      #ef4444;
  --text:     #e2e8f0;
  --muted:    #64748b;
  --soft:     #94a3b8;
  --display:  'Outfit', sans-serif;
  --mono:     'JetBrains Mono', monospace;
  --serif:    'Playfair Display', serif;
}

html { scroll-behavior: smooth; }

body {
  font-family: var(--display);
  background: var(--bg);
  color: var(--text);
  min-height: 100vh;
  overflow-x: hidden;
  cursor: none;
}

/* ── CUSTOM CURSOR ── */
.cursor {
  position: fixed;
  width: 12px; height: 12px;
  background: var(--glow);
  border-radius: 50%;
  pointer-events: none;
  z-index: 9999;
  transform: translate(-50%, -50%);
  transition: transform 0.1s, background 0.2s;
  mix-blend-mode: screen;
}
.cursor-ring {
  position: fixed;
  width: 36px; height: 36px;
  border: 1.5px solid var(--glow);
  border-radius: 50%;
  pointer-events: none;
  z-index: 9998;
  transform: translate(-50%, -50%);
  transition: transform 0.15s ease, width 0.2s, height 0.2s, opacity 0.2s;
  opacity: 0.4;
}

/* ── GRID BACKGROUND ── */
body::before {
  content: '';
  position: fixed;
  inset: 0;
  background-image:
    linear-gradient(rgba(0,212,255,0.03) 1px, transparent 1px),
    linear-gradient(90deg, rgba(0,212,255,0.03) 1px, transparent 1px);
  background-size: 48px 48px;
  pointer-events: none;
  z-index: 0;
}

/* ── AMBIENT ORBS ── */
.orb {
  position: fixed;
  border-radius: 50%;
  filter: blur(120px);
  pointer-events: none;
  z-index: 0;
  animation: pulse 8s ease-in-out infinite alternate;
}
.orb1 { width:500px; height:500px; background:rgba(0,212,255,0.06); top:-200px; right:-100px; }
.orb2 { width:400px; height:400px; background:rgba(124,58,237,0.07); bottom:-100px; left:-100px; animation-delay: -4s; }
.orb3 { width:300px; height:300px; background:rgba(245,158,11,0.04); top:40%; left:40%; animation-delay: -2s; }

@keyframes pulse {
  from { transform: scale(1) translate(0,0); opacity:0.6; }
  to   { transform: scale(1.2) translate(20px, -20px); opacity:1; }
}

/* ── WRAPPER ── */
.wrap {
  position: relative;
  z-index: 1;
  max-width: 900px;
  margin: 0 auto;
  padding: 0 24px 80px;
}

/* ── HERO ── */
.hero {
  padding: 80px 0 60px;
  display: grid;
  grid-template-columns: 1fr auto;
  gap: 40px;
  align-items: center;
  animation: fadeUp 0.8s ease both;
}

.status-badge {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  background: rgba(16,185,129,0.1);
  border: 1px solid rgba(16,185,129,0.25);
  color: var(--green);
  font-family: var(--mono);
  font-size: 11px;
  letter-spacing: 0.12em;
  padding: 5px 14px;
  border-radius: 100px;
  margin-bottom: 20px;
  text-transform: uppercase;
}
.status-dot {
  width: 7px; height: 7px;
  background: var(--green);
  border-radius: 50%;
  animation: blink 1.8s ease infinite;
}
@keyframes blink {
  0%,100% { opacity:1; } 50% { opacity:0.2; }
}

.hero-name {
  font-size: clamp(42px, 7vw, 72px);
  font-weight: 900;
  line-height: 1.0;
  letter-spacing: -0.03em;
  color: #fff;
}
.hero-name .highlight {
  background: linear-gradient(135deg, var(--glow), var(--glow2));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.hero-role {
  margin-top: 14px;
  font-family: var(--mono);
  font-size: 14px;
  color: var(--soft);
  line-height: 1.6;
}
.hero-role .tag {
  color: var(--glow);
  font-weight: 500;
}

.hero-bio {
  margin-top: 20px;
  font-size: 16px;
  line-height: 1.7;
  color: var(--muted);
  max-width: 520px;
}
.hero-bio strong { color: var(--text); font-weight: 600; }

.hero-cta {
  margin-top: 32px;
  display: flex;
  gap: 12px;
  flex-wrap: wrap;
}

.btn {
  font-family: var(--display);
  font-size: 13px;
  font-weight: 600;
  letter-spacing: 0.04em;
  padding: 11px 24px;
  border-radius: 8px;
  text-decoration: none;
  transition: all 0.25s ease;
  display: inline-flex;
  align-items: center;
  gap: 8px;
  cursor: none;
}
.btn-primary {
  background: linear-gradient(135deg, var(--glow), #0080ff);
  color: #000;
  box-shadow: 0 0 20px rgba(0,212,255,0.25);
}
.btn-primary:hover { transform: translateY(-2px); box-shadow: 0 0 40px rgba(0,212,255,0.4); }
.btn-secondary {
  background: transparent;
  color: var(--text);
  border: 1px solid var(--border);
}
.btn-secondary:hover { border-color: var(--glow); color: var(--glow); transform: translateY(-2px); }

/* ── AVATAR / STATS CARD ── */
.hero-card {
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: 16px;
  padding: 28px 24px;
  text-align: center;
  min-width: 200px;
  position: relative;
  overflow: hidden;
}
.hero-card::before {
  content: '';
  position: absolute;
  top: 0; left: 0; right: 0;
  height: 2px;
  background: linear-gradient(90deg, var(--glow), var(--glow2));
}
.avatar-ring {
  width: 90px; height: 90px;
  border-radius: 50%;
  margin: 0 auto 16px;
  background: linear-gradient(135deg, var(--glow), var(--glow2));
  padding: 3px;
  display: flex;
  align-items: center;
  justify-content: center;
}
.avatar-inner {
  width: 100%; height: 100%;
  border-radius: 50%;
  background: var(--card);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 32px;
  font-weight: 900;
  color: var(--glow);
  font-family: var(--display);
}
.card-name {
  font-size: 15px;
  font-weight: 700;
  color: #fff;
}
.card-handle {
  font-family: var(--mono);
  font-size: 11px;
  color: var(--muted);
  margin-top: 2px;
}
.card-stats {
  margin-top: 18px;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 10px;
}
.stat {
  background: rgba(255,255,255,0.03);
  border: 1px solid var(--border);
  border-radius: 8px;
  padding: 10px 6px;
}
.stat-val {
  font-size: 20px;
  font-weight: 800;
  color: var(--glow);
  line-height: 1;
}
.stat-lbl {
  font-size: 9.5px;
  font-family: var(--mono);
  color: var(--muted);
  margin-top: 3px;
  text-transform: uppercase;
  letter-spacing: 0.08em;
}

/* ── SECTION HEADER ── */
.sec-head {
  display: flex;
  align-items: center;
  gap: 12px;
  margin-bottom: 20px;
  margin-top: 52px;
}
.sec-icon {
  width: 32px; height: 32px;
  background: rgba(0,212,255,0.1);
  border: 1px solid rgba(0,212,255,0.2);
  border-radius: 8px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 15px;
  flex-shrink: 0;
}
.sec-title {
  font-size: 20px;
  font-weight: 800;
  color: #fff;
  letter-spacing: -0.02em;
}
.sec-line {
  flex: 1;
  height: 1px;
  background: linear-gradient(90deg, var(--border), transparent);
}

/* ── TECH GRID ── */
.tech-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(130px, 1fr));
  gap: 10px;
  animation: fadeUp 0.6s ease 0.2s both;
}
.tech-chip {
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: 10px;
  padding: 12px 14px;
  display: flex;
  align-items: center;
  gap: 10px;
  transition: all 0.2s;
  cursor: none;
}
.tech-chip:hover {
  border-color: var(--glow);
  background: rgba(0,212,255,0.05);
  transform: translateY(-2px);
  box-shadow: 0 4px 20px rgba(0,212,255,0.1);
}
.tech-icon { font-size: 18px; flex-shrink:0; }
.tech-name { font-size: 12px; font-weight: 600; color: var(--text); }
.tech-type { font-size: 9.5px; font-family: var(--mono); color: var(--muted); }

/* ── PROJECT CARDS ── */
.proj-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
  gap: 16px;
}
.proj-card {
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: 14px;
  padding: 22px;
  position: relative;
  overflow: hidden;
  transition: all 0.3s;
  cursor: none;
  animation: fadeUp 0.6s ease both;
}
.proj-card::after {
  content: '';
  position: absolute;
  inset: 0;
  background: linear-gradient(135deg, rgba(0,212,255,0.04), transparent 60%);
  opacity: 0;
  transition: opacity 0.3s;
}
.proj-card:hover {
  border-color: rgba(0,212,255,0.3);
  transform: translateY(-4px);
  box-shadow: 0 8px 32px rgba(0,0,0,0.4), 0 0 0 1px rgba(0,212,255,0.1);
}
.proj-card:hover::after { opacity: 1; }
.proj-card:nth-child(2) { animation-delay: 0.1s; }
.proj-card:nth-child(3) { animation-delay: 0.2s; }
.proj-card:nth-child(4) { animation-delay: 0.3s; }

.proj-top {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  margin-bottom: 12px;
}
.proj-emoji { font-size: 24px; }
.proj-links { display: flex; gap: 8px; }
.proj-link {
  font-family: var(--mono);
  font-size: 10px;
  color: var(--muted);
  text-decoration: none;
  border: 1px solid var(--border);
  padding: 3px 8px;
  border-radius: 5px;
  transition: all 0.2s;
}
.proj-link:hover { border-color: var(--glow); color: var(--glow); }
.proj-name {
  font-size: 15px;
  font-weight: 700;
  color: #fff;
  margin-bottom: 6px;
  letter-spacing: -0.01em;
}
.proj-desc {
  font-size: 12.5px;
  line-height: 1.6;
  color: var(--muted);
  margin-bottom: 14px;
}
.proj-stack {
  display: flex;
  flex-wrap: wrap;
  gap: 6px;
}
.stack-tag {
  font-family: var(--mono);
  font-size: 10px;
  padding: 2px 8px;
  border-radius: 4px;
  background: rgba(124,58,237,0.12);
  border: 1px solid rgba(124,58,237,0.2);
  color: #a78bfa;
}

/* ── EXPERIENCE TIMELINE ── */
.timeline { position: relative; padding-left: 28px; }
.timeline::before {
  content: '';
  position: absolute;
  left: 6px; top: 8px; bottom: 8px;
  width: 1px;
  background: linear-gradient(180deg, var(--glow), var(--glow2), transparent);
}
.tl-item {
  position: relative;
  margin-bottom: 28px;
  animation: fadeUp 0.6s ease both;
}
.tl-item:nth-child(2) { animation-delay: 0.1s; }
.tl-dot {
  position: absolute;
  left: -25px;
  top: 6px;
  width: 14px; height: 14px;
  border-radius: 50%;
  background: var(--bg);
  border: 2px solid var(--glow);
  box-shadow: 0 0 8px rgba(0,212,255,0.4);
}
.tl-card {
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: 12px;
  padding: 18px 20px;
  transition: border-color 0.2s;
}
.tl-card:hover { border-color: rgba(0,212,255,0.3); }
.tl-header { display: flex; justify-content: space-between; align-items: flex-start; flex-wrap: wrap; gap: 8px; }
.tl-company { font-size: 15px; font-weight: 700; color: #fff; }
.tl-date {
  font-family: var(--mono);
  font-size: 10.5px;
  color: var(--glow);
  background: rgba(0,212,255,0.08);
  border: 1px solid rgba(0,212,255,0.15);
  padding: 3px 10px;
  border-radius: 100px;
}
.tl-role {
  font-size: 12.5px;
  color: var(--amber);
  font-weight: 500;
  margin: 4px 0 8px;
  font-family: var(--mono);
}
.tl-desc { font-size: 12.5px; color: var(--muted); line-height: 1.65; }

/* ── ACHIEVEMENT CARDS ── */
.achieve-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(240px, 1fr));
  gap: 12px;
}
.achieve-card {
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: 12px;
  padding: 16px 18px;
  display: flex;
  gap: 14px;
  align-items: flex-start;
  transition: all 0.2s;
  animation: fadeUp 0.6s ease both;
}
.achieve-card:nth-child(2) { animation-delay:0.1s; }
.achieve-card:nth-child(3) { animation-delay:0.2s; }
.achieve-card:hover { border-color: rgba(245,158,11,0.3); transform: translateY(-2px); }
.achieve-icon { font-size: 22px; flex-shrink:0; }
.achieve-title { font-size: 12.5px; font-weight: 700; color: #fff; margin-bottom: 3px; }
.achieve-sub { font-size: 11px; color: var(--muted); line-height: 1.5; }

/* ── SOCIAL LINKS ── */
.social-row {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
  margin-top: 8px;
}
.social-btn {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  text-decoration: none;
  font-family: var(--mono);
  font-size: 11.5px;
  font-weight: 500;
  padding: 9px 16px;
  border-radius: 9px;
  border: 1px solid var(--border);
  color: var(--soft);
  background: var(--card);
  transition: all 0.2s;
  cursor: none;
  letter-spacing: 0.03em;
}
.social-btn:hover { transform: translateY(-2px); }
.social-btn.gh:hover  { border-color: #fff; color:#fff; }
.social-btn.li:hover  { border-color: #0a66c2; color:#0a66c2; }
.social-btn.tw:hover  { border-color: #1da1f2; color:#1da1f2; }
.social-btn.lc:hover  { border-color: var(--amber); color:var(--amber); }
.social-btn.pt:hover  { border-color: var(--glow); color:var(--glow); }
.social-btn.gm:hover  { border-color: #ef4444; color:#ef4444; }
.social-btn .s-icon   { font-size: 14px; }

/* ── FOCUS AREAS ── */
.focus-list {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 10px;
}
.focus-item {
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: 10px;
  padding: 14px 16px;
  display: flex;
  gap: 12px;
  align-items: center;
  font-size: 12.5px;
  color: var(--soft);
  transition: all 0.2s;
}
.focus-item:hover { border-color: var(--glow2); color: var(--text); }
.focus-item .fi { font-size: 18px; flex-shrink:0; }

/* ── MOTTO BANNER ── */
.motto {
  margin-top: 52px;
  background: linear-gradient(135deg, rgba(0,212,255,0.06), rgba(124,58,237,0.06));
  border: 1px solid var(--border);
  border-radius: 16px;
  padding: 36px 40px;
  text-align: center;
  position: relative;
  overflow: hidden;
}
.motto::before {
  content: '';
  position: absolute;
  top: 0; left: 0; right: 0;
  height: 2px;
  background: linear-gradient(90deg, var(--glow), var(--glow2), var(--amber));
}
.motto-text {
  font-family: var(--serif);
  font-style: italic;
  font-size: clamp(20px, 3vw, 28px);
  color: #fff;
  line-height: 1.4;
}
.motto-text em {
  font-style: normal;
  background: linear-gradient(135deg, var(--glow), var(--amber));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  font-weight: 700;
}
.motto-sub {
  margin-top: 12px;
  font-family: var(--mono);
  font-size: 12px;
  color: var(--muted);
  letter-spacing: 0.12em;
  text-transform: uppercase;
}

/* ── ANIMATIONS ── */
@keyframes fadeUp {
  from { opacity:0; transform:translateY(24px); }
  to   { opacity:1; transform:translateY(0); }
}

/* ── DIVIDER ── */
hr.div {
  border: none;
  height: 1px;
  background: linear-gradient(90deg, transparent, var(--border), transparent);
  margin: 8px 0;
}

</style>
</head>
<body>

<!-- CURSOR -->
<div class="cursor" id="cur"></div>
<div class="cursor-ring" id="curR"></div>

<!-- ORBS -->
<div class="orb orb1"></div>
<div class="orb orb2"></div>
<div class="orb orb3"></div>

<div class="wrap">

  <!-- ══ HERO ══ -->
  <section class="hero">
    <div class="hero-left">
      <div class="status-badge">
        <span class="status-dot"></span>
        Open to SDE / Full Stack roles
      </div>
      <h1 class="hero-name">
        Vivek<br/>
        <span class="highlight">Kumar Verma</span>
      </h1>
      <p class="hero-role">
        <span class="tag">Full Stack Developer</span> &nbsp;·&nbsp;
        DevRel Manager @ DevNovate &nbsp;·&nbsp;
        Community Builder
      </p>
      <p class="hero-bio">
        I build <strong>production-ready web systems</strong> with Next.js, Node.js & TypeScript —
        and grow <strong>developer communities</strong> that spark real innovation.
        700+ members led. 3+ hackathons organized. AI + full stack is my sweet spot.
      </p>
      <div class="hero-cta">
        <a href="mailto:vkumarverma670@gmail.com" class="btn btn-primary">
          ✉ Hire Me
        </a>
        <a href="https://vivekgitninja.github.io/Vivek-s-Portfolio" target="_blank" class="btn btn-secondary">
          ↗ Portfolio
        </a>
        <a href="https://github.com/VivekGitNinja" target="_blank" class="btn btn-secondary">
          ⌥ GitHub
        </a>
      </div>
    </div>

    <div class="hero-card">
      <div class="avatar-ring">
        <div class="avatar-inner">VK</div>
      </div>
      <div class="card-name">Vivek Kumar Verma</div>
      <div class="card-handle">@VivekGitNinja</div>
      <div class="card-stats">
        <div class="stat">
          <div class="stat-val">700+</div>
          <div class="stat-lbl">Community</div>
        </div>
        <div class="stat">
          <div class="stat-val">3+</div>
          <div class="stat-lbl">Hackathons</div>
        </div>
        <div class="stat">
          <div class="stat-val">85%</div>
          <div class="stat-lbl">ML Accuracy</div>
        </div>
        <div class="stat">
          <div class="stat-val">8+</div>
          <div class="stat-lbl">Certs</div>
        </div>
      </div>
    </div>
  </section>

  <!-- ══ TECH STACK ══ -->
  <div class="sec-head">
    <div class="sec-icon">⚡</div>
    <h2 class="sec-title">Tech Stack</h2>
    <div class="sec-line"></div>
  </div>

  <div class="tech-grid">
    <div class="tech-chip"><span class="tech-icon">🟨</span><div><div class="tech-name">JavaScript</div><div class="tech-type">Language</div></div></div>
    <div class="tech-chip"><span class="tech-icon">🔷</span><div><div class="tech-name">TypeScript</div><div class="tech-type">Language</div></div></div>
    <div class="tech-chip"><span class="tech-icon">🐍</span><div><div class="tech-name">Python</div><div class="tech-type">Language</div></div></div>
    <div class="tech-chip"><span class="tech-icon">☕</span><div><div class="tech-name">Java</div><div class="tech-type">Language</div></div></div>
    <div class="tech-chip"><span class="tech-icon">▲</span><div><div class="tech-name">Next.js</div><div class="tech-type">Frontend</div></div></div>
    <div class="tech-chip"><span class="tech-icon">⚛</span><div><div class="tech-name">React.js</div><div class="tech-type">Frontend</div></div></div>
    <div class="tech-chip"><span class="tech-icon">🌿</span><div><div class="tech-name">Node.js</div><div class="tech-type">Backend</div></div></div>
    <div class="tech-chip"><span class="tech-icon">🚂</span><div><div class="tech-name">Express.js</div><div class="tech-type">Backend</div></div></div>
    <div class="tech-chip"><span class="tech-icon">🍃</span><div><div class="tech-name">MongoDB</div><div class="tech-type">Database</div></div></div>
    <div class="tech-chip"><span class="tech-icon">🐬</span><div><div class="tech-name">MySQL</div><div class="tech-type">Database</div></div></div>
    <div class="tech-chip"><span class="tech-icon">🔴</span><div><div class="tech-name">Redis</div><div class="tech-type">Cache</div></div></div>
    <div class="tech-chip"><span class="tech-icon">🤖</span><div><div class="tech-name">scikit-learn</div><div class="tech-type">ML</div></div></div>
    <div class="tech-chip"><span class="tech-icon">🌊</span><div><div class="tech-name">Tailwind CSS</div><div class="tech-type">Styling</div></div></div>
    <div class="tech-chip"><span class="tech-icon">🐙</span><div><div class="tech-name">Git / GitHub</div><div class="tech-type">DevOps</div></div></div>
  </div>

  <!-- ══ PROJECTS ══ -->
  <div class="sec-head">
    <div class="sec-icon">🚀</div>
    <h2 class="sec-title">Featured Projects</h2>
    <div class="sec-line"></div>
  </div>

  <div class="proj-grid">

    <div class="proj-card">
      <div class="proj-top">
        <span class="proj-emoji">🛰️</span>
        <div class="proj-links">
          <a href="#" class="proj-link">Live ↗</a>
        </div>
      </div>
      <div class="proj-name">NX-913 Platform</div>
      <p class="proj-desc">Production-ready hackathon platform with RBAC auth, Redis caching, BullMQ job queues, and RAG-based AI with multi-provider failover for real-time assistance.</p>
      <div class="proj-stack">
        <span class="stack-tag">Next.js</span>
        <span class="stack-tag">TypeScript</span>
        <span class="stack-tag">MongoDB</span>
        <span class="stack-tag">Redis</span>
        <span class="stack-tag">Gemini API</span>
      </div>
    </div>

    <div class="proj-card">
      <div class="proj-top">
        <span class="proj-emoji">🧠</span>
        <div class="proj-links">
          <a href="#" class="proj-link">GitHub ↗</a>
        </div>
      </div>
      <div class="proj-name">Multi-Disease Predictor</div>
      <p class="proj-desc">ML system predicting 3 diseases (diabetes, heart disease, Parkinson's) with 85%+ accuracy. Real-time inference via Streamlit with full data pipeline.</p>
      <div class="proj-stack">
        <span class="stack-tag">Python</span>
        <span class="stack-tag">scikit-learn</span>
        <span class="stack-tag">Streamlit</span>
      </div>
    </div>

    <div class="proj-card">
      <div class="proj-top">
        <span class="proj-emoji">🛒</span>
        <div class="proj-links">
          <a href="#" class="proj-link">GitHub ↗</a>
        </div>
      </div>
      <div class="proj-name">E-Commerce Multivendor</div>
      <p class="proj-desc">Full multivendor platform supporting seller/buyer workflows, product management, order tracking, and Bootstrap admin dashboard.</p>
      <div class="proj-stack">
        <span class="stack-tag">PHP</span>
        <span class="stack-tag">MySQLi</span>
        <span class="stack-tag">Bootstrap</span>
      </div>
    </div>

    <div class="proj-card">
      <div class="proj-top">
        <span class="proj-emoji">🚗</span>
        <div class="proj-links">
          <a href="https://github.com/VivekGitNinja" class="proj-link">GitHub ↗</a>
        </div>
      </div>
      <div class="proj-name">Vehicle Identification Sys</div>
      <p class="proj-desc">AI-enabled vehicle data platform that identifies and retrieves vehicle information with an intelligent, interactive interface.</p>
      <div class="proj-stack">
        <span class="stack-tag">AI</span>
        <span class="stack-tag">JavaScript</span>
        <span class="stack-tag">Node.js</span>
      </div>
    </div>

  </div>

  <!-- ══ EXPERIENCE ══ -->
  <div class="sec-head">
    <div class="sec-icon">💼</div>
    <h2 class="sec-title">Experience</h2>
    <div class="sec-line"></div>
  </div>

  <div class="timeline">
    <div class="tl-item">
      <div class="tl-dot"></div>
      <div class="tl-card">
        <div class="tl-header">
          <span class="tl-company">DevNovate Technologies</span>
          <span class="tl-date">Jun 2025 – Present</span>
        </div>
        <div class="tl-role">DevRel Manager · Full-Time Remote · Delhi</div>
        <p class="tl-desc">Connecting developer communities across India by creating technical content, representing developer needs, and nurturing a vibrant ecosystem of innovators. Building bridges between developers and cutting-edge technology.</p>
      </div>
    </div>

    <div class="tl-item">
      <div class="tl-dot" style="border-color:var(--glow2); box-shadow: 0 0 8px rgba(124,58,237,0.4);"></div>
      <div class="tl-card">
        <div class="tl-header">
          <span class="tl-company">Microsoft & SAP · Edunet Foundation (TechSaksham)</span>
          <span class="tl-date">Feb – May 2025</span>
        </div>
        <div class="tl-role">AI Intern · Remote</div>
        <p class="tl-desc">Built a production-ready ML medical assistant — full pipeline from data preprocessing and model training to evaluation and real-time Streamlit inference. Achieved 85%+ accuracy across 3 diseases.</p>
      </div>
    </div>
  </div>

  <!-- ══ ACHIEVEMENTS ══ -->
  <div class="sec-head">
    <div class="sec-icon">🏆</div>
    <h2 class="sec-title">Achievements & Community</h2>
    <div class="sec-line"></div>
  </div>

  <div class="achieve-grid">
    <div class="achieve-card">
      <span class="achieve-icon">🛸</span>
      <div>
        <div class="achieve-title">ISRO Bharatiya Antariksh Hackathon 2025</div>
        <div class="achieve-sub">Submitted space-tech solution to ISRO's national hackathon.</div>
      </div>
    </div>
    <div class="achieve-card">
      <span class="achieve-icon">🌍</span>
      <div>
        <div class="achieve-title">GDG Solution Challenge 2025</div>
        <div class="achieve-sub">Developed social impact solution for Google Developer Groups global challenge.</div>
      </div>
    </div>
    <div class="achieve-card">
      <span class="achieve-icon">👥</span>
      <div>
        <div class="achieve-title">HackWithIndia NIET — Chapter President</div>
        <div class="achieve-sub">Led 700+ member community; organized 3+ hackathons with 200+ participants.</div>
      </div>
    </div>
    <div class="achieve-card">
      <span class="achieve-icon">🏅</span>
      <div>
        <div class="achieve-title">OpenCode '24 — IIIT Allahabad</div>
        <div class="achieve-sub">Open-source contributor; awarded Certificate of Appreciation by GeekHaven.</div>
      </div>
    </div>
    <div class="achieve-card">
      <span class="achieve-icon">📣</span>
      <div>
        <div class="achieve-title">INNOVA 2024 — Campus Rep (GDG GCET)</div>
        <div class="achieve-sub">Drove registrations via social media; earned Letter of Recommendation.</div>
      </div>
    </div>
  </div>

  <!-- ══ FOCUS AREAS ══ -->
  <div class="sec-head">
    <div class="sec-icon">🎯</div>
    <h2 class="sec-title">What I'm Building Towards</h2>
    <div class="sec-line"></div>
  </div>

  <div class="focus-list">
    <div class="focus-item"><span class="fi">🌐</span>Scalable Full Stack Web Systems</div>
    <div class="focus-item"><span class="fi">🤖</span>AI / ML Integrated Applications</div>
    <div class="focus-item"><span class="fi">🏗️</span>Developer Community & DevRel</div>
    <div class="focus-item"><span class="fi">🔗</span>IoT & Emerging Tech Products</div>
    <div class="focus-item"><span class="fi">🚀</span>Startup Ideas Fuelled by Innovation</div>
    <div class="focus-item"><span class="fi">🎤</span>Speaking & Mentoring at Tech Events</div>
  </div>

  <!-- ══ CONNECT ══ -->
  <div class="sec-head">
    <div class="sec-icon">🌐</div>
    <h2 class="sec-title">Find Me Online</h2>
    <div class="sec-line"></div>
  </div>

  <div class="social-row">
    <a href="https://github.com/VivekGitNinja" class="social-btn gh" target="_blank">
      <span class="s-icon">🐙</span> GitHub
    </a>
    <a href="https://www.linkedin.com/in/vivekumarverma" class="social-btn li" target="_blank">
      <span class="s-icon">💼</span> LinkedIn
    </a>
    <a href="https://x.com/_vivek_33" class="social-btn tw" target="_blank">
      <span class="s-icon">🐦</span> Twitter / X
    </a>
    <a href="https://leetcode.com/VivekLeetNinja/" class="social-btn lc" target="_blank">
      <span class="s-icon">🧩</span> LeetCode
    </a>
    <a href="https://vivekgitninja.github.io/Vivek-s-Portfolio" class="social-btn pt" target="_blank">
      <span class="s-icon">✦</span> Portfolio
    </a>
    <a href="mailto:vkumarverma670@gmail.com" class="social-btn gm">
      <span class="s-icon">✉</span> Gmail
    </a>
  </div>

  <!-- ══ MOTTO ══ -->
  <div class="motto">
    <p class="motto-text">
      "Anyone can write code.<br/>
      But only a few can code the <em>future</em>."
    </p>
    <p class="motto-sub">🚀 Let's Connect &amp; Create Something Legendary</p>
  </div>

</div>

<!-- CURSOR SCRIPT -->
<script>
  const cur  = document.getElementById('cur');
  const curR = document.getElementById('curR');
  let mx=0,my=0,rx=0,ry=0;
  document.addEventListener('mousemove',e=>{ mx=e.clientX; my=e.clientY; cur.style.left=mx+'px'; cur.style.top=my+'px'; });
  (function loop(){ rx+=(mx-rx)*0.12; ry+=(my-ry)*0.12; curR.style.left=rx+'px'; curR.style.top=ry+'px'; requestAnimationFrame(loop); })();
  document.querySelectorAll('a,button,.tech-chip,.proj-card,.achieve-card,.social-btn').forEach(el=>{
    el.addEventListener('mouseenter',()=>{ curR.style.width='56px'; curR.style.height='56px'; curR.style.opacity='0.7'; });
    el.addEventListener('mouseleave',()=>{ curR.style.width='36px'; curR.style.height='36px'; curR.style.opacity='0.4'; });
  });
</script>

</body>
</html>
