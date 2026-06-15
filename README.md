<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>IREN — International Radiation Experts Network</title>
<link href="https://fonts.googleapis.com/css2?family=DM+Sans:wght@300;400;500&family=DM+Serif+Display&display=swap" rel="stylesheet"/>
<style>
  :root {
    --green-darkest: #04342C;
    --green-dark: #085041;
    --green-mid: #0F6E56;
    --green-base: #1D9E75;
    --green-light: #5DCAA5;
    --green-pale: #9FE1CB;
    --mint: #E1F5EE;
    --mint-bg: #E8F5F0;
    --white: #ffffff;
    --text-dark: #04342C;
    --text-mid: #0F6E56;
    --text-light: #9FE1CB;
  }
  * { box-sizing: border-box; margin: 0; padding: 0; }
  html { scroll-behavior: smooth; }
  body { font-family: 'DM Sans', sans-serif; background: var(--mint-bg); color: var(--text-dark); line-height: 1.6; }

  /* NAV */
  nav {
    background: var(--green-darkest);
    padding: 0 3rem;
    display: flex;
    align-items: center;
    justify-content: space-between;
    height: 68px;
    position: sticky;
    top: 0;
    z-index: 100;
    border-bottom: 1px solid var(--green-mid);
  }
  .nav-brand { display: flex; align-items: center; gap: 14px; text-decoration: none; }
  .nav-wordmark { color: #E1F5EE; font-size: 20px; font-weight: 500; letter-spacing: 4px; }
  .nav-sub { color: var(--green-light); font-size: 8px; letter-spacing: 1.5px; margin-top: 1px; }
  .nav-links { display: flex; gap: 28px; align-items: center; }
  .nav-links a { color: var(--green-pale); font-size: 13px; text-decoration: none; transition: color 0.2s; }
  .nav-links a:hover { color: #E1F5EE; }
  .btn-nav { background: var(--green-base); color: var(--green-darkest); border: none; padding: 8px 20px; border-radius: 6px; font-size: 13px; font-weight: 500; cursor: pointer; font-family: inherit; transition: background 0.2s; }
  .btn-nav:hover { background: var(--green-light); }

  /* HERO */
  .hero {
    background: var(--green-dark);
    padding: 5rem 3rem;
    display: flex;
    align-items: center;
    gap: 4rem;
  }
  .hero-left { flex: 1; }
  .hero-badge {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    background: var(--green-mid);
    padding: 5px 14px;
    border-radius: 20px;
    margin-bottom: 1.5rem;
    color: var(--green-pale);
    font-size: 11px;
    letter-spacing: 1.2px;
  }
  .hero h1 { color: #E1F5EE; font-family: 'DM Serif Display', serif; font-size: 42px; line-height: 1.2; margin-bottom: 1.2rem; font-weight: 400; }
  .hero p { color: var(--green-pale); font-size: 15px; line-height: 1.8; margin-bottom: 2rem; max-width: 520px; }
  .hero-btns { display: flex; gap: 12px; }
  .btn-pri { background: var(--green-base); color: var(--green-darkest); border: none; padding: 12px 26px; border-radius: 7px; font-size: 14px; font-weight: 500; cursor: pointer; font-family: inherit; transition: background 0.2s; }
  .btn-pri:hover { background: var(--green-light); }
  .btn-sec { background: transparent; color: var(--green-pale); border: 1.5px solid var(--green-base); padding: 12px 26px; border-radius: 7px; font-size: 14px; font-weight: 500; cursor: pointer; font-family: inherit; transition: all 0.2s; }
  .btn-sec:hover { border-color: var(--green-pale); color: #E1F5EE; }
  .hero-stats { flex: 0 0 280px; display: flex; flex-direction: column; gap: 12px; }
  .stat-big { background: var(--green-mid); border-radius: 12px; padding: 1.4rem; text-align: center; border: 1px solid var(--green-base); }
  .stat-big .num { color: #E1F5EE; font-family: 'DM Serif Display', serif; font-size: 38px; }
  .stat-big .lbl { color: var(--green-pale); font-size: 10px; letter-spacing: 1.5px; margin-bottom: 4px; }
  .stat-row { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; }
  .stat-sm { background: var(--green-mid); border-radius: 10px; padding: 1rem; text-align: center; border: 1px solid var(--green-base); }
  .stat-sm .num { color: #E1F5EE; font-family: 'DM Serif Display', serif; font-size: 26px; }
  .stat-sm .lbl { color: var(--green-pale); font-size: 10px; letter-spacing: 1px; margin-bottom: 2px; }

  /* DIVIDER */
  .divider { height: 3px; background: var(--green-base); }

  /* SECTION */
  section { padding: 4rem 3rem; }
  .section-tag { display: inline-block; background: var(--green-base); color: var(--green-darkest); font-size: 11px; padding: 3px 12px; border-radius: 20px; font-weight: 500; letter-spacing: 0.5px; margin-bottom: 10px; }
  .section-title { font-family: 'DM Serif Display', serif; font-size: 28px; color: var(--green-darkest); font-weight: 400; margin-bottom: 2rem; }
  .section-header { display: flex; align-items: flex-start; justify-content: space-between; margin-bottom: 2rem; }

  /* PILLARS */
  .pillars { background: var(--mint-bg); }
  .pillars-inner { text-align: center; }
  .pillars-inner .section-title { margin-bottom: 2rem; }
  .card-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(160px, 1fr)); gap: 16px; }
  .pillar-card { background: var(--white); border-radius: 12px; padding: 1.5rem; border: 0.5px solid var(--green-pale); border-top: 3px solid var(--green-base); text-align: left; transition: transform 0.2s; }
  .pillar-card:hover { transform: translateY(-3px); }
  .pillar-icon { font-size: 24px; color: var(--green-base); margin-bottom: 12px; }
  .pillar-title { color: var(--text-dark); font-weight: 500; font-size: 14px; margin-bottom: 6px; }
  .pillar-desc { color: var(--text-mid); font-size: 13px; line-height: 1.6; }

  /* DISCIPLINES */
  .disciplines { background: var(--white); border-top: 0.5px solid var(--green-pale); }
  .disc-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 14px; }
  .disc-card { background: var(--mint); border-radius: 10px; padding: 1.2rem 1.2rem 1.2rem 1.5rem; border-left: 4px solid var(--green-dark); transition: border-color 0.2s; }
  .disc-card:hover { border-left-color: var(--green-base); }
  .disc-title { color: var(--text-dark); font-weight: 500; font-size: 14px; margin-bottom: 4px; }
  .disc-desc { color: var(--text-mid); font-size: 12px; line-height: 1.5; }

  /* NEWS */
  .news { background: var(--mint-bg); }
  .news-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 16px; }
  .news-card { background: var(--white); border-radius: 12px; padding: 1.25rem; border: 0.5px solid var(--green-pale); transition: transform 0.2s; }
  .news-card:hover { transform: translateY(-2px); }
  .news-thumb { background: var(--mint); border-radius: 8px; height: 90px; display: flex; align-items: center; justify-content: center; margin-bottom: 14px; font-size: 36px; color: var(--green-base); }
  .news-tag { background: var(--mint); color: var(--green-dark); font-size: 10px; padding: 2px 9px; border-radius: 10px; font-weight: 500; }
  .news-title { color: var(--text-dark); font-size: 13px; font-weight: 500; margin: 8px 0 4px; line-height: 1.5; }
  .news-date { color: var(--green-base); font-size: 11px; }

  /* TEAM */
  .team { background: var(--white); border-top: 0.5px solid var(--green-pale); }
  .team-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(180px, 1fr)); gap: 16px; }
  .team-card { background: var(--mint-bg); border-radius: 12px; padding: 1.5rem; text-align: center; border: 0.5px solid var(--green-pale); }
  .avatar, .team-photo { width: 60px; height: 60px; border-radius: 50%; background: var(--green-dark); display: flex; align-items: center; justify-content: center; color: var(--green-pale); font-size: 18px; font-weight: 500; margin: 0 auto 12px; font-family: 'DM Serif Display', serif; }
  .team-photo { width: 120px; height: 120px; object-fit: cover; border: 3px solid var(--green-base); cursor: pointer; background: transparent; }
  .team-photo:hover { transform: scale(1.03); }
  .team-name { color: var(--text-dark); font-weight: 500; font-size: 14px; }
  .team-role { color: var(--text-mid); font-size: 12px; margin-top: 3px; }
  .team-country { color: var(--green-base); font-size: 11px; margin-top: 6px; }

  .modal-overlay { display: none; position: fixed; inset: 0; background: rgba(4, 52, 44, 0.75); align-items: center; justify-content: center; padding: 1.5rem; z-index: 200; }
  .modal-overlay.active { display: flex; }
  .modal-content { background: #fff; border-radius: 18px; max-width: 540px; width: 100%; padding: 1.5rem; box-shadow: 0 18px 50px rgba(0, 0, 0, 0.2); position: relative; }
  .modal-close { position: absolute; top: 16px; right: 16px; border: none; background: transparent; font-size: 24px; color: var(--green-dark); cursor: pointer; }
  .modal-content img { width: 100%; border-radius: 14px; max-height: 320px; object-fit: cover; margin-bottom: 1rem; }
  .modal-text h3 { margin-bottom: 0.5rem; font-size: 20px; color: var(--text-dark); font-family: 'DM Serif Display', serif; }
  .modal-text p { color: var(--text-mid); font-size: 14px; line-height: 1.7; margin-bottom: 0.8rem; }
  .modal-link { color: var(--green-dark); font-weight: 600; text-decoration: none; display: inline-block; margin-top: 0.2rem; }
  .modal-link:hover { color: var(--green-base); }

  /* CONTACT */
  .contact { background: var(--mint-bg); border-top: 0.5px solid var(--green-pale); }
  .contact-inner { display: grid; grid-template-columns: 1fr 1fr; gap: 3rem; align-items: start; }
  .contact-info h2 { font-family: 'DM Serif Display', serif; font-size: 28px; color: var(--text-dark); font-weight: 400; margin-bottom: 1rem; }
  .contact-info p { color: var(--text-mid); font-size: 14px; line-height: 1.8; margin-bottom: 1.5rem; }
  .contact-detail { display: flex; align-items: center; gap: 10px; color: var(--text-mid); font-size: 13px; margin-bottom: 10px; }
  .contact-detail i { color: var(--green-base); font-size: 18px; }
  .contact-form { background: var(--white); border-radius: 14px; padding: 2rem; border: 0.5px solid var(--green-pale); }
  .form-group { margin-bottom: 1rem; }
  .form-group label { display: block; color: var(--text-dark); font-size: 13px; font-weight: 500; margin-bottom: 5px; }
  .form-group input, .form-group textarea, .form-group select {
    width: 100%; padding: 10px 14px; border: 1px solid var(--green-pale);
    border-radius: 7px; font-size: 13px; font-family: inherit;
    background: var(--mint-bg); color: var(--text-dark);
    outline: none; transition: border-color 0.2s;
  }
  .form-group input:focus, .form-group textarea:focus, .form-group select:focus { border-color: var(--green-base); }
  .form-group textarea { height: 110px; resize: vertical; }
  .form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; }
  .submit-btn { width: 100%; background: var(--green-dark); color: #E1F5EE; border: none; padding: 12px; border-radius: 7px; font-size: 14px; font-weight: 500; cursor: pointer; font-family: inherit; margin-top: 6px; transition: background 0.2s; }
  .submit-btn:hover { background: var(--green-base); color: var(--green-darkest); }

  /* MEMBERSHIP CTA */
  .cta {
    background: var(--green-dark);
    padding: 3rem;
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 2rem;
    flex-wrap: wrap;
  }
  .cta h2 { font-family: 'DM Serif Display', serif; color: #E1F5EE; font-size: 24px; font-weight: 400; }
  .cta p { color: var(--green-pale); font-size: 13px; margin-top: 4px; }
  .cta-btns { display: flex; gap: 12px; flex-wrap: wrap; }

  /* FOOTER */
  footer { background: var(--green-darkest); padding: 2rem 3rem; }
  .footer-top { display: flex; align-items: flex-start; justify-content: space-between; gap: 2rem; margin-bottom: 2rem; flex-wrap: wrap; }
  .footer-brand .wordmark { color: #E1F5EE; font-size: 20px; font-weight: 500; letter-spacing: 4px; }
  .footer-brand .tagline { color: var(--green-light); font-size: 12px; font-style: italic; margin-top: 4px; }
  .footer-links h4 { color: var(--green-pale); font-size: 11px; letter-spacing: 1.5px; margin-bottom: 10px; }
  .footer-links a { display: block; color: var(--green-light); font-size: 13px; margin-bottom: 6px; text-decoration: none; transition: color 0.2s; }
  .footer-links a:hover { color: #E1F5EE; }
  .footer-bottom { border-top: 0.5px solid var(--green-mid); padding-top: 1.2rem; display: flex; align-items: center; justify-content: space-between; }
  .footer-bottom span { color: var(--green-light); font-size: 12px; }

  /* UTIL */
  .btn-sm { padding: 8px 18px; font-size: 12px; }
  @media (max-width: 768px) {
    nav { padding: 0 1.5rem; }
    .nav-links { display: none; }
    .hero { flex-direction: column; padding: 3rem 1.5rem; }
    .hero-stats { width: 100%; }
    section { padding: 3rem 1.5rem; }
    .contact-inner { grid-template-columns: 1fr; }
    .cta { flex-direction: column; }
    .footer-top { flex-direction: column; }
  }
</style>
</head>
<body>

<!-- NAVBAR -->
<nav>
  <a class="nav-brand" href="#">
    <svg width="40" height="40" viewBox="0 0 80 80">
      <polygon points="40,4 72,22 72,58 40,76 8,58 8,22" fill="#085041" stroke="#1D9E75" stroke-width="3"/>
      <polygon points="40,14 64,28 64,52 40,66 16,52 16,28" fill="#0F6E56"/>
      <circle cx="40" cy="34" r="10" fill="#1D9E75"/>
      <circle cx="26" cy="50" r="10" fill="#1D9E75"/>
      <circle cx="54" cy="50" r="10" fill="#1D9E75"/>
      <circle cx="40" cy="44" r="8" fill="#085041"/>
      <circle cx="40" cy="44" r="4" fill="#04342C"/>
    </svg>
    <div>
      <div class="nav-wordmark">IREN</div>
      <div class="nav-sub">INTERNATIONAL RADIATION EXPERTS NETWORK</div>
    </div>
  </a>
  <div class="nav-links">
    <a href="#about">About</a>
    <a href="#research">Research</a>
    <a href="#team">Team</a>
    <a href="#news">News</a>
    <a href="#contact">Contact</a>
    <button class="btn-nav">Join IREN</button>
  </div>
</nav>

<!-- HERO -->
<div class="hero" id="about">
  <div class="hero-left">
    <div class="hero-badge">&#9737; RADIATION SCIENCE NETWORK</div>
    <h1>Uniting the world's radiation science experts</h1>
    <p>IREN connects leading specialists across gamma, neutron, optical, and particle radiation disciplines — fostering collaboration, advancing research, and promoting safe, beneficial applications globally.</p>
    <div class="hero-btns">
      <button class="btn-pri">Explore Research</button>
      <button class="btn-sec">Become a Member</button>
    </div>
  </div>
  <div class="hero-stats">
    <div class="stat-big">
      <div class="lbl">MEMBER EXPERTS</div>
      <div class="num">4,200+</div>
    </div>
    <div class="stat-row">
      <div class="stat-sm">
        <div class="lbl">COUNTRIES</div>
        <div class="num">82</div>
      </div>
      <div class="stat-sm">
        <div class="lbl">PUBLICATIONS</div>
        <div class="num">1,800+</div>
      </div>
    </div>
    <div class="stat-row">
      <div class="stat-sm">
        <div class="lbl">CONFERENCES</div>
        <div class="num">240</div>
      </div>
      <div class="stat-sm">
        <div class="lbl">INSTITUTIONS</div>
        <div class="num">310+</div>
      </div>
    </div>
  </div>
</div>
<div class="divider"></div>

<!-- PILLARS -->
<section class="pillars" id="research">
  <div class="pillars-inner">
    <span class="section-tag">Our pillars</span>
    <div class="section-title">What IREN stands for</div>
  </div>
  <div class="card-grid">
    <div class="pillar-card">
      <div class="pillar-icon">&#128300;</div>
      <div class="pillar-title">Research</div>
      <div class="pillar-desc">Collaborative studies across all radiation disciplines — from fundamental physics to clinical applications worldwide.</div>
    </div>
    <div class="pillar-card">
      <div class="pillar-icon">&#127979;</div>
      <div class="pillar-title">Education</div>
      <div class="pillar-desc">Training programs, international certifications, and open knowledge-sharing for radiation professionals at all levels.</div>
    </div>
    <div class="pillar-card">
      <div class="pillar-icon">&#127758;</div>
      <div class="pillar-title">Networking</div>
      <div class="pillar-desc">Connecting experts across borders, institutions, and disciplines through conferences, forums, and digital platforms.</div>
    </div>
    <div class="pillar-card">
      <div class="pillar-icon">&#128737;</div>
      <div class="pillar-title">Safety</div>
      <div class="pillar-desc">Developing and promoting global radiation safety standards, protocols, and best practices across all sectors.</div>
    </div>
    <div class="pillar-card">
      <div class="pillar-icon">&#128227;</div>
      <div class="pillar-title">Advocacy</div>
      <div class="pillar-desc">Influencing policy at national and international levels to ensure responsible use and public understanding of radiation science.</div>
    </div>
  </div>
</section>

<!-- DISCIPLINES -->
<section class="disciplines">
  <span class="section-tag">Disciplines</span>
  <div class="section-title">Areas of radiation science</div>
  <div class="disc-grid">
    <div class="disc-card">
      <div class="disc-title">Gamma Radiation</div>
      <div class="disc-desc">High-energy photon science, dosimetry, medical imaging, and industrial applications.</div>
    </div>
    <div class="disc-card">
      <div class="disc-title">Neutron Science</div>
      <div class="disc-desc">Neutron imaging, activation analysis, shielding design and reactor physics.</div>
    </div>
    <div class="disc-card">
      <div class="disc-title">Optical Radiation</div>
      <div class="disc-desc">UV, visible and infrared research — photobiology, phototherapy and laser safety.</div>
    </div>
    <div class="disc-card">
      <div class="disc-title">Particle Beams</div>
      <div class="disc-desc">Accelerator physics, proton therapy, heavy-ion research and beam dosimetry.</div>
    </div>
    <div class="disc-card">
      <div class="disc-title">X-ray Science</div>
      <div class="disc-desc">Diagnostic radiology, synchrotron applications, and radiation protection standards.</div>
    </div>
    <div class="disc-card">
      <div class="disc-title">Radioactive Materials</div>
      <div class="disc-desc">Isotope production, radiopharmaceuticals, nuclear waste and environmental monitoring.</div>
    </div>
  </div>
</section>

<!-- NEWS -->
<section class="news" id="news">
  <div class="section-header">
    <div>
      <span class="section-tag">Latest</span>
      <div class="section-title" style="margin-bottom:0">News &amp; updates</div>
    </div>
    <button class="btn-sec btn-sm" style="margin-top:1.2rem">View all</button>
  </div>
  <div class="news-grid">
    <div class="news-card">
      <div class="news-thumb">&#9883;</div>
      <span class="news-tag">Research</span>
      <div class="news-title">New gamma-ray dosimetry standards published for clinical use</div>
      <div class="news-date">May 2026</div>
    </div>
    <div class="news-card">
      <div class="news-thumb">&#127758;</div>
      <span class="news-tag">Event</span>
      <div class="news-title">IREN Annual Summit 2026 — Vienna, Austria</div>
      <div class="news-date">September 2026</div>
    </div>
    <div class="news-card">
      <div class="news-thumb">&#127891;</div>
      <span class="news-tag">Training</span>
      <div class="news-title">New neutron safety certification program now open for applications</div>
      <div class="news-date">April 2026</div>
    </div>
    <div class="news-card">
      <div class="news-thumb">&#128203;</div>
      <span class="news-tag">Policy</span>
      <div class="news-title">IREN submits recommendations to IAEA on optical radiation limits</div>
      <div class="news-date">March 2026</div>
    </div>
  </div>
</section>

<!-- TEAM -->
<section class="team" id="team">
  <span class="section-tag">Leadership</span>
  <div class="section-title">Meet our team</div>
  <div class="team-grid">
    <div class="team-card">
      <img class="team-photo" src="Bharat.JPG" alt="Dr. Bharat Singh Rawat" data-name="Dr. Bharat Singh Rawat" data-role="Director / CEO / Founder" data-description="Dr. Bharat Singh Rawat is an expert in charged particle transport. With over seven years of experience in beam diagnostics and ion source modelling, he brings his expertise to the IREN network as a founding member." />
      <div class="team-name">Dr. Bharat Singh Rawat</div>
      <div class="team-role">Director / CEO / Founder</div>
      <div class="team-country">&#127470;&#127475; India</div>
    </div>
    <div class="team-card">
      <img class="team-photo" src="Rajat.jpeg" alt="Dr. Rajat Rathod" data-name="Dr. Rajat Rathod" data-role="Researcher | Entrepreneur | Nuclear Engineer | Robotics Innovator" data-description="Dr. Rajat Rathod is a technology entrepreneur, researcher, and Ph.D. scholar specializing in robotics, nuclear engineering, artificial intelligence, and autonomous systems. With leadership experience across nuclear technology, mobility solutions, and advanced engineering ventures, he has pioneered autonomous robotic systems for reactor maintenance, nuclear microreactors, AI-powered industrial automation, and technology commercialization. His published research focuses on nuclear robotics, machine learning, autonomous vision systems, and advanced reactor technologies. Driven by sustainable innovation, he works at the convergence of deep-tech research, industrial automation, and next-generation energy systems." data-link="https://www.linkedin.com/in/irajatrathod/" />
      <div class="team-name">Dr. Rajat Rathod</div>
      <div class="team-role">Researcher | Entrepreneur | Nuclear Engineer | Robotics Innovator</div>
      <div class="team-country">&#127470;&#127475; India</div>
    </div>
    <div class="team-card">
      <div class="avatar">AR</div>
      <div class="team-name">Dr. Amara Reyes</div>
      <div class="team-role">Director General</div>
      <div class="team-country">&#127474;&#127466; Mexico</div>
    </div>
    <div class="team-card">
      <div class="avatar">SK</div>
      <div class="team-name">Prof. Sven Karlsson</div>
      <div class="team-role">Head of Research</div>
      <div class="team-country">&#127480;&#127466; Sweden</div>
    </div>
    <div class="team-card">
      <div class="avatar">FN</div>
      <div class="team-name">Dr. Fatima Nasser</div>
      <div class="team-role">Radiation Safety Lead</div>
      <div class="team-country">&#127462;&#127466; UAE</div>
    </div>
    <div class="team-card">
      <div class="avatar">RM</div>
      <div class="team-name">Dr. Ravi Mehta</div>
      <div class="team-role">Education Director</div>
      <div class="team-country">&#127470;&#127475; India</div>
    </div>
    <div class="team-card">
      <div class="avatar">LB</div>
      <div class="team-name">Dr. Léa Bernard</div>
      <div class="team-role">Policy &amp; Advocacy</div>
      <div class="team-country">&#127467;&#127479; France</div>
    </div>
    <div class="team-card">
      <div class="avatar">JO</div>
      <div class="team-name">Prof. James Okafor</div>
      <div class="team-role">Neutron Science Chair</div>
      <div class="team-country">&#127475;&#127468; Nigeria</div>
    </div>
  </div>
</section>

<div class="modal-overlay" id="profileModal" aria-hidden="true">
  <div class="modal-content" role="dialog" aria-modal="true" aria-labelledby="modalName">
    <button class="modal-close" id="modalClose" aria-label="Close profile details">×</button>
    <img id="modalImage" src="" alt="" />
    <div class="modal-text">
      <h3 id="modalName"></h3>
      <p id="modalRole"></p>
      <p id="modalDescription"></p>
      <a id="modalLink" class="modal-link" href="#" target="_blank" rel="noopener" hidden>View LinkedIn profile</a>
    </div>
  </div>
</div>

<!-- CONTACT -->
<section class="contact" id="contact">
  <div class="contact-inner">
    <div class="contact-info">
      <span class="section-tag">Get in touch</span>
      <h2>Contact IREN</h2>
      <p>Whether you're an expert looking to join our network, an institution seeking partnership, or a researcher interested in collaboration — we'd love to hear from you.</p>
      <div class="contact-detail">&#128205; &nbsp;Vienna International Centre, Vienna, Austria</div>
      <div class="contact-detail">&#128231; &nbsp;info@iren-network.org</div>
      <div class="contact-detail">&#128222; &nbsp;+43 1 2600 00000</div>
      <div class="contact-detail">&#127760; &nbsp;www.iren-network.org</div>
    </div>
    <div class="contact-form">
      <div style="color:var(--text-dark);font-size:16px;font-weight:500;margin-bottom:1.2rem">Send us a message</div>
      <div class="form-row">
        <div class="form-group">
          <label>First name</label>
          <input type="text" placeholder="Dr. Jane"/>
        </div>
        <div class="form-group">
          <label>Last name</label>
          <input type="text" placeholder="Smith"/>
        </div>
      </div>
      <div class="form-group">
        <label>Email address</label>
        <input type="email" placeholder="jane@university.edu"/>
      </div>
      <div class="form-group">
        <label>Institution / Organization</label>
        <input type="text" placeholder="MIT Radiation Lab"/>
      </div>
      <div class="form-group">
        <label>Area of interest</label>
        <select>
          <option>Membership inquiry</option>
          <option>Research collaboration</option>
          <option>Education &amp; training</option>
          <option>Partnership</option>
          <option>General inquiry</option>
        </select>
      </div>
      <div class="form-group">
        <label>Message</label>
        <textarea placeholder="Tell us about your work and how IREN can support you..."></textarea>
      </div>
      <button class="submit-btn">Send Message</button>
    </div>
  </div>
</section>

<!-- CTA -->
<div class="cta">
  <div>
    <h2>Ready to join the network?</h2>
    <p>Connect with 4,200+ radiation science experts across 82 countries.</p>
  </div>
  <div class="cta-btns">
    <button class="btn-pri">Apply for membership</button>
    <button class="btn-sec">Download brochure</button>
  </div>
</div>

<!-- FOOTER -->
<footer>
  <div class="footer-top">
    <div class="footer-brand">
      <div class="wordmark">IREN</div>
      <div class="tagline">Uniting Expertise. Advancing Science.</div>
      <div style="color:var(--green-light);font-size:11px;margin-top:8px;max-width:220px;line-height:1.6">International Radiation Experts Network — connecting radiation science globally since 2010.</div>
    </div>
    <div class="footer-links">
      <h4>ORGANIZATION</h4>
      <a href="#">About IREN</a>
      <a href="#">Leadership</a>
      <a href="#">Membership</a>
      <a href="#">Annual Reports</a>
    </div>
    <div class="footer-links">
      <h4>SCIENCE</h4>
      <a href="#">Research Areas</a>
      <a href="#">Publications</a>
      <a href="#">Conferences</a>
      <a href="#">Standards</a>
    </div>
    <div class="footer-links">
      <h4>RESOURCES</h4>
      <a href="#">News</a>
      <a href="#">Training</a>
      <a href="#">Safety Guidelines</a>
      <a href="#">Contact</a>
    </div>
  </div>
  <div class="footer-bottom">
    <span>© 2026 IREN — International Radiation Experts Network</span>
    <span>Privacy Policy &nbsp;|&nbsp; Terms of Use</span>
  </div>
</footer>

<script>
  const modal = document.getElementById('profileModal');
  const modalImage = document.getElementById('modalImage');
  const modalName = document.getElementById('modalName');
  const modalRole = document.getElementById('modalRole');
  const modalDescription = document.getElementById('modalDescription');
  const modalLink = document.getElementById('modalLink');
  const modalClose = document.getElementById('modalClose');

  document.querySelectorAll('.team-photo[data-name]').forEach(photo => {
    photo.addEventListener('click', () => {
      modalImage.src = photo.src;
      modalImage.alt = photo.alt;
      modalName.textContent = photo.dataset.name;
      modalRole.textContent = photo.dataset.role;
      modalDescription.textContent = photo.dataset.description;

      if (photo.dataset.link) {
        modalLink.href = photo.dataset.link;
        modalLink.hidden = false;
      } else {
        modalLink.hidden = true;
      }

      modal.classList.add('active');
      modal.setAttribute('aria-hidden', 'false');
    });
  });

  const closeModal = () => {
    modal.classList.remove('active');
    modal.setAttribute('aria-hidden', 'true');
  };

  modalClose.addEventListener('click', closeModal);
  modal.addEventListener('click', event => {
    if (event.target === modal) closeModal();
  });
  document.addEventListener('keydown', event => {
    if (event.key === 'Escape' && modal.classList.contains('active')) {
      closeModal();
    }
  });
</script>

</body>
</html>
