<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Benjamin · GitHub</title>
  <style>
    :root {
      --bg: #0b0b0c;
      --panel: #111113;
      --border: #2a2a2e;
      --text: #e4e4e7;
      --muted: #8a8a93;
      --accent: #f5f5f5;
    }

    * { box-sizing: border-box; margin: 0; padding: 0; }

    body {
      background: var(--bg);
      color: var(--text);
      font-family: "Segoe UI", system-ui, sans-serif;
      font-size: 14px;
      line-height: 1.5;
      padding: 24px;
    }

    .layout {
      display: grid;
      grid-template-columns: 260px 1fr;
      gap: 24px;
      max-width: 1100px;
      margin: 0 auto;
    }

    /* ---------- Sidebar ---------- */
    .sidebar { display: flex; flex-direction: column; gap: 12px; }

    .avatar {
      width: 260px;
      height: 260px;
      border-radius: 50%;
      border: 1px solid var(--border);
      background: radial-gradient(circle at 50% 40%, #3a3a40, #111113 70%);
      display: grid;
      place-items: center;
      color: var(--muted);
      font-size: 13px;
    }

    .name { font-size: 24px; font-weight: 600; margin-top: 8px; }
    .username { color: var(--muted); font-size: 18px; }
    .bio { margin: 8px 0; }
    .meta { color: var(--muted); font-size: 13px; }
    .meta div { margin: 4px 0; }

    .btn-edit {
      display: block;
      text-align: center;
      border: 1px solid var(--border);
      border-radius: 6px;
      padding: 5px;
      color: var(--text);
      text-decoration: none;
      background: var(--panel);
    }

    .sidebar hr { border: none; border-top: 1px solid var(--border); margin: 8px 0; }

    /* ---------- Main ---------- */
    .main {
      border: 1px solid var(--border);
      border-radius: 10px;
      padding: 20px;
      background: var(--panel);
    }

    .banner {
      height: 160px;
      border: 1px solid var(--border);
      border-radius: 6px;
      background:
        linear-gradient(180deg, transparent 40%, #0b0b0c),
        repeating-linear-gradient(0deg, #1a1a1d 0 2px, transparent 2px 12px);
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      font-family: "Fira Code", "Consolas", monospace;
      color: #d4d4d8;
    }
    .banner h1 { font-size: 22px; font-weight: 400; }
    .banner span { font-size: 22px; color: var(--muted); }

    .socials {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 8px;
      margin: 16px 0;
    }

    .badge {
      font-size: 11px;
      font-weight: 600;
      letter-spacing: 0.04em;
      text-transform: uppercase;
      border: 1px solid var(--border);
      border-radius: 4px;
      padding: 4px 10px;
      background: #17171a;
      white-space: nowrap;
    }

    .section-title {
      text-align: center;
      font-size: 17px;
      font-weight: 600;
      border-bottom: 1px solid var(--border);
      padding-bottom: 8px;
      margin: 24px 0 16px;
    }

    .about {
      display: grid;
      grid-template-columns: 1fr 180px;
      gap: 16px;
      align-items: center;
    }
    .about p { font-size: 13px; color: #c4c4cc; }
    .about .roles {
      text-align: center;
      font-size: 12px;
      margin-top: 12px;
      line-height: 1.8;
      font-style: italic;
    }
    .about .photo {
      height: 150px;
      border: 1px solid var(--border);
      border-radius: 6px;
      background: #000;
      display: grid;
      place-items: center;
      color: var(--muted);
      font-size: 12px;
    }

    .tech {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 8px;
    }

    /* ---------- Statistics ---------- */
    .stats-row {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 12px;
    }

    .card {
      border: 1px solid var(--border);
      border-radius: 6px;
      padding: 14px;
      background: #0d0d0f;
    }

    .card h3 { font-size: 13px; font-weight: 600; margin-bottom: 10px; }

    .stat-line {
      display: flex;
      justify-content: space-between;
      font-size: 12px;
      padding: 4px 0;
      color: #c4c4cc;
    }
    .stat-line strong { color: var(--text); }

    .streak {
      display: grid;
      grid-template-columns: 1fr 1fr 1fr;
      text-align: center;
      align-items: center;
    }
    .streak .big { font-size: 26px; font-weight: 600; }
    .streak .label { font-size: 11px; color: var(--muted); }
    .streak .ring {
      width: 56px;
      height: 56px;
      border-radius: 50%;
      border: 3px solid #d4d4d8;
      border-right-color: var(--border);
      display: grid;
      place-items: center;
      margin: 0 auto;
      font-weight: 600;
    }

    .graph {
      margin-top: 16px;
      border: 1px solid var(--border);
      border-radius: 6px;
      background: #0d0d0f;
      padding: 12px;
    }
    .graph h3 { text-align: center; font-size: 13px; margin-bottom: 8px; }
    .graph svg { width: 100%; height: auto; display: block; }

    /* ---------- Responsive ---------- */
    @media (max-width: 800px) {
      .layout { grid-template-columns: 1fr; }
      .avatar { width: 160px; height: 160px; margin: 0 auto; }
      .sidebar { align-items: center; text-align: center; }
      .about { grid-template-columns: 1fr; }
      .stats-row { grid-template-columns: 1fr; }
    }
  </style>
</head>
<body>
  <div class="layout">

    <!-- ===== Columna izquierda: perfil ===== -->
    <aside class="sidebar">
      <div class="avatar">Tu foto</div>
      <div class="name">Benjamin</div>
      <div class="username">Benjamin-Solano</div>
      <p class="bio">Systems Engineering Student | Competitor in ICPC (2025)</p>
      <a class="btn-edit" href="#">Edit profile</a>
      <div class="meta">
        <div>👥 6 followers · 15 following</div>
        <div>📍 San Jose / Costa Rica</div>
        <div>🔗 none</div>
      </div>
      <hr>
      <strong>Achievements</strong>
      <div class="badge" style="width:fit-content">🏅 ICPC</div>
    </aside>

    <!-- ===== Columna derecha: README ===== -->
    <main class="main">

      <div class="banner">
        <h1>Welcome to Benjamin's Github</h1>
        <span>&lt;/&gt;</span>
      </div>

      <nav class="socials">
        <span class="badge">LinkedIn</span>
        <span class="badge">Codeforces</span>
        <span class="badge">Codechef</span>
        <span class="badge">Pinterest</span>
        <span class="badge">Chess.com</span>
      </nav>

      <!-- Sobre mí -->
      <h2 class="section-title">👤 About me</h2>
      <div class="about">
        <div>
          <p>
            Hello There! I'm <strong>Benjamin Solano</strong>, a Systems Engineer student.
            I enjoy learning new technologies and problem solving at Codeforces and Vjudge.
            Now I'm working at some little side projects to put into practice my knowledge
            about JavaScript, React, Bootstrap and more.
          </p>
          <div class="roles">
            🏛 Studying at the National University of Costa Rica (UNA)<br>
            💼 Private tutor in C++ at the University<br>
            🏆 Competitor in the ICPC (2025)<br>
            ♟ Chess Player
          </div>
        </div>
        <div class="photo">Tu imagen</div>
      </div>

      <!-- Tecnologías -->
      <h2 class="section-title">🛠 Technologies</h2>
      <div class="tech">
        <span class="badge">C++</span>
        <span class="badge">Java</span>
        <span class="badge">Python</span>
        <span class="badge">C</span>
        <span class="badge">JavaScript</span>
        <span class="badge">HTML5</span>
        <span class="badge">CSS</span>
        <span class="badge">React</span>
        <span class="badge">Bootstrap</span>
        <span class="badge">Vue</span>
        <span class="badge">Angular</span>
        <span class="badge">Node.js</span>
        <span class="badge">Git</span>
        <span class="badge">PostgreSQL</span>
        <span class="badge">MySQL</span>
      </div>

      <!-- Estadísticas -->
      <h2 class="section-title">📊 Statistics</h2>
      <div class="stats-row">
        <div class="card">
          <h3>Benjamin's GitHub Stats</h3>
          <div class="stat-line"><span>⭐ Total Stars Earned</span><strong>1</strong></div>
          <div class="stat-line"><span>🔀 Total Commits (2025)</span><strong>87</strong></div>
          <div class="stat-line"><span>📁 Total PRs</span><strong>0</strong></div>
          <div class="stat-line"><span>⚠️ Total Issues</span><strong>0</strong></div>
          <div class="stat-line"><span>👥 Contributed to (last year)</span><strong>0</strong></div>
        </div>

        <div class="card streak">
          <div>
            <div class="big">119</div>
            <div class="label">Total Contributions</div>
            <div class="label">Sep 21, 2023 – Present</div>
          </div>
          <div>
            <div class="ring">7</div>
            <div class="label">Current Streak</div>
          </div>
          <div>
            <div class="big">7</div>
            <div class="label">Longest Streak</div>
            <div class="label">Nov 8, 2023 – Nov 14, 2023</div>
          </div>
        </div>
      </div>

      <!-- Gráfico de contribuciones (datos de ejemplo) -->
      <div class="graph">
        <h3>Benjamin's Contribution Graph</h3>
        <svg viewBox="0 0 600 200" xmlns="http://www.w3.org/2000/svg">
          <!-- Ejes y líneas guía -->
          <g stroke="#2a2a2e" stroke-width="1">
            <line x1="40" y1="20" x2="590" y2="20"/>
            <line x1="40" y1="60" x2="590" y2="60"/>
            <line x1="40" y1="100" x2="590" y2="100"/>
            <line x1="40" y1="140" x2="590" y2="140"/>
            <line x1="40" y1="180" x2="590" y2="180"/>
          </g>
          <g fill="#8a8a93" font-size="10" text-anchor="end">
            <text x="34" y="24">4</text>
            <text x="34" y="64">3</text>
            <text x="34" y="104">2</text>
            <text x="34" y="144">1</text>
            <text x="34" y="184">0</text>
          </g>
          <!-- Línea de contribuciones (datos de ejemplo) -->
          <polygon fill="rgba(245,245,245,0.06)"
            points="40,180 80,180 120,180 160,100 200,100 240,180 280,20 320,180 360,60 400,20 440,180 480,100 520,140 560,140 590,100 590,180"/>
          <polyline fill="none" stroke="#e4e4e7" stroke-width="2"
            points="40,180 80,180 120,180 160,100 200,100 240,180 280,20 320,180 360,60 400,20 440,180 480,100 520,140 560,140 590,100"/>
        </svg>
      </div>

    </main>
  </div>
</body>
</html>
