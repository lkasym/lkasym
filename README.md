<!-- index.html
  Single-file premium personal landing page for Lakshit Mundra (lkasym)
  Instructions:
  - Save as index.html in your repo or a directory served by GitHub Pages.
  - Replace placeholder images in /assets or repo root:
      ./assets/banner.jpg     (1200x300px, ~200KB)
      ./assets/hero-gif.gif   (optional; 400x400, lightweight)
      ./assets/project-*.png  (screenshots ~800x450)
      ./assets/avatar.jpg     (300x300 square)
  - Update contact email/link hrefs where noted.
  - This file is fully standalone (no external libs).
-->
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Lakshit Mundra — AI Engineer • Automated Agents • MLOps</title>
  <meta name="description" content="Lakshit Mundra — AI Intern at Allentics. Building automated AI agents, LLM workflows, and production ML pipelines." />
  <meta name="theme-color" content="#0ea5a4"/>
  <style>
    /* ---------- BASE ---------- */
    :root{
      --bg:#0b1020;
      --card:#071022;
      --muted:#9aa4b2;
      --accent:#00b3af;
      --accent-2:#ff7a18;
      --glass: rgba(255,255,255,0.04);
      --glass-2: rgba(255,255,255,0.02);
      --white: #e6eef6;
      --rounded: 14px;
      font-family: Inter, ui-sans-serif, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
    }
    html,body{height:100%;margin:0;background:
      linear-gradient(180deg,#051018 0%, #071026 60%); color:var(--white); -webkit-font-smoothing:antialiased;}
    a{color:var(--accent); text-decoration:none}
    img{max-width:100%;height:auto;display:block}
    .container{max-width:1100px;margin:28px auto;padding:24px}
    .card{background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01)); border-radius:var(--rounded); box-shadow:0 8px 30px rgba(2,6,23,0.6); padding:20px}
    header{display:flex;align-items:center;justify-content:space-between;gap:20px}
    .brand{display:flex;align-items:center;gap:14px}
    .brand img{width:56px;height:56px;border-radius:12px;object-fit:cover;border:2px solid rgba(255,255,255,0.06)}
    .brand h1{margin:0;font-size:20px;letter-spacing:0.2px}
    .nav{display:flex;gap:12px;align-items:center}
    .btn{background:linear-gradient(90deg,var(--accent),var(--accent-2));border:none;padding:10px 14px;border-radius:10px;color:#061017;font-weight:600;cursor:pointer;box-shadow:0 6px 20px rgba(0,179,175,0.12)}
    .ghost{background:transparent;border:1px solid rgba(255,255,255,0.06);padding:8px 12px;border-radius:10px;color:var(--white)}
    /* ---------- HERO ---------- */
    .hero{display:grid;grid-template-columns:1fr 420px;gap:28px;align-items:center;margin-top:18px}
    .hero-left h2{font-size:34px;margin:0 0 8px 0;line-height:1.05}
    .hero-left h3{color:var(--muted);margin:0 0 18px 0;font-weight:500}
    .badges{display:flex;gap:10px;flex-wrap:wrap;margin-bottom:18px}
    .badge{background:var(--glass);padding:8px 10px;border-radius:999px;color:var(--muted);font-weight:600;font-size:13px;border:1px solid rgba(255,255,255,0.02)}
    .hero-cta{display:flex;gap:12px;align-items:center}
    .hero-right{display:flex;align-items:center;justify-content:center}
    .hero-card{width:380px;border-radius:18px;padding:14px;background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));box-shadow:0 18px 60px rgba(0,0,0,0.6)}
    .hero-avatar{width:86px;height:86px;border-radius:12px;float:right;border:3px solid rgba(255,255,255,0.04);object-fit:cover}
    /* ---------- GRID ---------- */
    .columns{display:grid;grid-template-columns:2fr 1fr;gap:22px;margin-top:20px}
    .section-title{display:flex;align-items:center;gap:12px;margin:10px 0;color:var(--muted);font-weight:600}
    .small{font-size:13px;color:var(--muted)}
    /* ---------- PROJECT CARDS ---------- */
    .projects{display:grid;grid-template-columns:repeat(2,1fr);gap:14px}
    .proj{background:linear-gradient(0deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));border-radius:12px;padding:12px;display:flex;gap:12px;align-items:center}
    .proj img{width:120px;height:80px;border-radius:8px;object-fit:cover}
    .proj h4{margin:0 0 6px 0}
    .techs{display:flex;gap:8px;flex-wrap:wrap;margin-top:8px}
    .pill{background:rgba(255,255,255,0.03);padding:6px 8px;border-radius:10px;font-size:12px;color:var(--muted)}
    /* ---------- SKILLS ---------- */
    .skill-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:12px}
    .skill{background:var(--glass-2);padding:8px;border-radius:10px;text-align:center}
    /* ---------- CONTACT ---------- */
    .contact-form{display:flex;flex-direction:column;gap:10px}
    input,textarea{background:transparent;border:1px solid rgba(255,255,255,0.06);padding:10px;border-radius:8px;color:var(--white);resize:vertical}
    label{font-size:13px;color:var(--muted)}
    /* ---------- FOOTER ---------- */
    footer{margin-top:28px;text-align:center;color:var(--muted);font-size:13px}
    /* ---------- RESPONSIVE ---------- */
    @media (max-width:980px){
      .hero{grid-template-columns:1fr; padding-bottom:12px}
      .columns{grid-template-columns:1fr}
      .projects{grid-template-columns:1fr}
      .hero-right{order:-1}
    }
    /* ---------- ANIMATIONS ---------- */
    .appear{opacity:0;transform:translateY(10px);animation:appear .7s forwards}
    .delay-1{animation-delay:.08s} .delay-2{animation-delay:.16s} .delay-3{animation-delay:.24s}
    @keyframes appear{to{opacity:1;transform:none}}
  </style>
</head>
<body>
  <div class="container">
    <div class="card">
      <header class="appear">
        <div class="brand">
          <!-- Avatar: replace ./assets/avatar.jpg -->
          <img src="./assets/avatar.jpg" alt="Lakshit Mundra avatar" />
          <div>
            <h1 style="margin-bottom:4px">Lakshit Mundra</h1>
            <div class="small">AI Intern @ Allentics • Building automated AI agents & production ML</div>
          </div>
        </div>
        <nav class="nav">
          <a class="ghost" href="#projects">Projects</a>
          <a class="ghost" href="#skills">Skills</a>
          <a class="ghost" href="#contact">Contact</a>
          <button class="btn" onclick="document.querySelector('#contact').scrollIntoView({behavior:'smooth'})">Let's build →</button>
        </nav>
      </header>

      <!-- HERO -->
      <section class="hero">
        <div class="hero-left appear delay-1">
          <h2>Engineering Automated AI Agents & Intelligent Systems</h2>
          <h3>Designing LLM-driven workflows, multi-agent autonomy, and production ML that actually runs in business.</h3>

          <div class="badges">
            <span class="badge">AI Agents</span>
            <span class="badge">MLOps</span>
            <span class="badge">Computer Vision</span>
            <span class="badge">Time-series</span>
          </div>

          <p class="small" style="max-width:720px">
            I build systems that replace repetitive workflows, make intelligent decisions, and run end-to-end — from data ingestion to observability. My current focus is on autonomous agents that connect LLMs, tools, and monitoring for real business automation.
          </p>

          <div class="hero-cta" style="margin-top:18px">
            <button class="btn" onclick="scrollToSection('projects')">Explore projects</button>
            <a class="ghost" href="mailto:lakshit.mundra.16@gmail.com">Email me</a>
          </div>

          <div style="margin-top:14px" class="small">
            <strong>Quick wins I deliver:</strong> deployable pipelines, robust monitoring, multi-agent decision flows, and production-ready LLM integrations.
          </div>
        </div>

        <div class="hero-right appear delay-2">
          <div class="hero-card">
            <!-- Banner/animated gif: replace ./assets/hero-gif.gif or use banner -->
            <img src="./assets/hero-gif.gif" alt="hero gif" style="border-radius:10px;margin-bottom:10px"/>
            <div style="display:flex;justify-content:space-between;align-items:center">
              <div>
                <div style="font-weight:700">AI Intern — Allentics</div>
                <div class="small">Building automated agents & LLM workflows</div>
              </div>
              <img class="hero-avatar" src="./assets/avatar.jpg" alt="avatar small"/>
            </div>
          </div>
        </div>
      </section>

      <div style="height:18px"></div>
      <div class="columns">
        <!-- left column -->
        <div>
          <div id="projects" class="section-title appear delay-3">
            <svg width="18" height="18" viewBox="0 0 24 24" fill="none" style="opacity:.9"><path d="M3 7h18M3 12h18M3 17h18" stroke="currentColor" stroke-width="1.5" stroke-linecap="round"/></svg>
            <div>Selected Projects</div>
          </div>

          <div class="projects">
            <article class="proj appear delay-1">
              <img src="./assets/project-agents.png" alt="Autonomous Agents" />
              <div>
                <h4>Autonomous Agents Suite</h4>
                <div class="small">Multi-agent orchestration with memory, tool use, and observable pipelines.</div>
                <div class="techs">
                  <span class="pill">LLMs</span><span class="pill">FastAPI</span><span class="pill">Docker</span>
                </div>
              </div>
            </article>

            <article class="proj appear delay-2">
              <img src="./assets/project-echo.png" alt="Echocardiogram" />
              <div>
                <h4>Echocardiogram Phase Detection</h4>
                <div class="small">Unsupervised cardiac-phase detection (optical flow + contrastive learning).</div>
                <div class="techs">
                  <span class="pill">PyTorch</span><span class="pill">OpenCV</span><span class="pill">ML Ops</span>
                </div>
              </div>
            </article>

            <article class="proj appear delay-3">
              <img src="./assets/project-stock.png" alt="Stock" />
              <div>
                <h4>Predictive Stock Models</h4>
                <div class="small">Feature engineering + ensemble stacking for mid-cap NSE forecasting.</div>
                <div class="techs">
                  <span class="pill">Time-series</span><span class="pill">Pandas</span><span class="pill">Backtest</span>
                </div>
              </div>
            </article>

            <article class="proj appear delay-1">
              <img src="./assets/project-deepfake.png" alt="Deepfake" />
              <div>
                <h4>Deepfake Detection</h4>
                <div class="small">Spatio-temporal model to detect manipulated video sequences.</div>
                <div class="techs">
                  <span class="pill">CNN</span><span class="pill">Optical flow</span><span class="pill">ROC/PR</span>
                </div>
              </div>
            </article>
          </div>

          <div style="height:18px"></div>
          <div class="section-title">
            <svg width="18" height="18" viewBox="0 0 24 24" fill="none"><path d="M12 2v20M2 12h20" stroke="currentColor" stroke-width="1.4" stroke-linecap="round"/></svg>
            <div>Experience & Impact</div>
          </div>
          <div style="display:flex;gap:12px;flex-direction:column">
            <div class="card" style="padding:12px;background:linear-gradient(180deg, rgba(255,255,255,0.01), rgba(255,255,255,0.005))">
              <strong>AI Intern — Allentics IT Solutions (Present)</strong>
              <div class="small" style="margin-top:6px">Building autonomous agents, LLM-based workflows, integrating tools and APIs, delivering deployable pipelines with monitoring.</div>
            </div>

            <div class="card" style="padding:12px;background:linear-gradient(180deg, rgba(255,255,255,0.01), rgba(255,255,255,0.005))">
              <strong>Web Development Intern — OM Spare Parts Service (2023)</strong>
              <div class="small" style="margin-top:6px">Built production website, improved UX and performance metrics across the funnel.</div>
            </div>
          </div>
        </div>

        <!-- right column -->
        <aside>
          <div class="section-title">
            <svg width="18" height="18" viewBox="0 0 24 24" fill="none"><path d="M6 3h12v18H6z" stroke="currentColor" stroke-width="1.4" stroke-linecap="round" stroke-linejoin="round"/></svg>
            <div>Skills & Tools</div>
          </div>

          <div class="card small">
            <div class="small" style="font-weight:700;margin-bottom:8px">Languages</div>
            <div class="skill-grid">
              <div class="skill">Python</div>
              <div class="skill">C</div>
              <div class="skill">TypeScript</div>
            </div>

            <div style="height:12px"></div>
            <div class="small" style="font-weight:700;margin-bottom:8px">Frameworks & Tools</div>
            <div class="skill-grid">
              <div class="skill">PyTorch</div>
              <div class="skill">TensorFlow</div>
              <div class="skill">FastAPI</div>
            </div>

            <div style="height:12px"></div>
            <div class="small" style="font-weight:700;margin-bottom:8px">Deployment</div>
            <div class="skill-grid">
              <div class="skill">Docker</div>
              <div class="skill">CI/CD</div>
              <div class="skill">Monitoring</div>
            </div>

            <div style="height:14px"></div>
            <div class="small" style="font-weight:700;margin-bottom:8px">Data & BI</div>
            <div class="skill-grid">
              <div class="skill">Pandas</div>
              <div class="skill">SQL/MySQL</div>
              <div class="skill">PowerBI/Tableau</div>
            </div>
          </div>

          <div style="height:18px"></div>
          <div class="section-title">
            <div>Contact</div>
          </div>

          <div class="card">
            <div class="small" style="margin-bottom:8px">Let's build something. Tell me about your project or role.</div>
            <form id="contact" class="contact-form" onsubmit="handleContact(event)">
              <label for="name">Name</label>
              <input id="name" required placeholder="Your name" />
              <label for="email">Email</label>
              <input id="email" type="email" required placeholder="you@example.com" />
              <label for="message">What do you want to build?</label>
              <textarea id="message" rows="4" placeholder="Short description..."></textarea>
              <div style="display:flex;gap:8px;justify-content:space-between;align-items:center">
                <button class="btn" type="submit">Send message</button>
                <a class="ghost" href="mailto:lakshit.mundra.16@gmail.com">Or email me</a>
              </div>
              <div id="status" class="small" style="margin-top:8px;color:var(--muted)"></div>
            </form>
          </div>

          <div style="height:18px"></div>
          <div class="card small">
            <div style="font-weight:700">Quick links</div>
            <div style="margin-top:8px;display:flex;flex-direction:column;gap:6px">
              <a href="https://github.com/lkasym" target="_blank">GitHub / lkasym</a>
              <a href="https://linkedin.com/in/lakshit-mundra-909814249/" target="_blank">LinkedIn</a>
              <a href="mailto:lakshit.mundra.16@gmail.com">Email</a>
            </div>
          </div>
        </aside>
      </div>

      <footer>
        <div class="small">Designed & built by Lakshit — <span style="color:var(--muted)">AI Intern @ Allentics</span> • <a href="mailto:lakshit.mundra.16@gmail.com">lakshit.mundra.16@gmail.com</a></div>
      </footer>

    </div>
  </div>

  <script>
    /* Smooth scroll helper */
    function scrollToSection(id){
      const el = document.getElementById(id);
      if(el) el.scrollIntoView({behavior:'smooth'});
    }

    /* Contact handler: lightweight - uses mailto fallback
       For production you should connect to a server or form handler (Formspree, Netlify Forms, Zapier) */
    function handleContact(e){
      e.preventDefault();
      const name = document.getElementById('name').value.trim();
      const email = document.getElementById('email').value.trim();
      const message = document.getElementById('message').value.trim();
      const status = document.getElementById('status');
      if(!name || !email){ status.textContent = 'Please add name and email.'; return; }

      // Create mailto for quick demo
      const subject = encodeURIComponent('Portfolio contact from ' + name);
      const body = encodeURIComponent(
        `Name: ${name}\nEmail: ${email}\n\nMessage:\n${message}\n\n-- Sent from portfolio`
      );
      window.location.href = `mailto:lakshit.mundra.16@gmail.com?subject=${subject}&body=${body}`;
      status.textContent = 'Opening mail client...';
    }

    /* Appear animations trigger */
    document.addEventListener('DOMContentLoaded', () => {
      document.querySelectorAll('.appear').forEach((el,i)=> el.style.animationDelay = (i*0.06)+'s');
    });

    /* Small UX note: remove any broken images gracefully */
    window.addEventListener('error', (e) => {
      if(e.target && e.target.tagName === 'IMG') e.target.style.opacity = '0.6';
    }, true);
  </script>
</body>
</html>
