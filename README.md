<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Koushik KT — GitHub Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&family=Syne:wght@400;600;700;800&display=swap" rel="stylesheet"/>
<style>
  :root {
    --bg:       #0d1117;
    --surface:  #111827;
    --card:     #161b27;
    --border:   #1e2d40;
    --blue:     #70a5fd;
    --purple:   #bf91f3;
    --teal:     #38bdae;
    --text:     #c9d1d9;
    --muted:    #586272;
    --glow-b:   rgba(112,165,253,0.18);
    --glow-p:   rgba(191,145,243,0.15);
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Syne', sans-serif;
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* ── NOISE OVERLAY ── */
  body::before {
    content: '';
    position: fixed; inset: 0;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.04'/%3E%3C/svg%3E");
    pointer-events: none; z-index: 0;
  }

  .wrap { max-width: 900px; margin: 0 auto; padding: 0 24px 80px; position: relative; z-index: 1; }

  /* ── HERO ── */
  .hero {
    position: relative;
    padding: 72px 0 56px;
    text-align: center;
    overflow: hidden;
  }
  .hero::before {
    content: '';
    position: absolute; top: -60px; left: 50%; transform: translateX(-50%);
    width: 700px; height: 400px;
    background: radial-gradient(ellipse at 50% 40%, rgba(112,165,253,0.13) 0%, rgba(191,145,243,0.08) 50%, transparent 75%);
    pointer-events: none;
  }
  .hero-eyebrow {
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    letter-spacing: 0.3em;
    color: var(--teal);
    text-transform: uppercase;
    margin-bottom: 18px;
    opacity: 0;
    animation: fadeUp 0.6s 0.1s forwards;
  }
  .hero h1 {
    font-size: clamp(48px, 9vw, 82px);
    font-weight: 800;
    line-height: 1;
    letter-spacing: -0.03em;
    background: linear-gradient(135deg, #fff 30%, var(--blue) 70%, var(--purple) 100%);
    -webkit-background-clip: text; -webkit-text-fill-color: transparent;
    opacity: 0;
    animation: fadeUp 0.7s 0.25s forwards;
  }
  .hero-sub {
    margin-top: 14px;
    font-size: 15px;
    color: var(--muted);
    letter-spacing: 0.04em;
    opacity: 0;
    animation: fadeUp 0.7s 0.4s forwards;
  }
  .hero-sub span { color: var(--blue); }

  .contact-row {
    display: flex; flex-wrap: wrap; gap: 10px;
    justify-content: center;
    margin-top: 28px;
    opacity: 0;
    animation: fadeUp 0.7s 0.55s forwards;
  }
  .contact-pill {
    display: inline-flex; align-items: center; gap: 6px;
    padding: 6px 14px;
    border: 1px solid var(--border);
    border-radius: 100px;
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    color: var(--text);
    text-decoration: none;
    background: var(--card);
    transition: border-color 0.2s, color 0.2s, box-shadow 0.2s;
  }
  .contact-pill:hover {
    border-color: var(--blue);
    color: var(--blue);
    box-shadow: 0 0 12px var(--glow-b);
  }
  .contact-pill .dot {
    width: 6px; height: 6px; border-radius: 50%;
    background: var(--teal);
    flex-shrink: 0;
  }

  /* ── DIVIDER ── */
  .divider {
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--border) 30%, var(--border) 70%, transparent);
    margin: 8px 0 44px;
  }

  /* ── SECTION LABEL ── */
  .section-label {
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    letter-spacing: 0.3em;
    color: var(--purple);
    text-transform: uppercase;
    margin-bottom: 20px;
  }
  .section-label::before { content: '// '; opacity: 0.5; }

  /* ── ABOUT ── */
  .about-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
    margin-bottom: 48px;
  }
  @media(max-width:620px){ .about-grid { grid-template-columns: 1fr; } }

  .about-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 24px;
    position: relative;
    overflow: hidden;
    transition: border-color 0.25s, transform 0.25s;
  }
  .about-card::after {
    content: '';
    position: absolute; top: 0; left: 0; right: 0; height: 2px;
    background: linear-gradient(90deg, var(--blue), var(--purple));
    opacity: 0;
    transition: opacity 0.25s;
  }
  .about-card:hover { border-color: rgba(112,165,253,0.35); transform: translateY(-2px); }
  .about-card:hover::after { opacity: 1; }

  .about-card .label {
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    color: var(--muted);
    letter-spacing: 0.2em;
    text-transform: uppercase;
    margin-bottom: 8px;
  }
  .about-card .value {
    font-size: 15px;
    font-weight: 600;
    color: var(--text);
  }
  .about-card .value.accent { color: var(--blue); }
  .about-card .value.green  { color: var(--teal); }

  /* ── SKILLS ── */
  .skills-section { margin-bottom: 48px; }
  .skill-group { margin-bottom: 20px; }
  .skill-group-title {
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    color: var(--muted);
    letter-spacing: 0.15em;
    text-transform: uppercase;
    margin-bottom: 10px;
  }
  .badges { display: flex; flex-wrap: wrap; gap: 8px; }
  .badge {
    display: inline-flex; align-items: center; gap: 6px;
    padding: 5px 12px;
    border-radius: 8px;
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    font-weight: 700;
    letter-spacing: 0.04em;
    border: 1px solid transparent;
    transition: transform 0.15s, box-shadow 0.15s;
    cursor: default;
  }
  .badge:hover { transform: translateY(-2px); }

  .badge.lang   { background: rgba(112,165,253,0.1);  border-color: rgba(112,165,253,0.25); color: var(--blue);   }
  .badge.tool   { background: rgba(191,145,243,0.1);  border-color: rgba(191,145,243,0.25); color: var(--purple); }
  .badge.core   { background: rgba(56,189,174,0.1);   border-color: rgba(56,189,174,0.25);  color: var(--teal);   }
  .badge:hover.lang  { box-shadow: 0 4px 16px var(--glow-b); }
  .badge:hover.tool  { box-shadow: 0 4px 16px var(--glow-p); }
  .badge:hover.core  { box-shadow: 0 4px 16px rgba(56,189,174,0.15); }

  /* ── STATS GRID ── */
  .stats-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
    margin-bottom: 48px;
  }
  @media(max-width:580px){ .stats-grid { grid-template-columns: 1fr; } }

  .stat-img-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 14px;
    overflow: hidden;
    transition: border-color 0.25s;
  }
  .stat-img-card:hover { border-color: rgba(112,165,253,0.35); }
  .stat-img-card img { width: 100%; display: block; }

  .stat-img-full {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 14px;
    overflow: hidden;
    margin-bottom: 16px;
    transition: border-color 0.25s;
  }
  .stat-img-full:hover { border-color: rgba(112,165,253,0.35); }
  .stat-img-full img { width: 100%; display: block; }

  /* ── PROJECT ── */
  .project-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 28px;
    margin-bottom: 48px;
    position: relative;
    overflow: hidden;
    transition: border-color 0.25s, transform 0.25s;
  }
  .project-card::before {
    content: '';
    position: absolute; right: -40px; top: -40px;
    width: 180px; height: 180px;
    border-radius: 50%;
    background: radial-gradient(circle, rgba(112,165,253,0.08) 0%, transparent 70%);
    pointer-events: none;
  }
  .project-card:hover { border-color: rgba(112,165,253,0.4); transform: translateY(-2px); }

  .project-header {
    display: flex; align-items: flex-start; justify-content: space-between; gap: 12px;
    margin-bottom: 12px;
  }
  .project-name {
    font-size: 19px;
    font-weight: 700;
    color: #fff;
  }
  .project-icon {
    font-size: 28px; flex-shrink: 0;
  }
  .project-desc {
    font-size: 14px;
    color: var(--muted);
    line-height: 1.65;
    margin-bottom: 16px;
  }
  .project-bullets {
    list-style: none;
    display: flex; flex-direction: column; gap: 7px;
  }
  .project-bullets li {
    font-size: 13px;
    color: var(--text);
    padding-left: 16px;
    position: relative;
    line-height: 1.5;
  }
  .project-bullets li::before {
    content: '→';
    position: absolute; left: 0;
    color: var(--blue);
    font-family: 'Space Mono', monospace;
  }
  .project-stack {
    display: flex; flex-wrap: wrap; gap: 6px;
    margin-top: 16px;
  }
  .stack-tag {
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    padding: 3px 9px;
    border-radius: 6px;
    background: rgba(56,189,174,0.08);
    border: 1px solid rgba(56,189,174,0.2);
    color: var(--teal);
  }

  /* ── EDUCATION ── */
  .edu-list { display: flex; flex-direction: column; gap: 12px; margin-bottom: 48px; }
  .edu-card {
    display: grid;
    grid-template-columns: auto 1fr auto;
    gap: 16px;
    align-items: center;
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 18px 22px;
    transition: border-color 0.2s;
  }
  .edu-card:hover { border-color: rgba(191,145,243,0.35); }
  @media(max-width:580px){ .edu-card { grid-template-columns: 1fr; } }
  .edu-icon { font-size: 22px; }
  .edu-name { font-size: 14px; font-weight: 700; color: var(--text); margin-bottom: 3px; }
  .edu-sub  { font-size: 12px; color: var(--muted); font-family: 'Space Mono', monospace; }
  .edu-score {
    font-family: 'Space Mono', monospace;
    font-size: 13px;
    font-weight: 700;
    color: var(--teal);
    white-space: nowrap;
  }

  /* ── CERTS ── */
  .cert-list { display: flex; flex-direction: column; gap: 10px; margin-bottom: 48px; }
  .cert-card {
    display: flex; align-items: center; gap: 14px;
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 14px 18px;
    transition: border-color 0.2s;
  }
  .cert-card:hover { border-color: rgba(112,165,253,0.3); }
  .cert-icon { font-size: 20px; flex-shrink: 0; }
  .cert-name { font-size: 14px; font-weight: 600; color: var(--text); }
  .cert-by   { font-size: 11px; color: var(--muted); font-family: 'Space Mono', monospace; margin-top: 2px; }

  /* ── LEARNING ── */
  .learning-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(190px, 1fr));
    gap: 12px;
    margin-bottom: 48px;
  }
  .learn-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 16px 18px;
    transition: border-color 0.2s, transform 0.2s;
  }
  .learn-card:hover { border-color: rgba(191,145,243,0.35); transform: translateY(-2px); }
  .learn-emoji { font-size: 22px; margin-bottom: 8px; }
  .learn-topic { font-size: 13px; font-weight: 700; color: var(--text); margin-bottom: 4px; }
  .learn-sub   { font-size: 11px; color: var(--muted); font-family: 'Space Mono', monospace; }

  /* ── FOOTER ── */
  .footer {
    text-align: center;
    padding-top: 40px;
    border-top: 1px solid var(--border);
  }
  .footer-name {
    font-size: 28px;
    font-weight: 800;
    background: linear-gradient(135deg, var(--blue), var(--purple));
    -webkit-background-clip: text; -webkit-text-fill-color: transparent;
    margin-bottom: 6px;
  }
  .footer-tag {
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    color: var(--muted);
    letter-spacing: 0.15em;
  }

  /* ── ANIMATIONS ── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(18px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  .reveal {
    opacity: 0;
    animation: fadeUp 0.6s forwards;
  }
</style>
</head>
<body>
<div class="wrap">

  <!-- HERO -->
  <section class="hero">
    <p class="hero-eyebrow">GitHub Profile &nbsp;·&nbsp; ktkoushik07</p>
    <h1>Koushik KT</h1>
    <p class="hero-sub">
      1st Year ECE Student &nbsp;·&nbsp;
      <span>Aspiring Embedded Systems &amp; IoT Engineer</span>
    </p>
    <div class="contact-row">
      <a class="contact-pill" href="mailto:ktkoushik22@gmail.com">
        <span class="dot"></span> ktkoushik22@gmail.com
      </a>
      <a class="contact-pill" href="https://linkedin.com/in/koushik-kt-a639b7381" target="_blank">
        <span class="dot"></span> LinkedIn
      </a>
      <a class="contact-pill" href="https://github.com/ktkoushik07" target="_blank">
        <span class="dot"></span> GitHub
      </a>
      <a class="contact-pill" href="#">
        <span class="dot"></span> Chennai, Tamil Nadu 🇮🇳
      </a>
    </div>
  </section>

  <div class="divider"></div>

  <!-- ABOUT -->
  <div class="section-label">About</div>
  <div class="about-grid reveal" style="animation-delay:0.1s">
    <div class="about-card">
      <div class="label">Degree</div>
      <div class="value">B.E. – Electronics &amp; Communication</div>
    </div>
    <div class="about-card">
      <div class="label">University</div>
      <div class="value">R.M.D. Engineering College · Anna University</div>
    </div>
    <div class="about-card">
      <div class="label">Current CGPA</div>
      <div class="value accent">8.35 / 10</div>
    </div>
    <div class="about-card">
      <div class="label">Focus Areas</div>
      <div class="value green">Embedded Systems · IoT · PCB Design</div>
    </div>
  </div>

  <!-- SKILLS -->
  <div class="section-label" style="margin-top:8px">Tech Stack</div>
  <div class="skills-section reveal" style="animation-delay:0.2s">
    <div class="skill-group">
      <div class="skill-group-title">Languages</div>
      <div class="badges">
        <span class="badge lang">C</span>
        <span class="badge lang">C++</span>
        <span class="badge lang">Python</span>
        <span class="badge lang">Java</span>
        <span class="badge lang">JavaScript</span>
        <span class="badge lang">HTML5</span>
        <span class="badge lang">CSS3</span>
      </div>
    </div>
    <div class="skill-group" style="margin-top:14px">
      <div class="skill-group-title">Tools &amp; Software</div>
      <div class="badges">
        <span class="badge tool">Arduino IDE</span>
        <span class="badge tool">Tinkercad</span>
        <span class="badge tool">KiCad</span>
        <span class="badge tool">Autodesk Fusion 360</span>
      </div>
    </div>
    <div class="skill-group" style="margin-top:14px">
      <div class="skill-group-title">Core Areas</div>
      <div class="badges">
        <span class="badge core">Embedded Systems</span>
        <span class="badge core">IoT</span>
        <span class="badge core">Circuit Design</span>
        <span class="badge core">PCB Layout</span>
        <span class="badge core">Prototyping</span>
      </div>
    </div>
  </div>

  <!-- STATS -->
  <div class="section-label">GitHub Stats</div>
  <div class="stats-grid reveal" style="animation-delay:0.3s">
    <div class="stat-img-card">
      <img src="https://github-readme-stats.vercel.app/api?username=ktkoushik07&show_icons=true&theme=tokyonight&hide_border=true&include_all_commits=true&count_private=true&bg_color=0d1117&title_color=70a5fd&icon_color=bf91f3&text_color=c9d1d9&border_radius=10" alt="GitHub Stats"/>
    </div>
    <div class="stat-img-card">
      <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=ktkoushik07&layout=compact&theme=tokyonight&hide_border=true&bg_color=0d1117&title_color=70a5fd&text_color=c9d1d9&langs_count=8&border_radius=10" alt="Top Languages"/>
    </div>
  </div>

  <div class="stat-img-full reveal" style="animation-delay:0.35s">
    <img src="https://streak-stats.demolab.com?user=ktkoushik07&theme=tokyonight-duo&hide_border=true&background=0D1117&ring=70A5FD&fire=BF91F3&currStreakLabel=70A5FD&sideLabels=38BDAE&dates=8B949E&currStreakNum=C9D1D9&sideNums=C9D1D9&stroke=0D1117&border_radius=10" alt="Streak Stats"/>
  </div>

  <div class="stat-img-full reveal" style="animation-delay:0.4s">
    <img src="https://github-readme-activity-graph.vercel.app/graph?username=ktkoushik07&theme=tokyo-night&bg_color=0d1117&color=70a5fd&line=bf91f3&point=38bdae&area=true&hide_border=true" alt="Activity Graph"/>
  </div>

  <div class="stat-img-full reveal" style="animation-delay:0.45s">
    <img src="https://github-profile-trophy.vercel.app/?username=ktkoushik07&theme=tokyonight&no-frame=true&no-bg=true&row=1&column=7&margin-w=4" alt="Trophies"/>
  </div>

  <!-- PROJECT -->
  <div class="section-label">Featured Project</div>
  <div class="project-card reveal" style="animation-delay:0.5s">
    <div class="project-header">
      <div class="project-name">🌬️ Ventilation Safety Monitoring System</div>
      <div class="project-icon">🔌</div>
    </div>
    <p class="project-desc">
      A smart embedded safety system that monitors air quality and ventilation in enclosed spaces using gas sensors and a microcontroller. Detects harmful conditions and triggers real-time alerts to prevent accidents.
    </p>
    <ul class="project-bullets">
      <li>Designed and prototyped the full circuit on a breadboard with gas sensors and a microcontroller</li>
      <li>Integrated real-time sensor readings to detect harmful gases and unsafe conditions</li>
      <li>Programmed threshold-based alert mechanisms to notify users when readings exceed safe limits</li>
      <li>Simulated and validated circuit behaviour using Arduino IDE before physical deployment</li>
    </ul>
    <div class="project-stack">
      <span class="stack-tag">Arduino IDE</span>
      <span class="stack-tag">Gas Sensors</span>
      <span class="stack-tag">Microcontroller</span>
      <span class="stack-tag">Breadboard</span>
      <span class="stack-tag">C</span>
    </div>
  </div>

  <!-- EDUCATION -->
  <div class="section-label">Education</div>
  <div class="edu-list reveal" style="animation-delay:0.55s">
    <div class="edu-card">
      <div class="edu-icon">🎓</div>
      <div>
        <div class="edu-name">R.M.D. Engineering College · Anna University</div>
        <div class="edu-sub">B.E. – Electronics &amp; Communication Engineering · 2026–2029</div>
      </div>
      <div class="edu-score">CGPA 8.35</div>
    </div>
    <div class="edu-card">
      <div class="edu-icon">📚</div>
      <div>
        <div class="edu-name">Smt. G.B.C. Vivekananda Vidyalaya Hr. Sec. School</div>
        <div class="edu-sub">Higher Secondary · State Board · 2026</div>
      </div>
      <div class="edu-score">92.17%</div>
    </div>
    <div class="edu-card">
      <div class="edu-icon">🏫</div>
      <div>
        <div class="edu-name">Smt. G.B.C. Vivekananda Vidyalaya Hr. Sec. School</div>
        <div class="edu-sub">SSLC · State Board · 2024</div>
      </div>
      <div class="edu-score">90.6%</div>
    </div>
  </div>

  <!-- CERTIFICATIONS -->
  <div class="section-label">Certifications</div>
  <div class="cert-list reveal" style="animation-delay:0.6s">
    <div class="cert-card">
      <div class="cert-icon">🔬</div>
      <div>
        <div class="cert-name">VLSI for Beginners</div>
        <div class="cert-by">National Institute of Electronics &amp; Technology (NIET)</div>
      </div>
    </div>
    <div class="cert-card">
      <div class="cert-icon">🗣️</div>
      <div>
        <div class="cert-name">Soft Skills Development</div>
        <div class="cert-by">NPTEL</div>
      </div>
    </div>
  </div>

  <!-- CURRENTLY LEARNING -->
  <div class="section-label">Currently Learning</div>
  <div class="learning-grid reveal" style="animation-delay:0.65s">
    <div class="learn-card">
      <div class="learn-emoji">🔌</div>
      <div class="learn-topic">Embedded Systems</div>
      <div class="learn-sub">Microcontrollers · RTOS · Interrupts</div>
    </div>
    <div class="learn-card">
      <div class="learn-emoji">🧱</div>
      <div class="learn-topic">VLSI Design</div>
      <div class="learn-sub">Logic Gates · HDL · CMOS</div>
    </div>
    <div class="learn-card">
      <div class="learn-emoji">📡</div>
      <div class="learn-topic">IoT</div>
      <div class="learn-sub">Sensor Integration · Protocols</div>
    </div>
    <div class="learn-card">
      <div class="learn-emoji">🖥️</div>
      <div class="learn-topic">PCB Design</div>
      <div class="learn-sub">Schematic · KiCad Layout</div>
    </div>
  </div>

  <!-- FOOTER -->
  <div class="footer reveal" style="animation-delay:0.7s">
    <div class="footer-name">Koushik KT</div>
    <div class="footer-tag">BUILD &nbsp;·&nbsp; BREAK &nbsp;·&nbsp; LEARN &nbsp;·&nbsp; REPEAT</div>
  </div>

</div>

<script>
  // Intersection Observer for scroll-triggered reveals
  const els = document.querySelectorAll('.reveal');
  const io = new IntersectionObserver(entries => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        e.target.style.animationPlayState = 'running';
        io.unobserve(e.target);
      }
    });
  }, { threshold: 0.1 });
  els.forEach(el => {
    el.style.animationPlayState = 'paused';
    io.observe(el);
  });
</script>
</body>
</html>