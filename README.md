<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Mayank Charde · AI Full-Stack</title>
  <!-- Font & Icons -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,400;14..32,500;14..32,600;14..32,700;14..32,800&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }
    body {
      background: #0b0b1a;
      display: flex;
      justify-content: center;
      padding: 2rem 1rem;
      font-family: 'Inter', sans-serif;
    }
    .readme-card {
      max-width: 1000px;
      width: 100%;
      background: #0d1117;
      border-radius: 40px;
      padding: 2rem 2rem 1.5rem;
      box-shadow: 0 25px 50px -12px rgba(0,0,0,0.8), 0 0 0 1px rgba(88, 166, 255, 0.08);
      border: 1px solid rgba(88, 166, 255, 0.06);
      transition: all 0.3s ease;
      color: #e6edf3;
    }
    /* ---- animated elements ---- */
    @keyframes floatGlow {
      0% { opacity: 0.7; transform: scale(0.98); filter: blur(0px); }
      50% { opacity: 1; transform: scale(1.02); filter: blur(0px); }
      100% { opacity: 0.7; transform: scale(0.98); filter: blur(0px); }
    }
    .glow-pulse {
      animation: floatGlow 5s ease-in-out infinite;
    }
    @keyframes subtleSlide {
      0% { background-position: 0% 50%; }
      50% { background-position: 100% 50%; }
      100% { background-position: 0% 50%; }
    }
    .gradient-bar {
      height: 4px;
      width: 100%;
      background: linear-gradient(90deg, #6e40c9, #58a6ff, #6e40c9, #a78bfa);
      background-size: 300% 100%;
      animation: subtleSlide 4s ease infinite;
      border-radius: 4px;
      margin: 1.5rem 0 2rem;
    }
    @keyframes shimmer {
      0% { background-position: -200% 0; }
      100% { background-position: 200% 0; }
    }
    .shimmer-text {
      background: linear-gradient(90deg, #c4b5fd, #a78bfa, #8b5cf6, #6e40c9);
      background-size: 300% 100%;
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
      animation: shimmer 6s linear infinite;
      font-weight: 800;
    }
    /* header wave */
    .wave-banner {
      position: relative;
      width: 100%;
      height: 140px;
      background: linear-gradient(145deg, #0d1117, #160b2b);
      border-radius: 30px;
      overflow: hidden;
      margin-bottom: 1.5rem;
      border: 1px solid #2d1b4e;
      box-shadow: inset 0 0 40px rgba(110, 64, 201, 0.15);
    }
    .wave-banner svg {
      position: absolute;
      bottom: 0;
      width: 100%;
      height: 60px;
      fill: #1f1238;
    }
    .wave-banner .content {
      position: relative;
      z-index: 2;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      height: 100%;
      padding: 0 1rem;
    }
    .wave-banner h1 {
      font-size: 3.8rem;
      font-weight: 800;
      letter-spacing: -0.03em;
      background: linear-gradient(135deg, #f0eaff, #a78bfa, #58a6ff);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
      text-shadow: 0 0 30px rgba(88, 166, 255, 0.2);
      margin-bottom: 0.2rem;
    }
    .wave-banner .sub {
      font-size: 1.05rem;
      font-weight: 500;
      color: #a8b2d8;
      background: rgba(0,0,0,0.3);
      padding: 0.3rem 1.5rem;
      border-radius: 60px;
      backdrop-filter: blur(6px);
      border: 1px solid rgba(110, 64, 201, 0.3);
    }
    .badge-row {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 0.6rem 1.2rem;
      margin: 0.5rem 0 0.2rem;
    }
    .badge-row a {
      color: #e6edf3;
      text-decoration: none;
      font-size: 0.95rem;
      font-weight: 500;
      background: rgba(255,255,255,0.03);
      padding: 0.4rem 1rem;
      border-radius: 40px;
      border: 1px solid #2d2d4a;
      transition: all 0.2s ease;
      backdrop-filter: blur(4px);
      display: inline-flex;
      align-items: center;
      gap: 8px;
    }
    .badge-row a:hover {
      background: #1f1f3a;
      border-color: #6e40c9;
      transform: scale(1.02);
      box-shadow: 0 4px 15px rgba(110, 64, 201, 0.25);
    }
    .badge-row a i {
      color: #58a6ff;
    }
    .badge-row .count-badge {
      background: #1a1a2e;
      padding: 0.3rem 1.2rem;
      border-radius: 40px;
      border: 1px solid #2d2d4a;
      font-size: 0.9rem;
    }
    /* grid layout */
    .grid-2col {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 1.5rem;
      margin: 1.8rem 0;
    }
    @media (max-width: 700px) {
      .grid-2col { grid-template-columns: 1fr; }
      .wave-banner h1 { font-size: 2.6rem; }
    }
    .stat-box {
      background: #131825;
      border-radius: 28px;
      padding: 1.4rem 1.5rem;
      border: 1px solid #23273b;
      box-shadow: 0 8px 20px -8px rgba(0,0,0,0.6);
      transition: all 0.2s ease;
    }
    .stat-box:hover {
      border-color: #4b3b7a;
      box-shadow: 0 12px 30px -8px rgba(110, 64, 201, 0.2);
    }
    .stat-box h3 {
      font-size: 1rem;
      font-weight: 600;
      color: #8b8fa7;
      letter-spacing: 0.02em;
      margin-bottom: 0.8rem;
      display: flex;
      align-items: center;
      gap: 8px;
    }
    .stat-box h3 i {
      color: #6e40c9;
    }
    .stat-box img {
      width: 100%;
      border-radius: 16px;
      border: 1px solid #262b3f;
      background: #0b0e16;
    }
    .tech-grid {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 0.6rem 0.3rem;
      margin: 0.2rem 0;
    }
    .tech-grid img {
      height: 42px;
      width: auto;
      filter: drop-shadow(0 2px 6px rgba(0,0,0,0.5));
      transition: 0.15s ease;
    }
    .tech-grid img:hover {
      transform: scale(1.08);
      filter: drop-shadow(0 0 12px #6e40c966);
    }
    .trophy-row {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 0.6rem;
      margin: 0.5rem 0 0;
    }
    .trophy-row img {
      height: 48px;
      border-radius: 12px;
      background: #141b26;
      padding: 4px 6px;
      border: 1px solid #262b3f;
    }
    .footer-wave {
      margin-top: 2.5rem;
      position: relative;
    }
    .footer-wave svg {
      width: 100%;
      height: 50px;
      fill: #1a1a30;
      opacity: 0.5;
    }
    .footer-text {
      display: flex;
      justify-content: center;
      gap: 1.5rem;
      flex-wrap: wrap;
      margin-top: 0.2rem;
      font-size: 0.9rem;
      color: #6e7681;
    }
    .footer-text a {
      color: #a8b2d8;
      text-decoration: none;
      transition: 0.2s;
    }
    .footer-text a:hover { color: #58a6ff; }
    .snake-container {
      margin: 1.8rem 0 0.5rem;
      border-radius: 30px;
      overflow: hidden;
      background: #0b0e16;
      border: 1px solid #1f2338;
    }
    .snake-container img {
      width: 100%;
      display: block;
    }
    .divider-icon {
      text-align: center;
      color: #2d2d4a;
      font-size: 1.2rem;
      letter-spacing: 8px;
      margin: 0.2rem 0;
    }
    .small-note {
      font-size: 0.75rem;
      color: #4a4f66;
      text-align: center;
      margin-top: 0.8rem;
    }
    .gradient-line {
      width: 100%;
      height: 2px;
      background: linear-gradient(90deg, transparent, #6e40c9, #58a6ff, transparent);
      margin: 1rem 0;
    }
    .highlight-tag {
      display: inline-block;
      background: #1f1f3a;
      padding: 0.2rem 0.9rem;
      border-radius: 40px;
      color: #c4b5fd;
      font-size: 0.75rem;
      font-weight: 600;
      border: 1px solid #3a2d5e;
      margin: 0.1rem 0.2rem;
    }
  </style>
</head>
<body>
<div class="readme-card">

  <!-- ====== WAVE BANNER ====== -->
  <div class="wave-banner glow-pulse">
    <div class="content">
      <h1>Mayank Charde</h1>
      <span class="sub"><i class="fas fa-code" style="margin-right: 8px; color: #a78bfa;"></i> Full-Stack · AI · B.Tech AI</span>
    </div>
    <svg viewBox="0 0 1200 120" preserveAspectRatio="none">
      <path d="M0,0 C300,80 700,0 1200,60 L1200,120 L0,120 Z" opacity="0.3"/>
      <path d="M0,60 C400,0 800,80 1200,40 L1200,120 L0,120 Z" opacity="0.2"/>
    </svg>
  </div>

  <!-- ====== BADGE ROW ====== -->
  <div class="badge-row">
    <a href="#"><i class="fas fa-globe"></i> Portfolio</a>
    <a href="#"><i class="fab fa-linkedin"></i> LinkedIn</a>
    <a href="#"><i class="fas fa-envelope"></i> Email</a>
    <a href="#"><i class="fab fa-github"></i> GitHub</a>
    <span class="count-badge"><i class="fas fa-eye" style="color:#58a6ff;"></i> 4.2k views</span>
  </div>

  <!-- ====== SNAKE ANIMATION ====== -->
  <div class="snake-container">
    <img src="https://raw.githubusercontent.com/mayankcharde/mayankcharde/output/github-contribution-grid-snake-dark.svg" alt="snake animation" />
  </div>

  <!-- ====== GRADIENT BAR ====== -->
  <div class="gradient-bar"></div>

  <!-- ====== 2‑COLUMN STATS ====== -->
  <div class="grid-2col">
    <!-- left: about + typing -->
    <div class="stat-box" style="display: flex; flex-direction: column; justify-content: center;">
      <h3><i class="fas fa-user-astronaut"></i> About Me</h3>
      <div style="font-size: 0.95rem; line-height: 1.6; color: #c9d1d9;">
        <p><span class="highlight-tag">🚀 MERN</span> <span class="highlight-tag">🧠 GenAI</span> <span class="highlight-tag">⚡ LLM</span></p>
        <p style="margin: 0.6rem 0 0.2rem;">Full‑stack developer & aspiring AI engineer. Building intelligent web experiences with <strong style="color:#a78bfa;">React, Node, FastAPI</strong> and integrating <strong style="color:#58a6ff;">LLMs</strong>.</p>
        <div style="display: flex; gap: 0.8rem; flex-wrap: wrap; margin-top: 0.8rem;">
          <span><i class="fas fa-graduation-cap" style="color:#6e40c9;"></i> B.Tech AI</span>
          <span><i class="fas fa-map-pin" style="color:#6e40c9;"></i> India</span>
          <span><i class="fas fa-bolt" style="color:#fbbf24;"></i> 3+ projects</span>
        </div>
      </div>
      <!-- typing SVG inline (embedded) -->
      <div style="margin-top: 0.8rem; background: #10141f; padding: 0.4rem 1rem; border-radius: 60px; border:1px solid #2d2d4a; text-align:center;">
        <span style="font-size: 0.9rem; font-weight: 500; color: #a8b2d8;">
          <i class="fas fa-terminal" style="color:#58a6ff;"></i> 
          <span class="shimmer-text">🚀 AI‑powered MERN · DSA · Generative AI</span>
        </span>
      </div>
    </div>

    <!-- right: tech stack icons -->
    <div class="stat-box">
      <h3><i class="fas fa-layer-group"></i> Tech Stack</h3>
      <div class="tech-grid">
        <img src="https://skillicons.dev/icons?i=js,ts,react,nodejs,express,fastapi,python,java,mongodb,mysql,tensorflow,pytorch,aws,docker,git&theme=dark" alt="tech stack" />
      </div>
      <div style="margin-top: 0.7rem; display: flex; flex-wrap: wrap; gap: 0.3rem;">
        <span class="highlight-tag"><i class="fab fa-react"></i> React</span>
        <span class="highlight-tag"><i class="fab fa-node"></i> Node</span>
        <span class="highlight-tag"><i class="fas fa-brain"></i> PyTorch</span>
        <span class="highlight-tag"><i class="fas fa-cloud"></i> AWS</span>
        <span class="highlight-tag"><i class="fas fa-database"></i> MongoDB</span>
      </div>
    </div>
  </div>

  <!-- ====== METRICS: stats + streak + top langs ====== -->
  <div class="grid-2col">
    <div class="stat-box">
      <h3><i class="fas fa-chart-line"></i> GitHub Stats</h3>
      <img src="https://github-readme-stats.vercel.app/api?username=mayankcharde&show_icons=true&theme=tokyonight&hide_border=true&bg_color=0d1117&title_color=6e40c9&icon_color=58a6ff&text_color=a8b2d8&rank_icon=github&include_all_commits=true&count_private=true" alt="stats" />
    </div>
    <div class="stat-box">
      <h3><i class="fas fa-fire"></i> Streak</h3>
      <img src="https://nirzak-streak-stats.vercel.app/?user=mayankcharde&theme=tokyonight&hide_border=true&background=0d1117&stroke=6e40c9&ring=6e40c9&fire=ff9500&currStreakLabel=58a6ff&sideLabels=a8b2d8&currStreakNum=ffffff&sideNums=ffffff&dates=6e7681" alt="streak" />
    </div>
  </div>

  <!-- languages + activity (two more) -->
  <div class="grid-2col">
    <div class="stat-box">
      <h3><i class="fas fa-code"></i> Top Languages</h3>
      <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=mayankcharde&layout=donut&theme=tokyonight&hide_border=true&bg_color=0d1117&title_color=6e40c9&text_color=a8b2d8&include_all_commits=true&count_private=true" alt="top langs donut" />
    </div>
    <div class="stat-box">
      <h3><i class="fas fa-calendar-alt"></i> Isometric Calendar</h3>
      <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=mayankcharde&layout=compact&theme=tokyonight&hide_border=true&bg_color=0d1117&title_color=6e40c9&text_color=a8b2d8&include_all_commits=true" alt="compact langs" />
    </div>
  </div>

  <!-- ====== ACTIVITY GRAPH ====== -->
  <div class="stat-box" style="margin-top: 0.5rem;">
    <h3><i class="fas fa-chart-bar"></i> Contribution Activity</h3>
    <img src="https://github-readme-activity-graph.vercel.app/graph?username=mayankcharde&bg_color=0d1117&color=6e40c9&line=58a6ff&point=a8b2d8&area=true&area_color=6e40c922&hide_border=true&custom_title=Mayank's%20Contribution%20Graph&radius=8" alt="activity graph" />
  </div>

  <!-- ====== TROPHIES ====== -->
  <div class="stat-box" style="margin-top: 1.2rem;">
    <h3><i class="fas fa-trophy"></i> GitHub Trophies</h3>
    <div class="trophy-row">
      <img src="https://github-profile-trophy.vercel.app/?username=mayankcharde&theme=tokyonight&no-frame=true&no-bg=true&margin-w=6&column=7&title=Stars,Followers,Commits,Repositories,MultipleLang,PullRequest,Issues" alt="trophies" />
    </div>
  </div>

  <!-- ====== DIVIDER ====== -->
  <div class="divider-icon">✦ ✦ ✦</div>

  <!-- ====== SKILLS / EXPERTISE (mini) ====== -->
  <div class="grid-2col" style="margin-top: 0.2rem;">
    <div class="stat-box" style="background: #111624;">
      <h3><i class="fas fa-laptop-code"></i> Full‑Stack</h3>
      <ul style="list-style: none; font-size: 0.9rem; line-height: 1.8; color: #b0b8ce;">
        <li><i class="fas fa-check-circle" style="color:#6e40c9;"></i> MERN · REST APIs · JWT</li>
        <li><i class="fas fa-check-circle" style="color:#6e40c9;"></i> Socket.io · Real‑time</li>
        <li><i class="fas fa-check-circle" style="color:#6e40c9;"></i> Docker · Vercel · AWS</li>
      </ul>
    </div>
    <div class="stat-box" style="background: #111624;">
      <h3><i class="fas fa-robot"></i> AI / ML</h3>
      <ul style="list-style: none; font-size: 0.9rem; line-height: 1.8; color: #b0b8ce;">
        <li><i class="fas fa-check-circle" style="color:#6e40c9;"></i> TensorFlow · PyTorch · Keras</li>
        <li><i class="fas fa-check-circle" style="color:#6e40c9;"></i> LLMs · RAG · Prompt Eng.</li>
        <li><i class="fas fa-check-circle" style="color:#6e40c9;"></i> FastAPI · Model Serving</li>
      </ul>
    </div>
  </div>

  <!-- ====== FOOTER ====== -->
  <div class="footer-wave">
    <svg viewBox="0 0 1200 120" preserveAspectRatio="none">
      <path d="M0,40 C300,110 700,10 1200,70 L1200,120 L0,120 Z" opacity="0.2"/>
    </svg>
    <div class="footer-text">
      <span><i class="fas fa-crown" style="color:#6e40c9;"></i> Mayank Charde</span>
      <a href="#"><i class="fab fa-github"></i> mayankcharde</a>
      <a href="#"><i class="fas fa-envelope"></i> mayankcharde2@gmail.com</a>
      <span><i class="fas fa-map-marker-alt" style="color:#58a6ff;"></i> India</span>
    </div>
    <div style="text-align: center; margin-top: 1rem;">
      <img src="https://readme-typing-svg.demolab.com?font=Inter&size=15&duration=3500&pause=1200&color=6e40c9&center=true&vCenter=true&width=600&lines=⚡+Turning+complex+problems+into+intelligent+solutions;Thanks+for+visiting!+Drop+a+⭐+if+you+like+my+work+🙌" alt="footer typing" style="max-width:100%;" />
    </div>
    <div class="small-note">
      <i class="fas fa-code"></i> built with <i class="fas fa-heart" style="color:#6e40c9;"></i> · inspired by lowlighter/metrics
    </div>
  </div>
</div>
</body>
</html>
