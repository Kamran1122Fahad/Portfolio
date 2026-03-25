<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Kamran Studios | Motion Graphics Editor</title>
  <meta name="description" content="Kamran Studios portfolio website for motion graphics, YouTube editing, reels, and premium cinematic edits." />
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@500;600;700&display=swap');
    :root {
      --bg: #111111;
      --bg-2: #1b1b1b;
      --card: rgba(255,255,255,0.08);
      --text: #f5f5f5;
      --muted: #bdbdbd;
      --accent: #c1121f;
      --accent-2: #ff4d5a;
      --border: rgba(255,255,255,0.14);
      --shadow: 0 20px 50px rgba(0,0,0,0.35);
      --glow: 0 0 40px rgba(255,77,90,0.18);
      --max: 1160px;
    }

    * { box-sizing: border-box; }
    html { scroll-behavior: smooth; }

    body {
      margin: 0;
      font-family: "SF Pro Display", -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
      color: var(--text);
      background:
        radial-gradient(circle at top left, rgba(193,18,31,0.24), transparent 28%),
        radial-gradient(circle at top right, rgba(255,77,90,0.16), transparent 20%),
        linear-gradient(180deg, #121212 0%, #1b1b1b 50%, #0d0d0d 100%);
      line-height: 1.6;
      overflow-x: hidden;
    }

    a { color: inherit; text-decoration: none; }
    img { max-width: 100%; display: block; }

    .container {
      width: min(92%, var(--max));
      margin: 0 auto;
    }

    .nav {
      position: sticky;
      top: 0;
      z-index: 50;
      backdrop-filter: blur(18px) saturate(160%);
      -webkit-backdrop-filter: blur(18px) saturate(160%);
      background: rgba(18,18,18,0.58);
      border-bottom: 1px solid rgba(255,255,255,0.08);
    }

    .nav-inner {
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 14px 0;
      gap: 16px;
    }

    .brand {
      font-weight: 800;
      letter-spacing: 0.05em;
      font-size: 1.12rem;
      font-family: "SF Pro Display", -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
    }

    .brand span { color: var(--accent-2); }

    .menu {
      display: flex;
      gap: 18px;
      flex-wrap: wrap;
      color: var(--muted);
      font-size: 0.95rem;
    }

    .menu a {
      transition: transform 0.25s ease, color 0.25s ease;
    }

    .menu a:hover {
      color: var(--text);
      transform: translateY(-2px);
    }

    .hero {
      padding: 76px 0 52px;
      position: relative;
    }

    .hero::before {
      content: "";
      position: absolute;
      inset: 0;
      background:
        radial-gradient(circle at 20% 20%, rgba(255,77,90,0.16), transparent 0 24%),
        radial-gradient(circle at 80% 10%, rgba(193,18,31,0.14), transparent 0 20%);
      pointer-events: none;
      filter: blur(18px);
    }

    .hero-grid {
      display: grid;
      grid-template-columns: 1.1fr 0.9fr;
      gap: 28px;
      align-items: center;
    }

    .eyebrow {
      display: inline-flex;
      align-items: center;
      gap: 10px;
      font-size: 0.9rem;
      color: #ffd8db;
      padding: 8px 14px;
      border: 1px solid rgba(255,77,90,0.28);
      background: rgba(255,77,90,0.1);
      border-radius: 999px;
      box-shadow: var(--glow);
    }

    h1 {
      font-size: clamp(2.5rem, 5vw, 5rem);
      line-height: 1.02;
      margin: 18px 0 18px;
      letter-spacing: -0.04em;
      font-family: "SF Pro Display", -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
    }

    .highlight {
      background: linear-gradient(90deg, var(--accent), var(--accent-2));
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
    }

    .lead {
      color: var(--muted);
      font-size: 1.08rem;
      max-width: 60ch;
      margin-bottom: 24px;
    }

    .cta-row {
      display: flex;
      gap: 14px;
      flex-wrap: wrap;
      margin-bottom: 28px;
    }

    .btn {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 10px;
      padding: 13px 20px;
      border-radius: 14px;
      font-weight: 700;
      border: 1px solid transparent;
      transition: transform 0.25s ease, box-shadow 0.25s ease, border-color 0.25s ease;
      will-change: transform;
    }

    .btn-primary {
      background: linear-gradient(90deg, var(--accent), var(--accent-2));
      box-shadow: var(--shadow), var(--glow);
    }

    .btn-secondary {
      border-color: var(--border);
      background: rgba(255,255,255,0.04);
      color: var(--muted);
      backdrop-filter: blur(12px);
    }

    .btn-ghost {
      border-color: rgba(255,77,90,0.22);
      background: linear-gradient(90deg, rgba(193,18,31,0.14), rgba(255,255,255,0.04));
      color: #ffe7e9;
      box-shadow: 0 0 24px rgba(255,77,90,0.08);
    }

    .btn:hover {
      transform: translateY(-3px) scale(1.02);
      box-shadow: 0 22px 55px rgba(0,0,0,0.38), 0 0 30px rgba(255,77,90,0.18);
    }

    .stats {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 14px;
    }

    .stat, .card {
      background: linear-gradient(180deg, rgba(255,255,255,0.09), rgba(255,255,255,0.05));
      border: 1px solid rgba(255,255,255,0.14);
      border-radius: 22px;
      box-shadow: var(--shadow);
      backdrop-filter: blur(18px) saturate(140%);
      -webkit-backdrop-filter: blur(18px) saturate(140%);
      transition: transform 0.35s ease, box-shadow 0.35s ease, border-color 0.35s ease;
      will-change: transform;
    }

    .float:hover {
      transform: translateY(-8px);
      box-shadow: 0 26px 60px rgba(0,0,0,0.42), 0 0 36px rgba(255,77,90,0.14);
      border-color: rgba(255,77,90,0.32);
    }

    .stat {
      padding: 18px;
    }

    .stat h3 {
      margin: 0;
      font-size: 1.8rem;
    }

    .stat p {
      margin: 6px 0 0;
      color: var(--muted);
      font-size: 0.92rem;
    }

    .hero-card {
      padding: 22px;
      position: relative;
      overflow: hidden;
    }

    .hero-preview {
      aspect-ratio: 4 / 5;
      border-radius: 18px;
      padding: 22px;
      background:
        linear-gradient(180deg, rgba(193,18,31,0.18), rgba(255,77,90,0.08)),
        rgba(255,255,255,0.04);
      border: 1px solid rgba(255,255,255,0.08);
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      gap: 18px;
    }

    .hero-top {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 12px;
      flex-wrap: wrap;
    }

    .reel-badge, .chip {
      display: inline-block;
      border: 1px solid rgba(255,255,255,0.12);
      background: linear-gradient(90deg, rgba(193,18,31,0.18), rgba(255,77,90,0.10));
      border-radius: 999px;
      padding: 7px 12px;
      color: #ffe7e9;
      font-size: 0.86rem;
      box-shadow: 0 0 20px rgba(255,77,90,0.08);
    }

    .profile-mini {
      display: flex;
      align-items: center;
      gap: 12px;
      padding: 10px 12px;
      border-radius: 999px;
      background: linear-gradient(90deg, rgba(193,18,31,0.14), rgba(255,255,255,0.06));
      border: 1px solid rgba(255,77,90,0.18);
      backdrop-filter: blur(12px);
    }

    .avatar {
      width: 54px;
      height: 54px;
      border-radius: 50%;
      display: grid;
      place-items: center;
      font-weight: 800;
      letter-spacing: 0.08em;
      background: linear-gradient(135deg, rgba(193,18,31,0.95), rgba(255,77,90,0.72));
      color: white;
      border: 2px solid rgba(255,255,255,0.18);
      box-shadow: 0 0 30px rgba(255,77,90,0.18);
      flex-shrink: 0;
      overflow: hidden;
    }

    .avatar img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      border-radius: 50%;
      display: block;
    }

    .profile-mini strong,
    .profile-hero strong {
      display: block;
      line-height: 1.2;
    }

    .profile-mini span,
    .profile-hero span {
      color: var(--muted);
      font-size: 0.88rem;
    }

    .screen {
      border-radius: 18px;
      background: linear-gradient(180deg, #141414, #0f0f10);
      border: 1px solid rgba(255,255,255,0.08);
      padding: 16px;
      min-height: 230px;
      display: grid;
      gap: 12px;
      align-content: start;
    }

    .screen .bar {
      height: 10px;
      border-radius: 999px;
      background: linear-gradient(90deg, var(--accent), var(--accent-2));
      opacity: 0.9;
    }

    .screen .thumbs {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 10px;
    }

    .screen .thumb {
      aspect-ratio: 1 / 1;
      border-radius: 14px;
      background: linear-gradient(135deg, rgba(193,18,31,0.58), rgba(255,77,90,0.30));
      border: 1px solid rgba(255,255,255,0.08);
    }

    .hero-note {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 12px;
    }

    .glass-note {
      padding: 14px;
      border-radius: 16px;
      background: linear-gradient(180deg, rgba(193,18,31,0.10), rgba(255,255,255,0.04));
      border: 1px solid rgba(255,77,90,0.14);
      color: #e8d7d8;
      font-size: 0.92rem;
    }

    .section {
      padding: 32px 0 12px;
    }

    .section-title {
      font-size: clamp(1.9rem, 3vw, 2.7rem);
      margin: 0 0 10px;
      letter-spacing: -0.03em;
      font-family: "Cormorant Garamond", Georgia, serif;
      color: #ffe4e6;
    }

    .section-sub {
      color: var(--muted);
      max-width: 70ch;
      margin: 0 0 24px;
    }

    .services, .portfolio, .testimonials {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 18px;
    }

    #services .card:nth-child(1) {
      background: linear-gradient(180deg, rgba(193,18,31,0.18), rgba(255,255,255,0.05));
      border-color: rgba(255,77,90,0.22);
    }

    #services .card:nth-child(2) {
      background: linear-gradient(180deg, rgba(150,12,25,0.22), rgba(255,255,255,0.05));
      border-color: rgba(255,77,90,0.24);
    }

    #services .card:nth-child(3) {
      background: linear-gradient(180deg, rgba(255,77,90,0.16), rgba(255,255,255,0.05));
      border-color: rgba(255,77,90,0.26);
    }

    .card {
      padding: 22px;
    }

    .card h3 {
      margin-top: 8px;
      margin-bottom: 8px;
      font-size: 1.2rem;
      font-family: "Cormorant Garamond", Georgia, serif;
      color: #fff0f1;
    }

    .card p {
      margin: 0;
      color: var(--muted);
    }

    .portfolio .project {
      overflow: hidden;
      padding: 0;
      position: relative;
    }

    .project iframe {
      width: 100%;
      height: 220px;
      border: 0;
      display: block;
      background: #0a0a0a;
    }

    .project-toplink {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 10px;
      padding: 14px 18px 0;
      color: #ffe7e9;
      font-size: 0.92rem;
    }

    .project-toplink a {
      color: #ffd5d8;
      border-bottom: 1px solid rgba(255,77,90,0.22);
    }

    .project-content {
      padding: 18px;
    }

    .project-meta {
      display: flex;
      gap: 10px;
      flex-wrap: wrap;
      margin-top: 12px;
    }

    .reels-grid,
    .about-grid,
    .contact-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 18px;
    }

    .reel-placeholder {
      min-height: 230px;
      display: flex;
      flex-direction: column;
      justify-content: center;
      gap: 10px;
      border-radius: 18px;
      border: 1px dashed rgba(255,77,90,0.26);
      background: linear-gradient(180deg, rgba(193,18,31,0.10), rgba(255,255,255,0.02));
      padding: 24px;
      text-align: left;
    }

    .reel-placeholder h3 {
      margin: 0;
      font-size: 1.2rem;
    }

    .list {
      padding-left: 18px;
      color: var(--muted);
      margin: 14px 0 0;
    }

    .profile-hero {
      display: flex;
      align-items: center;
      gap: 14px;
      margin: 18px 0 20px;
      width: fit-content;
      padding: 12px 14px;
      border-radius: 20px;
      background: linear-gradient(90deg, rgba(193,18,31,0.16), rgba(255,255,255,0.05));
      border: 1px solid rgba(255,77,90,0.18);
      box-shadow: var(--glow);
    }

    .contact-card a,
    .inline-link {
      color: #ffd5d8;
    }

    .contact-list {
      display: grid;
      gap: 12px;
      margin-top: 14px;
    }

    .contact-item {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 12px;
      padding: 14px 16px;
      border-radius: 16px;
      background: linear-gradient(90deg, rgba(193,18,31,0.12), rgba(255,255,255,0.04));
      border: 1px solid rgba(255,77,90,0.16);
    }

    .contact-item span {
      color: var(--muted);
      font-size: 0.92rem;
    }

    .footer {
      padding: 36px 0 60px;
      color: var(--muted);
      text-align: center;
    }

    @keyframes floaty {
      0%, 100% { transform: translateY(0px); }
      50% { transform: translateY(-8px); }
    }

    .floating {
      animation: floaty 5s ease-in-out infinite;
    }

    @media (max-width: 920px) {
      .hero-grid,
      .about-grid,
      .contact-grid,
      .services,
      .portfolio,
      .testimonials,
      .hero-note,
      .reels-grid {
        grid-template-columns: 1fr;
      }

      .stats {
        grid-template-columns: 1fr;
      }

      .hero {
        padding-top: 44px;
      }
    }
  </style>
</head>
<body>
  <nav class="nav">
    <div class="container nav-inner">
      <a href="#top" class="brand">KAMRAN<span>STUDIOS</span></a>
      <div class="menu">
        <a href="#work">Work</a>
        <a href="#reels">Reels</a>
        <a href="#services">Services</a>
        <a href="#about">About</a>
        <a href="#contact">Contact</a>
      </div>
    </div>
  </nav>

  <header id="top" class="hero">
    <div class="container hero-grid">
      <div>
        <div class="eyebrow">🎬 Motion Graphics Editor • Reels • YouTube • Ads</div>
        <h1>I’m <span class="highlight">Kamran</span> — founder of <span class="highlight">Kamran Studios</span>.</h1>
        <p class="lead">
          I create premium motion graphics and high-retention edits for creators, brands, and businesses. My work is inspired by bold modern styles, fast pacing, cinematic storytelling, and energetic editing direction across famous creator and music-video inspired formats.
        </p>

        <div class="profile-hero float">
          <div class="avatar"><img src="profile.png" alt="Kamran profile picture" onerror="this.parentElement.innerHTML='K'" /></div>
          <div>
            <strong>Kamran</strong>
            <span>@realll_kamran</span>
          </div>
        </div>

        <div class="cta-row">
          <a class="btn btn-primary" href="#work">View My Work</a>
          <a class="btn btn-secondary" href="https://www.instagram.com/realll_kamran" target="_blank">Open Instagram</a>
          <a class="btn btn-ghost" href="#contact">Hire Me</a>
        </div>

        <div class="stats">
          <div class="stat float">
            <h3>50+</h3>
            <p>Projects delivered</p>
          </div>
          <div class="stat float">
            <h3>5M+</h3>
            <p>Total views supported</p>
          </div>
          <div class="stat float">
            <h3>24h</h3>
            <p>Fast turnaround option</p>
          </div>
        </div>
      </div>

      <div class="card hero-card float">
        <div class="hero-preview">
          <div class="hero-top">
            <div class="reel-badge">Kamran Studios • 2026 Edition</div>
            <a class="profile-mini" href="https://www.instagram.com/realll_kamran" target="_blank">
              <div class="avatar"><img src="profile.png" alt="Kamran profile picture" onerror="this.parentElement.innerHTML='K'" /></div>
              <div>
                <strong>Kamran</strong>
                <span>@realll_kamran</span>
              </div>
            </a>
          </div>

          <div class="screen">
            <div class="bar"></div>
            <div class="thumbs">
              <div class="thumb"></div>
              <div class="thumb"></div>
              <div class="thumb"></div>
            </div>
            <div class="bar" style="width: 72%"></div>
            <div class="bar" style="width: 48%"></div>
          </div>

          <div class="hero-note">
            <div class="glass-note">Liquid glass UI with floating interactive cards and glowing motion.</div>
            <div class="glass-note">Software: Premiere Pro • After Effects • DaVinci Resolve • Photoshop</div>
          </div>
        </div>
      </div>
    </div>
      </div>
    </div>
  </header>

  <section id="services" class="section">
    <div class="container">
      <h2 class="section-title">Services</h2>
      <p class="section-sub">Motion graphics, reels, YouTube editing, and visually aggressive high-retention styles tailored for creators, brands, and commercial projects.</p>
      <div class="services">
        <article class="card float">
          <div class="chip">Short-form</div>
          <h3>Reels & Short-form Editing</h3>
          <p>Fast cuts, animated subtitles, hooks, punchy transitions, motion graphics overlays, and platform-optimized pacing for viral-ready content.</p>
        </article>
        <article class="card float">
          <div class="chip">Long-form</div>
          <h3>YouTube Video Editing</h3>
          <p>Retention-first editing for talking-heads, vlogs, business content, and high-energy storytelling with modern creator-style structure.</p>
        </article>
        <article class="card float">
          <div class="chip">Motion</div>
          <h3>Motion Graphics & Commercials</h3>
          <p>Premium motion graphics, ad visuals, bold intros, stylized zooms, transitions, and visuals inspired by famous high-performance editing aesthetics.</p>
        </article>
      </div>
    </div>
  </section>

  <section id="work" class="section" style="background: linear-gradient(180deg, rgba(193,18,31,0.05), transparent 65%);">
    <div class="container">
      <h2 class="section-title">Featured Work</h2>
      <p class="section-sub">Live previews of client projects are embedded here so visitors can instantly see your editing quality and style.</p>
      <div class="portfolio">
        <article class="card project float">
          <div class="project-toplink"><span>Embedded Preview</span><a href="https://youtu.be/ifhJOleYru8?si=rI1kNDs6vhleV1i8" target="_blank">Open on YouTube</a></div>
          <iframe src="https://www.youtube.com/embed/ifhJOleYru8" title="Client Project 1" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
          <div class="project-content">
            <h3>Client Project 1</h3>
            <p>High-quality edit with cinematic pacing, polished visuals, and premium energy.</p>
            <div class="project-meta">
              <span class="chip">Motion Graphics</span>
              <span class="chip">Retention Edit</span>
            </div>
          </div>
        </article>

        <article class="card project float">
          <div class="project-toplink"><span>Embedded Preview</span><a href="https://youtu.be/Gd1_UkDNw30?si=m8zxIPxIFZ_Ophdh" target="_blank">Open on YouTube</a></div>
          <iframe src="https://www.youtube.com/embed/Gd1_UkDNw30" title="Client Project 2" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
          <div class="project-content">
            <h3>Client Project 2</h3>
            <p>Engaging storytelling, sleek transitions, and clean pacing for a more premium watch experience.</p>
            <div class="project-meta">
              <span class="chip">Cinematic</span>
              <span class="chip">YouTube Style</span>
            </div>
          </div>
        </article>

        <article class="card project float">
          <div class="project-toplink"><span>Embedded Preview</span><a href="https://youtu.be/17uSI-wuZ88?si=c39Xwd1Bis8v5aeA" target="_blank">Open on YouTube</a></div>
          <iframe src="https://www.youtube.com/embed/17uSI-wuZ88" title="Client Project 3" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
          <div class="project-content">
            <h3>Client Project 3</h3>
            <p>Optimized for audience retention, dynamic feel, and visually lively storytelling.</p>
            <div class="project-meta">
              <span class="chip">Fast Pace</span>
              <span class="chip">Creative Flow</span>
            </div>
          </div>
        </article>
      </div>
    </div>
  </section>

  <section id="reels" class="section" style="background: linear-gradient(180deg, rgba(255,77,90,0.05), transparent 70%);">
    <div class="container">
      <h2 class="section-title">Reels Section</h2>
      <p class="section-sub">I added a dedicated reels section so you can place your Instagram reels or short-form links here later without changing the whole website layout.</p>
      <div class="reels-grid">
        <article class="card float reel-placeholder">
          <div class="chip">Instagram Reels</div>
          <h3>Add Reel Link Here</h3>
          <p>Place your best reel embed, Instagram post link, or short-form preview in this block when you want to showcase viral-style edits.</p>
        </article>
        <article class="card float reel-placeholder">
          <div class="chip">Short-form Showcase</div>
          <h3>Add More Reels Later</h3>
          <p>This section is ready for future reel previews, hook edits, talking-head shorts, or motion graphic reel clips.</p>
        </article>
      </div>
    </div>
  </section>

  <section id="about" class="section" style="background: linear-gradient(180deg, rgba(193,18,31,0.04), transparent 70%);">
    <div class="container about-grid">
      <div class="card float">
        <h2 class="section-title">About Kamran Studios</h2>
        <p class="section-sub">
          Kamran Studios focuses on motion graphics, premium content editing, and high-energy visual storytelling for creators and brands that want edits with stronger attention retention.
        </p>
        <p>
          I work across modern creator-inspired styles, cinematic edit structures, music-video influenced movement, and polished commercial pacing. My focus is to make content feel more premium, more alive, and more memorable.
        </p>
      </div>
      <div class="card float">
        <h2 class="section-title">Software & Editing Direction</h2>
        <ul class="list">
          <li>Adobe Premiere Pro</li>
          <li>Adobe After Effects</li>
          <li>DaVinci Resolve</li>
          <li>Adobe Photoshop</li>
          <li>Motion graphics, subtitles, transitions, color work, and sound polish</li>
        </ul>
      </div>
    </div>
  </section>

  <section class="section">
    <div class="container">
      <h2 class="section-title">Client Feedback</h2>
      <p class="section-sub">A clean testimonial section to make the website feel more complete and trustworthy.</p>
      <div class="testimonials">
        <article class="card float">
          <p>“The final video looked premium and performed better than our older edits.”</p>
          <h3>— Brand Client</h3>
        </article>
        <article class="card float">
          <p>“Great pacing, clean captions, and super easy to work with.”</p>
          <h3>— YouTube Creator</h3>
        </article>
        <article class="card float">
          <p>“Fast turnaround and the edits matched exactly what we wanted.”</p>
          <h3>— Agency Team</h3>
        </article>
      </div>
    </div>
  </section>

  <section id="contact" class="section" style="background: linear-gradient(180deg, rgba(255,77,90,0.04), transparent 70%);">
    <div class="container contact-grid">
      <div class="card contact-card float">
        <h2 class="section-title">Let’s Work Together</h2>
        <p class="section-sub">Reach out for editing projects, motion graphics work, reels, YouTube videos, and branded content.</p>
        <div class="contact-list">
          <div class="contact-item">
            <div>
              <strong>Email</strong>
              <span>Replace with your updated email</span>
            </div>
            <a href="mailto:yournewemail@example.com">yournewemail@example.com</a>
          </div>
          <div class="contact-item">
            <div>
              <strong>Instagram</strong>
              <span>Your public creator profile</span>
            </div>
            <a href="https://www.instagram.com/realll_kamran" target="_blank">@realll_kamran</a>
          </div>
          <div class="contact-item">
            <div>
              <strong>WhatsApp</strong>
              <span>0349 1778455</span>
            </div>
            <a href="https://wa.me/923491778455" target="_blank">Chat now</a>
          </div>
        </div>
      </div>
      <div class="card float">
        <h2 class="section-title">Portfolio Links</h2>
        <p>Use this block for your extra links and public profiles:</p>
        <ul class="list">
          <li><a class="inline-link" href="https://www.instagram.com/realll_kamran" target="_blank">Instagram profile</a></li>
          <li><a class="inline-link" href="https://youtu.be/ifhJOleYru8?si=rI1kNDs6vhleV1i8" target="_blank">Client Project 1</a></li>
          <li><a class="inline-link" href="https://youtu.be/Gd1_UkDNw30?si=m8zxIPxIFZ_Ophdh" target="_blank">Client Project 2</a></li>
          <li><a class="inline-link" href="https://youtu.be/17uSI-wuZ88?si=c39Xwd1Bis8v5aeA" target="_blank">Client Project 3</a></li>
        </ul>
      </div>
    </div>
  </section>

  <footer class="footer">
    <div class="container">
      © 2026 Kamran Studios • Motion Graphics & Video Editing Portfolio
    </div>
  </footer>
</body>
</html>
