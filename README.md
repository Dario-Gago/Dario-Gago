<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Darío — Full Stack Developer</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&family=DM+Sans:wght@300;400;500;600&display=swap" rel="stylesheet" />
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    body {
      font-family: 'DM Sans', sans-serif;
      background: #f8fafc;
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 2rem;
    }

    .card {
      background: #ffffff;
      border: 1px solid #e2e8f0;
      border-radius: 20px;
      padding: 2.5rem;
      max-width: 680px;
      width: 100%;
    }

    /* Top bar */
    .top-bar {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 2.5rem;
    }

    .tag {
      font-family: 'Space Mono', monospace;
      font-size: 11px;
      color: #94a3b8;
      letter-spacing: 0.12em;
      text-transform: uppercase;
    }

    .status-dot {
      display: flex;
      align-items: center;
      gap: 6px;
      font-size: 12px;
      color: #64748b;
    }

    .dot {
      width: 7px;
      height: 7px;
      border-radius: 50%;
      background: #22c55e;
      box-shadow: 0 0 0 3px rgba(34, 197, 94, 0.2);
      animation: pulse 2s infinite;
    }

    @keyframes pulse {
      0%, 100% { box-shadow: 0 0 0 3px rgba(34, 197, 94, 0.2); }
      50%       { box-shadow: 0 0 0 6px rgba(34, 197, 94, 0.08); }
    }

    /* Hero */
    .hero {
      display: grid;
      grid-template-columns: 1fr auto;
      align-items: end;
      gap: 2rem;
      margin-bottom: 3rem;
      padding-bottom: 2rem;
      border-bottom: 1px solid #f1f5f9;
    }

    .name-block h1 {
      font-family: 'Space Mono', monospace;
      font-size: 42px;
      font-weight: 700;
      line-height: 1;
      margin-bottom: 0.5rem;
      color: #0f172a;
      letter-spacing: -0.02em;
    }

    .name-block h1 span { color: #2563eb; }

    .name-block p {
      font-size: 15px;
      color: #64748b;
      font-weight: 300;
    }

    .role-line {
      display: flex;
      align-items: center;
      gap: 10px;
      margin-top: 0.75rem;
    }

    .role-pill {
      font-size: 12px;
      font-weight: 500;
      background: #eff6ff;
      color: #1d4ed8;
      padding: 4px 12px;
      border-radius: 100px;
      border: 1px solid #bfdbfe;
    }

    .avatar {
      width: 72px;
      height: 72px;
      border-radius: 18px;
      background: linear-gradient(135deg, #2563eb 0%, #7c3aed 100%);
      display: flex;
      align-items: center;
      justify-content: center;
      font-family: 'Space Mono', monospace;
      font-size: 22px;
      font-weight: 700;
      color: white;
    }

    /* Section label */
    .section-label {
      font-family: 'Space Mono', monospace;
      font-size: 10px;
      letter-spacing: 0.15em;
      text-transform: uppercase;
      color: #94a3b8;
      margin-bottom: 1rem;
    }

    /* Tech grid */
    .tech-grid {
      display: grid;
      grid-template-columns: 1fr 1fr 1fr;
      gap: 0.75rem;
      margin-bottom: 2rem;
    }

    .tech-group {
      background: #f8fafc;
      border: 1px solid #e2e8f0;
      border-radius: 12px;
      padding: 1rem;
    }

    .tech-group-title {
      font-size: 10px;
      font-family: 'Space Mono', monospace;
      letter-spacing: 0.1em;
      text-transform: uppercase;
      color: #94a3b8;
      margin-bottom: 0.75rem;
    }

    .badge-list {
      display: flex;
      flex-direction: column;
      gap: 6px;
    }

    .badge {
      display: flex;
      align-items: center;
      gap: 8px;
      font-size: 13px;
      font-weight: 500;
      color: #0f172a;
      padding: 5px 8px;
      border-radius: 6px;
      border: 1px solid #e2e8f0;
      background: #ffffff;
      transition: border-color 0.15s;
      cursor: default;
    }

    .badge:hover { border-color: #cbd5e1; }

    .badge-dot {
      width: 8px;
      height: 8px;
      border-radius: 2px;
      flex-shrink: 0;
    }

    /* Stats */
    .stat-row {
      display: grid;
      grid-template-columns: 1fr 1fr 1fr;
      gap: 0.75rem;
      margin-top: 0.5rem;
    }

    .stat-card {
      background: #f8fafc;
      border-radius: 10px;
      padding: 0.875rem 1rem;
      text-align: center;
    }

    .stat-num {
      font-family: 'Space Mono', monospace;
      font-size: 22px;
      font-weight: 700;
      color: #0f172a;
      line-height: 1;
      margin-bottom: 4px;
      display: block;
    }

    .stat-num span { color: #2563eb; }
    .stat-lbl { font-size: 11px; color: #94a3b8; }

    /* CTA buttons */
    .cta-row {
      display: flex;
      gap: 0.75rem;
      margin-top: 1.5rem;
    }

    .btn {
      flex: 1;
      padding: 0.65rem 1rem;
      font-size: 13px;
      font-weight: 500;
      border-radius: 8px;
      border: 1px solid #e2e8f0;
      cursor: pointer;
      transition: all 0.15s;
      text-align: center;
      font-family: 'DM Sans', sans-serif;
      background: #ffffff;
      color: #0f172a;
    }

    .btn:hover { background: #f8fafc; }

    .btn.primary {
      background: #2563eb;
      color: white;
      border-color: #2563eb;
    }

    .btn.primary:hover { background: #1d4ed8; }

    /* Dark mode */
    @media (prefers-color-scheme: dark) {
      body { background: #0f172a; }

      .card {
        background: #1e293b;
        border-color: #334155;
      }

      .name-block h1 { color: #f1f5f9; }
      .tag, .status-dot { color: #64748b; }

      .hero { border-bottom-color: #334155; }

      .role-pill {
        background: #1e3a5f;
        color: #93c5fd;
        border-color: #1e40af;
      }

      .tech-group {
        background: #0f172a;
        border-color: #334155;
      }

      .badge {
        background: #1e293b;
        border-color: #334155;
        color: #f1f5f9;
      }

      .badge:hover { border-color: #475569; }

      .stat-card { background: #0f172a; }
      .stat-num { color: #f1f5f9; }

      .btn {
        background: #1e293b;
        border-color: #334155;
        color: #f1f5f9;
      }

      .btn:hover { background: #334155; }
    }
  </style>
</head>
<body>
  <div class="card">
    <div class="top-bar">
      <span class="tag">dev.profile / v2026</span>
      <div class="status-dot">
        <div class="dot"></div>
        disponible para proyectos
      </div>
    </div>

    <div class="hero">
      <div class="name-block">
        <h1>Dar<span>í</span>o</h1>
        <p>Construye interfaces bonitas y backends robustos</p>
        <div class="role-line">
          <span class="role-pill">Full Stack Developer</span>
        </div>
      </div>
      <div class="avatar">D</div>
    </div>

    <p class="section-label">Stack tecnológico</p>

    <div class="tech-grid">
      <div class="tech-group">
        <div class="tech-group-title">Frontend</div>
        <div class="badge-list">
          <div class="badge"><div class="badge-dot" style="background:#F7DF1E;"></div>JavaScript</div>
          <div class="badge"><div class="badge-dot" style="background:#61DAFB;"></div>React</div>
          <div class="badge"><div class="badge-dot" style="background:#E34F26;"></div>HTML5</div>
          <div class="badge"><div class="badge-dot" style="background:#1572B6;"></div>CSS3</div>
          <div class="badge"><div class="badge-dot" style="background:#38B2AC;"></div>Tailwind</div>
        </div>
      </div>

      <div class="tech-group">
        <div class="tech-group-title">Backend</div>
        <div class="badge-list">
          <div class="badge"><div class="badge-dot" style="background:#339933;"></div>Node.js</div>
          <div class="badge"><div class="badge-dot" style="background:#888888;"></div>Express</div>
        </div>
      </div>

      <div class="tech-group">
        <div class="tech-group-title">Base de datos</div>
        <div class="badge-list">
          <div class="badge"><div class="badge-dot" style="background:#316192;"></div>PostgreSQL</div>
        </div>
      </div>
    </div>

    <p class="section-label" style="margin-top:1.5rem;">En números</p>
    <div class="stat-row">
      <div class="stat-card">
        <span class="stat-num">3<span>+</span></span>
        <span class="stat-lbl">Años de experiencia</span>
      </div>
      <div class="stat-card">
        <span class="stat-num">7</span>
        <span class="stat-lbl">Tecnologías dominadas</span>
      </div>
      <div class="stat-card">
        <span class="stat-num"><span>∞</span></span>
        <span class="stat-lbl">Ganas de aprender</span>
      </div>
    </div>

    <div class="cta-row">
      <button class="btn">Ver proyectos ↗</button>
      <button class="btn primary">Contactar</button>
    </div>
  </div>
</body>
</html>
