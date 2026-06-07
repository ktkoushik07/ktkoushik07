<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Koushik KT — ECE Engineer</title>
<link href="https://fonts.googleapis.com/css2?family=Clash+Display:wght@400;500;600;700&family=Cabinet+Grotesk:wght@400;500;700;800;900&family=Bebas+Neue&family=Outfit:wght@300;400;500;600&display=swap" rel="stylesheet"/>
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Outfit:wght@300;400;500;600;700&family=Righteous&display=swap" rel="stylesheet"/>
<style>
:root {
  --bg: #07070f;
  --c1: #ff3cac;   /* hot pink */
  --c2: #784ba0;   /* violet */
  --c3: #2b86c5;   /* electric blue */
  --c4: #00f5a0;   /* mint green */
  --c5: #f9a825;   /* amber */
  --c6: #ff6b35;   /* orange */
  --c7: #e040fb;   /* magenta */
  --text: #f0eeff;
  --muted: #7b7a99;
  --card: #0e0d1c;
  --border: #1e1d36;
}

*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
html{scroll-behavior:smooth}
body{background:var(--bg);color:var(--text);font-family:'Outfit',sans-serif;overflow-x:hidden;cursor:none}

/* ─── CURSOR ─── */
#cur{width:10px;height:10px;border-radius:50%;background:var(--c1);position:fixed;pointer-events:none;z-index:9999;transform:translate(-50%,-50%);transition:width .15s,height .15s,background .2s;mix-blend-mode:screen}
#cur-r{width:34px;height:34px;border:2px solid rgba(255,60,172,.45);border-radius:50%;position:fixed;pointer-events:none;z-index:9998;transform:translate(-50%,-50%);transition:left .12s ease,top .12s ease,width .25s,height .25s}

/* ─── BACKGROUND ─── */
.bg-wrap{position:fixed;inset:0;z-index:0;overflow:hidden}
.bg-mesh{position:absolute;inset:0;background:
  radial-gradient(ellipse 60% 50% at 10% 10%, rgba(255,60,172,.09) 0%, transparent 60%),
  radial-gradient(ellipse 50% 60% at 90% 20%, rgba(43,134,197,.08) 0%, transparent 55%),
  radial-gradient(ellipse 40% 40% at 50% 80%, rgba(0,245,160,.06) 0%, transparent 50%),
  radial-gradient(ellipse 55% 45% at 80% 90%, rgba(120,75,160,.07) 0%, transparent 55%);
  animation:meshShift 14s ease-in-out infinite alternate}
@keyframes meshShift{
  0%{filter:hue-rotate(0deg)}
  100%{filter:hue-rotate(30deg)}
}
.grid-dots{position:absolute;inset:0;
  background-image:radial-gradient(rgba(255,255,255,.045) 1px, transparent 1px);
  background-size:32px 32px}
.noise{position:fixed;inset:0;z-index:2;pointer-events:none;opacity:.32;
  background-image:url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='.85' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='.08'/%3E%3C/svg%3E")}

/* ─── LAYOUT ─── */
.wrap{max-width:960px;margin:0 auto;padding:0 28px;position:relative;z-index:10}

/* ─── HERO ─── */
header{min-height:100vh;display:flex;flex-direction:column;justify-content:center;padding:80px 0 60px;position:relative;z-index:10}

.pill-row{display:flex;gap:10px;flex-wrap:wrap;margin-bottom:28px;opacity:0;animation:riseUp .5s .1s forwards}
.pill{font-size:.6rem;letter-spacing:.22em;text-transform:uppercase;padding:5px 14px;border-radius:100px;font-weight:600}
.pill-pink{background:rgba(255,60,172,.15);border:1px solid rgba(255,60,172,.35);color:var(--c1)}
.pill-blue{background:rgba(43,134,197,.15);border:1px solid rgba(43,134,197,.35);color:#5bc8ff}
.pill-green{background:rgba(0,245,160,.12);border:1px solid rgba(0,245,160,.3);color:var(--c4)}

.hero-name{font-family:'Bebas Neue',sans-serif;font-size:clamp(5rem,15vw,10rem);line-height:.88;letter-spacing:.01em;opacity:0;animation:riseUp .8s .25s forwards}
.n1{
  display:block;
  background:linear-gradient(100deg, #ff3cac, #784ba0, #2b86c5);
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;
  background-size:200%;
  animation:riseUp .8s .25s forwards, gradMove 4s linear infinite}
.n2{display:block;color:var(--text);-webkit-text-stroke:1px rgba(255,255,255,.25)}
@keyframes gradMove{0%{background-position:0%}100%{background-position:200%}}

.hero-sub{font-family:'Righteous',sans-serif;font-size:clamp(1rem,2.5vw,1.5rem);margin-top:20px;letter-spacing:.06em;opacity:0;animation:riseUp .7s .5s forwards}
.hero-sub span{display:inline-block;margin:0 2px}
.hs1{color:var(--c4)}
.hs2{color:var(--c5)}
.hs3{color:var(--c7)}

.hero-desc{font-size:.85rem;color:var(--muted);margin-top:20px;max-width:500px;line-height:1.85;opacity:0;animation:riseUp .7s .65s forwards}

.hero-btns{display:flex;gap:14px;flex-wrap:wrap;margin-top:36px;opacity:0;animation:riseUp .7s .85s forwards}
.hbtn{font-family:'Outfit',sans-serif;font-size:.72rem;font-weight:600;letter-spacing:.1em;text-transform:uppercase;padding:13px 30px;border-radius:100px;text-decoration:none;transition:all .25s;display:inline-flex;align-items:center;gap:8px}
.hbtn-a{background:linear-gradient(135deg,var(--c1),var(--c7));color:#fff}
.hbtn-a:hover{transform:translateY(-2px);box-shadow:0 8px 30px rgba(255,60,172,.4)}
.hbtn-b{border:1.5px solid var(--border);color:var(--muted)}
.hbtn-b:hover{border-color:var(--c3);color:#5bc8ff;background:rgba(43,134,197,.08)}
.hbtn-c{border:1.5px solid var(--border);color:var(--muted)}
.hbtn-c:hover{border-color:var(--c4);color:var(--c4);background:rgba(0,245,160,.07)}

.scroll-dot{position:absolute;bottom:40px;left:0;display:flex;align-items:center;gap:12px;opacity:0;animation:riseUp .6s 1.3s forwards}
.sd-line{width:1px;height:56px;background:linear-gradient(var(--c1),transparent)}
.sd-txt{font-size:.58rem;letter-spacing:.25em;color:var(--muted);text-transform:uppercase;writing-mode:vertical-rl}

@keyframes riseUp{from{opacity:0;transform:translateY(28px)}to{opacity:1;transform:translateY(0)}}

/* ─── SECTION HEAD ─── */
section{padding:90px 0;position:relative;z-index:10}
.sec-head{display:flex;align-items:center;gap:16px;margin-bottom:52px}
.sec-num{font-family:'Bebas Neue',sans-serif;font-size:1rem;letter-spacing:.15em}
.sec-title{font-family:'Righteous',sans-serif;font-size:1.6rem;letter-spacing:.04em}
.sec-line{flex:1;height:1px;background:linear-gradient(to right,var(--border),transparent)}
/* per-section colours */
.col-pink .sec-num{color:var(--c1)} .col-pink .sec-title{color:var(--c1)}
.col-blue .sec-num{color:#5bc8ff}  .col-blue .sec-title{color:#5bc8ff}
.col-green .sec-num{color:var(--c4)}.col-green .sec-title{color:var(--c4)}
.col-amber .sec-num{color:var(--c5)}.col-amber .sec-title{color:var(--c5)}
.col-orange .sec-num{color:var(--c6)}.col-orange .sec-title{color:var(--c6)}
.col-violet .sec-num{color:var(--c7)}.col-violet .sec-title{color:var(--c7)}

/* ─── ABOUT STAT CARDS ─── */
.stat-grid{display:grid;grid-template-columns:1fr 1fr;gap:3px}
.stat-card{background:var(--card);border:1px solid var(--border);padding:36px 30px;position:relative;overflow:hidden;transition:transform .25s,border-color .25s}
.stat-card:hover{transform:translateY(-3px)}
.stat-card::before{content:'';position:absolute;inset:0;opacity:0;transition:opacity .3s}
.sc-pink:hover{border-color:rgba(255,60,172,.4)} .sc-pink::before{background:linear-gradient(135deg,rgba(255,60,172,.06),transparent)}
.sc-blue:hover{border-color:rgba(91,200,255,.4)}  .sc-blue::before{background:linear-gradient(135deg,rgba(91,200,255,.06),transparent)}
.sc-green:hover{border-color:rgba(0,245,160,.4)}  .sc-green::before{background:linear-gradient(135deg,rgba(0,245,160,.06),transparent)}
.sc-amber:hover{border-color:rgba(249,168,37,.4)}  .sc-amber::before{background:linear-gradient(135deg,rgba(249,168,37,.06),transparent)}
.stat-card:hover::before{opacity:1}
.sn{font-family:'Bebas Neue',sans-serif;font-size:3.4rem;line-height:1}
.sn-pink{color:var(--c1)} .sn-blue{color:#5bc8ff} .sn-green{color:var(--c4)} .sn-amber{color:var(--c5)}
.sl{font-size:.62rem;letter-spacing:.18em;text-transform:uppercase;margin-top:6px;color:var(--muted)}
.sd{font-size:.78rem;color:#9896be;margin-top:14px;line-height:1.8}

/* ─── SKILLS ─── */
.skill-group{margin-bottom:36px}
.sg-label{font-family:'Righteous',sans-serif;font-size:.78rem;letter-spacing:.12em;text-transform:uppercase;margin-bottom:14px}
.sg-pink{color:var(--c1)} .sg-blue{color:#5bc8ff} .sg-green{color:var(--c4)}
.pills-row{display:flex;flex-wrap:wrap;gap:8px}
.sp{font-size:.7rem;font-weight:500;padding:8px 18px;border-radius:100px;border:1.5px solid;cursor:default;transition:all .2s;position:relative;overflow:hidden}
.sp::after{content:'';position:absolute;inset:0;background:currentColor;opacity:0;transition:opacity .2s}
.sp:hover::after{opacity:.08}
.sp-pink{border-color:rgba(255,60,172,.35);color:var(--c1);background:rgba(255,60,172,.07)}
.sp-blue{border-color:rgba(91,200,255,.35);color:#5bc8ff;background:rgba(91,200,255,.07)}
.sp-green{border-color:rgba(0,245,160,.35);color:var(--c4);background:rgba(0,245,160,.07)}
.sp-amber{border-color:rgba(249,168,37,.35);color:var(--c5);background:rgba(249,168,37,.07)}
.sp-violet{border-color:rgba(224,64,251,.35);color:var(--c7);background:rgba(224,64,251,.07)}
.sp-orange{border-color:rgba(255,107,53,.35);color:var(--c6);background:rgba(255,107,53,.07)}

/* ─── PROJECT CARD ─── */
.proj-card{border:1px solid var(--border);background:var(--card);padding:44px 40px;position:relative;overflow:hidden;transition:all .3s;border-radius:2px}
.proj-card:hover{transform:translateY(-5px);box-shadow:0 20px 60px rgba(255,60,172,.1),0 0 0 1px rgba(255,60,172,.2)}
.proj-bar{position:absolute;top:0;left:0;right:0;height:3px;background:linear-gradient(90deg,var(--c1),var(--c7),var(--c3),var(--c4));background-size:200%;animation:barShift 3s linear infinite}
@keyframes barShift{0%{background-position:0%}100%{background-position:200%}}
.proj-ghost{font-family:'Bebas Neue',sans-serif;font-size:7rem;position:absolute;right:24px;top:8px;line-height:1;
  background:linear-gradient(135deg,rgba(255,60,172,.08),rgba(43,134,197,.06));
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;pointer-events:none}
.proj-title{font-family:'Righteous',sans-serif;font-size:1.5rem;color:var(--text);margin-bottom:14px}
.proj-desc{font-size:.8rem;color:#9896be;line-height:1.9;margin-bottom:26px}
.proj-chips{display:flex;flex-wrap:wrap;gap:7px}
.pc{font-size:.6rem;letter-spacing:.1em;text-transform:uppercase;font-weight:600;padding:5px 13px;border-radius:100px}
.pc1{background:rgba(255,60,172,.12);border:1px solid rgba(255,60,172,.25);color:var(--c1)}
.pc2{background:rgba(91,200,255,.12);border:1px solid rgba(91,200,255,.25);color:#5bc8ff}
.pc3{background:rgba(0,245,160,.1);border:1px solid rgba(0,245,160,.2);color:var(--c4)}
.pc4{background:rgba(249,168,37,.1);border:1px solid rgba(249,168,37,.2);color:var(--c5)}
.pc5{background:rgba(224,64,251,.1);border:1px solid rgba(224,64,251,.2);color:var(--c7)}

/* ─── EDUCATION TIMELINE ─── */
.edu-list{display:flex;flex-direction:column;gap:0}
.edu-row{display:grid;grid-template-columns:70px 1fr;gap:0 28px;padding-bottom:44px}
.edu-row:last-child{padding-bottom:0}
.edu-yr{font-family:'Bebas Neue',sans-serif;font-size:.85rem;letter-spacing:.1em;padding-top:3px;text-align:right;line-height:1.4}
.ey-pink{color:var(--c1)} .ey-blue{color:#5bc8ff} .ey-green{color:var(--c4)}
.edu-right{border-left:1px solid var(--border);padding-left:28px;position:relative}
.edu-right::before{content:'';position:absolute;left:-5px;top:5px;width:9px;height:9px;border-radius:50%}
.edot-pink::before{background:var(--c1);box-shadow:0 0 12px var(--c1)}
.edot-blue::before{background:#5bc8ff;box-shadow:0 0 12px #5bc8ff}
.edot-green::before{background:var(--c4);box-shadow:0 0 12px var(--c4)}
.edu-inst{font-family:'Righteous',sans-serif;font-size:1.05rem;color:var(--text)}
.edu-deg{font-size:.76rem;color:var(--muted);margin-top:6px;line-height:1.7}
.edu-badge{display:inline-flex;align-items:center;margin-top:12px;font-size:.63rem;font-weight:600;letter-spacing:.1em;padding:5px 14px;border-radius:100px}
.eb-pink{background:rgba(255,60,172,.12);border:1px solid rgba(255,60,172,.3);color:var(--c1)}
.eb-green{background:rgba(0,245,160,.1);border:1px solid rgba(0,245,160,.25);color:var(--c4)}

/* ─── CERT CARDS ─── */
.cert-row{display:grid;grid-template-columns:1fr 1fr;gap:3px}
.cert-card{background:var(--card);border:1px solid var(--border);padding:32px 28px;transition:all .25s;position:relative;overflow:hidden}
.cc-violet:hover{border-color:rgba(224,64,251,.4);box-shadow:0 0 30px rgba(224,64,251,.08)}
.cc-orange:hover{border-color:rgba(255,107,53,.4);box-shadow:0 0 30px rgba(255,107,53,.08)}
.cert-icon{font-size:2rem;margin-bottom:16px;display:block}
.cert-name{font-family:'Righteous',sans-serif;font-size:1rem;color:var(--text);margin-bottom:8px}
.cert-issuer{font-size:.7rem;color:var(--muted);letter-spacing:.04em}
.cc-bar{position:absolute;bottom:0;left:0;right:0;height:2px}
.ccb-violet{background:linear-gradient(90deg,var(--c7),var(--c2))}
.ccb-orange{background:linear-gradient(90deg,var(--c6),var(--c5))}

/* ─── CONTACT ─── */
.contact-grid{display:grid;grid-template-columns:1fr 1fr;gap:3px}
.contact-card{display:flex;align-items:center;justify-content:space-between;background:var(--card);border:1px solid var(--border);padding:28px 28px;text-decoration:none;color:var(--text);transition:all .25s;position:relative;overflow:hidden}
.contact-card::before{content:'';position:absolute;inset:0;opacity:0;transition:opacity .3s}
.cc2-pink::before{background:linear-gradient(135deg,rgba(255,60,172,.07),transparent)}
.cc2-blue::before{background:linear-gradient(135deg,rgba(91,200,255,.07),transparent)}
.cc2-green::before{background:linear-gradient(135deg,rgba(0,245,160,.06),transparent)}
.cc2-amber::before{background:linear-gradient(135deg,rgba(249,168,37,.06),transparent)}
.contact-card:hover::before{opacity:1}
.cc2-pink:hover{border-color:rgba(255,60,172,.35)} .cc2-blue:hover{border-color:rgba(91,200,255,.35)}
.cc2-green:hover{border-color:rgba(0,245,160,.3)} .cc2-amber:hover{border-color:rgba(249,168,37,.3)}
.cc-plat{font-size:.58rem;letter-spacing:.2em;text-transform:uppercase;margin-bottom:6px}
.plt-pink{color:var(--c1)} .plt-blue{color:#5bc8ff} .plt-green{color:var(--c4)} .plt-amber{color:var(--c5)}
.cc-handle{font-family:'Righteous',sans-serif;font-size:.95rem;color:var(--text)}
.cc-arrow{font-size:1.3rem;transition:transform .2s;position:relative;z-index:1}
.contact-card:hover .cc-arrow{transform:translate(4px,-4px)}
.arr-pink{color:var(--c1)} .arr-blue{color:#5bc8ff} .arr-green{color:var(--c4)} .arr-amber{color:var(--c5)}

/* ─── FOOTER ─── */
footer{padding:60px 0 44px;border-top:1px solid var(--border);position:relative;z-index:10}
.footer-row{display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap;gap:16px}
.footer-name{font-family:'Bebas Neue',sans-serif;font-size:1.4rem;letter-spacing:.08em;
  background:linear-gradient(90deg,var(--c1),var(--c7),var(--c3));
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text}
.footer-note{font-size:.65rem;color:var(--muted);letter-spacing:.1em}

/* ─── DIVIDER ─── */
.div{width:100%;height:1px;background:linear-gradient(to right,transparent,var(--border),transparent);position:relative;z-index:10}

/* ─── REVEAL ─── */
.rv{opacity:0;transform:translateY(28px);transition:opacity .65s ease,transform .65s ease}
.rv.on{opacity:1;transform:translateY(0)}
.rv1{transition-delay:.08s} .rv2{transition-delay:.18s} .rv3{transition-delay:.28s}

/* ─── RESPONSIVE ─── */
@media(max-width:600px){
  .stat-grid,.cert-row,.contact-grid{grid-template-columns:1fr}
  .hero-name{font-size:4.2rem}
  .proj-card{padding:28px 22px}
}
</style>
</head>
<body>

<div id="cur"></div>
<div id="cur-r"></div>
<div class="noise"></div>
<div class="bg-wrap">
  <div class="bg-mesh"></div>
  <div class="grid-dots"></div>
</div>

<!-- ════ HERO ════ -->
<header>
  <div class="wrap">
    <div class="pill-row">
      <span class="pill pill-pink">ECE Engineer</span>
      <span class="pill pill-blue">Chennai, India 🇮🇳</span>
      <span class="pill pill-green">Open to Internships</span>
    </div>

    <h1 class="hero-name">
      <span class="n1">KOUSHIK</span>
      <span class="n2">KT</span>
    </h1>

    <p class="hero-sub">
      <span class="hs1">Embedded Systems</span>
      <span style="color:var(--muted)"> · </span>
      <span class="hs2">IoT</span>
      <span style="color:var(--muted)"> · </span>
      <span class="hs3">Circuit Design</span>
    </p>

    <p class="hero-desc">
      1st year Electronics & Communication Engineering student at R.M.D. Engineering College,
      Anna University. Building hardware that talks to the real world — from gas sensors to
      PCB layouts to VLSI fundamentals.
    </p>

    <div class="hero-btns">
      <a href="mailto:ktkoushik22@gmail.com" class="hbtn hbtn-a">✉ Get in Touch</a>
      <a href="https://github.com/ktkoushik07" target="_blank" class="hbtn hbtn-b">GitHub ↗</a>
      <a href="https://www.linkedin.com/in/koushik-kt-a639b7381" target="_blank" class="hbtn hbtn-c">LinkedIn ↗</a>
    </div>

    <div class="scroll-dot">
      <div class="sd-line"></div>
      <span class="sd-txt">scroll</span>
    </div>
  </div>
</header>

<!-- ════ ABOUT ════ -->
<section>
  <div class="wrap">
    <div class="sec-head col-pink rv">
      <span class="sec-num">01</span>
      <span class="sec-title">About</span>
      <div class="sec-line"></div>
    </div>
    <div class="stat-grid">
      <div class="stat-card sc-pink rv rv1">
        <div class="sn sn-pink">8.35</div>
        <div class="sl">CGPA</div>
        <div class="sd">B.E. ECE at R.M.D. Engineering College, Anna University (2026–2029)</div>
      </div>
      <div class="stat-card sc-blue rv rv2">
        <div class="sn sn-blue">7+</div>
        <div class="sl">Languages</div>
        <div class="sd">C, C++, Java, JavaScript, Python, HTML & CSS across embedded and web domains.</div>
      </div>
      <div class="stat-card sc-green rv rv2">
        <div class="sn sn-green">92%</div>
        <div class="sl">HSC Score</div>
        <div class="sd">State Board Higher Secondary — consistent excellence through all academic levels.</div>
      </div>
      <div class="stat-card sc-amber rv rv3">
        <div class="sn sn-amber">1st</div>
        <div class="sl">Year Student</div>
        <div class="sd">Already shipping hardware projects and exploring VLSI and IoT systems.</div>
      </div>
    </div>
  </div>
</section>

<div class="div"></div>

<!-- ════ SKILLS ════ -->
<section>
  <div class="wrap">
    <div class="sec-head col-blue rv">
      <span class="sec-num">02</span>
      <span class="sec-title">Skills</span>
      <div class="sec-line"></div>
    </div>
    <div class="skill-group rv rv1">
      <p class="sg-label sg-pink">Programming Languages</p>
      <div class="pills-row">
        <span class="sp sp-pink">C</span>
        <span class="sp sp-pink">C++</span>
        <span class="sp sp-blue">Python</span>
        <span class="sp sp-blue">Java</span>
        <span class="sp sp-amber">JavaScript</span>
        <span class="sp sp-amber">HTML5</span>
        <span class="sp sp-orange">CSS3</span>
      </div>
    </div>
    <div class="skill-group rv rv2">
      <p class="sg-label sg-blue">Tools & Software</p>
      <div class="pills-row">
        <span class="sp sp-green">Arduino IDE</span>
        <span class="sp sp-green">Tinkercad</span>
        <span class="sp sp-violet">KiCad</span>
        <span class="sp sp-violet">Autodesk Fusion 360</span>
      </div>
    </div>
    <div class="skill-group rv rv3">
      <p class="sg-label sg-green">Core Engineering Areas</p>
      <div class="pills-row">
        <span class="sp sp-pink">Embedded Systems</span>
        <span class="sp sp-blue">IoT</span>
        <span class="sp sp-amber">Circuit Design</span>
        <span class="sp sp-green">PCB Layout</span>
        <span class="sp sp-orange">Prototyping</span>
        <span class="sp sp-violet">VLSI</span>
      </div>
    </div>
  