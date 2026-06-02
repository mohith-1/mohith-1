<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Mohith Reddy Kovvuri — Software & AI Engineer</title>
<link rel="preconnect" href="https://fonts.googleapis.com"/>
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin/>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,500;0,600;1,300;1,400;1,600&family=DM+Sans:ital,wght@0,300;0,400;0,500;0,600;1,300&family=Libre+Baskerville:ital@1&display=swap" rel="stylesheet"/>
<style>
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
:root{
  --bg:#f5f0e8;
  --bg2:#ede8de;
  --surface:#ede7da;
  --surface2:#e6dfd0;
  --card:#eee8da;
  --card2:#e8e0cf;
  --border:rgba(139,119,89,0.15);
  --border2:rgba(139,119,89,0.28);
  --ink:#1c1812;
  --ink2:#5a4f3e;
  --ink3:#9a8d78;
  --ink4:#c5b99f;
  --accent:#8b6f3e;
  --accent2:#c49a4a;
  --accent3:#6b4f2a;
  --warm:#d4a85a;
  --fh:'DM Sans',sans-serif;
  --fs:'Cormorant Garamond',serif;
}
html{scroll-behavior:smooth}
body{
  background:var(--bg);
  color:var(--ink);
  font-family:var(--fh);
  font-size:15px;
  line-height:1.65;
  overflow-x:hidden;
  cursor:none;
}

/* ── GRAIN TEXTURE ── */
body::before{
  content:'';position:fixed;inset:0;
  background-image:url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='300' height='300'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.75' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='300' height='300' filter='url(%23n)' opacity='0.035'/%3E%3C/svg%3E");
  pointer-events:none;z-index:900;opacity:1;
}

/* ── CURSOR ── */
.cur{
  position:fixed;width:8px;height:8px;border-radius:50%;
  background:var(--accent);pointer-events:none;z-index:9999;
  transform:translate(-50%,-50%);
  transition:width 0.3s,height 0.3s;
}
.cur-ring{
  position:fixed;width:32px;height:32px;border-radius:50%;
  border:1.5px solid rgba(139,111,62,0.45);
  pointer-events:none;z-index:9998;
  transform:translate(-50%,-50%);
  transition:width 0.3s,height 0.3s;
}

/* ── CANVAS ── */
#canvas{position:fixed;inset:0;z-index:0;pointer-events:none;opacity:0.35}

/* ── NAV ── */
nav{
  position:fixed;top:0;left:0;right:0;z-index:200;
  display:flex;justify-content:space-between;align-items:center;
  padding:0 64px;height:66px;
  background:rgba(245,240,232,0.82);
  backdrop-filter:blur(18px) saturate(160%);
  border-bottom:1px solid var(--border);
  transition:background 0.4s;
}
.nav-logo{
  font-family:var(--fs);font-weight:600;font-size:20px;
  color:var(--ink);text-decoration:none;letter-spacing:0.02em;
  display:flex;align-items:center;gap:5px;
}
.nav-logo .ndot{
  width:6px;height:6px;border-radius:50%;
  background:var(--accent2);
  box-shadow:0 0 6px var(--accent2);
  animation:glow 3s infinite;
}
@keyframes glow{
  0%,100%{box-shadow:0 0 4px var(--accent2),0 0 8px transparent}
  50%{box-shadow:0 0 10px var(--accent2),0 0 20px rgba(196,154,74,0.3)}
}
.nav-links{display:flex;gap:40px;list-style:none}
.nav-links a{
  color:var(--ink3);text-decoration:none;
  font-size:12.5px;letter-spacing:0.06em;font-weight:500;
  text-transform:uppercase;transition:color 0.2s;position:relative;
}
.nav-links a::after{
  content:'';position:absolute;bottom:-3px;left:0;right:0;
  height:1px;background:var(--accent);
  transform:scaleX(0);transition:transform 0.3s;transform-origin:left;
}
.nav-links a:hover{color:var(--ink)}
.nav-links a:hover::after{transform:scaleX(1)}
.nav-cta{
  padding:9px 22px;border:1.5px solid var(--accent);
  color:var(--accent3);text-decoration:none;font-size:12px;
  font-weight:600;letter-spacing:0.08em;text-transform:uppercase;
  border-radius:3px;transition:all 0.25s;
  background:transparent;font-family:var(--fh);
}
.nav-cta:hover{background:var(--accent);color:var(--bg);box-shadow:0 4px 20px rgba(139,111,62,0.25)}

/* ── SECTIONS ── */
section{position:relative;z-index:1}
.wrap{max-width:1160px;margin:0 auto;padding:110px 64px}

/* ── HERO ── */
#hero{
  min-height:100vh;display:flex;align-items:center;
  max-width:1160px;margin:0 auto;padding:0 64px;
}
.hero-inner{
  display:grid;grid-template-columns:1.15fr 0.85fr;
  gap:80px;align-items:center;width:100%;padding-top:66px;
}
.hero-eyebrow{
  display:inline-flex;align-items:center;gap:10px;
  font-family:var(--fh);font-size:11px;font-weight:600;
  letter-spacing:0.14em;text-transform:uppercase;
  color:var(--accent);margin-bottom:30px;
}
.hero-eyebrow::before{content:'';width:28px;height:1px;background:var(--accent2)}
.hero-eyebrow::after{content:'';width:28px;height:1px;background:var(--accent2)}
.avail-dot{
  width:7px;height:7px;border-radius:50%;
  background:var(--warm);animation:glow 2.5s infinite;
}
.hero-name{
  font-family:var(--fs);
  font-size:clamp(58px,7.5vw,104px);
  font-weight:300;line-height:0.95;
  letter-spacing:-1px;margin-bottom:10px;
  color:var(--ink);
}
.hero-name .italic{
  font-style:italic;font-weight:300;
  color:var(--accent);
  display:block;
}
.hero-rule{
  width:60px;height:1.5px;
  background:linear-gradient(90deg,var(--accent2),transparent);
  margin:22px 0;
}
.hero-role{
  font-size:13.5px;color:var(--ink3);letter-spacing:0.08em;
  font-weight:400;margin-bottom:24px;text-transform:uppercase;
  display:flex;align-items:center;gap:12px;
}
.role-dot{width:3px;height:3px;border-radius:50%;background:var(--ink4)}
.hero-desc{
  font-size:16px;color:var(--ink2);line-height:1.85;
  max-width:480px;margin-bottom:46px;font-weight:300;
  font-family:var(--fh);
}
.hero-desc strong{color:var(--ink);font-weight:600}
.hero-btns{display:flex;gap:14px;flex-wrap:wrap}
.btn-p{
  display:inline-flex;align-items:center;gap:9px;
  padding:13px 30px;border-radius:3px;
  background:var(--ink);
  color:var(--bg);text-decoration:none;font-size:12.5px;
  font-weight:600;letter-spacing:0.07em;text-transform:uppercase;
  transition:all 0.28s;font-family:var(--fh);
  box-shadow:0 4px 20px rgba(28,24,18,0.2);
}
.btn-p:hover{background:var(--accent3);transform:translateY(-2px);box-shadow:0 8px 28px rgba(107,79,42,0.3)}
.btn-g{
  display:inline-flex;align-items:center;gap:9px;
  padding:13px 30px;border-radius:3px;
  border:1.5px solid var(--border2);
  color:var(--ink2);text-decoration:none;font-size:12.5px;
  font-weight:600;letter-spacing:0.07em;text-transform:uppercase;
  background:transparent;transition:all 0.28s;font-family:var(--fh);
}
.btn-g:hover{border-color:var(--accent);color:var(--accent3);background:rgba(139,111,62,0.06)}

/* STAT CARDS */
.hero-stats{display:grid;grid-template-columns:1fr 1fr;gap:16px}
.stat{
  background:var(--card);
  border:1px solid var(--border);
  border-radius:6px;padding:26px 22px;
  position:relative;overflow:hidden;
  transition:border-color 0.3s,transform 0.3s,box-shadow 0.3s;
}
.stat:hover{
  border-color:var(--border2);
  transform:translateY(-3px);
  box-shadow:0 12px 32px rgba(139,111,62,0.12);
}
.stat::after{
  content:'';position:absolute;
  bottom:0;left:0;right:0;height:2px;
  background:linear-gradient(90deg,var(--accent2),transparent);
  transform:scaleX(0);transform-origin:left;
  transition:transform 0.4s;
}
.stat:hover::after{transform:scaleX(1)}
.stat-n{
  font-family:var(--fs);
  font-size:46px;font-weight:500;letter-spacing:-2px;
  line-height:1;margin-bottom:6px;color:var(--ink);
}
.stat-n em{font-style:normal;color:var(--accent2);font-size:22px;font-family:var(--fh)}
.stat-l{
  font-size:10.5px;color:var(--ink3);text-transform:uppercase;
  letter-spacing:0.12em;font-weight:500;
}

/* ── SECTION HEADER ── */
.sh{display:flex;align-items:center;gap:22px;margin-bottom:60px}
.sh-num{
  font-family:var(--fs);font-size:13px;color:var(--ink4);
  letter-spacing:0.1em;font-style:italic;
}
.sh-title{
  font-family:var(--fs);font-size:40px;font-weight:500;
  letter-spacing:-0.5px;color:var(--ink);
}
.sh-line{flex:1;height:1px;background:linear-gradient(90deg,var(--border2),transparent)}

/* ── EXPERIENCE ── */
#experience{
  background:var(--surface);
  border-top:1px solid var(--border);
  border-bottom:1px solid var(--border);
}
.exp-list{display:flex;flex-direction:column;gap:4px}
.exp-card{
  background:var(--bg);border:1px solid var(--border);
  border-radius:8px;overflow:hidden;
  transition:border-color 0.3s,box-shadow 0.3s;
}
.exp-card:hover{
  border-color:var(--border2);
  box-shadow:0 8px 40px rgba(139,111,62,0.08);
}
.exp-card:hover .exp-stripe{transform:scaleY(1)}
.exp-stripe{
  width:3px;position:absolute;top:0;left:0;bottom:0;
  background:linear-gradient(180deg,var(--accent2),var(--accent));
  transform:scaleY(0);transform-origin:top;
  transition:transform 0.5s ease;
}
.exp-top{
  padding:34px 38px 22px;position:relative;
  display:flex;justify-content:space-between;align-items:flex-start;
}
.exp-company{
  font-family:var(--fh);font-size:10.5px;font-weight:700;
  letter-spacing:0.14em;text-transform:uppercase;
  color:var(--accent);margin-bottom:7px;
}
.exp-role{
  font-family:var(--fs);font-size:26px;font-weight:500;
  letter-spacing:-0.3px;color:var(--ink);
}
.exp-chips{display:flex;flex-wrap:wrap;gap:7px;padding:0 38px 26px}
.chip{
  font-size:10px;padding:4px 12px;border-radius:3px;
  border:1px solid var(--border2);color:var(--ink3);
  font-weight:500;letter-spacing:0.05em;
  transition:all 0.2s;background:var(--surface2);
}
.chip:hover{border-color:var(--accent2);color:var(--accent3);background:rgba(196,154,74,0.08)}
.exp-bullets{padding:0 38px 34px;display:flex;flex-direction:column;gap:12px}
.exp-bullets li{
  list-style:none;padding-left:20px;position:relative;
  font-size:14px;color:var(--ink2);line-height:1.75;font-weight:300;
}
.exp-bullets li::before{
  content:'—';position:absolute;left:0;
  color:var(--accent2);font-size:11px;top:5px;line-height:1;
}
.exp-bullets li strong{color:var(--ink);font-weight:600}

/* ── PROJECTS ── */
#projects{background:var(--bg2)}
.proj-grid{display:grid;grid-template-columns:1fr 1fr;gap:24px}
.proj-card{
  background:var(--card);border:1px solid var(--border);
  border-radius:10px;overflow:hidden;
  display:flex;flex-direction:column;
  transition:border-color 0.3s,transform 0.35s,box-shadow 0.35s;
  position:relative;
}
.proj-card:hover{
  border-color:rgba(196,154,74,0.35);
  transform:translateY(-5px);
  box-shadow:0 20px 60px rgba(139,111,62,0.14);
}
.proj-img{
  height:240px;overflow:hidden;position:relative;
  background:var(--surface2);flex-shrink:0;
}
.proj-img img{
  width:100%;height:100%;object-fit:cover;object-position:top;
  transition:transform 0.6s ease;display:block;
  filter:sepia(8%) brightness(0.97);
}
.proj-card:hover .proj-img img{transform:scale(1.04)}
.proj-img-overlay{
  position:absolute;inset:0;
  background:linear-gradient(to bottom,rgba(245,240,232,0) 35%,var(--card) 100%);
  z-index:1;
}
.proj-live{
  position:absolute;top:14px;right:14px;z-index:2;
  display:flex;align-items:center;gap:6px;
  background:rgba(245,240,232,0.88);backdrop-filter:blur(10px);
  border:1px solid var(--border2);color:var(--accent3);
  font-size:10px;font-weight:700;letter-spacing:0.12em;
  padding:5px 13px;border-radius:3px;text-decoration:none;
  text-transform:uppercase;transition:all 0.25s;font-family:var(--fh);
}
.proj-live-dot{
  width:5px;height:5px;border-radius:50%;
  background:var(--warm);animation:glow 2s infinite;
}
.proj-live:hover{
  background:var(--ink);color:var(--bg);
  border-color:var(--ink);
}
.proj-body{padding:28px 30px 28px;flex:1;display:flex;flex-direction:column}
.proj-cat{
  font-size:10px;letter-spacing:0.14em;text-transform:uppercase;
  color:var(--accent2);margin-bottom:10px;font-weight:600;
}
.proj-name{
  font-family:var(--fs);font-size:28px;font-weight:500;
  letter-spacing:-0.3px;color:var(--ink);margin-bottom:12px;
}
.proj-desc{
  font-size:14px;color:var(--ink2);line-height:1.75;
  font-weight:300;flex:1;margin-bottom:22px;
}
.proj-divider{height:1px;background:var(--border);margin-bottom:20px}
.proj-metrics{display:flex;gap:26px;margin-bottom:20px}
.pm-val{
  font-family:var(--fs);font-size:24px;font-weight:500;
  letter-spacing:-0.5px;color:var(--ink);
}
.pm-val em{font-style:normal;color:var(--accent2);font-size:14px;font-family:var(--fh)}
.pm-lbl{font-size:10px;color:var(--ink3);text-transform:uppercase;letter-spacing:0.1em}
.proj-stack{display:flex;flex-wrap:wrap;gap:6px}

/* ── SKILLS ── */
#skills{
  background:var(--surface);
  border-top:1px solid var(--border);
  border-bottom:1px solid var(--border);
}
.skill-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:20px}
.skill-card{
  background:var(--bg);border:1px solid var(--border);
  border-radius:8px;padding:28px 24px;
  transition:border-color 0.3s,transform 0.3s,box-shadow 0.3s;
}
.skill-card:hover{
  border-color:var(--border2);transform:translateY(-3px);
  box-shadow:0 10px 30px rgba(139,111,62,0.08);
}
.skill-head{
  display:flex;align-items:center;gap:11px;margin-bottom:22px;
  padding-bottom:16px;border-bottom:1px solid var(--border);
}
.skill-icon{
  width:34px;height:34px;border-radius:6px;
  display:flex;align-items:center;justify-content:center;
  font-size:16px;background:var(--surface2);
  border:1px solid var(--border);
}
.skill-head-label{
  font-size:11px;font-weight:700;letter-spacing:0.12em;
  text-transform:uppercase;color:var(--ink2);
}
.skill-items{display:flex;flex-direction:column;gap:0}
.si{
  display:flex;align-items:center;
  font-size:13.5px;color:var(--ink2);font-weight:300;
  padding:9px 0;border-bottom:1px solid var(--border);
  transition:color 0.2s;gap:10px;
}
.si:last-child{border-bottom:none}
.si:hover{color:var(--ink)}
.si-dash{width:8px;height:1px;background:var(--accent2);flex-shrink:0}

/* ── CONTACT ── */
#contact{background:var(--bg);border-top:1px solid var(--border)}
.contact-wrap{
  max-width:820px;margin:0 auto;
  text-align:center;padding:120px 64px;
}
.contact-eyebrow{
  font-family:var(--fh);font-size:11px;letter-spacing:0.16em;
  text-transform:uppercase;color:var(--accent);
  margin-bottom:24px;font-weight:600;
  display:flex;align-items:center;justify-content:center;gap:14px;
}
.contact-eyebrow::before,.contact-eyebrow::after{
  content:'';width:40px;height:1px;background:var(--accent2);
}
.contact-h{
  font-family:var(--fs);
  font-size:clamp(44px,5.5vw,76px);font-weight:300;
  letter-spacing:-1.5px;line-height:1.05;margin-bottom:24px;
  color:var(--ink);
}
.contact-h em{
  font-style:italic;color:var(--accent);
}
.contact-sub{
  font-size:15.5px;color:var(--ink2);line-height:1.8;
  margin-bottom:54px;font-weight:300;max-width:560px;
  margin-left:auto;margin-right:auto;
}
.contact-links{
  display:flex;justify-content:center;gap:12px;flex-wrap:wrap;
}
.clink{
  display:flex;align-items:center;gap:9px;
  padding:12px 22px;border-radius:5px;
  border:1px solid var(--border2);
  color:var(--ink2);text-decoration:none;font-size:13px;
  font-weight:500;background:var(--card);
  transition:all 0.25s;
}
.clink svg{width:15px;height:15px;opacity:0.5}
.clink:hover{
  border-color:var(--accent);color:var(--accent3);
  background:rgba(139,111,62,0.07);
  transform:translateY(-2px);
  box-shadow:0 8px 24px rgba(139,111,62,0.1);
}

footer{
  text-align:center;padding:26px;
  font-size:11.5px;color:var(--ink4);
  border-top:1px solid var(--border);
  letter-spacing:0.08em;font-weight:400;
  background:var(--surface);
}

/* ── REVEAL ── */
.r{opacity:0;transform:translateY(24px);transition:opacity 0.75s ease,transform 0.75s ease}
.r.v{opacity:1;transform:none}

/* ── SCROLLBAR ── */
::-webkit-scrollbar{width:4px}
::-webkit-scrollbar-track{background:var(--bg)}
::-webkit-scrollbar-thumb{background:var(--ink4);border-radius:2px}
</style>
</head>
<body>

<div class="cur" id="cur"></div>
<div class="cur-ring" id="ring"></div>
<canvas id="canvas"></canvas>

<!-- NAV -->
<nav id="nav">
  <a href="#" class="nav-logo">MK<div class="ndot"></div></a>
  <ul class="nav-links">
    <li><a href="#experience">Experience</a></li>
    <li><a href="#projects">Projects</a></li>
    <li><a href="#skills">Skills</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
  <a href="#contact" class="nav-cta">Hire Me →</a>
</nav>

<!-- HERO -->
<section id="hero">
  <div class="hero-inner">
    <div class="r">
      <div class="hero-eyebrow">
        <div class="avail-dot"></div>
        Open to Full-Time &amp; Contract
      </div>
      <h1 class="hero-name">
        Mohith
        <span class="italic">Kovvuri.</span>
      </h1>
      <div class="hero-rule"></div>
      <p class="hero-role">
        Software &amp; AI Engineer
        <span class="role-dot"></span>
        MS Computer Science
      </p>
      <p class="hero-desc">
        I build <strong>end-to-end systems</strong> — from fine-tuning LLMs and shipping RAG pipelines to designing <strong>high-throughput backend services</strong> and cloud-native infrastructure that hold up at scale.
      </p>
      <div class="hero-btns">
        <a href="#projects" class="btn-p">View Projects ↗</a>
        <a href="#contact" class="btn-g">Get in Touch</a>
      </div>
    </div>
    <div class="hero-stats r" style="transition-delay:0.2s">
      <div class="stat">
        <div class="stat-n">2<em>+</em></div>
        <div class="stat-l">Live AI Products</div>
      </div>
      <div class="stat">
        <div class="stat-n">15<em>+</em></div>
        <div class="stat-l">Services HIPAA-Secured</div>
      </div>
      <div class="stat">
        <div class="stat-n">99<em>.2%</em></div>
        <div class="stat-l">Platform Uptime</div>
      </div>
      <div class="stat">
        <div class="stat-n">12<em>k+</em></div>
        <div class="stat-l">Daily Transactions</div>
      </div>
    </div>
  </div>
</section>

<!-- EXPERIENCE -->
<section id="experience">
  <div class="wrap">
    <div class="sh r">
      <span class="sh-num">01 —</span>
      <h2 class="sh-title">Experience</h2>
      <div class="sh-line"></div>
    </div>
    <div class="exp-list">

      <div class="exp-card r">
        <div class="exp-stripe"></div>
        <div class="exp-top">
          <div>
            <div class="exp-company">Johnson &amp; Johnson</div>
            <div class="exp-role">Software Engineer</div>
          </div>
        </div>
        <div class="exp-chips">
          <span class="chip">Java</span><span class="chip">Spring Boot</span>
          <span class="chip">Spring Security</span><span class="chip">PySpark</span>
          <span class="chip">Azure ML</span><span class="chip">Apache Kafka</span>
          <span class="chip">Resilience4j</span><span class="chip">Kubernetes</span>
          <span class="chip">OpenShift</span><span class="chip">Jenkins</span>
          <span class="chip">HIPAA</span><span class="chip">SonarQube</span>
        </div>
        <ul class="exp-bullets">
          <li>Designed scalable <strong>backend services &amp; RESTful APIs</strong> with Java and Spring Boot in a microservices architecture, enabling secure, high-throughput data exchange across distributed healthcare systems.</li>
          <li>Built <strong>predictive healthcare models</strong> in Python and Scikit-learn using ensemble techniques to identify patient risk, enabling earlier and more proactive clinical decision-making.</li>
          <li>Engineered scalable <strong>ML pipelines</strong> with Azure ML and PySpark; developed transformer-based NLP models to extract insights from unstructured medical records.</li>
          <li>Implemented <strong>async, fault-tolerant communication</strong> using Apache Kafka and Resilience4j — circuit breakers, timeouts, fallbacks — plus ThreadPoolExecutor for concurrent request handling.</li>
          <li>Ensured <strong>HIPAA compliance</strong> by detecting PHI across ~15 services, applying Spring method-level security, and building anomaly detection systems.</li>
          <li>Maintained quality via <strong>JUnit/Mockito</strong>, SonarQube scanning, and Jenkins CI/CD deploying on Kubernetes, OpenShift, and Apache Tomcat.</li>
        </ul>
      </div>

      <div class="exp-card r" style="transition-delay:0.12s">
        <div class="exp-stripe"></div>
        <div class="exp-top">
          <div>
            <div class="exp-company">Wipro</div>
            <div class="exp-role">Software Engineer Intern</div>
          </div>
        </div>
        <div class="exp-chips">
          <span class="chip">Java</span><span class="chip">Spring Boot</span>
          <span class="chip">Apache Kafka</span><span class="chip">React</span>
          <span class="chip">ThreadPoolExecutor</span>
          <span class="chip">JUnit</span><span class="chip">Mockito</span>
        </div>
        <ul class="exp-bullets">
          <li>Built <strong>Smarts Plus</strong> — a real-time network device monitoring &amp; alarm system — across the full development lifecycle in an Agile team.</li>
          <li>Developed <strong>RESTful APIs</strong> with Java and Spring Boot to process alarms, manage subscriptions, and raise tickets automatically.</li>
          <li>Configured and tuned <strong>Kafka</strong> producers, consumers, brokers, and topics for async messaging; used ThreadPoolExecutor for concurrent request handling.</li>
          <li>Built the front end as a <strong>React SPA</strong>; maintained code quality with JUnit/Mockito tests, bug fixing, and refactoring.</li>
        </ul>
      </div>

    </div>
  </div>
</section>

<!-- PROJECTS -->
<section id="projects">
  <div class="wrap">
    <div class="sh r">
      <span class="sh-num">02 —</span>
      <h2 class="sh-title">Selected Projects</h2>
      <div class="sh-line"></div>
    </div>
    <div class="proj-grid">

      <div class="proj-card r">
        <div class="proj-img">
          <img src="https://api.microlink.io/?url=https%3A%2F%2Fnovexhub.netlify.app&screenshot=true&meta=false&embed=screenshot.url" alt="Novex"
            onerror="this.style.display='none';this.parentElement.style.background='linear-gradient(135deg,#e8e0cf,#ddd5c2)'"/>
          <div class="proj-img-overlay"></div>
          <a href="https://novexhub.netlify.app/" target="_blank" class="proj-live">
            <div class="proj-live-dot"></div>Live Demo
          </a>
        </div>
        <div class="proj-body">
          <div class="proj-cat">LLMs · Productivity Tool</div>
          <div class="proj-name">Novex</div>
          <p class="proj-desc">Broadcast one prompt to all your AI models simultaneously — Claude, GPT, Gemini — and compare answers side by side. Multi-model AI hub, production-deployed.</p>
          <div class="proj-divider"></div>
          <div class="proj-metrics">
            <div><div class="pm-val">∞<em> models</em></div><div class="pm-lbl">Simultaneous</div></div>
            <div><div class="pm-val">1<em>-click</em></div><div class="pm-lbl">Broadcast</div></div>
            <div><div class="pm-val">Live<em> ↗</em></div><div class="pm-lbl">Production</div></div>
          </div>
          <div class="proj-stack">
            <span class="chip">LLMs</span><span class="chip">FastAPI</span>
            <span class="chip">React</span><span class="chip">AWS</span><span class="chip">Netlify</span>
          </div>
        </div>
      </div>

      <div class="proj-card r" style="transition-delay:0.14s">
        <div class="proj-img">
          <img src="https://api.microlink.io/?url=https%3A%2F%2Fhuggingface.co%2Fspaces%2FMoe32%2FGeoforge&screenshot=true&meta=false&embed=screenshot.url" alt="GeoForge"
            onerror="this.style.display='none';this.parentElement.style.background='linear-gradient(135deg,#e0ddd0,#d5d0bf)'"/>
          <div class="proj-img-overlay"></div>
          <a href="https://huggingface.co/spaces/Moe32/Geoforge" target="_blank" class="proj-live">
            <div class="proj-live-dot"></div>Live Demo
          </a>
        </div>
        <div class="proj-body">
          <div class="proj-cat">Geospatial AI · ML</div>
          <div class="proj-name">GeoForge</div>
          <p class="proj-desc">ML-powered geospatial analysis and visualization tool. Delivers intelligent geographic insights by combining machine learning with geospatial data pipelines. Deployed on Hugging Face Spaces.</p>
          <div class="proj-divider"></div>
          <div class="proj-metrics">
            <div><div class="pm-val">ML<em>-first</em></div><div class="pm-lbl">Architecture</div></div>
            <div><div class="pm-val">HF<em> ↗</em></div><div class="pm-lbl">Deployed</div></div>
            <div><div class="pm-val">Live<em> ↗</em></div><div class="pm-lbl">Production</div></div>
          </div>
          <div class="proj-stack">
            <span class="chip">Python</span><span class="chip">ML</span>
            <span class="chip">Gradio</span><span class="chip">Hugging Face</span>
          </div>
        </div>
      </div>

    </div>
  </div>
</section>

<!-- SKILLS -->
<section id="skills">
  <div class="wrap">
    <div class="sh r">
      <span class="sh-num">03 —</span>
      <h2 class="sh-title">Technical Stack</h2>
      <div class="sh-line"></div>
    </div>
    <div class="skill-grid">
      <div class="skill-card r">
        <div class="skill-head">
          <div class="skill-icon">🐍</div>
          <span class="skill-head-label">Languages</span>
        </div>
        <div class="skill-items">
          <div class="si"><span class="si-dash"></span>Python</div>
          <div class="si"><span class="si-dash"></span>Java</div>
          <div class="si"><span class="si-dash"></span>TypeScript</div>
          <div class="si"><span class="si-dash"></span>JavaScript</div>
          <div class="si"><span class="si-dash"></span>SQL</div>
        </div>
      </div>
      <div class="skill-card r" style="transition-delay:0.08s">
        <div class="skill-head">
          <div class="skill-icon">🤖</div>
          <span class="skill-head-label">AI / ML</span>
        </div>
        <div class="skill-items">
          <div class="si"><span class="si-dash"></span>LangChain</div>
          <div class="si"><span class="si-dash"></span>OpenAI GPT-4o</div>
          <div class="si"><span class="si-dash"></span>HuggingFace · T5</div>
          <div class="si"><span class="si-dash"></span>RAG Pipelines</div>
          <div class="si"><span class="si-dash"></span>Vector Databases</div>
          <div class="si"><span class="si-dash"></span>Scikit-learn · NLP</div>
          <div class="si"><span class="si-dash"></span>AWS SageMaker</div>
        </div>
      </div>
      <div class="skill-card r" style="transition-delay:0.16s">
        <div class="skill-head">
          <div class="skill-icon">⚙️</div>
          <span class="skill-head-label">Backend &amp; APIs</span>
        </div>
        <div class="skill-items">
          <div class="si"><span class="si-dash"></span>Spring Boot</div>
          <div class="si"><span class="si-dash"></span>Spring Security</div>
          <div class="si"><span class="si-dash"></span>FastAPI · NestJS</div>
          <div class="si"><span class="si-dash"></span>Microservices</div>
          <div class="si"><span class="si-dash"></span>Apache Kafka</div>
          <div class="si"><span class="si-dash"></span>PySpark</div>
          <div class="si"><span class="si-dash"></span>Resilience4j</div>
        </div>
      </div>
      <div class="skill-card r" style="transition-delay:0.24s">
        <div class="skill-head">
          <div class="skill-icon">☁️</div>
          <span class="skill-head-label">Cloud &amp; DevOps</span>
        </div>
        <div class="skill-items">
          <div class="si"><span class="si-dash"></span>AWS (EC2/S3/Lambda)</div>
          <div class="si"><span class="si-dash"></span>Azure ML</div>
          <div class="si"><span class="si-dash"></span>Docker · Kubernetes</div>
          <div class="si"><span class="si-dash"></span>OpenShift</div>
          <div class="si"><span class="si-dash"></span>Jenkins CI/CD</div>
          <div class="si"><span class="si-dash"></span>SonarQube</div>
          <div class="si"><span class="si-dash"></span>JUnit · Mockito</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <div class="contact-wrap r">
    <div class="contact-eyebrow">Let's work together</div>
    <h2 class="contact-h">Let's build something <em>real.</em></h2>
    <p class="contact-sub">
      MS Computer Science graduate open to full-time and contract roles in Software Engineering, AI/ML Engineering, and Backend Systems. Always happy to talk through interesting problems.
    </p>
    <div class="contact-links">
      <a href="mailto:mohithkovvuri92@gmail.com" class="clink">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="2" y="4" width="20" height="16" rx="2"/><path d="m22 7-8.97 5.7a1.94 1.94 0 0 1-2.06 0L2 7"/></svg>
        mohithkovvuri92@gmail.com
      </a>
      <a href="https://www.linkedin.com/in/mohithkovvuri1" target="_blank" class="clink">
        <svg viewBox="0 0 24 24" fill="currentColor"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6zM2 9h4v12H2z"/><circle cx="4" cy="4" r="2"/></svg>
        LinkedIn
      </a>
      <a href="https://github.com/mohith-1" target="_blank" class="clink">
        <svg viewBox="0 0 24 24" fill="currentColor"><path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"/></svg>
        GitHub
      </a>
      <a href="tel:+19039335277" class="clink">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07A19.5 19.5 0 0 1 4.69 13a19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 3.6 2h3a2 2 0 0 1 2 1.72c.127.96.361 1.903.7 2.81a2 2 0 0 1-.45 2.11L7.91 9.91a16 16 0 0 0 6.16 6.16l.91-.91a2 2 0 0 1 2.11-.45c.907.339 1.85.573 2.81.7A2 2 0 0 1 22 16.92z"/></svg>
        (903) 933-5277
      </a>
    </div>
  </div>
</section>

<footer>© 2026 Mohith Reddy Kovvuri &nbsp;·&nbsp; Crafted with care</footer>

<script>
/* ── CURSOR ── */
const cur=document.getElementById('cur'),ring=document.getElementById('ring');
let mx=0,my=0,rx=0,ry=0;
document.addEventListener('mousemove',e=>{
  mx=e.clientX;my=e.clientY;
  cur.style.left=mx+'px';cur.style.top=my+'px';
});
(function loop(){rx+=(mx-rx)*0.1;ry+=(my-ry)*0.1;ring.style.left=rx+'px';ring.style.top=ry+'px';requestAnimationFrame(loop)})();
document.querySelectorAll('a,button').forEach(el=>{
  el.addEventListener('mouseenter',()=>{cur.style.width='16px';cur.style.height='16px';ring.style.width='50px';ring.style.height='50px'});
  el.addEventListener('mouseleave',()=>{cur.style.width='8px';cur.style.height='8px';ring.style.width='32px';ring.style.height='32px'});
});

/* ── FLOATING DUST PARTICLES ── */
const canvas=document.getElementById('canvas');
const ctx=canvas.getContext('2d');
let W,H;
function resize(){W=canvas.width=window.innerWidth;H=canvas.height=window.innerHeight}
resize();window.addEventListener('resize',resize);
class Mote{
  constructor(){this.reset(true)}
  reset(init){
    this.x=Math.random()*W;
    this.y=init?Math.random()*H:H+10;
    this.vy=-(Math.random()*0.4+0.1);
    this.vx=(Math.random()-0.5)*0.15;
    this.r=Math.random()*1.8+0.4;
    this.life=init?Math.random():0;
    this.maxLife=Math.random()*0.6+0.3;
    this.growing=true;
    const p=Math.random();
    if(p<0.5)this.c='rgba(196,154,74,';
    else if(p<0.8)this.c='rgba(139,111,62,';
    else this.c='rgba(212,168,90,';
  }
  update(){
    this.x+=this.vx;this.y+=this.vy;
    if(this.growing){this.life+=0.006;if(this.life>=this.maxLife)this.growing=false}
    else{this.life-=0.004}
    if(this.life<=0||this.y<-10)this.reset(false);
  }
  draw(){
    const a=Math.min(this.life*1.4,0.55);
    ctx.beginPath();ctx.arc(this.x,this.y,this.r,0,Math.PI*2);
    ctx.fillStyle=this.c+a+')';ctx.fill();
  }
}
const motes=[];for(let i=0;i<80;i++)motes.push(new Mote());
function drawLines(){
  for(let i=0;i<motes.length;i++){
    for(let j=i+1;j<motes.length;j++){
      const dx=motes[i].x-motes[j].x,dy=motes[i].y-motes[j].y;
      const d=Math.sqrt(dx*dx+dy*dy);
      if(d<90){
        const a=(1-d/90)*0.07;
        ctx.strokeStyle=`rgba(196,154,74,${a})`;
        ctx.lineWidth=0.5;ctx.beginPath();
        ctx.moveTo(motes[i].x,motes[i].y);ctx.lineTo(motes[j].x,motes[j].y);ctx.stroke();
      }
    }
  }
}
(function anim(){
  ctx.clearRect(0,0,W,H);
  drawLines();motes.forEach(m=>{m.update();m.draw()});
  requestAnimationFrame(anim);
})();

/* ── SCROLL REVEAL ── */
const obs=new IntersectionObserver(entries=>{
  entries.forEach(e=>{if(e.isIntersecting){e.target.classList.add('v');obs.unobserve(e.target)}});
},{threshold:0.07});
document.querySelectorAll('.r').forEach(el=>obs.observe(el));
setTimeout(()=>document.querySelectorAll('#hero .r').forEach(el=>el.classList.add('v')),120);

/* ── NAV SCROLL ── */
const nav=document.getElementById('nav');
window.addEventListener('scroll',()=>{
  nav.style.background=window.scrollY>60
    ?'rgba(245,240,232,0.96)':'rgba(245,240,232,0.82)';
});
</script>
</body>
</html>
