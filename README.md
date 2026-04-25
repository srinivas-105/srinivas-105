<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Marati Srinivasa Rao — 3D GitHub Profile</title>
<link rel="preconnect" href="https://fonts.googleapis.com"/>
<link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&family=Share+Tech+Mono&family=Rajdhani:wght@300;400;600;700&display=swap" rel="stylesheet"/>
<style>
*{margin:0;padding:0;box-sizing:border-box;}
:root{
  --red:#e94560;--purple:#533483;--navy:#0f3460;
  --dark:#0d1117;--dark2:#1a1a2e;--dark3:#16213e;
  --text:#c9d1d9;
  --gr:0 0 20px #e94560aa,0 0 60px #e9456044;
  --gp:0 0 20px #533483aa,0 0 60px #53348344;
}
html{scroll-behavior:smooth;}
body{background:#0d1117;color:var(--text);font-family:'Rajdhani',sans-serif;overflow-x:hidden;}
#bg-canvas{position:fixed;top:0;left:0;width:100%;height:100%;z-index:0;pointer-events:none;}
body::before{content:'';position:fixed;top:0;left:0;width:100%;height:100%;background:repeating-linear-gradient(0deg,transparent,transparent 2px,rgba(0,0,0,.07) 2px,rgba(0,0,0,.07) 4px);z-index:1;pointer-events:none;}
.wrapper{position:relative;z-index:2;max-width:1100px;margin:0 auto;padding:0 24px;}

/* HERO */
.hero{min-height:100vh;display:flex;flex-direction:column;align-items:center;justify-content:center;text-align:center;padding:60px 24px;position:relative;}
.hero-tag{font-family:'Share Tech Mono',monospace;font-size:.82rem;letter-spacing:.22em;color:var(--red);border:1px solid var(--red);padding:6px 18px;border-radius:2px;margin-bottom:28px;text-transform:uppercase;animation:pulse-border 2.5s infinite;}
@keyframes pulse-border{0%,100%{box-shadow:0 0 0 0 #e9456033;}50%{box-shadow:0 0 0 8px #e9456000;}}
.avatar-scene{perspective:900px;margin:24px auto 32px;width:220px;height:220px;}
.avatar-card{width:100%;height:100%;position:relative;transform-style:preserve-3d;animation:card-float 6s ease-in-out infinite;border-radius:50%;}
@keyframes card-float{0%,100%{transform:rotateX(10deg) rotateY(-10deg) translateY(0);}25%{transform:rotateX(-8deg) rotateY(12deg) translateY(-12px);}50%{transform:rotateX(12deg) rotateY(8deg) translateY(-6px);}75%{transform:rotateX(-10deg) rotateY(-12deg) translateY(-14px);}}
.avatar-face{position:absolute;inset:0;border-radius:50%;border:3px solid var(--red);box-shadow:var(--gr),inset 0 0 30px #e9456022;display:flex;align-items:center;justify-content:center;font-family:'Orbitron',sans-serif;font-size:4.5rem;font-weight:900;background:conic-gradient(from 0deg,#e94560,#533483,#0f3460,#e94560);-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;filter:drop-shadow(0 0 20px #e94560);}
.avatar-ring{position:absolute;inset:-14px;border-radius:50%;border:2px solid transparent;border-top-color:var(--red);border-right-color:var(--purple);animation:rspin 3s linear infinite;}
.avatar-ring2{position:absolute;inset:-26px;border-radius:50%;border:1px solid transparent;border-bottom-color:var(--red);border-left-color:#0f3460;animation:rspin 5s linear infinite reverse;}
@keyframes rspin{to{transform:rotate(360deg);}}
.hero-name{font-family:'Orbitron',sans-serif;font-size:clamp(2.8rem,8vw,6.5rem);font-weight:900;line-height:1;letter-spacing:.04em;background:linear-gradient(135deg,#fff 0%,#e94560 45%,#533483 100%);-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;margin-bottom:8px;animation:nglow 3s ease-in-out infinite alternate;}
@keyframes nglow{from{filter:drop-shadow(0 0 20px #e9456044);}to{filter:drop-shadow(0 0 60px #e94560aa);}}
.hero-sub{font-family:'Orbitron',sans-serif;font-size:clamp(.7rem,2vw,1rem);letter-spacing:.25em;color:#8b949e;margin-bottom:36px;text-transform:uppercase;}
.typing-wrap{font-family:'Share Tech Mono',monospace;font-size:1.05rem;color:var(--red);min-height:1.6em;margin-bottom:36px;}
.cursor{animation:blink .7s step-end infinite;}
@keyframes blink{0%,100%{opacity:1;}50%{opacity:0;}}
.badge-row{display:flex;flex-wrap:wrap;gap:10px;justify-content:center;margin-bottom:14px;}
.badge{font-family:'Share Tech Mono',monospace;font-size:.7rem;letter-spacing:.1em;padding:7px 16px;border-radius:3px;text-transform:uppercase;position:relative;overflow:hidden;transition:all .3s;text-decoration:none;display:inline-block;}
.badge::before{content:'';position:absolute;inset:0;background:linear-gradient(90deg,transparent,rgba(255,255,255,.06),transparent);transform:translateX(-100%);transition:transform .4s;}
.badge:hover::before{transform:translateX(100%);}
.badge-red{background:#e9456011;border:1px solid var(--red);color:var(--red);}
.badge-purple{background:#53348311;border:1px solid var(--purple);color:#a08ad4;}
.badge-blue{background:#0f346011;border:1px solid #1d4ed8;color:#60a5fa;}
.badge-green{background:#22c55e11;border:1px solid #22c55e;color:#22c55e;}
.badge:hover{transform:translateY(-3px);box-shadow:0 8px 24px rgba(0,0,0,.4);}
.scroll-hint{margin-top:40px;display:flex;flex-direction:column;align-items:center;gap:6px;color:#444;font-size:.7rem;letter-spacing:.2em;font-family:'Share Tech Mono',monospace;text-transform:uppercase;animation:sfade 2s ease-in-out infinite;}
.scroll-chevron{width:20px;height:20px;border-right:2px solid #e94560;border-bottom:2px solid #e94560;transform:rotate(45deg);}
@keyframes sfade{0%,100%{opacity:.3;transform:translateY(0);}50%{opacity:1;transform:translateY(8px);}}

/* SECTIONS */
.section{padding:80px 0;}
.divider{width:100%;height:1px;background:linear-gradient(90deg,transparent,#21262d 20%,#21262d 80%,transparent);}
.sec-header{text-align:center;margin-bottom:56px;}
.sec-label{font-family:'Share Tech Mono',monospace;font-size:.73rem;letter-spacing:.3em;color:var(--red);text-transform:uppercase;margin-bottom:12px;display:block;}
.sec-title{font-family:'Orbitron',sans-serif;font-size:clamp(1.6rem,4vw,2.8rem);font-weight:700;background:linear-gradient(135deg,#fff,#8b949e);-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;}
.sec-line{width:80px;height:3px;margin:16px auto 0;background:linear-gradient(90deg,var(--red),var(--purple));border-radius:2px;position:relative;overflow:visible;}
.sec-line::after{content:'';position:absolute;top:50%;left:50%;transform:translate(-50%,-50%);width:10px;height:10px;background:var(--red);border-radius:50%;box-shadow:var(--gr);}

/* ABOUT */
.about-grid{display:grid;grid-template-columns:1fr 1fr;gap:32px;align-items:start;}
@media(max-width:700px){.about-grid{grid-template-columns:1fr;}}
.code-window{background:#0d1117;border:1px solid #30363d;border-radius:12px;overflow:hidden;box-shadow:0 24px 80px rgba(0,0,0,.5),var(--gp);transform:perspective(800px) rotateY(-5deg) rotateX(2deg);transition:transform .4s;}
.code-window:hover{transform:perspective(800px) rotateY(0) rotateX(0);}
.code-bar{background:#161b22;padding:10px 16px;display:flex;align-items:center;gap:8px;border-bottom:1px solid #30363d;}
.code-dot{width:12px;height:12px;border-radius:50%;}
.code-dot:nth-child(1){background:#ff5f57;}.code-dot:nth-child(2){background:#febc2e;}.code-dot:nth-child(3){background:#28c840;}
.code-fname{margin-left:auto;font-family:'Share Tech Mono',monospace;font-size:.68rem;color:#484f58;}
.code-body{padding:20px;font-family:'Share Tech Mono',monospace;font-size:.76rem;line-height:1.9;}
.ck{color:#ff7b72;}.cf{color:#d2a8ff;}.cs{color:#a5d6ff;}.cv{color:#79c0ff;}.cc{color:#484f58;}.cn{color:#f2cc60;}.cp{color:#8b949e;}
.about-info{display:flex;flex-direction:column;gap:16px;}
.info-card{background:#161b22;border:1px solid #21262d;border-radius:10px;padding:16px 20px;transition:all .3s;position:relative;overflow:hidden;}
.info-card::before{content:'';position:absolute;left:0;top:0;bottom:0;width:3px;background:linear-gradient(180deg,var(--red),var(--purple));border-radius:2px 0 0 2px;}
.info-card:hover{border-color:#30363d;transform:translateX(6px);}
.info-label{font-family:'Share Tech Mono',monospace;font-size:.65rem;letter-spacing:.15em;color:var(--red);text-transform:uppercase;margin-bottom:4px;}
.info-val{font-size:.95rem;font-weight:600;color:#e6edf3;}

/* TECH ORB CANVAS */
.orb-wrap{position:relative;width:100%;height:540px;cursor:grab;}
.orb-wrap:active{cursor:grabbing;}
#techCanvas{display:block;width:100%;height:100%;}
.orb-hint{text-align:center;margin-top:10px;font-family:'Share Tech Mono',monospace;font-size:.68rem;color:#484f58;letter-spacing:.15em;text-transform:uppercase;}

/* PROF BARS */
.prof-list{display:flex;flex-direction:column;gap:16px;margin-top:48px;}
.prof-item{background:#161b22;border:1px solid #21262d;border-radius:8px;padding:16px 20px;transition:all .3s;}
.prof-item:hover{border-color:#30363d;transform:translateX(4px);}
.prof-header{display:flex;align-items:center;justify-content:space-between;margin-bottom:10px;}
.prof-name{font-family:'Orbitron',sans-serif;font-size:.78rem;font-weight:700;letter-spacing:.04em;color:#e6edf3;}
.prof-pct{font-family:'Share Tech Mono',monospace;font-size:.78rem;color:var(--red);}
.prof-track{height:8px;background:#0d1117;border-radius:4px;overflow:hidden;}
.prof-fill{height:100%;border-radius:4px;background:linear-gradient(90deg,var(--red),var(--purple),#0f3460);background-size:200% 100%;animation:bshimmer 3s linear infinite;transition:width 1.4s cubic-bezier(.22,1,.36,1);position:relative;}
@keyframes bshimmer{0%{background-position:100% 0;}100%{background-position:-100% 0;}}
.prof-fill::after{content:'';position:absolute;right:0;top:0;bottom:0;width:4px;background:#fff;border-radius:2px;box-shadow:0 0 8px #fff;opacity:.6;}

/* STATS */
.stats-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(200px,1fr));gap:20px;margin-bottom:40px;}
.stat-card{background:#0d1117;border:1px solid #21262d;border-radius:12px;padding:24px;text-align:center;transition:all .4s;position:relative;overflow:hidden;}
.stat-card::before{content:'';position:absolute;bottom:0;left:0;right:0;height:2px;background:linear-gradient(90deg,var(--red),var(--purple));transform:scaleX(0);transition:transform .4s;}
.stat-card:hover::before{transform:scaleX(1);}
.stat-card:hover{border-color:#30363d;transform:translateY(-6px);box-shadow:0 20px 60px rgba(0,0,0,.4);}
.stat-num{font-family:'Orbitron',sans-serif;font-size:2.4rem;font-weight:900;background:linear-gradient(135deg,var(--red),var(--purple));-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;margin-bottom:6px;}
.stat-lbl{font-family:'Share Tech Mono',monospace;font-size:.68rem;letter-spacing:.15em;color:#8b949e;text-transform:uppercase;}

/* PROJECTS */
.projects-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(280px,1fr));gap:24px;}
.proj-card{background:#0d1117;border:1px solid #21262d;border-radius:14px;padding:26px;position:relative;overflow:hidden;text-decoration:none;display:block;transition:all .4s cubic-bezier(.23,1,.32,1);}
.proj-card::before{content:'';position:absolute;inset:0;border-radius:14px;background:linear-gradient(135deg,#e9456008,#53348308);opacity:0;transition:opacity .4s;}
.proj-card:hover::before{opacity:1;}
.proj-card:hover{border-color:var(--red);transform:perspective(800px) rotateX(-4deg) rotateY(4deg) translateY(-8px);box-shadow:var(--gr),0 32px 80px rgba(0,0,0,.5);}
.proj-logo{width:52px;height:52px;border-radius:10px;background:#161b22;border:1px solid #30363d;display:flex;align-items:center;justify-content:center;margin-bottom:16px;overflow:hidden;padding:10px;}
.proj-logo img{width:100%;height:100%;object-fit:contain;}
.proj-name{font-family:'Orbitron',sans-serif;font-size:.92rem;font-weight:700;color:#e6edf3;margin-bottom:8px;letter-spacing:.03em;}
.proj-desc{font-size:.87rem;line-height:1.6;color:#8b949e;margin-bottom:16px;}
.proj-tags{display:flex;flex-wrap:wrap;gap:6px;}
.proj-tag{font-family:'Share Tech Mono',monospace;font-size:.63rem;padding:3px 10px;border-radius:3px;background:#21262d;color:#58a6ff;border:1px solid #30363d;letter-spacing:.04em;}
.proj-corner{position:absolute;top:0;right:0;width:60px;height:60px;background:linear-gradient(135deg,transparent 50%,#e9456011 50%);border-radius:0 14px 0 0;transition:all .4s;}
.proj-card:hover .proj-corner{background:linear-gradient(135deg,transparent 50%,#e9456033 50%);}

/* ROADMAP */
.roadmap{display:flex;flex-direction:column;gap:16px;}
.road-item{background:#161b22;border:1px solid #21262d;border-radius:10px;padding:18px 22px;display:grid;grid-template-columns:200px 1fr 60px;align-items:center;gap:16px;transition:all .3s;}
@media(max-width:600px){.road-item{grid-template-columns:1fr;gap:8px;}}
.road-item:hover{border-color:#30363d;box-shadow:0 8px 32px rgba(0,0,0,.3);}
.road-name{font-family:'Orbitron',sans-serif;font-size:.75rem;font-weight:700;color:#e6edf3;letter-spacing:.04em;}
.road-track{height:10px;background:#0d1117;border-radius:5px;overflow:hidden;}
.road-fill{height:100%;border-radius:5px;background:linear-gradient(90deg,var(--red),var(--purple));position:relative;}
.road-fill::after{content:'';position:absolute;right:0;top:0;bottom:0;width:3px;background:var(--red);border-radius:2px;box-shadow:0 0 10px var(--red);}
.road-pct{font-family:'Share Tech Mono',monospace;font-size:.85rem;color:var(--red);text-align:right;font-weight:700;}

/* CONTACT */
.contact-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(240px,1fr));gap:20px;}
.contact-card{background:#161b22;border:1px solid #21262d;border-radius:12px;padding:22px;display:flex;align-items:center;gap:16px;text-decoration:none;color:inherit;transition:all .35s;}
.contact-card:hover{border-color:var(--red);transform:translateY(-4px) scale(1.02);box-shadow:var(--gr);}
.contact-icon{width:48px;height:48px;border-radius:10px;background:#0d1117;border:1px solid #30363d;display:flex;align-items:center;justify-content:center;flex-shrink:0;transition:all .35s;overflow:hidden;padding:11px;}
.contact-icon img{width:100%;height:100%;object-fit:contain;}
.contact-card:hover .contact-icon{border-color:var(--red);box-shadow:var(--gr);}
.contact-platform{font-family:'Orbitron',sans-serif;font-size:.73rem;font-weight:700;letter-spacing:.06em;color:#8b949e;text-transform:uppercase;margin-bottom:2px;}
.contact-val{font-size:.88rem;color:#e6edf3;word-break:break-all;}

/* FOOTER */
.footer{text-align:center;padding:60px 24px 80px;border-top:1px solid #21262d;}
.footer-name{font-family:'Orbitron',sans-serif;font-size:1.1rem;font-weight:700;letter-spacing:.12em;color:#e6edf3;margin-bottom:8px;}
.footer-sub{font-family:'Share Tech Mono',monospace;font-size:.7rem;letter-spacing:.1em;color:#484f58;}

/* REVEAL */
.reveal{opacity:0;transform:translateY(40px);transition:opacity .7s ease,transform .7s ease;}
.reveal.visible{opacity:1;transform:translateY(0);}
</style>
</head>
<body>
<canvas id="bg-canvas"></canvas>
<div class="wrapper">

  <!-- HERO -->
  <section class="hero">
    <div class="hero-tag">// Full-Stack &nbsp;·&nbsp; AI/ML &nbsp;·&nbsp; Backend Architect</div>
    <div class="avatar-scene">
      <div class="avatar-card">
        <div class="avatar-ring"></div>
        <div class="avatar-ring2"></div>
        <div class="avatar-face">SR</div>
      </div>
    </div>
    <h1 class="hero-name">SRINIVASA RAO</h1>
    <p class="hero-sub">Marati Srinivasa Rao &nbsp;·&nbsp; github.com/srinivas-105</p>
    <div class="typing-wrap"><span id="typed"></span><span class="cursor">|</span></div>
    <div class="badge-row">
      <span class="badge badge-green">Open to Work</span>
      <span class="badge badge-blue">Kurnool, Andhra Pradesh</span>
      <span class="badge badge-purple">CGPA 8.39 / 10</span>
      <span class="badge badge-red">AI/ML + SWE Internships</span>
    </div>
    <div class="badge-row">
      <a href="mailto:m.srinivasarao051@gmail.com" class="badge badge-red">Gmail</a>
      <a href="https://linkedin.com/in/srinivasa-rao-73732b2bb" class="badge badge-blue">LinkedIn</a>
      <a href="https://github.com/srinivas-105" class="badge badge-purple">GitHub</a>
    </div>
    <div class="scroll-hint"><span>Scroll to explore</span><div class="scroll-chevron"></div></div>
  </section>

  <div class="divider"></div>

  <!-- ABOUT -->
  <section class="section">
    <div class="sec-header reveal">
      <span class="sec-label">01 // Who I Am</span>
      <h2 class="sec-title">About Me</h2>
      <div class="sec-line"></div>
    </div>
    <div class="about-grid reveal">
      <div class="code-window">
        <div class="code-bar">
          <div class="code-dot"></div><div class="code-dot"></div><div class="code-dot"></div>
          <span class="code-fname">developer.py</span>
        </div>
        <div class="code-body">
<span class="ck">class</span> <span class="cf">Developer</span><span class="cp">:</span><br>
&nbsp;&nbsp;<span class="ck">def</span> <span class="cf">__init__</span><span class="cp">(</span><span class="cv">self</span><span class="cp">):</span><br>
&nbsp;&nbsp;&nbsp;&nbsp;<span class="cv">self</span><span class="cp">.</span><span class="cn">name</span> <span class="cp">=</span> <span class="cs">"Marati Srinivasa Rao"</span><br>
&nbsp;&nbsp;&nbsp;&nbsp;<span class="cv">self</span><span class="cp">.</span><span class="cn">role</span> <span class="cp">=</span> <span class="cs">"AI/ML Engineer"</span><br>
&nbsp;&nbsp;&nbsp;&nbsp;<span class="cv">self</span><span class="cp">.</span><span class="cn">edu</span>  <span class="cp">=</span> <span class="cs">"B.Tech CSE-AI @ GPCET"</span><br>
&nbsp;&nbsp;&nbsp;&nbsp;<span class="cv">self</span><span class="cp">.</span><span class="cn">cgpa</span> <span class="cp">=</span> <span class="cn">8.39</span><br><br>
&nbsp;&nbsp;&nbsp;&nbsp;<span class="cv">self</span><span class="cp">.</span><span class="cn">languages</span> <span class="cp">= [</span><br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs">"Python"</span><span class="cp">,</span> <span class="cs">"Java"</span><span class="cp">,</span><br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs">"JavaScript"</span><span class="cp">,</span> <span class="cs">"SQL"</span><span class="cp">]</span><br>
&nbsp;&nbsp;&nbsp;&nbsp;<span class="cv">self</span><span class="cp">.</span><span class="cn">ml_stack</span> <span class="cp">= [</span><br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs">"Scikit-learn"</span><span class="cp">,</span><br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs">"OpenCV"</span><span class="cp">,</span> <span class="cs">"NumPy"</span><span class="cp">]</span><br>
&nbsp;&nbsp;&nbsp;&nbsp;<span class="cv">self</span><span class="cp">.</span><span class="cn">backend</span> <span class="cp">= [</span><span class="cs">"Spring Boot"</span><span class="cp">,</span><br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="cs">"REST APIs"</span><span class="cp">,</span> <span class="cs">"MySQL"</span><span class="cp">]</span><br><br>
&nbsp;&nbsp;&nbsp;&nbsp;<span class="cv">self</span><span class="cp">.</span><span class="cn">motto</span> <span class="cp">=</span> <span class="cs">"Engineer systems that<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;think, heal &amp; protect"</span><br><br>
<span class="cc"># Initializing...</span><br>
<span class="cf">me</span> <span class="cp">=</span> <span class="cf">Developer</span><span class="cp">()</span>
        </div>
      </div>
      <div class="about-info">
        <div class="info-card"><div class="info-label">Role</div><div class="info-val">AI/ML Engineer &amp; Backend Architect</div></div>
        <div class="info-card"><div class="info-label">Education</div><div class="info-val">B.Tech CSE-AI · GPCET · CGPA 8.39</div></div>
        <div class="info-card"><div class="info-label">Location</div><div class="info-val">Kurnool, Andhra Pradesh, India</div></div>
        <div class="info-card"><div class="info-label">Phone</div><div class="info-val">+91 7997110446</div></div>
        <div class="info-card"><div class="info-label">Mission</div><div class="info-val">Build AI systems with real-world impact</div></div>
      </div>
    </div>
  </section>

  <div class="divider"></div>

  <!-- TECH STACK — 3D ORB SPHERE -->
  <section class="section">
    <div class="sec-header reveal">
      <span class="sec-label">02 // Technical Arsenal</span>
      <h2 class="sec-title">Tech Stack — 3D Orbit</h2>
      <div class="sec-line"></div>
    </div>
    <div class="reveal">
      <div class="orb-wrap"><canvas id="techCanvas"></canvas></div>
      <p class="orb-hint">Drag to rotate &nbsp;·&nbsp; Hover an orb to highlight</p>
    </div>

    <div class="prof-list reveal">
      <div class="prof-item">
        <div class="prof-header"><span class="prof-name">Python</span><span class="prof-pct">95%</span></div>
        <div class="prof-track"><div class="prof-fill" data-w="95" style="width:0"></div></div>
      </div>
      <div class="prof-item">
        <div class="prof-header"><span class="prof-name">Java</span><span class="prof-pct">88%</span></div>
        <div class="prof-track"><div class="prof-fill" data-w="88" style="width:0"></div></div>
      </div>
      <div class="prof-item">
        <div class="prof-header"><span class="prof-name">Machine Learning</span><span class="prof-pct">82%</span></div>
        <div class="prof-track"><div class="prof-fill" data-w="82" style="width:0"></div></div>
      </div>
      <div class="prof-item">
        <div class="prof-header"><span class="prof-name">Spring Boot</span><span class="prof-pct">78%</span></div>
        <div class="prof-track"><div class="prof-fill" data-w="78" style="width:0"></div></div>
      </div>
      <div class="prof-item">
        <div class="prof-header"><span class="prof-name">Computer Vision</span><span class="prof-pct">72%</span></div>
        <div class="prof-track"><div class="prof-fill" data-w="72" style="width:0"></div></div>
      </div>
      <div class="prof-item">
        <div class="prof-header"><span class="prof-name">JavaScript</span><span class="prof-pct">60%</span></div>
        <div class="prof-track"><div class="prof-fill" data-w="60" style="width:0"></div></div>
      </div>
    </div>
  </section>

  <div class="divider"></div>

  <!-- GITHUB STATS -->
  <section class="section">
    <div class="sec-header reveal">
      <span class="sec-label">03 // GitHub Analytics</span>
      <h2 class="sec-title">By The Numbers</h2>
      <div class="sec-line"></div>
    </div>
    <div class="stats-grid reveal">
      <div class="stat-card"><div class="stat-num">4+</div><div class="stat-lbl">Featured Projects</div></div>
      <div class="stat-card"><div class="stat-num">8.39</div><div class="stat-lbl">CGPA Score</div></div>
      <div class="stat-card"><div class="stat-num">10+</div><div class="stat-lbl">Technologies</div></div>
      <div class="stat-card"><div class="stat-num">100%</div><div class="stat-lbl">Commitment</div></div>
    </div>
    <div class="reveal" style="display:grid;grid-template-columns:repeat(auto-fit,minmax(300px,1fr));gap:20px;">
      <img src="https://github-readme-stats.vercel.app/api?username=srinivas-105&show_icons=true&theme=radical&hide_border=true&bg_color=0d1117&title_color=e94560&icon_color=533483&text_color=c9d1d9&border_radius=12&include_all_commits=true&count_private=true&rank_icon=github" style="width:100%;border-radius:12px;" alt="GitHub Stats"/>
      <img src="https://github-readme-streak-stats.herokuapp.com/?user=srinivas-105&theme=radical&hide_border=true&background=0d1117&ring=e94560&fire=533483&currStreakLabel=e94560&sideLabels=c9d1d9&dates=8b949e&border_radius=12" style="width:100%;border-radius:12px;" alt="Streak"/>
    </div>
    <div class="reveal" style="margin-top:20px;">
      <img src="https://github-readme-activity-graph.vercel.app/graph?username=srinivas-105&theme=redical&hide_border=true&bg_color=0d1117&color=e94560&line=533483&point=e94560&area=true&area_color=e9456020" style="width:100%;border-radius:12px;" alt="Activity"/>
    </div>
  </section>

  <div class="divider"></div>

  <!-- PROJECTS -->
  <section class="section">
    <div class="sec-header reveal">
      <span class="sec-label">04 // What I've Built</span>
      <h2 class="sec-title">Featured Projects</h2>
      <div class="sec-line"></div>
    </div>
    <div class="projects-grid reveal">
      <a href="https://github.com/srinivas-105/HeartDiseaseDetection" class="proj-card">
        <div class="proj-corner"></div>
        <div class="proj-logo"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg" alt="Python"/></div>
        <div class="proj-name">Heart Disease Detection</div>
        <div class="proj-desc">ML-powered cardiac risk assessment using Scikit-learn with high-accuracy classification for early disease detection.</div>
        <div class="proj-tags"><span class="proj-tag">Python</span><span class="proj-tag">Scikit-learn</span><span class="proj-tag">ML</span><span class="proj-tag">Healthcare</span></div>
      </a>
      <a href="https://github.com/srinivas-105/CloudHealthMonitoring" class="proj-card">
        <div class="proj-corner"></div>
        <div class="proj-logo"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/spring/spring-original.svg" alt="Spring Boot"/></div>
        <div class="proj-name">Cloud Health Monitoring</div>
        <div class="proj-desc">Real-time cloud infrastructure health dashboard with automated alerts and intelligent anomaly detection.</div>
        <div class="proj-tags"><span class="proj-tag">Java</span><span class="proj-tag">Spring Boot</span><span class="proj-tag">Cloud</span><span class="proj-tag">REST API</span></div>
      </a>
      <a href="https://github.com/srinivas-105/BankingSpring" class="proj-card">
        <div class="proj-corner"></div>
        <div class="proj-logo"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/java/java-original.svg" alt="Java"/></div>
        <div class="proj-name">Banking Spring System</div>
        <div class="proj-desc">Full-featured banking backend with Spring Boot microservices, JDBC, and MySQL for secure transactions.</div>
        <div class="proj-tags"><span class="proj-tag">Spring Boot</span><span class="proj-tag">MySQL</span><span class="proj-tag">JDBC</span><span class="proj-tag">Microservices</span></div>
      </a>
      <a href="https://github.com/srinivas-105/Sleep-alaram" class="proj-card">
        <div class="proj-corner"></div>
        <div class="proj-logo"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/opencv/opencv-original.svg" alt="OpenCV"/></div>
        <div class="proj-name">Sleep Alarm — CV System</div>
        <div class="proj-desc">Computer vision drowsiness detection using OpenCV eye-tracking to alert drivers in real-time.</div>
        <div class="proj-tags"><span class="proj-tag">Python</span><span class="proj-tag">OpenCV</span><span class="proj-tag">CV</span><span class="proj-tag">Safety</span></div>
      </a>
    </div>
  </section>

  <div class="divider"></div>

  <!-- ROADMAP -->
  <section class="section">
    <div class="sec-header reveal">
      <span class="sec-label">05 // Where I'm Headed</span>
      <h2 class="sec-title">Skill Development Roadmap</h2>
      <div class="sec-line"></div>
    </div>
    <div class="roadmap reveal">
      <div class="road-item"><div class="road-name">Reinforcement Learning</div><div class="road-track"><div class="road-fill" style="width:82%"></div></div><div class="road-pct">82%</div></div>
      <div class="road-item"><div class="road-name">Computer Vision (OpenCV)</div><div class="road-track"><div class="road-fill" style="width:74%"></div></div><div class="road-pct">74%</div></div>
      <div class="road-item"><div class="road-name">Spring Boot Microservices</div><div class="road-track"><div class="road-fill" style="width:66%"></div></div><div class="road-pct">66%</div></div>
      <div class="road-item"><div class="road-name">Cloud &amp; System Design</div><div class="road-track"><div class="road-fill" style="width:50%"></div></div><div class="road-pct">50%</div></div>
      <div class="road-item"><div class="road-name">Docker &amp; DevOps</div><div class="road-track"><div class="road-fill" style="width:34%"></div></div><div class="road-pct">34%</div></div>
    </div>
  </section>

  <div class="divider"></div>

  <!-- CONTACT -->
  <section class="section">
    <div class="sec-header reveal">
      <span class="sec-label">06 // Let's Connect</span>
      <h2 class="sec-title">Get In Touch</h2>
      <div class="sec-line"></div>
    </div>
    <div class="contact-grid reveal">
      <a href="mailto:m.srinivasarao051@gmail.com" class="contact-card">
        <div class="contact-icon"><img src="https://cdn.simpleicons.org/gmail/ea4335" alt="Gmail"/></div>
        <div><div class="contact-platform">Email</div><div class="contact-val">m.srinivasarao051@gmail.com</div></div>
      </a>
      <a href="https://linkedin.com/in/srinivasa-rao-73732b2bb" class="contact-card">
        <div class="contact-icon"><img src="https://cdn.simpleicons.org/linkedin/0077b5" alt="LinkedIn"/></div>
        <div><div class="contact-platform">LinkedIn</div><div class="contact-val">srinivasa-rao-73732b2bb</div></div>
      </a>
      <a href="https://github.com/srinivas-105" class="contact-card">
        <div class="contact-icon"><img src="https://cdn.simpleicons.org/github/ffffff" alt="GitHub"/></div>
        <div><div class="contact-platform">GitHub</div><div class="contact-val">github.com/srinivas-105</div></div>
      </a>
      <div class="contact-card">
        <div class="contact-icon" style="font-family:'Orbitron',sans-serif;font-size:.68rem;font-weight:700;color:var(--red);padding:0;display:flex;align-items:center;justify-content:center;">TEL</div>
        <div><div class="contact-platform">Phone</div><div class="contact-val">+91 7997110446</div></div>
      </div>
    </div>
  </section>

</div>

<footer class="footer">
  <div class="footer-name">MARATI SRINIVASA RAO</div>
  <div class="footer-sub">From Kurnool, India &nbsp;·&nbsp; Engineering Intelligent Solutions &nbsp;·&nbsp; github.com/srinivas-105</div>
  <br>
  <div class="footer-sub" style="color:#30363d;">CSS 3D &nbsp;·&nbsp; Canvas Particle Field &nbsp;·&nbsp; Real Devicon Logos &nbsp;·&nbsp; Interactive 3D Sphere</div>
</footer>

<script>
/* ══════════════════════════════════
   PARTICLE BACKGROUND
══════════════════════════════════ */
(function(){
  const cv=document.getElementById('bg-canvas'),ctx=cv.getContext('2d');
  let W,H,pts=[];
  function resize(){W=cv.width=innerWidth;H=cv.height=innerHeight;}
  resize();addEventListener('resize',resize);
  function P(){
    this.reset=function(){this.x=Math.random()*W;this.y=Math.random()*H;this.z=Math.random();this.r=this.z*1.6+.3;this.vx=(Math.random()-.5)*.35;this.vy=(Math.random()-.5)*.35;this.a=this.z*.7+.1;this.red=Math.random()<.15;};
    this.update=function(){this.x+=this.vx;this.y+=this.vy;if(this.x<0||this.x>W||this.y<0||this.y>H)this.reset();};
    this.draw=function(){ctx.beginPath();ctx.arc(this.x,this.y,this.r,0,Math.PI*2);ctx.fillStyle=this.red?`rgba(233,69,96,${this.a})`:`rgba(83,52,131,${this.a})`;ctx.fill();};
    this.reset();
  }
  for(let i=0;i<130;i++){const p=new P();pts.push(p);}
  function grid(){ctx.strokeStyle='rgba(20,30,50,.28)';ctx.lineWidth=.5;for(let x=0;x<W;x+=60){ctx.beginPath();ctx.moveTo(x,0);ctx.lineTo(x,H);ctx.stroke();}for(let y=0;y<H;y+=60){ctx.beginPath();ctx.moveTo(0,y);ctx.lineTo(W,y);ctx.stroke();}}
  function conns(){for(let i=0;i<pts.length;i++)for(let j=i+1;j<pts.length;j++){const dx=pts[i].x-pts[j].x,dy=pts[i].y-pts[j].y,d=Math.hypot(dx,dy);if(d<110){ctx.strokeStyle=`rgba(233,69,96,${(1-d/110)*.1})`;ctx.lineWidth=.5;ctx.beginPath();ctx.moveTo(pts[i].x,pts[i].y);ctx.lineTo(pts[j].x,pts[j].y);ctx.stroke();}}}
  (function loop(){ctx.clearRect(0,0,W,H);grid();conns();pts.forEach(p=>{p.update();p.draw();});requestAnimationFrame(loop);})();
})();

/* ══════════════════════════════════
   3D TECH SPHERE ORBS
══════════════════════════════════ */
(function(){
  const cv = document.getElementById('techCanvas');
  const ctx = cv.getContext('2d');

  const TECHS = [
    {name:'Python',  src:'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg',    col:'#3776AB'},
    {name:'Java',    src:'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/java/java-original.svg',        col:'#ED8B00'},
    {name:'Spring',  src:'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/spring/spring-original.svg',    col:'#6DB33F'},
    {name:'JS',      src:'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg', col:'#F7DF1E'},
    {name:'React',   src:'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/react/react-original.svg',      col:'#61DAFB'},
    {name:'MySQL',   src:'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mysql/mysql-original.svg',      col:'#4479A1'},
    {name:'Git',     src:'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/git/git-original.svg',          col:'#F05032'},
    {name:'Linux',   src:'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/linux/linux-original.svg',      col:'#FCC624'},
    {name:'HTML5',   src:'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg',      col:'#E34F26'},
    {name:'CSS3',    src:'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg',        col:'#1572B6'},
    {name:'OpenCV',  src:'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/opencv/opencv-original.svg',    col:'#5C3EE8'},
    {name:'Node.js', src:'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nodejs/nodejs-original.svg',    col:'#339933'},
    {name:'VS Code', src:'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vscode/vscode-original.svg',    col:'#007ACC'},
    {name:'GitHub',  src:'https://cdn.simpleicons.org/github/ffffff',                                        col:'#aaaaaa'},
    {name:'Postman', src:'https://cdn.simpleicons.org/postman/ff6c37',                                       col:'#FF6C37'},
    {name:'NumPy',   src:'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/numpy/numpy-original.svg',      col:'#4DABCF'},
  ];

  const imgs = {};
  TECHS.forEach(t => {
    const img = new Image();
    img.crossOrigin = 'anonymous';
    img.src = t.src;
    img.onload = () => { imgs[t.name] = img; };
  });

  // Fibonacci sphere distribution
  const R = 185;
  const PHI = Math.PI * (Math.sqrt(5) - 1);
  const POS = TECHS.map((_, i) => {
    const y1 = 1 - (i / (TECHS.length - 1)) * 2;
    const rad = Math.sqrt(1 - y1 * y1);
    const theta = PHI * i;
    return { ox: Math.cos(theta) * rad * R, oy: y1 * R, oz: Math.sin(theta) * rad * R };
  });

  let rotX = 0.25, rotY = 0;
  let velX = 0, velY = 0.003;
  let drag = false, lmx = 0, lmy = 0;
  let hovIdx = -1;

  function resize() {
    const wrap = cv.parentElement;
    cv.width = wrap.offsetWidth || 800;
    cv.height = 540;
  }
  resize();
  window.addEventListener('resize', resize);

  cv.addEventListener('mousedown', e => { drag = true; lmx = e.clientX; lmy = e.clientY; cv.style.cursor = 'grabbing'; });
  window.addEventListener('mouseup', () => { drag = false; cv.style.cursor = 'grab'; });
  window.addEventListener('mousemove', e => {
    if (drag) {
      const dx = e.clientX - lmx, dy = e.clientY - lmy;
      velX = dy * 0.006; velY = dx * 0.006;
      rotX += velX; rotY += velY;
      lmx = e.clientX; lmy = e.clientY;
    }
    const rect = cv.getBoundingClientRect();
    const mx = (e.clientX - rect.left) * (cv.width / rect.width);
    const my = (e.clientY - rect.top) * (cv.height / rect.height);
    const projected = project();
    hovIdx = -1;
    // check front to back
    const sorted = [...projected].sort((a,b) => b.z - a.z);
    for (const p of sorted) {
      if (Math.hypot(mx - (cv.width/2 + p.sx), my - (cv.height/2 + p.sy)) < p.r + 6) {
        hovIdx = p.idx; break;
      }
    }
    cv.style.cursor = hovIdx >= 0 ? 'pointer' : (drag ? 'grabbing' : 'grab');
  });

  // Touch support
  let tlast = null;
  cv.addEventListener('touchstart', e => { tlast = e.touches[0]; });
  cv.addEventListener('touchmove', e => {
    e.preventDefault();
    const t = e.touches[0];
    const dx = t.clientX - tlast.clientX, dy = t.clientY - tlast.clientY;
    velX = dy * 0.006; velY = dx * 0.006;
    rotX += velX; rotY += velY;
    tlast = t;
  }, {passive:false});

  function rot3(x, y, z, rx, ry) {
    const cy = Math.cos(ry), sy = Math.sin(ry);
    const nx = x*cy + z*sy, nz = -x*sy + z*cy;
    const cx2 = Math.cos(rx), sx2 = Math.sin(rx);
    const ny = y*cx2 - nz*sx2, nz2 = y*sx2 + nz*cx2;
    return {x: nx, y: ny, z: nz2};
  }

  function project() {
    const FOV = 650;
    return POS.map((p, i) => {
      const r3 = rot3(p.ox, p.oy, p.oz, rotX, rotY);
      const s = FOV / (FOV - r3.z);
      const depth = (r3.z + R) / (2 * R);
      const radius = Math.max(26, 38 * s * 0.55);
      return { sx: r3.x * s, sy: r3.y * s, z: r3.z, depth, r: radius, idx: i };
    });
  }

  function hexRgb(h) {
    const c = h.replace('#','');
    if (c.length < 6) return {r:128,g:128,b:128};
    return { r: parseInt(c.slice(0,2),16)||128, g: parseInt(c.slice(2,4),16)||128, b: parseInt(c.slice(4,6),16)||128 };
  }

  function drawOrb(x, y, r, col, img, hov, depth) {
    const {r:cr,g:cg,b:cb} = hexRgb(col);
    const a = 0.38 + depth * 0.52;
    ctx.save();
    ctx.translate(x, y);

    // Drop shadow
    ctx.shadowColor = 'rgba(0,0,0,0.7)';
    ctx.shadowBlur = 22;
    ctx.shadowOffsetX = 5; ctx.shadowOffsetY = 8;

    // Sphere body — radial gradient for 3D look
    const grd = ctx.createRadialGradient(-r*.32, -r*.38, r*.06, 0, 0, r);
    grd.addColorStop(0,   `rgba(${Math.min(255,cr+100)},${Math.min(255,cg+100)},${Math.min(255,cb+100)},${a})`);
    grd.addColorStop(0.35,`rgba(${cr},${cg},${cb},${a})`);
    grd.addColorStop(0.8, `rgba(${Math.max(0,cr-70)},${Math.max(0,cg-70)},${Math.max(0,cb-70)},${a})`);
    grd.addColorStop(1,   `rgba(${Math.max(0,cr-120)},${Math.max(0,cg-120)},${Math.max(0,cb-120)},${a*.75})`);
    ctx.beginPath();
    ctx.arc(0, 0, r, 0, Math.PI*2);
    ctx.fillStyle = grd;
    ctx.fill();

    ctx.shadowBlur = 0; ctx.shadowOffsetX = 0; ctx.shadowOffsetY = 0;

    // Border
    ctx.strokeStyle = hov ? '#e94560' : `rgba(${cr},${cg},${cb},${0.25 + depth*.45})`;
    ctx.lineWidth = hov ? 2.5 : 1;
    ctx.stroke();

    // Hover outer glow ring
    if (hov) {
      ctx.save();
      ctx.strokeStyle = 'rgba(233,69,96,0.55)';
      ctx.lineWidth = 3;
      ctx.shadowColor = '#e94560';
      ctx.shadowBlur = 25;
      ctx.beginPath();
      ctx.arc(0, 0, r + 5, 0, Math.PI*2);
      ctx.stroke();
      ctx.restore();
    }

    // Logo image clipped inside sphere
    if (img && img.complete && img.naturalWidth > 0) {
      ctx.save();
      ctx.beginPath();
      ctx.arc(0, 0, r * 0.58, 0, Math.PI*2);
      ctx.clip();
      const lr = r * 0.58;
      ctx.drawImage(img, -lr, -lr, lr*2, lr*2);
      ctx.restore();
    } else {
      // Fallback: tech name text
      ctx.fillStyle = `rgba(220,230,240,${a})`;
      ctx.font = `700 ${Math.max(7,r*0.25)}px Orbitron,sans-serif`;
      ctx.textAlign = 'center';
      ctx.textBaseline = 'middle';
      ctx.fillText(TECHS[0] ? '' : '', 0, 0);
    }

    // Specular highlight (top-left sheen)
    const hl = ctx.createRadialGradient(-r*.35,-r*.4,0, -r*.22,-r*.28, r*.52);
    hl.addColorStop(0,   `rgba(255,255,255,${.22 + depth*.1})`);
    hl.addColorStop(0.55,`rgba(255,255,255,.04)`);
    hl.addColorStop(1,   'rgba(255,255,255,0)');
    ctx.beginPath();
    ctx.arc(0, 0, r, 0, Math.PI*2);
    ctx.fillStyle = hl;
    ctx.fill();

    ctx.restore();

    // Name label — only show for front-facing orbs or hovered
    if (hov || depth > 0.62) {
      const la = hov ? 1 : (depth - 0.62) / 0.38;
      ctx.save();
      ctx.font = `600 ${Math.max(9,r*.3)}px Rajdhani,sans-serif`;
      ctx.textAlign = 'center';
      ctx.textBaseline = 'top';
      ctx.fillStyle = `rgba(${hov?'233,69,96':'190,200,215'},${la * .9})`;
      ctx.fillText(TECHS[hovIdx >= 0 && hovIdx === POS.indexOf(POS.find((_,i)=>i===hovIdx)) ? hovIdx : 0] ? '' : '', x, y + r + 5);
      ctx.restore();
    }
  }

  function drawLabel(x, y, r, name, hov, depth) {
    if (!hov && depth <= 0.58) return;
    const la = hov ? 1 : (depth - 0.58) / 0.42;
    ctx.save();
    ctx.font = `600 ${Math.max(9, r * 0.3)}px Rajdhani, sans-serif`;
    ctx.textAlign = 'center';
    ctx.textBaseline = 'top';
    ctx.fillStyle = hov ? `rgba(233,69,96,${la})` : `rgba(180,192,210,${la * .85})`;
    ctx.fillText(name, x, y + r + 6);
    ctx.restore();
  }

  function frame() {
    if (!drag) {
      velX *= 0.97;
      velY = velY * 0.98 + 0.0028 * (1 - Math.abs(velY)/0.015);
      rotY += velY;
      rotX += velX;
    }

    const W = cv.width, H = cv.height;
    ctx.clearRect(0, 0, W, H);
    const cx = W/2, cy = H/2;

    const proj = project().sort((a,b) => a.z - b.z); // back to front

    proj.forEach(p => {
      const t = TECHS[p.idx];
      drawOrb(cx + p.sx, cy + p.sy, p.r, t.col, imgs[t.name] || null, p.idx === hovIdx, p.depth);
    });

    proj.forEach(p => {
      const t = TECHS[p.idx];
      drawLabel(cx + p.sx, cy + p.sy, p.r, t.name, p.idx === hovIdx, p.depth);
    });

    requestAnimationFrame(frame);
  }
  requestAnimationFrame(frame);
})();

/* ══════════════════════════════════
   TYPING ANIMATION
══════════════════════════════════ */
(function(){
  const lines=["Building Intelligent Systems","Spring Boot Microservices Architect","Machine Learning · Computer Vision","Python · Java · OpenCV · Scikit-Learn","Open for AI/ML & SWE Internships"];
  let li=0,ci=0,del=false;
  const el=document.getElementById('typed');
  function tick(){
    const line=lines[li];
    if(!del){el.textContent=line.slice(0,++ci);if(ci===line.length){setTimeout(()=>{del=true;tick();},1800);return;}}
    else{el.textContent=line.slice(0,--ci);if(ci===0){del=false;li=(li+1)%lines.length;}}
    setTimeout(tick,del?38:58);
  }
  tick();
})();

/* ══════════════════════════════════
   SCROLL REVEAL
══════════════════════════════════ */
const revObs = new IntersectionObserver(es=>es.forEach(e=>{if(e.isIntersecting){e.target.classList.add('visible');revObs.unobserve(e.target);}}),{threshold:.1});
document.querySelectorAll('.reveal').forEach(el=>revObs.observe(el));

/* ══════════════════════════════════
   PROGRESS BARS
══════════════════════════════════ */
const barObs = new IntersectionObserver(es=>es.forEach(e=>{if(e.isIntersecting){setTimeout(()=>{e.target.style.width=e.target.getAttribute('data-w')+'%';},250);barObs.unobserve(e.target);}}),{threshold:.1});
document.querySelectorAll('.prof-fill').forEach(b=>barObs.observe(b));

/* ══════════════════════════════════
   PROJECT CARD 3D TILT
══════════════════════════════════ */
document.querySelectorAll('.proj-card').forEach(card=>{
  card.addEventListener('mousemove',e=>{
    const r=card.getBoundingClientRect();
    const dx=(e.clientX-r.left-r.width/2)/r.width*2;
    const dy=(e.clientY-r.top-r.height/2)/r.height*2;
    card.style.transform=`perspective(800px) rotateX(${-dy*6}deg) rotateY(${dx*8}deg) translateY(-8px)`;
  });
  card.addEventListener('mouseleave',()=>card.style.transform='');
});
</script>
</body>
</html>
