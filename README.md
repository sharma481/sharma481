<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Manish Sharma — Full Stack Developer</title>
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;700&family=Syne:wght@400;700;800&display=swap" rel="stylesheet"/>
<style>
*{box-sizing:border-box;margin:0;padding:0}
:root{
  --accent:#00e5ff;
  --accent2:#7c3aed;
  --green:#22c55e;
  --gold:#fbbf24;
  --dark:#060c1a;
  --card:#0d1528;
  --card2:#111b30;
  --text:#e2e8f0;
  --muted:#7a8aa0;
  --border:rgba(0,229,255,0.12);
}
html{scroll-behavior:smooth}
body{
  background:var(--dark);
  color:var(--text);
  font-family:'Syne',sans-serif;
  min-height:100vh;
  overflow-x:hidden;
}

/* ── CANVAS PARTICLES ── */
#particles{position:fixed;inset:0;z-index:0;pointer-events:none}

/* ── GRID BG ── */
.bg-grid{
  position:fixed;inset:0;z-index:0;pointer-events:none;
  background-image:
    linear-gradient(rgba(0,229,255,0.03) 1px,transparent 1px),
    linear-gradient(90deg,rgba(0,229,255,0.03) 1px,transparent 1px);
  background-size:48px 48px;
}
.bg-orb{
  position:fixed;border-radius:50%;pointer-events:none;z-index:0;
  filter:blur(80px);
}
.orb1{width:600px;height:600px;background:rgba(124,58,237,0.08);top:-150px;left:-150px;animation:drift1 12s ease-in-out infinite alternate}
.orb2{width:500px;height:500px;background:rgba(0,229,255,0.06);bottom:-100px;right:-100px;animation:drift2 15s ease-in-out infinite alternate}
@keyframes drift1{to{transform:translate(80px,60px)}}
@keyframes drift2{to{transform:translate(-60px,-40px)}}

/* ── LAYOUT ── */
.page{position:relative;z-index:1;max-width:900px;margin:0 auto;padding:3rem 2rem 5rem}

/* ── HERO ── */
.hero{
  display:flex;align-items:center;gap:2.5rem;
  margin-bottom:4rem;
  animation:fadeUp .7s both;
}
.avatar-wrap{position:relative;flex-shrink:0}
.avatar{
  width:90px;height:90px;border-radius:50%;
  background:linear-gradient(135deg,var(--accent2),var(--accent));
  display:flex;align-items:center;justify-content:center;
  font-family:'JetBrains Mono',monospace;font-size:30px;font-weight:700;color:#fff;
  position:relative;z-index:1;
}
.avatar-ring{
  position:absolute;inset:-6px;border-radius:50%;
  border:2px solid transparent;
  background:linear-gradient(var(--dark),var(--dark)) padding-box,
             linear-gradient(135deg,var(--accent),var(--accent2)) border-box;
  animation:spin 6s linear infinite;
}
@keyframes spin{to{transform:rotate(360deg)}}
.hero-text h1{
  font-size:36px;font-weight:800;letter-spacing:-1px;
  background:linear-gradient(90deg,#fff 30%,var(--accent));
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;
  line-height:1.1;
}
.hero-role{
  font-family:'JetBrains Mono',monospace;font-size:13px;
  color:var(--accent);margin-top:6px;opacity:.85;
}
.hero-role::before{content:'> ';opacity:.5}
.hero-badges{display:flex;flex-wrap:wrap;gap:8px;margin-top:14px}
.badge{
  font-family:'JetBrains Mono',monospace;font-size:11px;
  padding:4px 12px;border-radius:20px;
  border:1px solid var(--border);
  color:var(--muted);background:rgba(255,255,255,0.03);
  transition:all .2s;
}
.badge:hover{border-color:var(--accent);color:var(--accent)}
.status-row{display:flex;align-items:center;gap:6px;margin-top:10px}
.dot{width:8px;height:8px;border-radius:50%;background:var(--green);animation:blink 1.5s ease-in-out infinite}
@keyframes blink{0%,100%{opacity:1}50%{opacity:.2}}
.status-row span{font-family:'JetBrains Mono',monospace;font-size:12px;color:var(--muted)}

/* ── SECTION LABEL ── */
.sec-label{
  font-family:'JetBrains Mono',monospace;font-size:11px;
  text-transform:uppercase;letter-spacing:2.5px;
  color:var(--accent);opacity:.65;margin-bottom:1.2rem;
}

/* ── STATS CARDS ── */
.stats-row{display:grid;grid-template-columns:repeat(auto-fit,minmax(140px,1fr));gap:12px;margin-bottom:3rem}
.stat-card{
  background:var(--card);border:1px solid var(--border);border-radius:14px;
  padding:1.4rem 1.2rem;text-align:center;
  animation:fadeUp .5s both;transition:transform .2s,border-color .2s;
}
.stat-card:hover{transform:translateY(-4px);border-color:rgba(0,229,255,.35)}
.stat-num{
  font-size:38px;font-weight:800;
  background:linear-gradient(135deg,#fff,var(--accent));
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;
  line-height:1;
}
.stat-lbl{font-family:'JetBrains Mono',monospace;font-size:11px;color:var(--muted);margin-top:5px}
.stat-icon{font-size:20px;margin-bottom:8px}

/* ── TROPHIES ── */
.trophy-section{margin-bottom:3rem}
.trophy-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(160px,1fr));gap:12px}
.trophy-card{
  background:var(--card);border:1px solid rgba(251,191,36,.15);border-radius:14px;
  padding:1.2rem 1rem;text-align:center;
  animation:fadeUp .5s both;transition:all .2s;
  position:relative;overflow:hidden;
}
.trophy-card::before{
  content:'';position:absolute;inset:0;
  background:linear-gradient(135deg,rgba(251,191,36,0.05),transparent);
  opacity:0;transition:opacity .2s;
}
.trophy-card:hover{transform:translateY(-4px);border-color:rgba(251,191,36,.5)}
.trophy-card:hover::before{opacity:1}
.trophy-icon{font-size:32px;margin-bottom:8px;filter:drop-shadow(0 0 8px rgba(251,191,36,.4))}
.trophy-title{font-weight:700;font-size:13px;color:var(--gold)}
.trophy-sub{font-family:'JetBrains Mono',monospace;font-size:11px;color:var(--muted);margin-top:4px}

/* ── SKILLS ── */
.skills-section{margin-bottom:3rem}
.skills-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(110px,1fr));gap:10px}
.skill-card{
  background:var(--card);border:1px solid var(--border);border-radius:10px;
  padding:14px 8px;text-align:center;
  animation:fadeUp .4s both;transition:all .2s;cursor:default;
}
.skill-card:hover{transform:translateY(-5px);border-color:var(--accent);box-shadow:0 0 20px rgba(0,229,255,.12)}
.sk-icon{font-size:22px;margin-bottom:6px}
.sk-name{font-family:'JetBrains Mono',monospace;font-size:11px;font-weight:700;color:var(--text)}
.sk-cat{font-size:10px;color:var(--muted);margin-top:3px}
.sk-bar-wrap{margin-top:8px;height:3px;background:rgba(255,255,255,.07);border-radius:2px;overflow:hidden}
.sk-bar{height:100%;border-radius:2px;background:linear-gradient(90deg,var(--accent2),var(--accent));width:0%;transition:width 1.3s cubic-bezier(.4,0,.2,1)}

/* ── LANG BAR ── */
.langs-section{margin-bottom:3rem}
.lang-row{display:flex;flex-direction:column;gap:10px}
.lang-item{display:grid;grid-template-columns:130px 1fr 40px;align-items:center;gap:12px;animation:fadeUp .5s both}
.lang-name{font-family:'JetBrains Mono',monospace;font-size:12px;color:var(--text)}
.lang-track{height:8px;background:rgba(255,255,255,.07);border-radius:4px;overflow:hidden}
.lang-fill{height:100%;border-radius:4px;width:0%;transition:width 1.4s cubic-bezier(.4,0,.2,1)}
.lang-pct{font-family:'JetBrains Mono',monospace;font-size:11px;color:var(--muted);text-align:right}

/* ── PROJECTS ── */
.projects-section{margin-bottom:3rem}
.proj-grid{display:grid;gap:12px}
.proj-card{
  background:var(--card);border:1px solid var(--border);border-radius:14px;
  padding:1.2rem 1.4rem;display:flex;align-items:flex-start;gap:1.2rem;
  animation:fadeUp .5s both;transition:all .2s;
}
.proj-card:hover{border-color:rgba(124,58,237,.5);transform:translateX(5px)}
.proj-icon-wrap{
  width:44px;height:44px;border-radius:10px;flex-shrink:0;
  display:flex;align-items:center;justify-content:center;font-size:22px;
}
.proj-title{font-weight:700;font-size:15px}
.proj-desc{font-size:13px;color:var(--muted);font-family:'JetBrains Mono',monospace;margin-top:3px}
.proj-tags{display:flex;gap:6px;flex-wrap:wrap;margin-top:8px}
.tag{
  font-family:'JetBrains Mono',monospace;font-size:10px;
  padding:3px 10px;border-radius:20px;
  border:1px solid rgba(0,229,255,.25);color:var(--accent);
  background:rgba(0,229,255,.06);
}

/* ── QUOTE ── */
.quote{
  border-left:3px solid var(--accent);
  padding:1.2rem 1.4rem;border-radius:0 12px 12px 0;
  background:rgba(0,229,255,.04);
  margin-bottom:3rem;animation:fadeUp .6s both;
}
.quote p{font-size:15px;font-style:italic;line-height:1.8;color:var(--text)}
.quote-author{font-family:'JetBrains Mono',monospace;font-size:12px;color:var(--muted);margin-top:8px}
.quote-author::before{content:'— '}

/* ── CONNECT ── */
.connect-section{margin-bottom:2rem}
.connect-grid{display:flex;flex-wrap:wrap;gap:10px}
.connect-btn{
  font-family:'JetBrains Mono',monospace;font-size:12px;
  padding:10px 18px;border-radius:10px;
  border:1px solid var(--border);color:var(--text);
  background:var(--card);cursor:pointer;text-decoration:none;
  display:flex;align-items:center;gap:8px;
  transition:all .2s;
}
.connect-btn:hover{border-color:var(--accent);color:var(--accent);box-shadow:0 0 16px rgba(0,229,255,.15);transform:translateY(-2px)}

/* ── CONTRIBUTION GRAPH ── */
.contrib-section{margin-bottom:3rem}
.contrib-grid{display:flex;gap:3px;flex-wrap:wrap}
.contrib-week{display:flex;flex-direction:column;gap:3px}
.contrib-day{
  width:13px;height:13px;border-radius:3px;
  background:rgba(255,255,255,.05);
  transition:all .2s;cursor:default;
}
.contrib-day:hover{transform:scale(1.3)}
.c0{background:rgba(255,255,255,.05)}
.c1{background:rgba(0,229,255,.2)}
.c2{background:rgba(0,229,255,.4)}
.c3{background:rgba(0,229,255,.65)}
.c4{background:rgba(0,229,255,.9)}

/* ── ANIMATIONS ── */
@keyframes fadeUp{from{opacity:0;transform:translateY(22px)}to{opacity:1;transform:translateY(0)}}
.d1{animation-delay:.05s}.d2{animation-delay:.1s}.d3{animation-delay:.15s}
.d4{animation-delay:.2s}.d5{animation-delay:.25s}.d6{animation-delay:.3s}
.d7{animation-delay:.35s}.d8{animation-delay:.4s}.d9{animation-delay:.45s}
.d10{animation-delay:.5s}.d11{animation-delay:.55s}.d12{animation-delay:.6s}
.d13{animation-delay:.65s}.d14{animation-delay:.7s}

/* ── FOOTER ── */
.footer{text-align:center;font-family:'JetBrains Mono',monospace;font-size:12px;color:var(--muted);padding-top:2rem;border-top:1px solid var(--border)}
.footer span{color:var(--accent)}

/* ── RESPONSIVE ── */
@media(max-width:600px){
  .hero{flex-direction:column;text-align:center}
  .hero-badges{justify-content:center}
  .status-row{justify-content:center}
  .stats-row{grid-template-columns:repeat(2,1fr)}
  .lang-item{grid-template-columns:90px 1fr 34px}
}
</style>
</head>
<body>

<canvas id="particles"></canvas>
<div class="bg-grid"></div>
<div class="bg-orb orb1"></div>
<div class="bg-orb orb2"></div>

<div class="page">

  <!-- ═══ HERO ═══ -->
  <div class="hero">
    <div class="avatar-wrap">
      <div class="avatar-ring"></div>
      <div class="avatar">MS</div>
    </div>
    <div class="hero-text">
      <h1>Manish Sharma</h1>
      <div class="hero-role">Full Stack Developer · MERN · Backend Systems · Cloud</div>
      <div class="hero-badges">
        <span class="badge">Node.js</span>
        <span class="badge">React</span>
        <span class="badge">PostgreSQL</span>
        <span class="badge">MongoDB</span>
        <span class="badge">AWS · GCP</span>
        <span class="badge">Docker</span>
        <span class="badge">Socket.io</span>
        <span class="badge">NestJS</span>
      </div>
      <div class="status-row">
        <div class="dot"></div>
        <span>Open to collaboration & new challenges</span>
      </div>
    </div>
  </div>

  <!-- ═══ STATS ═══ -->
  <div class="sec-label">// github stats</div>
  <div class="stats-row">
    <div class="stat-card d1">
      <div class="stat-icon">📁</div>
      <div class="stat-num" id="s-repos">0</div>
      <div class="stat-lbl">repositories</div>
    </div>
    <div class="stat-card d2">
      <div class="stat-icon">✅</div>
      <div class="stat-num" id="s-commits">0</div>
      <div class="stat-lbl">total commits</div>
    </div>
    <div class="stat-card d3">
      <div class="stat-icon">⭐</div>
      <div class="stat-num" id="s-stars">0</div>
      <div class="stat-lbl">stars earned</div>
    </div>
    <div class="stat-card d4">
      <div class="stat-icon">🔥</div>
      <div class="stat-num" id="s-streak">0</div>
      <div class="stat-lbl">day streak</div>
    </div>
    <div class="stat-card d5">
      <div class="stat-icon">🍴</div>
      <div class="stat-num" id="s-prs">0</div>
      <div class="stat-lbl">pull requests</div>
    </div>
  </div>

  <!-- ═══ TROPHIES ═══ -->
  <div class="trophy-section">
    <div class="sec-label">// achievements & trophies</div>
    <div class="trophy-grid">
      <div class="trophy-card d1">
        <div class="trophy-icon">🏆</div>
        <div class="trophy-title">Multi-Language</div>
        <div class="trophy-sub">JS · TS · Python</div>
      </div>
      <div class="trophy-card d2">
        <div class="trophy-icon">🥇</div>
        <div class="trophy-title">Commit Master</div>
        <div class="trophy-sub">1300+ commits</div>
      </div>
      <div class="trophy-card d3">
        <div class="trophy-icon">🚀</div>
        <div class="trophy-title">Early Adopter</div>
        <div class="trophy-sub">Cloud & Microservices</div>
      </div>
      <div class="trophy-card d4">
        <div class="trophy-icon">⚡</div>
        <div class="trophy-title">Realtime Dev</div>
        <div class="trophy-sub">Socket.io Expert</div>
      </div>
      <div class="trophy-card d5">
        <div class="trophy-icon">🔥</div>
        <div class="trophy-title">Streak Legend</div>
        <div class="trophy-sub">87-day streak</div>
      </div>
      <div class="trophy-card d6">
        <div class="trophy-icon">🛡️</div>
        <div class="trophy-title">Full Stack</div>
        <div class="trophy-sub">MERN + PostgreSQL</div>
      </div>
    </div>
  </div>

  <!-- ═══ SKILLS ═══ -->
  <div class="skills-section">
    <div class="sec-label">// tech stack</div>
    <div class="skills-grid">
      <div class="skill-card d1"><div class="sk-icon">🟢</div><div class="sk-name">Node.js</div><div class="sk-cat">Backend</div><div class="sk-bar-wrap"><div class="sk-bar" data-w="95"></div></div></div>
      <div class="skill-card d2"><div class="sk-icon">⚛️</div><div class="sk-name">React</div><div class="sk-cat">Frontend</div><div class="sk-bar-wrap"><div class="sk-bar" data-w="90"></div></div></div>
      <div class="skill-card d3"><div class="sk-icon">🍃</div><div class="sk-name">MongoDB</div><div class="sk-cat">Database</div><div class="sk-bar-wrap"><div class="sk-bar" data-w="85"></div></div></div>
      <div class="skill-card d4"><div class="sk-icon">🐘</div><div class="sk-name">PostgreSQL</div><div class="sk-cat">Database</div><div class="sk-bar-wrap"><div class="sk-bar" data-w="82"></div></div></div>
      <div class="skill-card d5"><div class="sk-icon">🟦</div><div class="sk-name">TypeScript</div><div class="sk-cat">Language</div><div class="sk-bar-wrap"><div class="sk-bar" data-w="88"></div></div></div>
      <div class="skill-card d6"><div class="sk-icon">🐍</div><div class="sk-name">Python</div><div class="sk-cat">Language</div><div class="sk-bar-wrap"><div class="sk-bar" data-w="72"></div></div></div>
      <div class="skill-card d7"><div class="sk-icon">🐳</div><div class="sk-name">Docker</div><div class="sk-cat">DevOps</div><div class="sk-bar-wrap"><div class="sk-bar" data-w="80"></div></div></div>
      <div class="skill-card d8"><div class="sk-icon">☁️</div><div class="sk-name">AWS</div><div class="sk-cat">Cloud</div><div class="sk-bar-wrap"><div class="sk-bar" data-w="70"></div></div></div>
      <div class="skill-card d9"><div class="sk-icon">🔵</div><div class="sk-name">GCP</div><div class="sk-cat">Cloud</div><div class="sk-bar-wrap"><div class="sk-bar" data-w="65"></div></div></div>
      <div class="skill-card d10"><div class="sk-icon">⚡</div><div class="sk-name">Redis</div><div class="sk-cat">Cache</div><div class="sk-bar-wrap"><div class="sk-bar" data-w="78"></div></div></div>
      <div class="skill-card d11"><div class="sk-icon">📨</div><div class="sk-name">Kafka</div><div class="sk-cat">Messaging</div><div class="sk-bar-wrap"><div class="sk-bar" data-w="68"></div></div></div>
      <div class="skill-card d12"><div class="sk-icon">☸️</div><div class="sk-name">Kubernetes</div><div class="sk-cat">Infra</div><div class="sk-bar-wrap"><div class="sk-bar" data-w="60"></div></div></div>
      <div class="skill-card d13"><div class="sk-icon">🌐</div><div class="sk-name">Socket.io</div><div class="sk-cat">Realtime</div><div class="sk-bar-wrap"><div class="sk-bar" data-w="86"></div></div></div>
      <div class="skill-card d14"><div class="sk-icon">🔩</div><div class="sk-name">NestJS</div><div class="sk-cat">Framework</div><div class="sk-bar-wrap"><div class="sk-bar" data-w="75"></div></div></div>
    </div>
  </div>

  <!-- ═══ TOP LANGUAGES ═══ -->
  <div class="langs-section">
    <div class="sec-label">// top languages</div>
    <div class="lang-row">
      <div class="lang-item d1">
        <div class="lang-name">TypeScript</div>
        <div class="lang-track"><div class="lang-fill" data-w="42" style="background:linear-gradient(90deg,#3178c6,#00e5ff)"></div></div>
        <div class="lang-pct">42%</div>
      </div>
      <div class="lang-item d2">
        <div class="lang-name">JavaScript</div>
        <div class="lang-track"><div class="lang-fill" data-w="30" style="background:linear-gradient(90deg,#f7df1e,#fbbf24)"></div></div>
        <div class="lang-pct">30%</div>
      </div>
      <div class="lang-item d3">
        <div class="lang-name">Python</div>
        <div class="lang-track"><div class="lang-fill" data-w="15" style="background:linear-gradient(90deg,#3572a5,#22c55e)"></div></div>
        <div class="lang-pct">15%</div>
      </div>
      <div class="lang-item d4">
        <div class="lang-name">Shell</div>
        <div class="lang-track"><div class="lang-fill" data-w="8" style="background:linear-gradient(90deg,#7c3aed,#ec4899)"></div></div>
        <div class="lang-pct">8%</div>
      </div>
      <div class="lang-item d5">
        <div class="lang-name">Other</div>
        <div class="lang-track"><div class="lang-fill" data-w="5" style="background:rgba(255,255,255,.3)"></div></div>
        <div class="lang-pct">5%</div>
      </div>
    </div>
  </div>

  <!-- ═══ CONTRIBUTION GRAPH ═══ -->
  <div class="contrib-section">
    <div class="sec-label">// contribution activity</div>
    <div class="contrib-grid" id="contrib-graph"></div>
  </div>

  <!-- ═══ PROJECTS ═══ -->
  <div class="projects-section">
    <div class="sec-label">// featured projects</div>
    <div class="proj-grid">
      <div class="proj-card d1">
        <div class="proj-icon-wrap" style="background:rgba(0,229,255,.1)">⚙️</div>
        <div>
          <div class="proj-title">Automation System</div>
          <div class="proj-desc">IoT device orchestration at scale with real-time control</div>
          <div class="proj-tags">
            <span class="tag">Node.js</span><span class="tag">MQTT</span><span class="tag">Docker</span>
          </div>
        </div>
      </div>
      <div class="proj-card d2">
        <div class="proj-icon-wrap" style="background:rgba(124,58,237,.15)">💪</div>
        <div>
          <div class="proj-title">Fitness Tracker App</div>
          <div class="proj-desc">Full-stack health monitoring with live workout APIs</div>
          <div class="proj-tags">
            <span class="tag">MongoDB</span><span class="tag">Express</span><span class="tag">React</span><span class="tag">Socket.io</span>
          </div>
        </div>
      </div>
      <div class="proj-card d3">
        <div class="proj-icon-wrap" style="background:rgba(34,197,94,.1)">📊</div>
        <div>
          <div class="proj-title">IoT Dashboard</div>
          <div class="proj-desc">Live edge-device data streaming with rich visualizations</div>
          <div class="proj-tags">
            <span class="tag">GCP</span><span class="tag">WebSockets</span><span class="tag">Data Viz</span>
          </div>
        </div>
      </div>
    </div>
  </div>

  <!-- ═══ QUOTE ═══ -->
  <div class="quote">
    <p>"I focus on building scalable systems, writing clean code, and solving real-world problems efficiently."</p>
    <div class="quote-author">Manish Sharma</div>
  </div>

  <!-- ═══ CONNECT ═══ -->
  <div class="connect-section">
    <div class="sec-label">// connect with me</div>
    <div class="connect-grid">
      <a class="connect-btn" href="https://linkedin.com/in/manish-sharma-3065882ab" target="_blank">
        <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M16 8a6 6 0 016 6v7h-4v-7a2 2 0 00-2-2 2 2 0 00-2 2v7h-4v-7a6 6 0 016-6zM2 9h4v12H2z"/><circle cx="4" cy="4" r="2"/></svg>
        LinkedIn
      </a>
      <a class="connect-btn" href="https://twitter.com/const_gaju91" target="_blank">
        <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M23 3a10.9 10.9 0 01-3.14 1.53 4.48 4.48 0 00-7.86 3v1A10.66 10.66 0 013 4s-4 9 5 13a11.64 11.64 0 01-7 2c9 5 20 0 20-11.5a4.5 4.5 0 00-.08-.83A7.72 7.72 0 0023 3z"/></svg>
        Twitter
      </a>
      <a class="connect-btn" href="https://hashnode.com/gajuhere" target="_blank">
        <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M4 4h16v16H4z" rx="4"/></svg>
        Hashnode
      </a>
      <a class="connect-btn" href="https://medium.com/gajuhere" target="_blank">
        <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><ellipse cx="7" cy="12" rx="4" ry="7"/><ellipse cx="17.5" cy="12" rx="2.5" ry="6.5"/><ellipse cx="22" cy="12" rx="1" ry="6"/></svg>
        Medium
      </a>
      <a class="connect-btn" href="https://github.com/sharma481" target="_blank">
        <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 00-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0020 4.77 5.07 5.07 0 0019.91 1S18.73.65 16 2.48a13.38 13.38 0 00-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 005 4.77a5.44 5.44 0 00-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 009 18.13V22"/></svg>
        GitHub
      </a>
    </div>
  </div>

  <!-- FOOTER -->
  <div class="footer">
    <p>Built with <span>❤️</span> by Manish Sharma &nbsp;·&nbsp; <span>@sharma481</span></p>
  </div>

</div>

<script>
/* ── PARTICLES ── */
const canvas = document.getElementById('particles');
const ctx = canvas.getContext('2d');
let W, H, particles = [];

function resize(){
  W = canvas.width = window.innerWidth;
  H = canvas.height = window.innerHeight;
}
resize();
window.addEventListener('resize', resize);

class Particle {
  constructor(){this.reset()}
  reset(){
    this.x = Math.random()*W;
    this.y = Math.random()*H;
    this.vx = (Math.random()-.5)*.4;
    this.vy = (Math.random()-.5)*.4;
    this.r = Math.random()*1.5+.5;
    this.alpha = Math.random()*.4+.1;
  }
  update(){
    this.x+=this.vx; this.y+=this.vy;
    if(this.x<0||this.x>W||this.y<0||this.y>H) this.reset();
  }
  draw(){
    ctx.beginPath();
    ctx.arc(this.x,this.y,this.r,0,Math.PI*2);
    ctx.fillStyle=`rgba(0,229,255,${this.alpha})`;
    ctx.fill();
  }
}

for(let i=0;i<90;i++) particles.push(new Particle());

function loop(){
  ctx.clearRect(0,0,W,H);
  particles.forEach(p=>{p.update();p.draw()});
  // draw lines between nearby particles
  for(let i=0;i<particles.length;i++){
    for(let j=i+1;j<particles.length;j++){
      const dx=particles[i].x-particles[j].x;
      const dy=particles[i].y-particles[j].y;
      const d=Math.sqrt(dx*dx+dy*dy);
      if(d<100){
        ctx.beginPath();
        ctx.moveTo(particles[i].x,particles[i].y);
        ctx.lineTo(particles[j].x,particles[j].y);
        ctx.strokeStyle=`rgba(0,229,255,${.07*(1-d/100)})`;
        ctx.lineWidth=.5;
        ctx.stroke();
      }
    }
  }
  requestAnimationFrame(loop);
}
loop();

/* ── COUNTER ANIMATION ── */
function counter(el, target, suffix, dur){
  let s=0, step=target/(dur/16);
  const t=setInterval(()=>{
    s=Math.min(s+step,target);
    el.textContent=Math.floor(s)+suffix;
    if(s>=target) clearInterval(t);
  },16);
}

window.addEventListener('load',()=>{
  setTimeout(()=>{
    counter(document.getElementById('s-repos'),42,'+',1000);
    counter(document.getElementById('s-commits'),1300,'+',1600);
    counter(document.getElementById('s-stars'),87,'+',1200);
    counter(document.getElementById('s-streak'),87,'',1400);
    counter(document.getElementById('s-prs'),234,'+',1500);
  },300);

  // Animate skill bars
  document.querySelectorAll('.sk-bar').forEach(b=>{
    b.style.width=b.dataset.w+'%';
  });

  // Animate lang bars
  document.querySelectorAll('.lang-fill').forEach(b=>{
    b.style.width=b.dataset.w+'%';
  });
});

/* ── CONTRIBUTION GRAPH ── */
(function(){
  const grid = document.getElementById('contrib-graph');
  const levels = [0,0,0,1,1,1,2,2,3,3,4];
  for(let w=0;w<52;w++){
    const week = document.createElement('div');
    week.className='contrib-week';
    for(let d=0;d<7;d++){
      const day = document.createElement('div');
      const lv = Math.random()<.35 ? 0 : levels[Math.floor(Math.random()*levels.length)];
      day.className='contrib-day c'+lv;
      day.title=`Contributions`;
      week.appendChild(day);
    }
    grid.appendChild(week);
  }
})();
</script>
</body>
</html>
