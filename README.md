<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Mayank Charde · AI Full‑Stack</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,400;14..32,500;14..32,600;14..32,700;14..32,800&display=swap" rel="stylesheet" />
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css" />
  <style>
    * { margin: 0; padding: 0; box-sizing: border-box; }
    body {
      background: #08080f;
      display: flex;
      justify-content: center;
      padding: 2.4rem 1.2rem;
      font-family: 'Inter', sans-serif;
      line-height: 1.5;
    }
    .readme {
      max-width: 1024px;
      width: 100%;
      background: #0d1117;
      border-radius: 44px;
      padding: 2.4rem 2.4rem 1.8rem;
      box-shadow: 0 30px 60px -20px rgba(0,0,0,0.9), 0 0 0 1px rgba(88,166,255,0.06);
      border: 1px solid rgba(88,166,255,0.04);
      transition: all 0.2s ease;
      color: #e6edf3;
    }
    /* --- animations --- */
    @keyframes softPulse {
      0% { opacity: 0.8; transform: scale(0.98); }
      50% { opacity: 1; transform: scale(1.01); }
      100% { opacity: 0.8; transform: scale(0.98); }
    }
    .pulse-soft { animation: softPulse 6s ease-in-out infinite; }

    @keyframes gradientMove {
      0% { background-position: 0% 50%; }
      50% { background-position: 100% 50%; }
      100% { background-position: 0% 50%; }
    }
    .gradient-underline {
      height: 3px;
      width: 100%;
      background: linear-gradient(90deg, #6e40c9, #58a6ff, #a78bfa, #6e40c9);
      background-size: 300% 100%;
      animation: gradientMove 4.5s ease infinite;
      border-radius: 6px;
      margin: 1.6rem 0 2rem;
    }

    @keyframes shimmerText {
      0% { background-position: -200% 0; }
      100% { background-position: 200% 0; }
    }
    .shimmer {
      background: linear-gradient(90deg, #c4b5fd, #a78bfa, #8b5cf6, #6e40c9);
      background-size: 300% 100%;
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
      animation: shimmerText 5s linear infinite;
      font-weight: 700;
    }

    /* --- header wave --- */
    .wave-header {
      position: relative;
      width: 100%;
      height: 148px;
      background: linear-gradient(160deg, #0d1117, #150f2a);
      border-radius: 34px;
      overflow: hidden;
      margin-bottom: 1.2rem;
      border: 1px solid #2a1f44;
      box-shadow: inset 0 0 60px rgba(110,64,201,0.10);
    }
    .wave-header svg {
      position: absolute;
      bottom: 0;
      width: 100%;
      height: 54px;
      fill: #1b1433;
    }
    .wave-header .inner {
      position: relative;
      z-index: 2;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      height: 100%;
      padding: 0 1.2rem;
    }
    .wave-header h1 {
      font-size: 3.6rem;
      font-weight: 800;
      letter-spacing: -0.02em;
      background: linear-gradient(135deg, #f0eaff, #b49aff, #58a6ff);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
      text-shadow: 0 0 40px rgba(88,166,255,0.12);
      margin-bottom: 0.1rem;
      line-height: 1.1;
    }
    .wave-header .tagline {
      font-size: 0.95rem;
      font-weight: 500;
      color: #b0b8d0;
      background: rgba(0,0,0,0.35);
      padding: 0.3rem 1.8rem;
      border-radius: 60px;
      backdrop-filter: blur(6px);
      border: 1px solid rgba(110,64,201,0.25);
      letter-spacing: 0.3px;
    }
    .wave-header .tagline i { color: #a78bfa; margin-right: 6px; }

    /* --- badge row --- */
    .badge-row {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 0.6rem 1rem;
      margin: 0.3rem 0 0.5rem;
    }
    .badge-row a {
      color: #e6edf3;
      text-decoration: none;
      font-size: 0.85rem;
      font-weight: 500;
      background: rgba(255,255,255,0.02);
      padding: 0.35rem 1.2rem;
      border-radius: 40px;
      border: 1px solid #2a2a48;
      transition: all 0.2s ease;
      backdrop-filter: blur(4px);
      display: inline-flex;
      align-items: center;
      gap: 8px;
    }
    .badge-row a:hover {
      background: #1b1b32;
      border-color: #6e40c9;
      transform: scale(1.02);
      box-shadow: 0 4px 16px rgba(110,64,201,0.20);
    }
    .badge-row a i { color: #58a6ff; }
    .badge-row .views {
      background: #121826;
      padding: 0.3rem 1.2rem;
      border-radius: 40px;
      border: 1px solid #2a2a48;
      font-size: 0.8rem;
      color: #8b8fa7;
    }
    .badge-row .views i { color: #58a6ff; margin-right: 4px; }

    /* --- grid --- */
    .grid-2 {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 1.5rem;
      margin: 1.6rem 0;
    }
    @media (max-width: 680px) { .grid-2 { grid-template-columns: 1fr; } }

    .card {
      background: #111823;
      border-radius: 28px;
      padding: 1.4rem 1.6rem;
      border: 1px solid #20263b;
      box-shadow: 0 10px 24px -12px rgba(0,0,0,0.7);
      transition: all 0.2s ease;
    }
    .card:hover { border-color: #3f3368; box-shadow: 0 12px 32px -12px rgba(110,64,201,0.15); }
    .card h3 {
      font-size: 0.9rem;
      font-weight: 600;
      color: #8b8fa7;
      letter-spacing: 0.03em;
      margin-bottom: 0.7rem;
      display: flex;
      align-items: center;
      gap: 8px;
    }
    .card h3 i { color: #6e40c9; }
    .card img {
      width: 100%;
      border-radius: 16px;
      border: 1px solid #262b3f;
      background: #0b0e16;
    }
    .tech-icons {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 0.4rem 0.2rem;
    }
    .tech-icons img {
      height: 40px;
      width: auto;
      filter: drop-shadow(0 2px 8px rgba(0,0,0,0.5));
      transition: 0.15s ease;
    }
    .tech-icons img:hover {
      transform: scale(1.07);
      filter: drop-shadow(0 0 14px #6e40c966);
    }
    .tag {
      display: inline-block;
      background: #191f30;
      padding: 0.15rem 0.9rem;
      border-radius: 40px;
      color: #c4b5fd;
      font-size: 0.7rem;
      font-weight: 600;
      border: 1px solid #332a54;
      margin: 0.1rem 0.2rem;
      letter-spacing: 0.2px;
    }
    .tag i { margin-right: 4px; }

    .trophy-grid {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 0.4rem;
    }
    .trophy-grid img {
      height: 46px;
      border-radius: 12px;
      background: #101824;
      padding: 4px 6px;
      border: 1px solid #262b3f;
    }

    .snake-box {
      margin: 1.6rem 0 0.4rem;
      border-radius: 32px;
      overflow: hidden;
      background: #0a0e16;
      border: 1px solid #1d2236;
    }
    .snake-box img { width: 100%; display: block; }

    .divider-dots {
      text-align: center;
      color: #2d2d4a;
      font-size: 1rem;
      letter-spacing: 10px;
      margin: 0.2rem 0;
      opacity: 0.6;
    }
    .footer-wave {
      margin-top: 2.2rem;
      position: relative;
    }
    .footer-wave svg {
      width: 100%;
      height: 44px;
      fill: #161c2b;
      opacity: 0.35;
    }
    .footer-links {
      display: flex;
      justify-content: center;
      gap: 1.8rem;
      flex-wrap: wrap;
      margin-top: 0.2rem;
      font-size: 0.85rem;
      color: #6e7681;
    }
    .footer-links a {
      color: #b0b8d0;
      text-decoration: none;
      transition: 0.2s;
      font-weight: 450;
    }
    .footer-links a:hover { color: #58a6ff; }
    .footer-links i { margin-right: 6px; color: #6e40c9; }
    .small-note {
      font-size: 0.7rem;
      color: #3d4257;
      text-align: center;
      margin-top: 0.8rem;
      letter-spacing: 0.3px;
    }
    .small-note i { color: #6e40c9; }
    .gradient-line {
      width: 100%;
      height: 2px;
      background: linear-gradient(90deg, transparent, #6e40c9, #58a6ff, transparent);
      margin: 0.8rem 0 1.4rem;
      opacity: 0.6;
    }
    .inline-typing {
      background: #10141f;
      padding: 0.4rem 1.2rem;
      border-radius: 60px;
      border: 1px solid #282d48;
      text-align: center;
      font-size: 0.85rem;
      font-weight: 500;
      color: #b0b8d0;
    }
    .inline-typing i { color: #58a6ff; margin-right: 6px; }
    .list-skill {
      list-style: none;
      font-size: 0.85rem;
      line-height: 1.9;
      color: #b8c0d6;
    }
    .list-skill li i { color: #6e40c9; width: 20px; }
  </style>
</head>
<body>
<div class="readme">

  <!-- ===== HEADER WAVE ===== -->
  <div class="wave-header pulse-soft">
    <div class="inner">
      <h1>Mayank Charde</h1>
      <span class="tagline"><i class="fas fa-code"></i> Full‑Stack · AI Engineer · B.Tech AI</span>
    </div>
    <svg viewBox="0 0 1200 120" preserveAspectRatio="none">
      <path d="M0,0 C300,80 700,0 1200,60 L1200,120 L0,120 Z" opacity="0.25"/>
      <path d="M0,60 C400,0 800,80 1200,40 L1200,120 L0,120 Z" opacity="0.15"/>
    </svg>
  </div>

  <!-- ===== BADGE ROW ===== -->
  <div class="badge-row">
    <a href="#"><i class="fas fa-globe"></i> Portfolio</a>
    <a href="#"><i class="fab fa-linkedin"></i> LinkedIn</a>
    <a href="#"><i class="fas fa-envelope"></i> Email</a>
    <a href="#"><i class="fab fa-github"></i> GitHub</a>
    <span class="views"><i class="fas fa-eye"></i> 4.2k views</span>
  </div>

  <!-- ===== SNAKE ===== -->
  <div class="snake-box">
    <img src="https://raw.githubusercontent.com/mayankcharde/mayankcharde/output/github-contribution-grid-snake-dark.svg" alt="contribution snake" />
  </div>

  <!-- ===== GRADIENT LINE ===== -->
  <div class="gradient-underline"></div>

  <!-- ===== ABOUT + TECH ===== -->
  <div class="grid-2">
    <div class="card" style="display: flex; flex-direction: column; justify-content: center;">
      <h3><i class="fas fa-user-astronaut"></i> About</h3>
      <p style="font-size:0.92rem; color:#c9d1d9; line-height:1.6;">
        <span class="tag"><i class="fas fa-rocket"></i> MERN</span>
        <span class="tag"><i class="fas fa-brain"></i> GenAI</span>
        <span class="tag"><i class="fas fa-microchip"></i> LLM</span>
      </p>
      <p style="margin:0.5rem 0 0.2rem; font-size:0.92rem; color:#c9d1d9;">
        Full‑stack developer & aspiring AI engineer. Building intelligent web experiences with <strong style="color:#a78bfa;">React, Node, FastAPI</strong> and integrating <strong style="color:#58a6ff;">LLMs</strong>.
      </p>
      <div style="display:flex; gap:1.2rem; flex-wrap:wrap; margin-top:0.7rem; font-size:0.85rem;">
        <span><i class="fas fa-graduation-cap" style="color:#6e40c9;"></i> B.Tech AI</span>
        <span><i class="fas fa-map-pin" style="color:#6e40c9;"></i> India</span>
        <span><i class="fas fa-bolt" style="color:#fbbf24;"></i> 5+ projects</span>
      </div>
      <div class="inline-typing" style="margin-top:0.8rem;">
        <i class="fas fa-terminal"></i> <span class="shimmer">🚀 AI‑powered MERN · DSA · RAG</span>
      </div>
    </div>

    <div class="card">
      <h3><i class="fas fa-layer-group"></i> Tech Stack</h3>
      <div class="tech-icons">
        <img src="https://skillicons.dev/icons?i=js,ts,react,nodejs,express,fastapi,python,java,mongodb,mysql,tensorflow,pytorch,aws,docker,git&theme=dark" alt="stack" />
      </div>
      <div style="margin-top:0.7rem; display:flex; flex-wrap:wrap; gap:0.3rem;">
        <span class="tag"><i class="fab fa-react"></i> React</span>
        <span class="tag"><i class="fab fa-node"></i> Node</span>
        <span class="tag"><i class="fas fa-brain"></i> PyTorch</span>
        <span class="tag"><i class="fas fa-cloud"></i> AWS</span>
        <span class="tag"><i class="fas fa-database"></i> MongoDB</span>
      </div>
    </div>
  </div>

  <!-- ===== STATS + STREAK ===== -->
  <div class="grid-2">
    <div class="card">
      <h3><i class="fas fa-chart-line"></i> GitHub Stats</h3>
      <img src="https://github-readme-stats.vercel.app/api?username=mayankcharde&show_icons=true&theme=tokyonight&hide_border=true&bg_color=0d1117&title_color=6e40c9&icon_color=58a6ff&text_color=a8b2d8&rank_icon=github&include_all_commits=true&count_private=true" alt="stats" />
    </div>
    <div class="card">
      <h3><i class="fas fa-fire"></i> Streak</h3>
      <img src="https://nirzak-streak-stats.vercel.app/?user=mayankcharde&theme=tokyonight&hide_border=true&background=0d1117&stroke=6e40c9&ring=6e40c9&fire=ff9500&currStreakLabel=58a6ff&sideLabels=a8b2d8&currStreakNum=ffffff&sideNums=ffffff&dates=6e7681" alt="streak" />
    </div>
  </div>

  <!-- ===== LANGUAGES + CALENDAR ===== -->
  <div class="grid-2">
    <div class="card">
      <h3><i class="fas fa-code"></i> Top Languages</h3>
      <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=mayankcharde&layout=donut&theme=tokyonight&hide_border=true&bg_color=0d1117&title_color=6e40c9&text_color=a8b2d8&include_all_commits=true&count_private=true" alt="donut" />
    </div>
    <div class="card">
      <h3><i class="fas fa-calendar-alt"></i> Isometric Calendar</h3>
      <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=mayankcharde&layout=compact&theme=tokyonight&hide_border=true&bg_color=0d1117&title_color=6e40c9&text_color=a8b2d8&include_all_commits=true" alt="compact" />
    </div>
  </div>

  <!-- ===== ACTIVITY GRAPH ===== -->
  <div class="card" style="margin-top:0.3rem;">
    <h3><i class="fas fa-chart-bar"></i> Contribution Activity</h3>
    <img src="https://github-readme-activity-graph.vercel.app/graph?username=mayankcharde&bg_color=0d1117&color=6e40c9&line=58a6ff&point=a8b2d8&area=true&area_color=6e40c922&hide_border=true&custom_title=Mayank's%20Contribution%20Graph&radius=8" alt="graph" />
  </div>

  <!-- ===== TROPHIES ===== -->
  <div class="card" style="margin-top:1.2rem;">
    <h3><i class="fas fa-trophy"></i> GitHub Trophies</h3>
    <div class="trophy-grid">
      <img src="https://github-profile-trophy.vercel.app/?username=mayankcharde&theme=tokyonight&no-frame=true&no-bg=true&margin-w=6&column=7&title=Stars,Followers,Commits,Repositories,MultipleLang,PullRequest,Issues" alt="trophies" />
    </div>
  </div>

  <!-- ===== DIVIDER ===== -->
  <div class="divider-dots">✦ ✦ ✦</div>

  <!-- ===== EXPERTISE (2‑col) ===== -->
  <div class="grid-2" style="margin-top:0.2rem;">
    <div class="card" style="background:#101724;">
      <h3><i class="fas fa-laptop-code"></i> Full‑Stack</h3>
      <ul class="list-skill">
        <li><i class="fas fa-check-circle"></i> MERN · REST APIs · JWT</li>
        <li><i class="fas fa-check-circle"></i> Socket.io · Real‑time</li>
        <li><i class="fas fa-check-circle"></i> Docker · Vercel · AWS</li>
      </ul>
    </div>
    <div class="card" style="background:#101724;">
      <h3><i class="fas fa-robot"></i> AI / ML</h3>
      <ul class="list-skill">
        <li><i class="fas fa-check-circle"></i> TensorFlow · PyTorch · Keras</li>
        <li><i class="fas fa-check-circle"></i> LLMs · RAG · Prompt Eng.</li>
        <li><i class="fas fa-check-circle"></i> FastAPI · Model Serving</li>
      </ul>
    </div>
  </div>

  <!-- ===== FOOTER ===== -->
  <div class="footer-wave">
    <svg viewBox="0 0 1200 120" preserveAspectRatio="none">
      <path d="M0,40 C300,110 700,10 1200,70 L1200,120 L0,120 Z" opacity="0.2"/>
    </svg>
    <div class="footer-links">
      <span><i class="fas fa-crown"></i> Mayank Charde</span>
      <a href="#"><i class="fab fa-github"></i> mayankcharde</a>
      <a href="#"><i class="fas fa-envelope"></i> mayankcharde2@gmail.com</a>
      <span><i class="fas fa-map-marker-alt" style="color:#58a6ff;"></i> India</span>
    </div>
    <div style="text-align:center; margin-top:0.8rem;">
      <img src="https://readme-typing-svg.demolab.com?font=Inter&size=15&duration=3500&pause=1200&color=6e40c9&center=true&vCenter=true&width=600&lines=⚡+Turning+complex+problems+into+intelligent+solutions;Thanks+for+visiting!+Drop+a+⭐+if+you+like+my+work+🙌" alt="typing footer" style="max-width:100%;" />
    </div>
    <div class="small-note">
      <i class="fas fa-code"></i> built with <i class="fas fa-heart" style="color:#6e40c9;"></i> · inspired by lowlighter/metrics
    </div>
  </div>
</div>
</body>
</html>
