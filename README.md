<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Portfolio — Kartik Yadav</title>
  <meta name="description" content="Portfolio of Kartik Yadav, a web developer focused on modern front-end, React, and MERN." />
  <!-- Favicon: place favicon.ico or favicon.png alongside this file -->
  <link rel="icon" href="favicon.ico" type="image/x-icon" />
  <link rel="icon" href="favicon.png" type="image/png" />
  <style>
    :root{
      --sunset-deep:#003f5c;
      --sunset-violet:#58508d;
      --sunset-magenta:#bc5090;
      --sunset-coral:#ff6361;
      --sunset-amber:#ffa600;

      --bg:#0b1220; --text:#f7f8fc; --muted:#cfd6e6; --card-border:rgba(255,255,255,0.14);
      --shadow:0 10px 40px rgba(8,24,58,0.4);

      --radius-lg:20px; --radius-md:14px;

      --grad-sky: radial-gradient(1200px 800px at 20% 10%, rgba(255,166,0,0.25) 0%, rgba(252,99,84,0.20) 30%, rgba(188,80,144,0.18) 55%, rgba(88,80,141,0.16) 75%, rgba(0,63,92,0.14) 100%);
      --grad-header: linear-gradient(135deg, rgba(255,166,0,0.22), rgba(252,99,97,0.20) 35%, rgba(188,80,144,0.18) 70%);
      --grad-border: linear-gradient(135deg, rgba(255,166,0,0.9), rgba(252,99,97,0.9) 40%, rgba(188,80,144,0.9) 75%);
      --transition:240ms cubic-bezier(.2,.7,.2,1);
    }

    html,body{
      margin:0; padding:0; height:100%;
      background:
        radial-gradient(900px 600px at 85% 10%, rgba(253,94,83,0.18), transparent 60%),
        radial-gradient(900px 600px at 15% 80%, rgba(88,80,141,0.20), transparent 60%),
        var(--grad-sky),
        var(--bg);
      color:var(--text);
      font-family: ui-sans-serif, system-ui, -apple-system, Segoe UI, Roboto, Inter, Arial, sans-serif;
      line-height:1.6; overflow-x:hidden;
    }

    .glow{ position:fixed; inset:0; pointer-events:none; z-index:0; }
    .blob{ position:absolute; filter: blur(60px); opacity:.45; mix-blend-mode: screen; animation: float var(--dur,18s) ease-in-out infinite; }
    .blob.one{ background: radial-gradient(circle, var(--sunset-amber), transparent 60%); width:480px;height:480px; top:8%; left:8%; --dur:22s;}
    .blob.two{ background: radial-gradient(circle, var(--sunset-coral), transparent 60%); width:420px;height:420px; top:18%; right:10%; --dur:26s;}
    .blob.three{ background: radial-gradient(circle, var(--sunset-magenta), transparent 60%); width:520px;height:520px; bottom:6%; left:18%; --dur:28s;}
    @keyframes float{ 0%,100%{transform:translateY(0) translateX(0) scale(1);} 50%{transform:translateY(-18px) translateX(8px) scale(1.03);} }

    main{
      position:relative; z-index:1; width:100%; max-width:960px; margin: clamp(24px, 6vw, 60px) auto;
      padding: clamp(16px, 3vw, 24px); border-radius: var(--radius-lg);
      background: linear-gradient(180deg, rgba(255,255,255,0.06), rgba(255,255,255,0.02));
      backdrop-filter: blur(14px) saturate(120%); -webkit-backdrop-filter: blur(14px) saturate(120%);
      border:1px solid var(--card-border); box-shadow: var(--shadow);
    }

    header{
      padding: 48px 16px 28px; text-align:center; border-radius: var(--radius-md);
      background: var(--grad-header); border:1px solid rgba(255,255,255,0.18); position:relative; overflow:hidden;
    }
    header::after{
      content:""; position:absolute; inset:-2px; border-radius:inherit; padding:1px;
      background: var(--grad-border);
      -webkit-mask: linear-gradient(#000 0 0) content-box, linear-gradient(#000 0 0);
      -webkit-mask-composite: xor; mask-composite: exclude; pointer-events:none; opacity:.35;
    }
    h1{ margin:0 0 8px; font-size: clamp(28px, 4.5vw, 44px); letter-spacing:.5px; text-shadow: 0 2px 14px rgba(255,166,0,0.22); }
    h2{ margin:8px 0 0; font-weight:600; color:#e2e7f7; letter-spacing:.3px; }

    .cta-row{ display:flex; gap:12px; justify-content:center; margin-top: 14px; flex-wrap: wrap; }
    .btn{
      appearance:none; border:0; cursor:pointer; text-decoration:none; padding:10px 16px; border-radius:12px; font-weight:600;
      color:#0b1220; background: linear-gradient(135deg, var(--sunset-amber), var(--sunset-coral));
      box-shadow: 0 8px 24px rgba(255,166,0,0.35);
      transition: transform var(--transition), box-shadow var(--transition), filter var(--transition);
    }
    .btn:hover{ transform: translateY(-3px); filter: saturate(1.1); box-shadow: 0 14px 40px rgba(188,80,144,0.35); }

    section{
      margin: 28px 0; padding: 28px; border-radius: var(--radius-md);
      background: linear-gradient(180deg, rgba(255,255,255,0.06), rgba(255,255,255,0.02));
      border:1px solid rgba(255,255,255,0.14); backdrop-filter: blur(8px); -webkit-backdrop-filter: blur(8px);
      transition: transform var(--transition), box-shadow var(--transition), border-color var(--transition); text-align:center;
    }
    section:hover{ transform: translateY(-4px); box-shadow: 0 14px 50px rgba(0,0,0,0.28); border-color: rgba(255,166,0,0.45); }

    .about-me p{ margin:0; font-size:clamp(16px, 2.4vw, 18px); color:#e9efff; max-width: 70ch; margin-inline:auto; }

    .skills-list{ display:flex; flex-wrap:wrap; gap:12px; justify-content:center; margin-top:10px; }
    .skill{
      background: linear-gradient(135deg, rgba(0,63,92,0.25), rgba(88,80,141,0.25));
      border:1px solid rgba(255,255,255,0.18); color:#f9fbff; padding:10px 16px; border-radius:999px; font-size:15px; letter-spacing:.2px;
      transition: transform var(--transition), background var(--transition), border-color var(--transition);
    }
    .skill:hover{
      transform: translateY(-2px);
      background: linear-gradient(135deg, rgba(255,166,0,0.30), rgba(252,99,97,0.28) 50%, rgba(188,80,144,0.28) 100%);
      border-color: rgba(255,166,0,0.45);
    }

    ul{ list-style:none; padding:0; margin: 10px 0 0; }
    li{ margin:10px 0; color:#e6ecff; }

    .tag{
      display:inline-block; margin-left:8px; padding:2px 8px; border-radius:999px; font-size:12px; letter-spacing:.2px; color:#0b1220;
      background: linear-gradient(135deg, var(--sunset-amber), var(--sunset-coral) 60%, var(--sunset-magenta));
      box-shadow: 0 4px 18px rgba(255,166,0,0.35);
    }

    /* Projects grid */
    .projects .grid{
      display:grid;
      grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
      gap:16px;
      margin-top:12px;
    }
    .card{
      text-align:left;
      padding:18px;
      border-radius:16px;
      border:1px solid rgba(255,255,255,0.14);
      background: linear-gradient(180deg, rgba(255,255,255,0.06), rgba(255,255,255,0.02));
      backdrop-filter: blur(8px);
      transition: transform var(--transition), border-color var(--transition), box-shadow var(--transition);
    }
    .card:hover{
      transform: translateY(-3px);
      border-color: rgba(255,166,0,0.45);
      box-shadow: 0 10px 28px rgba(0,0,0,0.25);
    }
    .card h3{ margin:0 0 6px; font-size:18px; }
    .card p{ margin:0; color:#e9efff; font-size:15px; }

    /* Back to top */
    #toTop{
      position:fixed; right:18px; bottom:18px; z-index:10;
      display:none; border:0; border-radius:999px; padding:10px 14px;
      background: linear-gradient(135deg, var(--sunset-amber), var(--sunset-coral));
      color:#0b1220; font-weight:700; cursor:pointer;
      box-shadow: 0 8px 24px rgba(255,166,0,0.35);
    }
    #toTop:focus{ outline:2px solid #fff; outline-offset:2px; }

    @media (max-width: 640px){ main{ padding:14px; } section{ padding:18px; } }
    @media (prefers-reduced-motion: reduce){
      *{ animation:none !important; transition:none !important; }
      html{ scroll-behavior: auto !important; }
    }
  </style>
</head>
<body>
  <div id="top"></div>

  <div class="glow">
    <div class="blob one"></div>
    <div class="blob two"></div>
    <div class="blob three"></div>
  </div>

  <main>
    <header>
      <h1>Kartik Yadav</h1>
      <h2>Web Developer</h2>
      <div class="cta-row">
        <a class="btn" href="mailto:kartik8.net@gmail.com" aria-label="Email Kartik Yadav">Contact</a>
        <a class="btn" style="background: linear-gradient(135deg, var(--sunset-coral), var(--sunset-magenta));" href="#" aria-label="Download Resume">Resume</a>
      </div>
    </header>

    <section class="about-me">
      <h2>About Me</h2>
      <p>Front‑end web developer crafting performant, accessible interfaces with modern tooling and clean architecture. Comfortable across HTML, CSS, JavaScript, React, Node.js, and MongoDB, with a focus on translating design systems into responsive, production‑ready components. Passionate about UX, performance optimization, and collaborative delivery, with ongoing self‑directed learning via YouTube and AI to stay aligned with current best practices.</p>
    </section>

    <section class="skills">
      <h2>Skills</h2>
      <div class="skills-list">
        <span class="skill">HTML</span>
        <span class="skill">CSS</span>
        <span class="skill">JavaScript</span>
        <span class="skill">React</span>
        <span class="skill">Node.js</span>
        <span class="skill">MongoDB</span>
      </div>
    </section>

    <section class="experience">
      <h2>Experience</h2>
      <ul>
        <li>Front-End Developer at Company A (2023–2025) <span class="tag">React</span></li>
        <li>Intern at Tech Startup (2022) <span class="tag">UI</span></li>
      </ul>
    </section>

    <section class="projects">
      <h2>Projects</h2>
      <div class="grid">
        <article class="card">
          <h3>UI Components Library</h3>
          <p>Reusable, accessible React components with theming and tests.</p>
        </article>
        <article class="card">
          <h3>API Dashboard</h3>
          <p>Node.js + MongoDB metrics dashboard with JWT auth.</p>
        </article>
        <article class="card">
          <h3>Portfolio Theme</h3>
          <p>Responsive CSS Grid layout with glassmorphism accents.</p>
        </article>
      </div>
    </section>

    <section class="education">
      <h2>Education</h2>
      <ul>
        <li><strong>Self‑Directed Learning</strong> — YouTube tutorials and AI‑assisted study in web development, front‑end frameworks, and MERN concepts (ongoing) <span class="tag">Continuous</span></li>
      </ul>
    </section>
  </main>

  <button id="toTop" aria-label="Back to top">↑</button>

  <script>
    // Section entrance
    const cards = document.querySelectorAll('section, header');
    const obs = new IntersectionObserver((entries)=>{
      entries.forEach(e=>{
        if(e.isIntersecting){
          e.target.animate(
            [{ transform:'translateY(16px)', opacity:0 }, { transform:'translateY(0)', opacity:1 }],
            { duration: 500, easing:'cubic-bezier(.2,.7,.2,1)', fill:'forwards' }
          );
          obs.unobserve(e.target);
        }
      });
    }, { threshold: 0.15 });
    cards.forEach(c=>obs.observe(c));

    // Back to top visibility + behavior
    const toTop = document.getElementById('toTop');
    const showAfter = 300; // px
    window.addEventListener('scroll', () => {
      if (window.scrollY > showAfter) toTop.style.display = 'inline-block';
      else toTop.style.display = 'none';
    });
    toTop.addEventListener('click', () => {
      document.getElementById('top').scrollIntoView({ behavior: 'smooth' });
      toTop.focus();
    });
  </script>
</body>
</html>
