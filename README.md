<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Dhairyashil Shinde | Builder</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />

  <!-- =========================
       GLOBAL STYLES
  ========================== -->
  <style>
    :root {
      --bg-dark: #0b1220;
      --bg-card: #111827;
      --green: #22c55e;
      --blue: #0ea5e9;
      --text-main: #e5e7eb;
      --text-muted: #9ca3af;
      --glow: rgba(34,197,94,0.4);
    }

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Segoe UI', system-ui, -apple-system, BlinkMacSystemFont, sans-serif;
      background: var(--bg-dark);
      color: var(--text-main);
      overflow-x: hidden;
    }

    a {
      text-decoration: none;
      color: inherit;
    }

    /* =========================
       HERO SECTION
    ========================== */

    .hero {
      position: relative;
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      background: linear-gradient(
        120deg,
        #0f172a,
        #022c22,
        #020617
      );
      overflow: hidden;
    }

    /* Animated gradient overlay */
    .hero::before {
      content: "";
      position: absolute;
      inset: 0;
      background: linear-gradient(
        270deg,
        var(--green),
        var(--blue),
        #16a34a,
        #0284c7
      );
      background-size: 600% 600%;
      opacity: 0.15;
      animation: gradientMove 14s ease infinite;
      z-index: 0;
    }

    @keyframes gradientMove {
      0% { background-position: 0% 50%; }
      50% { background-position: 100% 50%; }
      100% { background-position: 0% 50%; }
    }

    /* Floating particles */
    .particle {
      position: absolute;
      width: 6px;
      height: 6px;
      background: var(--green);
      border-radius: 50%;
      opacity: 0.2;
      animation: floatUp linear infinite;
    }

    @keyframes floatUp {
      from {
        transform: translateY(100vh) scale(0.8);
        opacity: 0;
      }
      to {
        transform: translateY(-10vh) scale(1.2);
        opacity: 0.6;
      }
    }

    .hero-content {
      position: relative;
      z-index: 2;
      text-align: center;
      max-width: 900px;
      padding: 40px;
    }

    .hero h1 {
      font-size: 3.5rem;
      font-weight: 700;
      letter-spacing: -1px;
      margin-bottom: 20px;
    }

    .hero h1 span {
      background: linear-gradient(90deg, var(--green), var(--blue));
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }

    .hero p {
      font-size: 1.3rem;
      line-height: 1.6;
      color: var(--text-muted);
      max-width: 700px;
      margin: 0 auto;
    }

    .hero-tagline {
      margin-top: 30px;
      display: inline-block;
      padding: 10px 18px;
      border-radius: 999px;
      background: rgba(34,197,94,0.08);
      border: 1px solid rgba(34,197,94,0.25);
      font-size: 0.95rem;
      color: var(--green);
    }

    /* =========================
       SECTION BASE
    ========================== */

    section {
      padding: 90px 8%;
    }

    .section-title {
      text-align: center;
      font-size: 2.2rem;
      margin-bottom: 20px;
    }

    .section-subtitle {
      text-align: center;
      color: var(--text-muted);
      max-width: 700px;
      margin: 0 auto 60px;
      font-size: 1.1rem;
    }

    /* =========================
       TOOLS SECTION
    ========================== */

    .tools-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(140px, 1fr));
      gap: 30px;
      max-width: 900px;
      margin: 0 auto;
    }

    .tool-card {
      background: var(--bg-card);
      border-radius: 16px;
      padding: 25px 15px;
      text-align: center;
      border: 1px solid rgba(255,255,255,0.05);
      transition: all 0.35s ease;
      position: relative;
      overflow: hidden;
    }

    .tool-card::before {
      content: "";
      position: absolute;
      inset: 0;
      background: radial-gradient(circle at top, var(--glow), transparent 70%);
      opacity: 0;
      transition: opacity 0.35s ease;
    }

    .tool-card:hover::before {
      opacity: 1;
    }

    .tool-card:hover {
      transform: translateY(-8px) scale(1.03);
      border-color: rgba(34,197,94,0.4);
    }

    .tool-card img {
      width: 48px;
      margin-bottom: 12px;
    }

    .tool-card span {
      display: block;
      font-size: 0.95rem;
      color: var(--text-muted);
    }

    /* =========================
       CONNECT SECTION
    ========================== */

    .connect {
      text-align: center;
    }

    .connect-links {
      display: flex;
      justify-content: center;
      gap: 40px;
      margin-top: 40px;
    }

    .connect-card {
      background: var(--bg-card);
      padding: 22px 26px;
      border-radius: 18px;
      border: 1px solid rgba(255,255,255,0.06);
      transition: all 0.35s ease;
      display: flex;
      align-items: center;
      gap: 14px;
      min-width: 220px;
      justify-content: center;
    }

    .connect-card:hover {
      transform: translateY(-6px);
      border-color: rgba(14,165,233,0.5);
      box-shadow: 0 10px 40px rgba(14,165,233,0.15);
    }

    .connect-card img {
      width: 32px;
    }

    .connect-card span {
      font-size: 1rem;
      color: var(--text-main);
    }

    /* =========================
       FOOTER
    ========================== */

    footer {
      padding: 50px 20px;
      text-align: center;
      color: var(--text-muted);
      font-size: 0.9rem;
    }

    footer span {
      color: var(--green);
    }

    /* =========================
       RESPONSIVE
    ========================== */

    @media (max-width: 768px) {
      .hero h1 {
        font-size: 2.6rem;
      }

      .hero p {
        font-size: 1.05rem;
      }

      section {
        padding: 70px 6%;
      }
    }
  </style>
</head>

<body>

  <!-- =========================
       HERO
  ========================== -->
  <div class="hero" id="hero">
    <div class="hero-content">
      <h1>
        Dhairyashil <span>Shinde</span>
      </h1>
      <p>
        I build systems, not just software.  
        My focus is on efficiency, sustainability, and real-world impact —
        from agriculture to digital infrastructure.
      </p>

      <div class="hero-tagline">
        Think • Build • Measure • Optimize • Repeat
      </div>
    </div>
  </div>

  <!-- =========================
       TOOLS
  ========================== -->
  <section>
    <h2 class="section-title">Tools & Technologies</h2>
    <p class="section-subtitle">
      Tools are not my identity — they are instruments.
      I use them to build efficient, scalable, and responsible systems.
    </p>

    <div class="tools-grid">
      <div class="tool-card">
        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg">
        <span>Python</span>
      </div>
      <div class="tool-card">
        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mysql/mysql-original.svg">
        <span>DBMS / SQL</span>
      </div>
      <div class="tool-card">
        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/linux/linux-original.svg">
        <span>Linux</span>
      </div>
      <div class="tool-card">
        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/git/git-original.svg">
        <span>Git</span>
      </div>
      <div class="tool-card">
        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/github/github-original.svg">
        <span>GitHub</span>
      </div>
      <div class="tool-card">
        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg">
        <span>HTML</span>
      </div>
      <div class="tool-card">
        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg">
        <span>CSS</span>
      </div>
      <div class="tool-card">
        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg">
        <span>JavaScript</span>
      </div>
    </div>
  </section>

  <!-- =========================
       CONNECT
  ========================== -->
  <section class="connect">
    <h2 class="section-title">Connect</h2>
    <p class="section-subtitle">
      Open to conversations, collaboration, and learning.
    </p>

    <div class="connect-links">
      <a class="connect-card" href="https://www.linkedin.com/in/YOUR-LINKEDIN" target="_blank">
        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/linkedin/linkedin-original.svg">
        <span>LinkedIn</span>
      </a>

      <a class="connect-card" href="mailto:yourgmail@gmail.com">
        <img src="https://cdn-icons-png.flaticon.com/512/732/732200.png">
        <span>Email</span>
      </a>
    </div>
  </section>

  <footer>
    Built with intent, not noise.  
    <br />
    © <span>Dhairyashil Shinde</span>
  </footer>

  <!-- =========================
       PARTICLE SCRIPT
  ========================== -->
  <script>
    const hero = document.getElementById("hero");

    for (let i = 0; i < 45; i++) {
      const p = document.createElement("div");
      p.classList.add("particle");
      p.style.left = Math.random() * 100 + "%";
      p.style.animationDuration = (10 + Math.random() * 20) + "s";
      p.style.animationDelay = Math.random() * 10 + "s";
      p.style.background = Math.random() > 0.5 ? "#22c55e" : "#0ea5e9";
      hero.appendChild(p);
    }
  </script>

</body>
</html>

