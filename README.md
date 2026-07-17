<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>C B Anshy Prabha — Portfolio</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #080810;
    --surface: #0f0f1a;
    --border: #1e1e35;
    --pink: #be609d;
    --pink-glow: rgba(255,45,120,0.15);
    --pink-soft: #ff6aa7;
    --text: #eeeaec;
    --muted: #7a6a80;
    --tag-bg: #16101e;
  }
  * { margin:0; padding:0; box-sizing:border-box; }
  html { scroll-behavior: smooth; }
  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Space Grotesk', sans-serif;
    font-size: 16px;
    line-height: 1.6;
  }
  body::before {
    content: '';
    position: fixed; inset: 0;
    background: repeating-linear-gradient(0deg, transparent, transparent 2px, rgba(255,45,120,0.010) 2px, rgba(255,45,120,0.010) 4px);
    pointer-events: none; z-index: 0;
  }
  nav {
    position: fixed; top:0; left:0; right:0; z-index:100;
    display:flex; justify-content:space-between; align-items:center;
    padding: 1rem 2.5rem;
    background: rgba(8,8,16,0.92);
    backdrop-filter: blur(14px);
    border-bottom: 1px solid var(--border);
  }
  .nav-name {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.82rem; color: var(--pink);
    letter-spacing: 0.08em;
    text-shadow: 0 0 12px var(--pink);
  }
  .nav-links { display:flex; gap:2rem; list-style:none; }
  .nav-links a {
    color: var(--muted); text-decoration:none;
    font-size: 0.78rem; font-weight:500;
    letter-spacing: 0.06em; text-transform:uppercase;
    transition: color 0.2s, text-shadow 0.2s;
  }
  .nav-links a:hover { color: var(--pink); text-shadow: 0 0 10px var(--pink); }
  .hero {
    min-height: 100vh;
    display:flex; flex-direction:column; justify-content:center;
    padding: 8rem 2.5rem 4rem;
    max-width: 950px; margin: 0 auto;
    position: relative; z-index: 1;
  }
  .hero-eyebrow {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.75rem; color: var(--pink);
    letter-spacing: 0.16em; text-transform:uppercase;
    margin-bottom: 1.2rem;
    text-shadow: 0 0 10px var(--pink);
  }
  .hero h1 {
    font-size: clamp(2.8rem, 7vw, 5.5rem);
    font-weight: 700; line-height: 1.02;
    letter-spacing: -0.03em; margin-bottom: 1.5rem;
  }
  .hero h1 .glow {
    color: var(--pink);
    text-shadow: 0 0 30px rgba(255,45,120,0.7), 0 0 60px rgba(255,45,120,0.3);
  }
  .hero-sub {
    font-size: 1.05rem; color: var(--muted);
    max-width: 540px; margin-bottom: 2.5rem; line-height: 1.75;
  }
  .hero-cta { display:flex; gap:1rem; flex-wrap:wrap; }
  .btn {
    display:inline-block; padding:0.7rem 1.6rem;
    border-radius:5px; font-size:0.82rem; font-weight:600;
    text-decoration:none; letter-spacing:0.05em; transition:all 0.2s;
  }
  .btn-primary { background:var(--pink); color:#fff; box-shadow:0 0 18px rgba(255,45,120,0.45); }
  .btn-primary:hover { background:#ff5599; box-shadow:0 0 28px rgba(255,45,120,0.7); }
  .btn-outline { border:1px solid var(--pink); color:var(--pink); }
  .btn-outline:hover { background:var(--pink-glow); }
  .stat-strip {
    display:flex; gap:3rem; flex-wrap:wrap;
    margin-top:4rem; padding-top:2rem;
    border-top:1px solid var(--border);
  }
  .stat-num {
    font-family:'JetBrains Mono',monospace;
    font-size:2.2rem; font-weight:500;
    color:var(--pink);
    text-shadow:0 0 16px rgba(255,45,120,0.6);
  }
  .stat-label { font-size:0.7rem; color:var(--muted); text-transform:uppercase; letter-spacing:0.1em; margin-top:0.2rem; }
  section {
    max-width:950px; margin:0 auto;
    padding:5rem 2.5rem;
    border-top:1px solid var(--border);
    position:relative; z-index:1;
  }
  .section-label {
    font-family:'JetBrains Mono',monospace;
    font-size:0.7rem; color:var(--pink);
    letter-spacing:0.16em; text-transform:uppercase;
    margin-bottom:0.5rem;
    text-shadow:0 0 8px var(--pink);
  }
  .section-title { font-size:2rem; font-weight:700; letter-spacing:-0.02em; margin-bottom:2.5rem; }
  .projects-grid { display:grid; gap:1.5rem; }
  .project-card {
    background:var(--surface); border:1px solid var(--border);
    border-radius:10px; padding:2rem;
    transition:border-color 0.25s, box-shadow 0.25s, transform 0.2s;
    position:relative; overflow:hidden;
  }
  .project-card::before {
    content:''; position:absolute;
    top:0; left:0; right:0; height:2px;
    background:linear-gradient(90deg,var(--pink),#c200fb);
    opacity:0; transition:opacity 0.25s;
  }
  .project-card:hover { border-color:var(--pink); box-shadow:0 0 24px rgba(255,45,120,0.15); transform:translateY(-3px); }
  .project-card:hover::before { opacity:1; }
  .project-header { display:flex; justify-content:space-between; align-items:flex-start; gap:1rem; margin-bottom:1rem; }
  .project-title { font-size:1.12rem; font-weight:600; }
  .project-date { font-family:'JetBrains Mono',monospace; font-size:0.7rem; color:var(--muted); white-space:nowrap; padding-top:0.3rem; }
  .project-desc { color:var(--muted); font-size:0.9rem; line-height:1.75; margin-bottom:1.2rem; }
  .project-stat {
    display:inline-flex; align-items:center; gap:0.5rem;
    background:rgba(255,45,120,0.08); border:1px solid rgba(255,45,120,0.25);
    border-radius:4px; padding:0.4rem 0.85rem;
    font-family:'JetBrains Mono',monospace; font-size:0.78rem;
    color:var(--pink); margin-bottom:1.2rem;
    text-shadow:0 0 8px rgba(255,45,120,0.5);
  }
  .tags { display:flex; flex-wrap:wrap; gap:0.45rem; }
  .tag {
    background:var(--tag-bg); color:var(--muted);
    border-radius:4px; padding:0.22rem 0.6rem;
    font-size:0.72rem; font-family:'JetBrains Mono',monospace;
    border:1px solid var(--border);
  }
  .project-links { display:flex; gap:0.8rem; margin-top:1.2rem; }
  .proj-link { font-size:0.8rem; color:var(--pink-soft); text-decoration:none; font-weight:500; }
  .proj-link:hover { text-decoration:underline; text-shadow:0 0 8px var(--pink); }
  .skills-grid { display:grid; grid-template-columns:repeat(auto-fill,minmax(210px,1fr)); gap:1rem; }
  .skill-group {
    background:var(--surface); border:1px solid var(--border);
    border-radius:8px; padding:1.2rem 1.4rem; transition:border-color 0.2s;
  }
  .skill-group:hover { border-color:rgba(255,45,120,0.3); }
  .skill-group-title { font-size:0.68rem; color:var(--pink); text-transform:uppercase; letter-spacing:0.12em; margin-bottom:0.8rem; font-family:'JetBrains Mono',monospace; }
  .skill-list { display:flex; flex-wrap:wrap; gap:0.4rem; }
  .skill-pill { background:var(--tag-bg); border:1px solid var(--border); border-radius:4px; padding:0.2rem 0.55rem; font-size:0.76rem; color:var(--text); }
  .certs-list { display:grid; gap:0.8rem; }
  .cert-item {
    display:flex; justify-content:space-between; align-items:center; gap:1rem;
    padding:1rem 1.3rem; background:var(--surface);
    border:1px solid var(--border); border-radius:8px; transition:border-color 0.2s;
  }
  .cert-item:hover { border-color:rgba(255,45,120,0.3); }
  .cert-name { font-weight:500; font-size:0.93rem; }
  .cert-issuer { font-size:0.76rem; color:var(--muted); margin-top:0.2rem; }
  .cert-date { font-family:'JetBrains Mono',monospace; font-size:0.7rem; color:var(--muted); white-space:nowrap; }
  .edu-list { display:grid; gap:1rem; }
  .edu-item {
    padding:1.2rem 1.4rem; background:var(--surface);
    border:1px solid var(--border); border-radius:8px;
    display:flex; justify-content:space-between; align-items:center; gap:1rem; transition:border-color 0.2s;
  }
  .edu-item:hover { border-color:rgba(255,45,120,0.3); }
  .edu-name { font-weight:600; font-size:0.93rem; }
  .edu-detail { font-size:0.8rem; color:var(--muted); margin-top:0.3rem; }
  .edu-score { font-family:'JetBrains Mono',monospace; font-size:0.85rem; color:var(--pink); white-space:nowrap; text-shadow:0 0 8px rgba(255,45,120,0.5); }
  .vol-card {
    background:var(--surface); border:1px solid var(--border);
    border-radius:10px; padding:1.8rem 2rem; transition:border-color 0.2s;
  }
  .vol-card:hover { border-color:rgba(255,45,120,0.3); }
  .vol-header { display:flex; justify-content:space-between; align-items:flex-start; gap:1rem; margin-bottom:0.8rem; }
  .vol-title { font-weight:600; font-size:1rem; }
  .vol-role { font-size:0.78rem; color:var(--pink); margin-top:0.2rem; }
  .vol-desc { font-size:0.88rem; color:var(--muted); line-height:1.75; }
  .contact-grid { display:flex; flex-wrap:wrap; gap:1rem; }
  .contact-card {
    display:flex; align-items:center; gap:0.7rem;
    background:var(--surface); border:1px solid var(--border);
    border-radius:8px; padding:0.85rem 1.2rem;
    font-size:0.86rem; color:var(--text); text-decoration:none;
    transition:border-color 0.2s, box-shadow 0.2s;
  }
  .contact-card:hover { border-color:var(--pink); box-shadow:0 0 14px rgba(255,45,120,0.15); }
  .contact-icon { color:var(--pink); }
  footer {
    text-align:center; padding:2rem;
    border-top:1px solid var(--border);
    color:var(--muted); font-size:0.75rem;
    font-family:'JetBrains Mono',monospace;
    position:relative; z-index:1;
  }
  footer span { color:var(--pink); }
  @media (max-width:640px) {
    nav { padding:1rem 1.2rem; }
    .nav-links { gap:1rem; }
    .hero, section { padding-left:1.2rem; padding-right:1.2rem; }
    .stat-strip { gap:2rem; }
    .edu-item, .cert-item { flex-direction:column; align-items:flex-start; }
    .vol-header { flex-direction:column; }
  }
</style>
</head>
<body>
<nav>
  <div class="nav-name">// anshy.prabha</div>
  <ul class="nav-links">
    <li><a href="#projects">Projects</a></li>
    <li><a href="#skills">Skills</a></li>
    <li><a href="#certs">Certs</a></li>
    <li><a href="#edu">Education</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</nav>
<div class="hero">
  <div class="hero-eyebrow">// B.Tech CSE · SRM IST Trichy · Graduating 2027</div>
  <h1><span class="glow">C B Anshy<br>Prabha</span></h1>
  <p class="hero-sub">
    <strong>Aspiring AI &amp; Machine Learning Engineer</strong><br><br>

    I'm a B.Tech Computer Science and Engineering student at
    <strong>SRM Institute of Science and Technology</strong>,
    graduating in <strong>2027</strong>.

    I'm passionate about building intelligent software using
    <strong>Python</strong>,
    <strong>Django</strong>,
    <strong>Machine Learning</strong>,
    <strong>Reinforcement Learning</strong>,
    and <strong>Cybersecurity</strong>, with a focus on solving real-world problems through innovative and scalable solutions.
</p>
  <div class="hero-cta">

    <a href="#projects" class="btn btn-primary">
        View Projects
    </a>

    <a href="resume.pdf" class="btn btn-outline" download>
        Download Resume
    </a>

    <a href="https://github.com/cp4925" target="_blank" class="btn btn-outline">
        GitHub
    </a>

    <a href="https://www.linkedin.com/in/anshy-prabha-7a4b04297/" target="_blank" class="btn btn-outline">
        LinkedIn
    </a>

<div class="stat-strip">

    <div>
        <div class="stat-num">3+</div>
        <div class="stat-label">Projects</div>
    </div>

    <div>
        <div class="stat-num">1</div>
        <div class="stat-label">Internship</div>
    </div>

    <div>
        <div class="stat-num">3</div>
        <div class="stat-label">Certifications</div>
    </div>

    <div>
        <div class="stat-num">8.51</div>
        <div class="stat-label">CGPA</div>
    </div>

    <div>
        <div class="stat-num">2027</div>
        <div class="stat-label">Expected Graduation</div>
    </div>

</div>
</div>
<section id="projects">
  <div class="section-label">// 01 · work</div>
  <h2 class="section-title">Projects</h2>
  <div class="projects-grid">
    <div class="project-card">
      <div class="project-header">
        <div class="project-title">Reinforcement Learning for Signal Optimization</div>
        <div class="project-date">2025 – 2026</div>
      </div>
      <div class="project-stat">⚡ 86.24% efficiency improvement over fixed-time controllers</div>
      <p class="project-desc">Built a Deep Q-Network (DQN) agent that learns to manage traffic light phases at a simulated intersection in SUMO. Trained for 20,000 timesteps using PyTorch and Stable-Baselines3, dramatically outperforming fixed-time controllers.</p>
      <div class="tags">
        <span class="tag">Python</span><span class="tag">PyTorch</span><span class="tag">Reinforcement Learning</span>
        <span class="tag">DQN</span><span class="tag">SUMO Simulator</span><span class="tag">Stable-Baselines3</span>
        <span class="tag">Gymnasium</span><span class="tag">TraCI</span>
      </div>
      <div class="project-links">
        <a href="https://github.com/cp4925/Reinforcement-Learning-for-Signal-Optimization" target="_blank" class="proj-link">↗ GitHub Repo</a>
      </div>
    </div>
    <div class="project-card">
      <div class="project-header">
        <div class="project-title">Regex IP Filter Firewall</div>
        <div class="project-date">Aug – Dec 2025</div>
      </div>
      <p class="project-desc">Designed a regex-based IP Filter Firewall in Python to validate, detect, and filter IPv4 addresses in real time. Flags suspicious IP patterns and restricts unauthorised access using efficient firewall rule processing.</p>
      <div class="tags">
        <span class="tag">Python</span><span class="tag">Regex</span><span class="tag">Firewall</span>
        <span class="tag">IPv4 Filtering</span><span class="tag">Network Security</span>
        <span class="tag">Cybersecurity</span><span class="tag">Scapy</span>
      </div>
      <div class="project-links">
        <a href="https://github.com/cp4925" target="_blank" class="proj-link">↗ GitHub</a>
      </div>
    </div>
  </div>
</section>
<section id="skills">
  <div class="section-label">// 02 · toolbox</div>
  <h2 class="section-title">Skills</h2>
  <div class="skills-grid">
    <div class="skill-group"><div class="skill-group-title">Languages</div><div class="skill-list"><span class="skill-pill">Python</span><span class="skill-pill">C++</span><span class="skill-pill">SQL</span><span class="skill-pill">JavaScript</span><span class="skill-pill">HTML</span></div></div>
    <div class="skill-group"><div class="skill-group-title">AI / ML</div><div class="skill-list"><span class="skill-pill">PyTorch</span><span class="skill-pill">DQN</span><span class="skill-pill">Reinforcement Learning</span><span class="skill-pill">Stable-Baselines3</span></div></div>
    <div class="skill-group"><div class="skill-group-title">Security</div><div class="skill-list"><span class="skill-pill">Cybersecurity</span><span class="skill-pill">IP Filtering</span><span class="skill-pill">Scapy</span><span class="skill-pill">Network Security</span><span class="skill-pill">Regex</span></div></div>
    <div class="skill-group"><div class="skill-group-title">Tools & Systems</div><div class="skill-list"><span class="skill-pill">Operating Systems</span><span class="skill-pill">SUMO</span><span class="skill-pill">GitHub</span><span class="skill-pill">TraCI</span><span class="skill-pill">VS Code</span></div></div>
    <div class="skill-group"><div class="skill-group-title">Languages Spoken</div><div class="skill-list"><span class="skill-pill">English</span><span class="skill-pill">Tamil</span><span class="skill-pill">Hindi</span><span class="skill-pill">Malayalam</span></div></div>
  </div>
</section>
<section id="certs">
  <div class="section-label">// 03 · credentials</div>
  <h2 class="section-title">Certifications</h2>
  <div class="certs-list">
    <div class="cert-item"><div><div class="cert-name">Oracle Cloud Infrastructure</div><div class="cert-issuer">Oracle University</div></div><div class="cert-date">Oct 2025 – Oct 2027</div></div>
    <div class="cert-item"><div><div class="cert-name">Computer Networks and Network Security</div><div class="cert-issuer">IBM</div></div><div class="cert-date">Oct 2025</div></div>
    <div class="cert-item"><div><div class="cert-name">Advanced Algorithms and Complexity</div><div class="cert-issuer">UC San Diego · ID: RM8E8EGAAPTE</div></div><div class="cert-date">May 2025</div></div>
  </div>
</section>
<section id="edu">
  <div class="section-label">// 04 · education</div>
  <h2 class="section-title">Education</h2>
  <div class="edu-list">
    <div class="edu-item"><div><div class="edu-name">SRM Institute of Science and Technology, Trichy</div><div class="edu-detail">B.Tech · Computer Science and Engineering · Expected 2027</div></div><div class="edu-score">8.61 / 10</div></div>
    <div class="edu-item"><div><div class="edu-name">Kendriya Vidyalaya No.3 ONGC, Surat</div><div class="edu-detail">Class XII – CBSE · MPC · 2023</div></div><div class="edu-score">60%</div></div>
    <div class="edu-item"><div><div class="edu-name">Kendriya Vidyalaya No.3 ONGC, Surat</div><div class="edu-detail">Class X – CBSE · BMPC · 2021</div></div><div class="edu-score">86%</div></div>
  </div>
</section>
<section id="volunteer">
  <div class="section-label">// 05 · community</div>
  <h2 class="section-title">Volunteering</h2>
  <div class="vol-card">
    <div class="vol-header">
      <div><div class="vol-title">Blue NGO (BLUE Charitable Trust)</div><div class="vol-role">Community Connect Intern · Community Development</div></div>
      <div class="cert-date">Jun – Jul 2025</div>
    </div>
    <p class="vol-desc">Contributed to community-based projects including field surveys, educational outreach, and event organisation. Developed communication, leadership, problem-solving, and critical thinking skills through hands-on social impact initiatives.</p>
  </div>
</section>
<section id="contact">
  <div class="section-label">// 06 · reach me</div>
  <h2 class="section-title">Contact</h2>
  <div class="contact-grid">
    <a href="mailto:cp4925@srmist.edu.in" class="contact-card"><span class="contact-icon">✉</span> cp4925@srmist.edu.in</a>
    <a href="tel:+917904372131" class="contact-card"><span class="contact-icon">📞</span> +91 79043 72131</a>
    <a href="https://github.com/cp4925" target="_blank" class="contact-card"><span class="contact-icon">⌥</span> github.com/cp4925</a>
    <a href="https://linkedin.com" target="_blank" class="contact-card"><span class="contact-icon">in</span> LinkedIn</a>
  </div>
</section>
<footer><span>// C B Anshy Prabha</span> · 2026 · All rights reserved</footer>
</body>
</html>
