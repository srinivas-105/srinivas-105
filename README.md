<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Marati Srinivasa Rao — Portfolio Sections</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@700;900&family=Rajdhani:wght@400;600;700&display=swap');

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    background: #04020f;
    color: #e2e0f0;
    font-family: 'Rajdhani', sans-serif;
    min-height: 100vh;
    padding: 60px 40px;
  }

  /* ── SECTION HEADING ── */
  .section-heading {
    text-align: center;
    margin-bottom: 48px;
  }
  .section-heading h2 {
    font-family: 'Orbitron', monospace;
    font-size: 28px;
    font-weight: 900;
    color: #fff;
    letter-spacing: 3px;
    position: relative;
    display: inline-block;
  }
  .section-heading h2::after {
    content: '';
    display: block;
    margin: 10px auto 0;
    width: 60%;
    height: 2px;
    background: linear-gradient(90deg, transparent, #7c3aed, #a78bfa, #7c3aed, transparent);
  }

  /* ── SUBSECTION LABEL ── */
  .sub-label {
    text-align: center;
    font-family: 'Orbitron', monospace;
    font-size: 13px;
    letter-spacing: 4px;
    color: #a78bfa;
    margin-bottom: 24px;
    margin-top: 40px;
    text-transform: uppercase;
  }

  /* ── 3D BADGE GRID ── */
  .badge-grid {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 16px;
    margin-bottom: 8px;
    perspective: 800px;
  }

  /* ── 3D BADGE CARD ── */
  .badge-card {
    position: relative;
    display: flex;
    align-items: center;
    gap: 10px;
    padding: 10px 20px;
    border-radius: 10px;
    cursor: pointer;
    transform-style: preserve-3d;
    transform: perspective(400px) rotateX(0deg) rotateY(0deg) translateZ(0);
    transition: transform 0.15s ease, box-shadow 0.15s ease;
    min-width: 140px;
  }
  .badge-card::before {
    content: '';
    position: absolute;
    inset: 0;
    border-radius: 10px;
    background: linear-gradient(135deg, rgba(255,255,255,0.12) 0%, transparent 60%);
    pointer-events: none;
    z-index: 2;
  }
  .badge-card::after {
    content: '';
    position: absolute;
    bottom: -8px;
    left: 10%;
    width: 80%;
    height: 10px;
    border-radius: 50%;
    background: rgba(124,58,237,0.4);
    filter: blur(6px);
    transform: translateY(4px);
    transition: opacity 0.15s ease, transform 0.15s ease;
    z-index: -1;
  }
  .badge-card:hover {
    transform: perspective(400px) rotateX(-8deg) rotateY(6deg) translateZ(16px) scale(1.06);
  }
  .badge-card:hover::after {
    opacity: 0.7;
    transform: translateY(8px) scaleX(1.1);
  }

  .badge-card .icon {
    width: 26px;
    height: 26px;
    flex-shrink: 0;
    object-fit: contain;
    filter: drop-shadow(0 2px 4px rgba(0,0,0,0.5));
  }
  .badge-card .label {
    font-family: 'Rajdhani', sans-serif;
    font-weight: 700;
    font-size: 14px;
    letter-spacing: 1.5px;
    color: #fff;
    text-transform: uppercase;
    text-shadow: 0 1px 3px rgba(0,0,0,0.6);
  }

  /* colour themes per badge */
  .b-python   { background: linear-gradient(135deg,#1e3a5f,#3776AB); box-shadow: 0 6px 20px rgba(55,118,171,0.45), inset 0 1px 0 rgba(255,255,255,0.18); }
  .b-java     { background: linear-gradient(135deg,#5a3500,#ED8B00); box-shadow: 0 6px 20px rgba(237,139,0,0.45),   inset 0 1px 0 rgba(255,255,255,0.18); }
  .b-js       { background: linear-gradient(135deg,#4a4000,#F7DF1E); box-shadow: 0 6px 20px rgba(247,223,30,0.45),  inset 0 1px 0 rgba(255,255,255,0.18); }
  .b-js .label{ color: #111; }
  .b-sql      { background: linear-gradient(135deg,#0d2a4a,#4479A1); box-shadow: 0 6px 20px rgba(68,121,161,0.45),  inset 0 1px 0 rgba(255,255,255,0.18); }
  .b-html     { background: linear-gradient(135deg,#5a1a00,#E34F26); box-shadow: 0 6px 20px rgba(227,79,38,0.45),   inset 0 1px 0 rgba(255,255,255,0.18); }
  .b-css      { background: linear-gradient(135deg,#0a2a5a,#1572B6); box-shadow: 0 6px 20px rgba(21,114,182,0.45),  inset 0 1px 0 rgba(255,255,255,0.18); }
  .b-sklearn  { background: linear-gradient(135deg,#5a3000,#F7931E); box-shadow: 0 6px 20px rgba(247,147,30,0.45),  inset 0 1px 0 rgba(255,255,255,0.18); }
  .b-opencv   { background: linear-gradient(135deg,#1a0a5a,#5C3EE8); box-shadow: 0 6px 20px rgba(92,62,232,0.45),   inset 0 1px 0 rgba(255,255,255,0.18); }
  .b-numpy    { background: linear-gradient(135deg,#0a3050,#4DABCF); box-shadow: 0 6px 20px rgba(77,171,207,0.45),  inset 0 1px 0 rgba(255,255,255,0.18); }
  .b-pandas   { background: linear-gradient(135deg,#06041a,#150458); box-shadow: 0 6px 20px rgba(21,4,88,0.6),      inset 0 1px 0 rgba(255,255,255,0.18); }
  .b-mpl      { background: linear-gradient(135deg,#04101f,#11557c); box-shadow: 0 6px 20px rgba(17,85,124,0.45),   inset 0 1px 0 rgba(255,255,255,0.18); }
  .b-spring   { background: linear-gradient(135deg,#1a3a0a,#6DB33F); box-shadow: 0 6px 20px rgba(109,179,63,0.45),  inset 0 1px 0 rgba(255,255,255,0.18); }
  .b-mysql    { background: linear-gradient(135deg,#0d2a4a,#4479A1); box-shadow: 0 6px 20px rgba(68,121,161,0.45),  inset 0 1px 0 rgba(255,255,255,0.18); }
  .b-rest     { background: linear-gradient(135deg,#4a2000,#FF6C37); box-shadow: 0 6px 20px rgba(255,108,55,0.45),  inset 0 1px 0 rgba(255,255,255,0.18); }
  .b-jdbc     { background: linear-gradient(135deg,#5a3500,#ED8B00); box-shadow: 0 6px 20px rgba(237,139,0,0.45),   inset 0 1px 0 rgba(255,255,255,0.18); }
  .b-micro    { background: linear-gradient(135deg,#1a3a0a,#6DB33F); box-shadow: 0 6px 20px rgba(109,179,63,0.45),  inset 0 1px 0 rgba(255,255,255,0.18); }
  .b-git      { background: linear-gradient(135deg,#4a1000,#F05032); box-shadow: 0 6px 20px rgba(240,80,50,0.45),   inset 0 1px 0 rgba(255,255,255,0.18); }
  .b-github   { background: linear-gradient(135deg,#1a0a3a,#a78bfa); box-shadow: 0 6px 20px rgba(167,139,250,0.45), inset 0 1px 0 rgba(255,255,255,0.18); }
  .b-linux    { background: linear-gradient(135deg,#3a3000,#FCC624); box-shadow: 0 6px 20px rgba(252,198,36,0.45),  inset 0 1px 0 rgba(255,255,255,0.18); }
  .b-linux .label { color: #111; }
  .b-vscode   { background: linear-gradient(135deg,#001a4a,#007ACC); box-shadow: 0 6px 20px rgba(0,122,204,0.45),   inset 0 1px 0 rgba(255,255,255,0.18); }
  .b-ij       { background: linear-gradient(135deg,#0a0a0a,#1e1e1e); box-shadow: 0 6px 20px rgba(90,60,200,0.45),   inset 0 1px 0 rgba(255,255,255,0.18); }
  .b-postman  { background: linear-gradient(135deg,#4a2000,#FF6C37); box-shadow: 0 6px 20px rgba(255,108,55,0.45),  inset 0 1px 0 rgba(255,255,255,0.18); }

  /* ── DIVIDER ── */
  .divider {
    height: 1px;
    background: linear-gradient(90deg, transparent, #7c3aed44, #a78bfa66, #7c3aed44, transparent);
    margin: 60px 0;
  }

  /* ── CONNECT SECTION ── */
  .connect-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 20px;
    max-width: 840px;
    margin: 0 auto 40px;
    perspective: 1000px;
  }

  .connect-card {
    position: relative;
    border-radius: 16px;
    padding: 24px 16px 20px;
    text-align: center;
    cursor: pointer;
    transform-style: preserve-3d;
    transform: perspective(600px) rotateX(0) rotateY(0) translateZ(0);
    transition: transform 0.15s ease, box-shadow 0.15s ease;
    text-decoration: none;
    display: block;
  }
  .connect-card::before {
    content: '';
    position: absolute;
    inset: 0;
    border-radius: 16px;
    background: linear-gradient(160deg, rgba(255,255,255,0.14) 0%, transparent 55%);
    pointer-events: none;
    z-index: 2;
  }
  .connect-card::after {
    content: '';
    position: absolute;
    bottom: -12px;
    left: 15%;
    width: 70%;
    height: 14px;
    border-radius: 50%;
    filter: blur(8px);
    opacity: 0.5;
    transition: opacity 0.15s, transform 0.15s;
    z-index: -1;
  }
  .connect-card:hover {
    transform: perspective(600px) rotateX(-10deg) rotateY(5deg) translateZ(20px) scale(1.05);
  }
  .connect-card:hover::after {
    opacity: 0.8;
    transform: translateY(6px);
  }

  .connect-card .c-icon {
    width: 40px;
    height: 40px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    margin: 0 auto 12px;
    font-size: 20px;
  }
  .connect-card .c-title {
    font-family: 'Orbitron', monospace;
    font-size: 11px;
    font-weight: 700;
    letter-spacing: 2px;
    color: #fff;
    margin-bottom: 8px;
  }
  .connect-card .c-sub {
    font-size: 11px;
    color: rgba(255,255,255,0.65);
    word-break: break-all;
  }

  .cc-gmail   { background: linear-gradient(145deg,#5a0a00,#EA4335); box-shadow: 0 8px 30px rgba(234,67,53,0.5),  inset 0 1px 0 rgba(255,255,255,0.2); }
  .cc-gmail::after   { background: #EA4335; }
  .cc-linkedin{ background: linear-gradient(145deg,#002244,#0A66C2); box-shadow: 0 8px 30px rgba(10,102,194,0.5), inset 0 1px 0 rgba(255,255,255,0.2); }
  .cc-linkedin::after{ background: #0A66C2; }
  .cc-github  { background: linear-gradient(145deg,#1a0a3a,#7c3aed); box-shadow: 0 8px 30px rgba(124,58,237,0.5),inset 0 1px 0 rgba(255,255,255,0.2); }
  .cc-github::after  { background: #7c3aed; }
  .cc-wa      { background: linear-gradient(145deg,#003a14,#25D366); box-shadow: 0 8px 30px rgba(37,211,102,0.5), inset 0 1px 0 rgba(255,255,255,0.2); }
  .cc-wa::after      { background: #25D366; }

  /* ── STATS ROW ── */
  .stats-row {
    display: flex;
    justify-content: center;
    gap: 20px;
    flex-wrap: wrap;
  }
  .stat-pill {
    display: flex;
    align-items: center;
    gap: 0;
    border-radius: 8px;
    overflow: hidden;
    box-shadow: 0 4px 16px rgba(124,58,237,0.3), inset 0 1px 0 rgba(255,255,255,0.1);
    transform: perspective(300px) rotateX(-4deg);
    transition: transform 0.15s;
  }
  .stat-pill:hover {
    transform: perspective(300px) rotateX(-8deg) scale(1.05);
  }
  .stat-pill .pill-label {
    background: #1a0533;
    padding: 8px 14px;
    font-family: 'Rajdhani', sans-serif;
    font-weight: 700;
    font-size: 12px;
    letter-spacing: 1.5px;
    color: #c9b8fa;
    text-transform: uppercase;
  }
  .stat-pill .pill-val {
    padding: 8px 14px;
    font-family: 'Orbitron', monospace;
    font-size: 12px;
    font-weight: 700;
    color: #fff;
  }
  .pv .pill-val { background: #7c3aed; }
  .fo .pill-val { background: #a78bfa; color: #1a0533; }
  .st .pill-val { background: #e879f9; color: #1a0533; }
</style>
</head>
<body>

<!-- ══════════ TECH ARSENAL ══════════ -->
<div class="section-heading">
  <h2>🛠&nbsp; Tech Arsenal</h2>
</div>

<p class="sub-label">🔤 Languages</p>
<div class="badge-grid">
  <div class="badge-card b-python">
    <img class="icon" src="https://cdn.jsdelivr.net/npm/simple-icons@v10/icons/python.svg" style="filter:invert(1)"/>
    <span class="label">Python</span>
  </div>
  <div class="badge-card b-java">
    <img class="icon" src="https://cdn.jsdelivr.net/npm/simple-icons@v10/icons/openjdk.svg" style="filter:invert(1)"/>
    <span class="label">Java</span>
  </div>
  <div class="badge-card b-js">
    <img class="icon" src="https://cdn.jsdelivr.net/npm/simple-icons@v10/icons/javascript.svg"/>
    <span class="label">JavaScript</span>
  </div>
  <div class="badge-card b-sql">
    <img class="icon" src="https://cdn.jsdelivr.net/npm/simple-icons@v10/icons/mysql.svg" style="filter:invert(1)"/>
    <span class="label">SQL</span>
  </div>
  <div class="badge-card b-html">
    <img class="icon" src="https://cdn.jsdelivr.net/npm/simple-icons@v10/icons/html5.svg" style="filter:invert(1)"/>
    <span class="label">HTML5</span>
  </div>
  <div class="badge-card b-css">
    <img class="icon" src="https://cdn.jsdelivr.net/npm/simple-icons@v10/icons/css3.svg" style="filter:invert(1)"/>
    <span class="label">CSS3</span>
  </div>
</div>

<p class="sub-label">🤖 AI / ML & Data Science</p>
<div class="badge-grid">
  <div class="badge-card b-sklearn">
    <img class="icon" src="https://cdn.jsdelivr.net/npm/simple-icons@v10/icons/scikitlearn.svg" style="filter:invert(1)"/>
    <span class="label">Scikit-Learn</span>
  </div>
  <div class="badge-card b-opencv">
    <img class="icon" src="https://cdn.jsdelivr.net/npm/simple-icons@v10/icons/opencv.svg" style="filter:invert(1)"/>
    <span class="label">OpenCV</span>
  </div>
  <div class="badge-card b-numpy">
    <img class="icon" src="https://cdn.jsdelivr.net/npm/simple-icons@v10/icons/numpy.svg" style="filter:invert(1)"/>
    <span class="label">NumPy</span>
  </div>
  <div class="badge-card b-pandas">
    <img class="icon" src="https://cdn.jsdelivr.net/npm/simple-icons@v10/icons/pandas.svg" style="filter:invert(1)"/>
    <span class="label">Pandas</span>
  </div>
  <div class="badge-card b-mpl">
    <img class="icon" src="https://cdn.jsdelivr.net/npm/simple-icons@v10/icons/python.svg" style="filter:invert(1)"/>
    <span class="label">Matplotlib</span>
  </div>
</div>

<p class="sub-label">⚙️ Backend & Databases</p>
<div class="badge-grid">
  <div class="badge-card b-spring">
    <img class="icon" src="https://cdn.jsdelivr.net/npm/simple-icons@v10/icons/springboot.svg" style="filter:invert(1)"/>
    <span class="label">Spring Boot</span>
  </div>
  <div class="badge-card b-mysql">
    <img class="icon" src="https://cdn.jsdelivr.net/npm/simple-icons@v10/icons/mysql.svg" style="filter:invert(1)"/>
    <span class="label">MySQL</span>
  </div>
  <div class="badge-card b-rest">
    <img class="icon" src="https://cdn.jsdelivr.net/npm/simple-icons@v10/icons/postman.svg" style="filter:invert(1)"/>
    <span class="label">REST APIs</span>
  </div>
  <div class="badge-card b-jdbc">
    <img class="icon" src="https://cdn.jsdelivr.net/npm/simple-icons@v10/icons/openjdk.svg" style="filter:invert(1)"/>
    <span class="label">JDBC</span>
  </div>
  <div class="badge-card b-micro">
    <img class="icon" src="https://cdn.jsdelivr.net/npm/simple-icons@v10/icons/spring.svg" style="filter:invert(1)"/>
    <span class="label">Microservices</span>
  </div>
</div>

<p class="sub-label">🧰 DevTools & Platforms</p>
<div class="badge-grid">
  <div class="badge-card b-git">
    <img class="icon" src="https://cdn.jsdelivr.net/npm/simple-icons@v10/icons/git.svg" style="filter:invert(1)"/>
    <span class="label">Git</span>
  </div>
  <div class="badge-card b-github">
    <img class="icon" src="https://cdn.jsdelivr.net/npm/simple-icons@v10/icons/github.svg" style="filter:invert(1)"/>
    <span class="label">GitHub</span>
  </div>
  <div class="badge-card b-linux">
    <img class="icon" src="https://cdn.jsdelivr.net/npm/simple-icons@v10/icons/linux.svg"/>
    <span class="label">Linux</span>
  </div>
  <div class="badge-card b-vscode">
    <img class="icon" src="https://cdn.jsdelivr.net/npm/simple-icons@v10/icons/visualstudiocode.svg" style="filter:invert(1)"/>
    <span class="label">VS Code</span>
  </div>
  <div class="badge-card b-ij">
    <img class="icon" src="https://cdn.jsdelivr.net/npm/simple-icons@v10/icons/intellijidea.svg" style="filter:invert(1)"/>
    <span class="label">IntelliJ</span>
  </div>
  <div class="badge-card b-postman">
    <img class="icon" src="https://cdn.jsdelivr.net/npm/simple-icons@v10/icons/postman.svg" style="filter:invert(1)"/>
    <span class="label">Postman</span>
  </div>
</div>

<div class="divider"></div>

<!-- ══════════ LET'S CONNECT ══════════ -->
<div class="section-heading">
  <h2>🤝 Let's Connect</h2>
</div>

<div class="connect-grid">
  <a href="mailto:m.srinivasarao051@gmail.com" class="connect-card cc-gmail">
    <div class="c-icon" style="background:rgba(255,255,255,0.15)">✉</div>
    <div class="c-title">Email</div>
    <div class="c-sub">m.srinivasarao051<br/>@gmail.com</div>
  </a>
  <a href="https://linkedin.com/in/srinivasa-rao-73732b2bb" class="connect-card cc-linkedin">
    <div class="c-icon" style="background:rgba(255,255,255,0.15)">in</div>
    <div class="c-title">LinkedIn</div>
    <div class="c-sub">srinivasa-rao<br/>-73732b2bb</div>
  </a>
  <a href="https://github.com/srinivas-105" class="connect-card cc-github">
    <div class="c-icon" style="background:rgba(255,255,255,0.15)">⌥</div>
    <div class="c-title">GitHub</div>
    <div class="c-sub">github.com/<br/>srinivas-105</div>
  </a>
  <a href="https://wa.me/917997110446" class="connect-card cc-wa">
    <div class="c-icon" style="background:rgba(255,255,255,0.15)">✆</div>
    <div class="c-title">WhatsApp</div>
    <div class="c-sub">+91 7997110446</div>
  </a>
</div>

<div class="stats-row">
  <div class="stat-pill pv">
    <span class="pill-label">Profile Views</span>
    <span class="pill-val">16</span>
  </div>
  <div class="stat-pill fo">
    <span class="pill-label">Followers</span>
    <span class="pill-val">2</span>
  </div>
  <div class="stat-pill st">
    <span class="pill-label">Total Stars</span>
    <span class="pill-val">0</span>
  </div>
</div>

<script>
  document.querySelectorAll('.badge-card, .connect-card').forEach(card => {
    card.addEventListener('mousemove', e => {
      const r = card.getBoundingClientRect();
      const x = e.clientX - r.left - r.width / 2;
      const y = e.clientY - r.top - r.height / 2;
      const rx = -(y / r.height) * 18;
      const ry =  (x / r.width)  * 18;
      card.style.transform = `perspective(500px) rotateX(${rx}deg) rotateY(${ry}deg) translateZ(18px) scale(1.06)`;
    });
    card.addEventListener('mouseleave', () => {
      card.style.transform = '';
    });
  });
</script>
</body>
</html>
