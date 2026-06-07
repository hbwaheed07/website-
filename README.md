<DOCTYPE Hb6>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>HBWAHEED Electrical ICT Solution</title>
<link href="https://fonts.googleapis.com/css2?family=Barlow+Condensed:wght@400;600;700;800;900&family=Barlow:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
  :root {
    --sky: #c8e6f5;
    --navy: #0d1b2a;
    --navy2: #122436;
    --orange: #f4820a;
    --orange2: #e06c00;
    --white: #ffffff;
    --light: #e8f4fc;
    --mid: #5a8baa;
    --text: #1a2e3f;
  }

  * { margin:0; padding:0; box-sizing:border-box; }

  html { scroll-behavior: smooth; }

  body {
    font-family: 'Barlow', sans-serif;
    background: var(--sky);
    color: var(--text);
    overflow-x: hidden;
  }

  /* ── NAV ── */
  nav {
    position: fixed;
    top: 0; left: 0; right: 0;
    background: var(--navy);
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 0 2.5rem;
    height: 70px;
    z-index: 1000;
    border-bottom: 3px solid var(--orange);
  }

  .nav-logo {
    display: flex;
    align-items: center;
    gap: 0.8rem;
    text-decoration: none;
  }

  .nav-logo img {
    height: 46px;
    width: 46px;
    border-radius: 50%;
    object-fit: cover;
    border: 2px solid var(--orange);
  }

  .nav-brand {
    font-family: 'Barlow Condensed', sans-serif;
    font-weight: 800;
    font-size: 1.2rem;
    color: var(--white);
    letter-spacing: 0.05em;
    line-height: 1.1;
  }

  .nav-brand span {
    display: block;
    font-weight: 400;
    font-size: 0.7rem;
    color: var(--orange);
    letter-spacing: 0.15em;
    text-transform: uppercase;
  }

  .nav-links {
    display: flex;
    gap: 0.2rem;
    list-style: none;
  }

  .nav-links a {
    color: #b0c8d8;
    text-decoration: none;
    font-size: 0.82rem;
    font-weight: 600;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    padding: 0.4rem 0.9rem;
    border-radius: 4px;
    transition: all 0.2s;
  }

  .nav-links a:hover { color: var(--white); background: rgba(244,130,10,0.15); }

  .nav-cta {
    background: var(--orange) !important;
    color: var(--white) !important;
    border-radius: 4px;
    padding: 0.45rem 1.1rem !important;
  }

  .nav-cta:hover { background: var(--orange2) !important; }

  /* hamburger */
  .hamburger { display: none; flex-direction: column; gap: 5px; cursor: pointer; }
  .hamburger span { width: 26px; height: 2px; background: var(--white); }

  /* ── HERO ── */
  #home {
    min-height: 100vh;
    background: linear-gradient(135deg, var(--navy) 0%, #1a3a54 50%, #0d2540 100%);
    display: flex;
    align-items: center;
    padding-top: 70px;
    position: relative;
    overflow: hidden;
  }

  #home::before {
    content: '';
    position: absolute;
    inset: 0;
    background: radial-gradient(circle at 70% 50%, rgba(244,130,10,0.08) 0%, transparent 60%),
                radial-gradient(circle at 20% 80%, rgba(200,230,245,0.05) 0%, transparent 50%);
  }

  .hero-inner {
    max-width: 1200px;
    margin: 0 auto;
    padding: 4rem 2.5rem;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 4rem;
    align-items: center;
    position: relative;
    z-index: 1;
  }

  .hero-text .badge {
    display: inline-block;
    background: rgba(244,130,10,0.2);
    border: 1px solid var(--orange);
    color: var(--orange);
    font-size: 0.72rem;
    font-weight: 700;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    padding: 0.3rem 0.9rem;
    border-radius: 2px;
    margin-bottom: 1.2rem;
  }

  .hero-text h1 {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: clamp(2.8rem, 5vw, 4.2rem);
    font-weight: 900;
    color: var(--white);
    line-height: 1.05;
    margin-bottom: 1.2rem;
    text-transform: uppercase;
  }

  .hero-text h1 em {
    font-style: normal;
    color: var(--orange);
  }

  .hero-text p {
    color: #8bb0c8;
    font-size: 1.05rem;
    line-height: 1.7;
    max-width: 460px;
    margin-bottom: 2rem;
  }

  .hero-btns {
    display: flex;
    gap: 1rem;
    flex-wrap: wrap;
  }

  .btn-primary {
    background: var(--orange);
    color: var(--white);
    padding: 0.85rem 2rem;
    border-radius: 4px;
    text-decoration: none;
    font-weight: 700;
    font-size: 0.9rem;
    letter-spacing: 0.05em;
    text-transform: uppercase;
    transition: all 0.2s;
    display: inline-block;
  }

  .btn-primary:hover { background: var(--orange2); transform: translateY(-2px); }

  .btn-outline {
    border: 2px solid rgba(200,230,245,0.4);
    color: #c8e6f5;
    padding: 0.85rem 2rem;
    border-radius: 4px;
    text-decoration: none;
    font-weight: 600;
    font-size: 0.9rem;
    letter-spacing: 0.05em;
    text-transform: uppercase;
    transition: all 0.2s;
    display: inline-block;
  }

  .btn-outline:hover { border-color: var(--orange); color: var(--orange); }

  .hero-stats {
    display: flex;
    gap: 2rem;
    margin-top: 2.5rem;
    padding-top: 2rem;
    border-top: 1px solid rgba(200,230,245,0.15);
  }

  .stat { text-align: left; }
  .stat-num {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 2rem;
    font-weight: 900;
    color: var(--orange);
    line-height: 1;
  }
  .stat-lbl { font-size: 0.72rem; color: #7aA0b8; letter-spacing: 0.05em; margin-top: 0.2rem; }

  /* Hero visual */
  .hero-visual {
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .logo-showcase {
    position: relative;
    width: 340px;
    height: 340px;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .logo-ring {
    position: absolute;
    inset: 0;
    border-radius: 50%;
    border: 2px solid rgba(244,130,10,0.25);
    animation: spin 20s linear infinite;
  }

  .logo-ring::after {
    content: '';
    position: absolute;
    top: -4px; left: 50%;
    width: 8px; height: 8px;
    background: var(--orange);
    border-radius: 50%;
    transform: translateX(-50%);
  }

  .logo-ring2 {
    position: absolute;
    inset: 20px;
    border-radius: 50%;
    border: 1px solid rgba(200,230,245,0.15);
    animation: spin 30s linear infinite reverse;
  }

  @keyframes spin { to { transform: rotate(360deg); } }

  .logo-img-wrap {
    width: 220px;
    height: 220px;
    border-radius: 50%;
    overflow: hidden;
    border: 4px solid var(--orange);
    box-shadow: 0 0 60px rgba(244,130,10,0.3), 0 0 120px rgba(244,130,10,0.1);
    position: relative;
    z-index: 2;
  }

  .logo-img-wrap img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

  /* ── TICKER ── */
  .ticker {
    background: var(--orange);
    padding: 0.75rem 0;
    overflow: hidden;
    white-space: nowrap;
  }

  .ticker-inner {
    display: inline-flex;
    animation: ticker 25s linear infinite;
  }

  .ticker-inner span {
    padding: 0 2rem;
    font-family: 'Barlow Condensed', sans-serif;
    font-weight: 700;
    font-size: 0.85rem;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--white);
  }

  .ticker-inner span::before {
    content: '✦';
    margin-right: 2rem;
    opacity: 0.6;
  }

  @keyframes ticker { 0% { transform: translateX(0); } 100% { transform: translateX(-50%); } }

  /* ── SECTIONS ── */
  section { padding: 6rem 2.5rem; }

  .section-inner { max-width: 1200px; margin: 0 auto; }

  .section-label {
    font-family: 'Barlow Condensed', sans-serif;
    font-weight: 700;
    font-size: 0.75rem;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--orange);
    margin-bottom: 0.6rem;
  }

  .section-title {
    font-family: 'Barlow Condensed', sans-serif;
    font-weight: 900;
    font-size: clamp(2rem, 4vw, 3rem);
    text-transform: uppercase;
    color: var(--navy);
    line-height: 1.1;
    margin-bottom: 1rem;
  }

  .section-title em {
    font-style: normal;
    color: var(--orange);
  }

  /* ── SERVICES ── */
  #services { background: var(--sky); }

  .services-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 1.5rem;
    margin-top: 3rem;
  }

  .service-card {
    background: var(--white);
    border-radius: 8px;
    padding: 2rem;
    border-top: 4px solid var(--orange);
    transition: transform 0.25s, box-shadow 0.25s;
    position: relative;
    overflow: hidden;
  }

  .service-card::before {
    content: '';
    position: absolute;
    inset: 0;
    background: linear-gradient(135deg, rgba(13,27,42,0.03) 0%, transparent 60%);
  }

  .service-card:hover { transform: translateY(-6px); box-shadow: 0 20px 50px rgba(13,27,42,0.12); }

  .svc-icon { font-size: 2rem; margin-bottom: 1rem; }

  .svc-num {
    position: absolute;
    top: 1.2rem; right: 1.5rem;
    font-family: 'Barlow Condensed', sans-serif;
    font-weight: 900;
    font-size: 3.5rem;
    color: var(--sky);
    line-height: 1;
    z-index: 0;
  }

  .svc-title {
    font-family: 'Barlow Condensed', sans-serif;
    font-weight: 800;
    font-size: 1.25rem;
    text-transform: uppercase;
    color: var(--navy);
    margin-bottom: 0.7rem;
    position: relative;
    z-index: 1;
  }

  .svc-text { font-size: 0.88rem; color: #4a6a80; line-height: 1.65; position: relative; z-index: 1; }

  .svc-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 0.4rem;
    margin-top: 1rem;
    position: relative;
    z-index: 1;
  }

  .svc-tags span {
    background: var(--sky);
    color: var(--navy);
    font-size: 0.7rem;
    font-weight: 600;
    padding: 0.2rem 0.6rem;
    border-radius: 2px;
    letter-spacing: 0.04em;
  }

  /* ── ABOUT ── */
  #about { background: var(--navy); }

  #about .section-title { color: var(--white); }

  .about-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 4rem;
    align-items: center;
    margin-top: 3rem;
  }

  .about-logo {
    display: flex;
    justify-content: center;
  }

  .about-logo-wrap {
    width: 260px;
    height: 260px;
    border-radius: 50%;
    overflow: hidden;
    border: 5px solid var(--orange);
    box-shadow: 0 0 80px rgba(244,130,10,0.25);
  }

  .about-logo-wrap img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

  .about-text p {
    color: #8bb0c8;
    line-height: 1.75;
    font-size: 0.95rem;
    margin-bottom: 1rem;
  }

  .about-pillars {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 1rem;
    margin-top: 2rem;
  }

  .pillar {
    background: rgba(200,230,245,0.06);
    border: 1px solid rgba(200,230,245,0.12);
    border-radius: 6px;
    padding: 1.2rem;
    text-align: center;
  }

  .pillar-icon { font-size: 1.6rem; margin-bottom: 0.5rem; }

  .pillar-name {
    font-family: 'Barlow Condensed', sans-serif;
    font-weight: 800;
    font-size: 1rem;
    text-transform: uppercase;
    color: var(--orange);
    margin-bottom: 0.3rem;
  }

  .pillar-text { font-size: 0.78rem; color: #7090a8; line-height: 1.5; }

  /* ── GALLERY ── */
  #gallery { background: var(--light); }

  .filter-bar {
    display: flex;
    gap: 0.6rem;
    flex-wrap: wrap;
    margin: 2.5rem 0;
  }

  .filter-btn {
    background: var(--white);
    border: 2px solid transparent;
    color: var(--navy);
    font-family: 'Barlow Condensed', sans-serif;
    font-weight: 700;
    font-size: 0.8rem;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    padding: 0.45rem 1.1rem;
    border-radius: 4px;
    cursor: pointer;
    transition: all 0.2s;
  }

  .filter-btn:hover, .filter-btn.active {
    background: var(--navy);
    color: var(--white);
    border-color: var(--orange);
  }

  .gallery-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    gap: 1.5rem;
  }

  .gallery-card {
    background: var(--white);
    border-radius: 8px;
    overflow: hidden;
    transition: transform 0.25s, box-shadow 0.25s;
    border-bottom: 4px solid var(--orange);
    display: block;
  }

  .gallery-card:hover { transform: translateY(-5px); box-shadow: 0 18px 45px rgba(13,27,42,0.14); }

  .gallery-card[data-hidden="true"] { display: none; }

  .gallery-thumb {
    width: 100%;
    height: 210px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 3rem;
    position: relative;
    overflow: hidden;
  }

  .gallery-thumb.cctv    { background: linear-gradient(135deg, #1a3a54 0%, #0d2030 100%); }
  .gallery-thumb.net     { background: linear-gradient(135deg, #1a2a44 0%, #0e1a30 100%); }
  .gallery-thumb.solar   { background: linear-gradient(135deg, #2a3010 0%, #1a2008 100%); }
  .gallery-thumb.fire    { background: linear-gradient(135deg, #3a1010 0%, #260808 100%); }
  .gallery-thumb.intercom{ background: linear-gradient(135deg, #1a1a3a 0%, #0e0e26 100%); }
  .gallery-thumb.elec    { background: linear-gradient(135deg, #2a2010 0%, #1a1408 100%); }

  .gallery-thumb .ph-label {
    position: absolute;
    bottom: 0.8rem;
    left: 0;
    right: 0;
    text-align: center;
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 0.7rem;
    font-weight: 700;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: rgba(200,230,245,0.5);
    padding: 0 1rem;
  }

  .gallery-info {
    padding: 1.2rem 1.4rem;
  }

  .gallery-cat {
    font-family: 'Barlow Condensed', sans-serif;
    font-weight: 700;
    font-size: 0.68rem;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--orange);
    margin-bottom: 0.3rem;
  }

  .gallery-title {
    font-family: 'Barlow Condensed', sans-serif;
    font-weight: 800;
    font-size: 1.1rem;
    text-transform: uppercase;
    color: var(--navy);
    margin-bottom: 0.3rem;
  }

  .gallery-meta { font-size: 0.78rem; color: #7090a8; }

  .gallery-upload-notice {
    background: rgba(13,27,42,0.06);
    border: 2px dashed rgba(13,27,42,0.2);
    border-radius: 8px;
    padding: 2rem;
    text-align: center;
    margin-top: 2rem;
  }

  .gallery-upload-notice p {
    color: var(--mid);
    font-size: 0.88rem;
    line-height: 1.6;
  }

  .gallery-upload-notice strong { color: var(--navy); }

  /* ── HOW WE WORK ── */
  #process { background: var(--navy); }
  #process .section-title { color: var(--white); }

  .process-steps {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
    gap: 1.5rem;
    margin-top: 3rem;
  }

  .step {
    position: relative;
    padding: 2rem;
    background: rgba(200,230,245,0.05);
    border: 1px solid rgba(200,230,245,0.1);
    border-radius: 8px;
    text-align: center;
  }

  .step-num {
    font-family: 'Barlow Condensed', sans-serif;
    font-weight: 900;
    font-size: 4rem;
    color: rgba(244,130,10,0.15);
    line-height: 1;
    position: absolute;
    top: 1rem;
    right: 1.2rem;
  }

  .step-icon { font-size: 2rem; margin-bottom: 0.8rem; }

  .step-title {
    font-family: 'Barlow Condensed', sans-serif;
    font-weight: 800;
    font-size: 1.1rem;
    text-transform: uppercase;
    color: var(--white);
    margin-bottom: 0.6rem;
  }

  .step-text { font-size: 0.85rem; color: #7090a8; line-height: 1.6; }

  /* ── CONTACT ── */
  #contact { background: var(--sky); }

  .contact-grid {
    display: grid;
    grid-template-columns: 1fr 1.4fr;
    gap: 3rem;
    margin-top: 3rem;
  }

  .contact-info { }

  .contact-info p { color: #4a6a80; line-height: 1.7; margin-bottom: 2rem; font-size: 0.95rem; }

  .contact-item {
    display: flex;
    align-items: flex-start;
    gap: 1rem;
    margin-bottom: 1.5rem;
  }

  .ci-icon {
    width: 44px;
    height: 44px;
    background: var(--navy);
    border-radius: 6px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 1.2rem;
    flex-shrink: 0;
  }

  .ci-label { font-size: 0.72rem; font-weight: 700; letter-spacing: 0.1em; text-transform: uppercase; color: var(--mid); }
  .ci-val { font-size: 1rem; font-weight: 600; color: var(--navy); margin-top: 0.2rem; }
  .ci-val a { color: var(--navy); text-decoration: none; }
  .ci-val a:hover { color: var(--orange); }

  .contact-form {
    background: var(--white);
    border-radius: 10px;
    padding: 2.5rem;
    border-top: 5px solid var(--orange);
    box-shadow: 0 10px 40px rgba(13,27,42,0.08);
  }

  .form-title {
    font-family: 'Barlow Condensed', sans-serif;
    font-weight: 800;
    font-size: 1.4rem;
    text-transform: uppercase;
    color: var(--navy);
    margin-bottom: 1.5rem;
  }

  .form-group { margin-bottom: 1.2rem; }

  .form-group label {
    display: block;
    font-size: 0.78rem;
    font-weight: 700;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    color: var(--navy);
    margin-bottom: 0.4rem;
  }

  .form-group input,
  .form-group select,
  .form-group textarea {
    width: 100%;
    padding: 0.75rem 1rem;
    border: 1.5px solid #d0e4f0;
    border-radius: 5px;
    font-family: 'Barlow', sans-serif;
    font-size: 0.9rem;
    color: var(--navy);
    background: #f8fbfe;
    transition: border-color 0.2s;
    outline: none;
  }

  .form-group input:focus,
  .form-group select:focus,
  .form-group textarea:focus {
    border-color: var(--orange);
    background: var(--white);
  }

  .form-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; }

  .submit-btn {
    width: 100%;
    padding: 0.9rem;
    background: var(--orange);
    color: var(--white);
    border: none;
    border-radius: 5px;
    font-family: 'Barlow Condensed', sans-serif;
    font-weight: 800;
    font-size: 1rem;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    cursor: pointer;
    margin-top: 0.5rem;
    transition: background 0.2s;
  }

  .submit-btn:hover { background: var(--orange2); }

  .success-msg {
    display: none;
    background: #e8f8ee;
    border: 1.5px solid #4caf50;
    border-radius: 6px;
    padding: 1.2rem;
    text-align: center;
    color: #2e7d32;
    margin-top: 1rem;
  }

  /* ── FOOTER ── */
  footer {
    background: var(--navy);
    border-top: 3px solid var(--orange);
    padding: 3rem 2.5rem 1.5rem;
  }

  .footer-inner {
    max-width: 1200px;
    margin: 0 auto;
  }

  .footer-top {
    display: grid;
    grid-template-columns: 1.5fr 1fr 1fr;
    gap: 3rem;
    padding-bottom: 2rem;
    border-bottom: 1px solid rgba(200,230,245,0.1);
    margin-bottom: 1.5rem;
  }

  .footer-brand {
    display: flex;
    align-items: center;
    gap: 0.8rem;
    margin-bottom: 1rem;
  }

  .footer-brand img {
    height: 48px;
    width: 48px;
    border-radius: 50%;
    object-fit: cover;
    border: 2px solid var(--orange);
  }

  .footer-brand-name {
    font-family: 'Barlow Condensed', sans-serif;
    font-weight: 800;
    color: var(--white);
    font-size: 1.1rem;
    line-height: 1.15;
  }

  .footer-brand-name span {
    display: block;
    font-size: 0.65rem;
    font-weight: 400;
    color: var(--orange);
    letter-spacing: 0.15em;
    text-transform: uppercase;
  }

  .footer-tagline { color: #6888a0; font-size: 0.85rem; line-height: 1.65; }

  .footer-col-title {
    font-family: 'Barlow Condensed', sans-serif;
    font-weight: 800;
    font-size: 0.85rem;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--orange);
    margin-bottom: 1rem;
  }

  .footer-links { list-style: none; }
  .footer-links li { margin-bottom: 0.5rem; }
  .footer-links a { color: #7090a8; font-size: 0.85rem; text-decoration: none; transition: color 0.2s; }
  .footer-links a:hover { color: var(--white); }

  .footer-contact { font-size: 0.85rem; color: #7090a8; line-height: 1.8; }
  .footer-contact a { color: #7090a8; text-decoration: none; }
  .footer-contact a:hover { color: var(--orange); }

  .footer-bottom {
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    gap: 0.5rem;
  }

  .footer-copy { font-size: 0.78rem; color: #4a6a80; }

  /* ── CTA BAND ── */
  .cta-band {
    background: var(--orange);
    padding: 3rem 2.5rem;
    text-align: center;
  }

  .cta-band h2 {
    font-family: 'Barlow Condensed', sans-ser
