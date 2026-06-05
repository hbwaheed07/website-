<HBWAHEED>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>HBWAHEED – Electrical ICT Solutions</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=DM+Sans:wght@300;400;500;600&family=Syne+Mono&display=swap" rel="stylesheet">
<style>
/* ═══════════════════════════════════════════
   RESET & TOKENS
═══════════════════════════════════════════ */
*, *::before, *::after { margin:0; padding:0; box-sizing:border-box; }
:root {
  --orange:  #FF5C00;
  --yellow:  #FFD000;
  --blue:    #0057FF;
  --cyan:    #00CFFF;
  --navy:    #06090F;
  --navy2:   #0C1220;
  --navy3:   #121B2E;
  --white:   #FAFCFF;
  --muted:   #8899BB;
  --border:  rgba(255,255,255,0.08);

  --heading: 'Syne', sans-serif;
  --body:    'DM Sans', sans-serif;
  --mono:    'Syne Mono', monospace;
}
html { scroll-behavior: smooth; }
body {
  font-family: var(--body);
  background: var(--navy);
  color: var(--white);
  overflow-x: hidden;
  cursor: default;
}
a { color: inherit; text-decoration: none; }
img { display: block; max-width: 100%; }
button { cursor: pointer; border: none; background: none; font-family: inherit; }

/* ═══════════════════════════════════════════
   SCROLLBAR
═══════════════════════════════════════════ */
::-webkit-scrollbar { width:6px; }
::-webkit-scrollbar-track { background: var(--navy2); }
::-webkit-scrollbar-thumb { background: var(--orange); border-radius:3px; }

/* ═══════════════════════════════════════════
   PAGES SYSTEM
═══════════════════════════════════════════ */
.page { display:none; min-height:100vh; }
.page.active { display:block; }

/* ═══════════════════════════════════════════
   NOISE OVERLAY
═══════════════════════════════════════════ */
body::after {
  content:''; position:fixed; inset:0;
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.03'/%3E%3C/svg%3E");
  pointer-events:none; z-index:9000; opacity:0.4;
}

/* ═══════════════════════════════════════════
   NAVBAR
═══════════════════════════════════════════ */
.nav {
  position: fixed; top:0; left:0; right:0; z-index:8000;
  background: rgba(6,9,15,0.92);
  backdrop-filter: blur(20px);
  border-bottom: 1px solid var(--border);
  display: flex; align-items: center; justify-content: space-between;
  padding: 0 40px; height: 72px;
}
.nav-logo {
  font-family: var(--heading);
  font-size: 22px; font-weight: 800;
  letter-spacing: -0.5px;
}
.nav-logo span { color: var(--orange); }
.nav-logo em {
  font-style: normal;
  font-size: 11px; font-weight: 400;
  color: var(--muted); letter-spacing: 2px;
  display: block; margin-top: -4px;
}
.nav-links {
  display: flex; align-items: center; gap: 4px;
  list-style: none;
}
.nav-links li button {
  font-family: var(--body);
  font-size: 14px; font-weight: 500;
  color: var(--muted);
  padding: 8px 16px; border-radius: 6px;
  transition: color .2s, background .2s;
  letter-spacing: 0.2px;
}
.nav-links li button:hover { color: var(--white); background: rgba(255,255,255,0.06); }
.nav-links li button.active { color: var(--orange); background: rgba(255,92,0,0.1); }
.nav-cta {
  background: var(--orange);
  color: #fff !important;
  padding: 10px 22px !important;
  border-radius: 6px !important;
  font-weight: 600 !important;
  transition: background .2s, transform .2s !important;
}
.nav-cta:hover { background: #e04e00 !important; transform: translateY(-1px) !important; }
.nav-hamburger { display:none; flex-direction:column; gap:5px; padding:8px; }
.nav-hamburger span { display:block; width:24px; height:2px; background:var(--white); border-radius:2px; transition:.3s; }
.mobile-menu { display:none; }

/* ═══════════════════════════════════════════
   SECTIONS UTILITY
═══════════════════════════════════════════ */
.section { padding: 100px 40px; }
.section-tag {
  font-family: var(--mono);
  font-size: 12px; letter-spacing: 3px;
  color: var(--orange); text-transform: uppercase;
  display: flex; align-items: center; gap: 10px;
  margin-bottom: 14px;
}
.section-tag::before { content:''; display:inline-block; width:28px; height:2px; background:var(--orange); }
.section-title {
  font-family: var(--heading);
  font-size: clamp(38px, 5vw, 64px);
  font-weight: 800; line-height: 1.05;
  letter-spacing: -1.5px;
}
.section-title em { font-style:normal; color:var(--orange); }
.section-sub {
  font-size: 17px; color: var(--muted);
  line-height: 1.75; max-width: 560px;
  margin-top: 16px; font-weight: 400;
}
.max-w { max-width: 1200px; margin: 0 auto; }

/* ═══════════════════════════════════════════
   BUTTONS
═══════════════════════════════════════════ */
.btn {
  display: inline-flex; align-items: center; gap: 8px;
  font-family: var(--body); font-weight: 600;
  font-size: 15px; letter-spacing: 0.3px;
  padding: 14px 28px; border-radius: 8px;
  transition: all .25s; cursor: pointer;
}
.btn-orange { background: var(--orange); color: #fff; }
.btn-orange:hover { background: #e04e00; transform: translateY(-2px); box-shadow: 0 12px 30px rgba(255,92,0,0.35); }
.btn-outline { border: 1.5px solid rgba(255,255,255,0.2); color: var(--white); }
.btn-outline:hover { border-color: var(--orange); color: var(--orange); background: rgba(255,92,0,0.07); }
.btn-blue { background: var(--blue); color: #fff; }
.btn-blue:hover { background: #0049dd; transform: translateY(-2px); box-shadow: 0 12px 30px rgba(0,87,255,0.35); }

/* ═══════════════════════════════════════════
   ★ PAGE: HOME
═══════════════════════════════════════════ */
.hero {
  padding-top: 72px;
  min-height: 100vh;
  display: grid;
  grid-template-columns: 1fr 1fr;
  align-items: center;
  gap: 0;
  overflow: hidden;
  position: relative;
}
.hero-left {
  padding: 80px 40px 80px 80px;
  position: relative; z-index: 2;
}
.hero-badge {
  display: inline-flex; align-items: center; gap: 8px;
  background: rgba(255,208,0,0.1);
  border: 1px solid rgba(255,208,0,0.25);
  color: var(--yellow); border-radius: 100px;
  font-size: 12px; font-weight: 600;
  letter-spacing: 1.5px; text-transform: uppercase;
  padding: 6px 16px; margin-bottom: 28px;
}
.hero-badge::before {
  content:''; width:7px; height:7px; border-radius:50%;
  background: var(--yellow);
  animation: blink 1.5s ease infinite;
}
@keyframes blink { 0%,100%{opacity:1} 50%{opacity:0.3} }
.hero-h1 {
  font-family: var(--heading);
  font-size: clamp(48px, 6vw, 86px);
  font-weight: 800; line-height: 0.95;
  letter-spacing: -2px;
}
.hero-h1 .line-orange { color: var(--orange); }
.hero-h1 .line-stroke {
  -webkit-text-stroke: 2px var(--white);
  color: transparent;
}
.hero-desc {
  font-size: 17px; color: var(--muted);
  line-height: 1.75; max-width: 440px;
  margin: 24px 0 36px; font-weight: 400;
}
.hero-desc strong { color: var(--white); font-weight: 600; }
.hero-btns { display:flex; gap:14px; flex-wrap:wrap; }
.hero-stats {
  display: flex; gap: 40px;
  margin-top: 54px; padding-top: 40px;
  border-top: 1px solid var(--border);
}
.h-stat-num {
  font-family: var(--heading);
  font-size: 36px; font-weight: 800;
  color: var(--white);
}
.h-stat-num span { color: var(--orange); }
.h-stat-label {
  font-size: 13px; color: var(--muted);
  margin-top: 2px; font-weight: 400;
}

/* Hero Right Panel */
.hero-right {
  background: linear-gradient(135deg, #0D1B35 0%, #06090F 100%);
  height: 100%;
  min-height: 100vh;
  position: relative;
  display: flex; align-items: center; justify-content: center;
  overflow: hidden;
}
.hero-right::before {
  content:'';
  position: absolute; inset: 0;
  background:
    radial-gradient(ellipse 60% 50% at 80% 20%, rgba(255,92,0,0.18) 0%, transparent 60%),
    radial-gradient(ellipse 50% 60% at 20% 80%, rgba(0,87,255,0.15) 0%, transparent 60%);
}
.hero-visual {
  position: relative; z-index: 2;
  width: 80%;
}
.hero-cam-card {
  background: rgba(255,255,255,0.04);
  border: 1px solid rgba(255,255,255,0.1);
  border-radius: 20px;
  padding: 32px;
  backdrop-filter: blur(10px);
}
.hcc-label {
  font-family: var(--mono);
  font-size: 11px; letter-spacing: 3px;
  color: var(--cyan); margin-bottom: 20px;
}
.cam-svg-wrap {
  display: flex; justify-content: center; align-items: center;
  height: 220px;
}
.cam-svg-wrap svg { filter: drop-shadow(0 20px 60px rgba(255,92,0,0.3)); }
.hcc-status-row {
  display: flex; justify-content: space-between;
  margin-top: 24px; padding-top: 20px;
  border-top: 1px solid rgba(255,255,255,0.08);
}
.hcc-status {
  font-family: var(--mono); font-size: 12px;
  color: var(--muted);
}
.hcc-status strong { color: #4ADB88; display: block; font-size: 14px; }
.hero-float-1, .hero-float-2, .hero-float-3 {
  position: absolute; z-index: 3;
  background: rgba(255,255,255,0.04);
  border: 1px solid rgba(255,255,255,0.1);
  border-radius: 12px; padding: 14px 18px;
  backdrop-filter: blur(10px);
  font-family: var(--mono); font-size: 12px;
}
.hero-float-1 { top: 18%; right: -30px; color: var(--yellow); animation: float 4s ease-in-out infinite; }
.hero-float-2 { bottom: 25%; left: -30px; color: var(--cyan); animation: float 5s ease-in-out 1s infinite; }
.hero-float-3 { top: 55%; right: -20px; color: var(--orange); animation: float 3.5s ease-in-out 0.5s infinite; }
@keyframes float { 0%,100%{transform:translateY(0)} 50%{transform:translateY(-10px)} }

/* Ticker */
.ticker-bar {
  background: var(--orange);
  overflow: hidden; white-space: nowrap;
  padding: 13px 0;
}
.ticker-track {
  display: inline-flex;
  animation: scroll 20s linear infinite;
}
.ticker-track:hover { animation-play-state: paused; }
.ticker-item {
  font-family: var(--mono); font-size: 13px;
  letter-spacing: 2px; text-transform: uppercase;
  color: #fff; padding: 0 48px;
}
.ticker-dot { opacity: 0.5; }
@keyframes scroll { from{transform:translateX(0)} to{transform:translateX(-50%)} }

/* ── Services Preview on Home ── */
.home-services {
  padding: 90px 80px;
  background: var(--navy2);
}
.services-row {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 2px; margin-top: 60px;
}
.srv-mini {
  background: var(--navy3);
  padding: 36px 30px;
  position: relative; overflow: hidden;
  transition: background .3s;
}
.srv-mini::after {
  content: '';
  position: absolute; bottom: 0; left: 0; right: 0; height: 3px;
  background: linear-gradient(90deg, var(--orange), var(--yellow));
  transform: scaleX(0); transform-origin: left;
  transition: transform .4s;
}
.srv-mini:hover { background: #141D2F; }
.srv-mini:hover::after { transform: scaleX(1); }
.srv-emoji { font-size: 32px; margin-bottom: 18px; }
.srv-name {
  font-family: var(--heading);
  font-size: 20px; font-weight: 700;
  margin-bottom: 10px; letter-spacing: -0.3px;
}
.srv-desc { font-size: 14px; color: var(--muted); line-height: 1.65; }
.srv-arrow {
  margin-top: 20px; font-size: 18px; color: var(--orange);
  opacity: 0; transform: translateX(-6px);
  transition: opacity .3s, transform .3s;
  display: inline-block;
}
.srv-mini:hover .srv-arrow { opacity:1; transform:translateX(0); }

/* CTA Strip */
.cta-strip {
  background: linear-gradient(135deg, var(--orange), #C73A00);
  padding: 70px 80px;
  display: flex; align-items: center; justify-content: space-between;
  gap: 30px; flex-wrap: wrap;
}
.cta-strip h2 {
  font-family: var(--heading);
  font-size: clamp(28px, 4vw, 48px);
  font-weight: 800; letter-spacing: -1px;
  max-width: 500px;
}
.btn-white {
  background: #fff; color: var(--orange); font-weight: 700;
  border-radius: 8px; padding: 16px 32px; font-size: 15px;
  letter-spacing: 0.3px; white-space: nowrap;
  transition: transform .2s, box-shadow .2s;
}
.btn-white:hover { transform: translateY(-2px); box-shadow: 0 12px 30px rgba(0,0,0,0.3); }

/* ═══════════════════════════════════════════
   ★ PAGE: SERVICES
═══════════════════════════════════════════ */
.services-hero {
  padding: 160px 80px 80px;
  background: linear-gradient(160deg, var(--navy2) 0%, var(--navy) 100%);
  position: relative; overflow: hidden;
}
.services-hero::before {
  content:''; position:absolute; top:-100px; right:-100px;
  width:500px; height:500px; border-radius:50%;
  background: radial-gradient(circle, rgba(255,92,0,0.12) 0%, transparent 70%);
}
.services-grid-full {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 24px; margin-top: 30px;
}
.srv-card {
  background: var(--navy2);
  border: 1px solid var(--border);
  border-radius: 16px; padding: 40px;
  position: relative; overflow: hidden;
  transition: border-color .3s, transform .3s, box-shadow .3s;
}
.srv-card:hover {
  border-color: var(--orange);
  transform: translateY(-6px);
  box-shadow: 0 24px 60px rgba(255,92,0,0.12);
}
.srv-card-num {
  font-family: var(--mono); font-size: 12px;
  color: rgba(255,92,0,0.4); letter-spacing: 2px;
  position: absolute; top: 24px; right: 24px;
}
.srv-card-icon {
  width: 56px; height: 56px; border-radius: 14px;
  display: flex; align-items: center; justify-content: center;
  font-size: 26px; margin-bottom: 22px;
}
.ic-orange { background: rgba(255,92,0,0.15); }
.ic-blue   { background: rgba(0,87,255,0.15); }
.ic-yellow { background: rgba(255,208,0,0.15); }
.ic-cyan   { background: rgba(0,207,255,0.15); }
.ic-green  { background: rgba(74,219,136,0.15); }
.ic-purple { background: rgba(161,87,255,0.15); }
.srv-card-title {
  font-family: var(--heading);
  font-size: 24px; font-weight: 700;
  letter-spacing: -0.3px; margin-bottom: 12px;
}
.srv-card-desc { font-size: 15px; color: var(--muted); line-height: 1.7; }
.srv-card-tags {
  display: flex; flex-wrap: wrap; gap: 8px; margin-top: 24px;
}
.tag {
  font-size: 12px; font-weight: 600;
  padding: 5px 12px; border-radius: 100px;
  background: rgba(255,255,255,0.06);
  color: var(--muted); letter-spacing: 0.3px;
}

/* Process section */
.process-section {
  padding: 90px 80px;
  background: var(--navy2);
}
.process-steps {
  display: grid;
  grid-template-columns: repeat(4,1fr);
  gap: 2px; margin-top: 60px;
  position: relative;
}
.process-step {
  padding: 36px 28px;
  background: var(--navy3);
  position: relative;
  border-top: 3px solid transparent;
  transition: border-color .3s;
}
.process-step:nth-child(1) { border-color: var(--orange); }
.process-step:nth-child(2) { border-color: var(--yellow); }
.process-step:nth-child(3) { border-color: var(--cyan); }
.process-step:nth-child(4) { border-color: #4ADB88; }
.step-num {
  font-family: var(--heading);
  font-size: 52px; font-weight: 800;
  color: rgba(255,255,255,0.05);
  position: absolute; top: 10px; right: 20px;
}
.step-title {
  font-family: var(--heading);
  font-size: 20px; font-weight: 700;
  margin: 14px 0 10px;
}
.step-desc { font-size: 14px; color: var(--muted); line-height: 1.65; }

/* ═══════════════════════════════════════════
   ★ PAGE: ABOUT
═══════════════════════════════════════════ */
.about-hero {
  padding: 160px 80px 100px;
  display: grid; grid-template-columns: 1fr 1fr;
  gap: 80px; align-items: center;
  background: var(--navy2);
  position: relative; overflow: hidden;
}
.about-hero::after {
  content:''; position:absolute; bottom:-200px; right:-200px;
  width:600px; height:600px; border-radius:50%;
  background: radial-gradient(circle, rgba(0,87,255,0.1) 0%, transparent 70%);
}
.about-visual {
  position: relative; z-index: 2;
}
.about-big-num {
  font-family: var(--heading);
  font-size: clamp(100px, 15vw, 180px);
  font-weight: 800; letter-spacing: -6px;
  line-height: 1; color: rgba(255,255,255,0.04);
  position: absolute; top: -20px; left: -20px;
  pointer-events:none;
}
.about-card {
  background: var(--navy3);
  border: 1px solid var(--border);
  border-radius: 20px; padding: 36px;
  position: relative; z-index: 2;
}
.about-card-title {
  font-family: var(--heading);
  font-size: 18px; font-weight: 700;
  margin-bottom: 16px;
}
.value-list { list-style: none; }
.value-list li {
  padding: 12px 0; border-bottom: 1px solid var(--border);
  display: flex; align-items: center; gap: 12px;
  font-size: 15px; color: var(--muted); font-weight: 400;
}
.value-list li:last-child { border-bottom: none; }
.value-list li::before {
  content:''; width:8px; height:8px; border-radius:2px;
  background: var(--orange); flex-shrink:0;
}

.about-text .section-title { letter-spacing: -1.5px; }
.about-text p {
  font-size: 16px; color: var(--muted);
  line-height: 1.85; margin-top: 20px;
}
.about-text p + p { margin-top: 14px; }

/* Team / Trust section */
.trust-section {
  padding: 90px 80px;
}
.trust-grid {
  display: grid; grid-template-columns: repeat(3,1fr);
  gap: 24px; margin-top: 60px;
}
.trust-card {
  padding: 36px; border-radius: 16px;
  border: 1px solid var(--border);
  background: var(--navy2);
  text-align: center;
  transition: border-color .3s, transform .3s;
}
.trust-card:hover { border-color: var(--orange); transform: translateY(-4px); }
.trust-icon {
  font-size: 36px; margin-bottom: 16px;
  display: block;
}
.trust-title {
  font-family: var(--heading);
  font-size: 20px; font-weight: 700;
  margin-bottom: 10px;
}
.trust-desc { font-size: 14px; color: var(--muted); line-height: 1.65; }

/* Credentials */
.creds-section {
  background: var(--navy2);
  padding: 70px 80px;
  display: flex; gap: 0; flex-wrap: wrap;
}
.cred-item {
  flex: 1; min-width: 200px;
  padding: 36px;
  border-right: 1px solid var(--border);
  text-align: center;
}
.cred-item:last-child { border-right: none; }
.cred-num {
  font-family: var(--heading);
  font-size: 52px; font-weight: 800;
  color: var(--orange);
}
.cred-label { font-size: 14px; color: var(--muted); margin-top: 4px; }

/* ═══════════════════════════════════════════
   ★ PAGE: GALLERY
═══════════════════════════════════════════ */
.gallery-hero {
  padding: 160px 80px 70px;
  background: var(--navy2);
}
.gallery-filters {
  display: flex; gap: 10px; flex-wrap: wrap;
  margin: 40px 0 50px;
}
.filter-btn {
  font-family: var(--body); font-size: 14px; font-weight: 600;
  padding: 10px 22px; border-radius: 100px;
  border: 1.5px solid var(--border);
  color: var(--muted); background: transparent;
  transition: all .2s; cursor: pointer;
}
.filter-btn.active, .filter-btn:hover {
  border-color: var(--orange); color: var(--orange);
  background: rgba(255,92,0,0.08);
}
.gallery-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 16px;
  padding: 0 80px 90px;
}
.gallery-item {
  border-radius: 14px; overflow: hidden;
  position: relative; aspect-ratio: 4/3;
  background: var(--navy3);
  border: 1px solid var(--border);
  cursor: pointer; transition: transform .3s, box-shadow .3s;
}
.gallery-item:hover { transform: scale(1.03); box-shadow: 0 20px 50px rgba(0,0,0,0.4); }
.gallery-item:nth-child(1) { grid-column: span 2; }
.gallery-item:nth-child(4) { grid-column: span 2; }
.gi-inner {
  width:100%; height:100%;
  display: flex; flex-direction: column;
  align-items: center; justify-content: center;
  gap: 12px; padding: 24px;
}
.gi-icon { font-size: 48px; opacity:0.6; }
.gi-overlay {
  position: absolute; inset: 0;
  background: linear-gradient(to top, rgba(6,9,15,0.9) 0%, transparent 60%);
  opacity: 0; transition: opacity .3s;
  display: flex; align-items: flex-end; padding: 20px;
}
.gallery-item:hover .gi-overlay { opacity: 1; }
.gi-label {
  font-family: var(--heading);
  font-size: 18px; font-weight: 700;
  color: var(--white);
}
.gi-sub { font-size: 13px; color: var(--muted); margin-top: 2px; }

.gi-bg-1  { background: linear-gradient(135deg, #1A0A00 0%, #2D1000 100%); }
.gi-bg-2  { background: linear-gradient(135deg, #001A30 0%, #002850 100%); }
.gi-bg-3  { background: linear-gradient(135deg, #001020 0%, #001E3A 100%); }
.gi-bg-4  { background: linear-gradient(135deg, #0A1A00 0%, #152800 100%); }
.gi-bg-5  { background: linear-gradient(135deg, #1A1200 0%, #2A1D00 100%); }
.gi-bg-6  { background: linear-gradient(135deg, #100020 0%, #1A003A 100%); }

/* ═══════════════════════════════════════════
   ★ PAGE: CONTACT
═══════════════════════════════════════════ */
.contact-page {
  padding: 140px 80px 90px;
  display: grid; grid-template-columns: 1fr 1.4fr;
  gap: 80px; align-items: start;
}
.contact-info h1 {
  font-family: var(--heading);
  font-size: clamp(38px, 5vw, 60px);
  font-weight: 800; letter-spacing: -1.5px;
  line-height: 1.05; margin-bottom: 20px;
}
.contact-info h1 em { font-style:normal; color:var(--orange); }
.contact-info p {
  font-size: 16px; color: var(--muted);
  line-height: 1.75; margin-bottom: 40px;
}
.contact-method {
  display: flex; align-items: flex-start; gap: 16px;
  margin-bottom: 24px;
}
.cm-icon {
  width: 48px; height: 48px; border-radius: 12px;
  background: rgba(255,92,0,0.1);
  border: 1px solid rgba(255,92,0,0.2);
  display: flex; align-items: center; justify-content: center;
  font-size: 20px; flex-shrink: 0;
}
.cm-label { font-size: 12px; color: var(--muted); letter-spacing: 1px; text-transform: uppercase; }
.cm-value {
  font-size: 17px; font-weight: 600;
  color: var(--white); margin-top: 3px;
}
.cm-value a { transition: color .2s; }
.cm-value a:hover { color: var(--orange); }
.contact-note {
  margin-top: 40px; padding: 20px 24px;
  background: rgba(255,208,0,0.07);
  border: 1px solid rgba(255,208,0,0.2);
  border-radius: 12px;
  font-size: 14px; color: var(--yellow);
  line-height: 1.6;
}
.contact-note strong { display: block; margin-bottom: 4px; font-size: 15px; }

/* Quote Form */
.quote-form {
  background: var(--navy2);
  border: 1px solid var(--border);
  border-radius: 24px; padding: 44px;
}
.form-title {
  font-family: var(--heading);
  font-size: 26px; font-weight: 700;
  letter-spacing: -0.5px; margin-bottom: 6px;
}
.form-subtitle { font-size: 15px; color: var(--muted); margin-bottom: 32px; }
.form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; }
.form-group { margin-bottom: 20px; }
.form-group label {
  display: block; font-size: 13px;
  font-weight: 600; color: var(--muted);
  letter-spacing: 0.5px; margin-bottom: 8px;
  text-transform: uppercase;
}
.form-group input,
.form-group select,
.form-group textarea {
  width: 100%;
  background: var(--navy3);
  border: 1.5px solid var(--border);
  border-radius: 10px;
  color: var(--white);
  font-family: var(--body); font-size: 15px;
  padding: 13px 16px;
  outline: none;
  transition: border-color .2s, box-shadow .2s;
  -webkit-appearance: none;
}
.form-group select option { background: var(--navy2); }
.form-group input:focus,
.form-group select:focus,
.form-group textarea:focus {
  border-color: var(--orange);
  box-shadow: 0 0 0 3px rgba(255,92,0,0.12);
}
.form-group textarea { resize: vertical; min-height: 110px; }
.form-submit {
  width: 100%;
  background: var(--orange); color: #fff;
  border: none; border-radius: 10px;
  padding: 16px; font-family: var(--heading);
  font-size: 17px; font-weight: 700;
  letter-spacing: 0.3px; cursor: pointer;
  transition: background .2s, transform .2s, box-shadow .2s;
  margin-top: 8px;
}
.form-submit:hover {
  background: #e04e00; transform: translateY(-2px);
  box-shadow: 0 12px 30px rgba(255,92,0,0.3);
}
.form-success {
  display: none; text-align: center;
  padding: 40px 20px;
}
.form-success .success-icon { font-size: 56px; margin-bottom: 16px; }
.form-success h3 {
  font-family: var(--heading);
  font-size: 26px; font-weight: 800;
  margin-bottom: 10px;
}
.form-success p { color: var(--muted); font-size: 15px; }

/* ═══════════════════════════════════════════
   FOOTER
═══════════════════════════════════════════ */
.footer {
  background: var(--navy2);
  border-top: 1px solid var(--border);
  padding: 60px 80px 30px;
}
.footer-top {
  display: grid; grid-template-columns: 1.5fr 1fr 1fr;
  gap: 60px; margin-bottom: 50px;
}
.footer-brand {
  font-family: var(--heading);
  font-size: 26px; font-weight: 800;
  margin-bottom: 14px;
}
.footer-brand span { color: var(--orange); }
.footer-tagline { font-size: 14px; color: var(--muted); line-height: 1.65; max-width: 280px; }
.footer-col-title {
  font-family: var(--heading);
  font-size: 14px; font-weight: 700;
  letter-spacing: 1px; text-transform: uppercase;
  color: var(--muted); margin-bottom: 18px;
}
.footer-links { list-style: none; }
.footer-links li { margin-bottom: 12px; }
.footer-links li button {
  font-size: 14px; color: var(--muted);
  transition: color .2s;
  font-family: var(--body);
  background: none; border: none; cursor: pointer; padding: 0;
}
.footer-links li button:hover { color: var(--orange); }
.footer-bottom {
  border-top: 1px solid var(--border);
  padding-top: 24px;
  display: flex; justify-content: space-between;
  align-items: center; flex-wrap: wrap; gap: 12px;
  font-size: 13px; color: var(--muted);
}
.footer-bottom a:hover { color: var(--orange); }

/* ═══════════════════════════════════════════
   RESPONSIVE
═══════════════════════════════════════════ */
@media (max-width: 960px) {
  .hero { grid-template-columns: 1fr; }
  .hero-right { display: none; }
  .hero-left { padding: 100px 24px 60px; }
  .home-services { padding: 60px 24px; }
  .services-row { grid-template-columns: 1fr; }
  .cta-strip { padding: 50px 24px; }
  .services-hero { padding: 120px 24px 60px; }
  .services-grid-full { grid-template-columns: 1fr; }
  .process-section { padding: 60px 24px; }
  .process-steps { grid-template-columns: 1fr 1fr; }
  .about-hero { grid-template-columns: 1fr; padding: 120px 24px 60px; gap: 40px; }
  .trust-section { padding: 60px 24px; }
  .trust-grid { grid-template-columns: 1fr 1fr; }
  .creds-section { padding: 50px 24px; }
  .gallery-hero { padding: 120px 24px 50px; }
  .gallery-grid { grid-template-columns: 1fr; padding: 0 24px 60px; }
  .gallery-item:nth-child(1), .gallery-item:nth-child(4) { grid-column: span 1; }
  .contact-page { grid-template-columns: 1fr; padding: 120px 24px 60px; gap: 50px; }
  .form-row { grid-template-columns: 1fr; }
  .footer { padding: 50px 24px 24px; }
  .footer-top { grid-template-columns: 1fr; gap: 36px; }
  .footer-bottom { flex-direction: column; text-align: center; }
  .nav { padding: 0 20px; }
  .nav-links { display: none; }
  .nav-hamburger { display: flex; }
  .mobile-menu {
    position: fixed; top:72px; left:0; right:0; bottom:0;
    background: rgba(6,9,15,0.97); backdrop-filter:blur(20px);
    z-index: 7999; padding: 30px 24px;
    flex-direction: column; gap: 8px;
  }
  .mobile-menu.open { display: flex; }
  .mobile-menu button {
    font-family: var(--body); font-size: 18px;
    font-weight: 600; color: var(--muted);
    padding: 16px; border-radius: 10px;
    text-align: left; width: 100%;
    transition: color .2s, background .2s;
  }
  .mobile-menu button:hover, .mobile-menu button.active {
    color: var(--orange); background: rgba(255,92,0,0.08);
  }
  .section { padding: 70px 24px; }
}

/* ═══════════════════════════════════════════
   ANIMATIONS
═══════════════════════════════════════════ */
.fade-in {
  opacity: 0; transform: translateY(24px);
  transition: opacity .6s ease, transform .6s ease;
}
.fade-in.visible { opacity:1; transform:translateY(0); }
</style>
</head>
<body>

<!-- ═══════════ NAVBAR ═══════════ -->
<nav class="nav">
  <div class="nav-logo">
    HB<span>WAHEED</span>
    <em>ELECTRICAL ICT SOLUTION</em>
  </div>
  <ul class="nav-links">
    <li><button onclick="goto('home')" id="nb-home" class="active">Home</button></li>
    <li><button onclick="goto('services')" id="nb-services">Services</button></li>
    <li><button onclick="goto('about')" id="nb-about">About Us</button></li>
    <li><button onclick="goto('gallery')" id="nb-gallery">Gallery</button></li>
    <li><button onclick="goto('contact')" id="nb-contact" class="nav-cta">Get a Quote</button></li>
  </ul>
  <button class="nav-hamburger" onclick="toggleMobile()" id="hamburger" aria-label="Menu">
    <span></span><span></span><span></span>
  </button>
</nav>

<!-- Mobile Menu -->
<div class="mobile-menu" id="mobileMenu">
  <button onclick="goto('home');toggleMobile()" id="mb-home" class="active">Home</button>
  <button onclick="goto('services');toggleMobile()" id="mb-services">Services</button>
  <button onclick="goto('about');toggleMobile()" id="mb-about">About Us</button>
  <button onclick="goto('gallery');toggleMobile()" id="mb-gallery">Gallery</button>
  <button onclick="goto('contact');toggleMobile()" id="mb-contact">Get a Quote</button>
</div>

<!-- ═══════════════════════════════════════════
     PAGE: HOME
═══════════════════════════════════════════ -->
<div class="page active" id="page-home">

  <!-- Ticker -->
  <div class="ticker-bar">
    <div class="ticker-track">
      <span class="ticker-item">CCTV Surveillance</span><span class="ticker-dot">✦</span>
      <span class="ticker-item">Network Infrastructure</span><span class="ticker-dot">✦</span>
      <span class="ticker-item">Solar Installations</span><span class="ticker-dot">✦</span>
      <span class="ticker-item">Fire Alarm Systems</span><span class="ticker-dot">✦</span>
      <span class="ticker-item">Intercom Solutions</span><span class="ticker-dot">✦</span>
      <span class="ticker-item">Electrical Works</span><span class="ticker-dot">✦</span>
      <span class="ticker-item">CCTV Surveillance</span><span class="ticker-dot">✦</span>
      <span class="ticker-item">Network Infrastructure</span><span class="ticker-dot">✦</span>
      <span class="ticker-item">Solar Installations</span><span class="ticker-dot">✦</span>
      <span class="ticker-item">Fire Alarm Systems</span><span class="ticker-dot">✦</span>
      <span class="ticker-item">Intercom Solutions</span><span class="ticker-dot">✦</span>
      <span class="ticker-item">Electrical Works</span><span class="ticker-dot">✦</span>
    </div>
  </div>

  <!-- Hero -->
  <section class="hero">
    <div class="hero-left fade-in">
      <div class="hero-badge">Available Now — Free Consultation</div>
      <h1 class="hero-h1">
        <span>ELECTRICAL</span>
        <span class="line-orange">ICT</span>
        <span class="line-stroke">SOLUTIONS</span>
      </h1>
      <p class="hero-desc">
        <strong>HBWAHEED</strong> specializes in professional installation of CCTV systems, networking equipment, solar panels, fire alarms, and intercom systems — for homes and businesses across Nigeria.
      </p>
      <div class="hero-btns">
        <button class="btn btn-orange" onclick="goto('contact')">Get a Free Quote →</button>
        <button class="btn btn-outline" onclick="goto('services')">Our Services</button>
      </div>
      <div class="hero-stats">
        <div>
          <div class="h-stat-num">500<span>+</span></div>
          <div class="h-stat-label">Installations Done</div>
        </div>
        <div>
          <div class="h-stat-num">10<span>+</span></div>
          <div class="h-stat-label">Years Experience</div>
        </div>
        <div>
          <div class="h-stat-num">100<span>%</span></div>
          <div class="h-stat-label">Client Satisfaction</div>
        </div>
      </div>
    </div>

    <div class="hero-right">
      <div class="hero-visual">
        <!-- Floating badges -->
        <div class="hero-float-1">● LIVE MONITORING</div>
        <div class="hero-float-2">⚡ 10kW SOLAR READY</div>
        <div class="hero-float-3">🔴 REC ACTIVE</div>

        <div class="hero-cam-card">
          <div class="hcc-label">// SURVEILLANCE SYSTEM ACTIVE</div>
          <div class="cam-svg-wrap">
            <svg width="300" height="200" viewBox="0 0 300 200" fill="none" xmlns="http://www.w3.org/2000/svg">
              <!-- Radar rings -->
              <circle cx="220" cy="100" r="70" stroke="rgba(0,207,255,0.15)" stroke-width="1"/>
              <circle cx="220" cy="100" r="50" stroke="rgba(0,207,255,0.2)" stroke-width="1"/>
              <circle cx="220" cy="100" r="30" stroke="rgba(0,207,255,0.25)" stroke-width="1"/>
              <!-- Detection cone -->
              <path d="M90 80 L20 30 L20 170 L90 120" fill="rgba(255,92,0,0.08)" stroke="rgba(255,92,0,0.3)" stroke-width="1.5" stroke-dasharray="6 4"/>
              <!-- Camera body -->
              <rect x="90" y="75" width="160" height="60" rx="10" fill="#E8EEF8"/>
              <rect x="90" y="75" width="160" height="60" rx="10" fill="url(#camG)"/>
              <!-- Lens -->
              <circle cx="118" cy="105" r="24" fill="#1A2A3A"/>
              <circle cx="118" cy="105" r="16" fill="#0D1E33"/>
              <circle cx="118" cy="105" r="9"  fill="rgba(0,207,255,0.8)"/>
              <circle cx="121" cy="102" r="3.5" fill="rgba(255,255,255,0.4)"/>
              <!-- LED -->
              <circle cx="228" cy="86" r="5" fill="#FF5C00">
                <animate attributeName="opacity" values="1;0.2;1" dur="1.4s" repeatCount="indefinite"/>
              </circle>
              <!-- Vents -->
              <rect x="158" y="87" width="2.5" height="36" rx="1.25" fill="#B0C0D8" opacity="0.5"/>
              <rect x="168" y="87" width="2.5" height="36" rx="1.25" fill="#B0C0D8" opacity="0.5"/>
              <rect x="178" y="87" width="2.5" height="36" rx="1.25" fill="#B0C0D8" opacity="0.5"/>
              <!-- Brand -->
              <text x="195" y="110" font-family="sans-serif" font-size="10" fill="#4A6080" text-anchor="middle" letter-spacing="2">HBWAHEED</text>
              <!-- Mount -->
              <rect x="158" y="134" width="12" height="30" fill="#1A2A3A"/>
              <rect x="142" y="160" width="44" height="10" rx="3" fill="#1A2A3A"/>
              <!-- Blip dots -->
              <circle cx="200" cy="80" r="4" fill="#FF5C00" opacity="0.7">
                <animate attributeName="opacity" values="0.7;0.1;0.7" dur="2s" repeatCount="indefinite"/>
              </circle>
              <circle cx="245" cy="115" r="3" fill="#FFD000" opacity="0.8">
                <animate attributeName="opacity" values="0.8;0.2;0.8" dur="1.7s" begin="0.5s" repeatCount="indefinite"/>
              </circle>
              <defs>
                <linearGradient id="camG" x1="90" y1="75" x2="250" y2="135" gradientUnits="userSpaceOnUse">
                  <stop offset="0%" stop-color="#F5F9FF"/>
                  <stop offset="100%" stop-color="#C4D2E8"/>
                </linearGradient>
              </defs>
            </svg>
          </div>
          <div class="hcc-status-row">
            <div class="hcc-status">STATUS <strong>● ONLINE</strong></div>
            <div class="hcc-status">CAMERAS <strong>8 ACTIVE</strong></div>
            <div class="hcc-status">RECORDING <strong>24/7</strong></div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Services Preview -->
  <section class="home-services">
    <div class="section-tag">What We Offer</div>
    <h2 class="section-title">Six services.<br><em>One trusted team.</em></h2>
    <div class="services-row">
      <div class="srv-mini fade-in">
        <div class="srv-emoji">📹</div>
        <div class="srv-name">CCTV & Surveillance</div>
        <p class="srv-desc">IP cameras, NVR/DVR systems, and remote monitoring for total security coverage.</p>
        <span class="srv-arrow">→</span>
      </div>
      <div class="srv-mini fade-in">
        <div class="srv-emoji">🌐</div>
        <div class="srv-name">Network Infrastructure</div>
        <p class="srv-desc">Structured cabling, switches, routers, and Wi-Fi solutions for fast, reliable connectivity.</p>
        <span class="srv-arrow">→</span>
      </div>
      <div class="srv-mini fade-in">
        <div class="srv-emoji">☀️</div>
        <div class="srv-name">Solar Installations</div>
        <p class="srv-desc">Complete solar setups with inverters and battery backup for homes and businesses.</p>
        <span class="srv-arrow">→</span>
      </div>
      <div class="srv-mini fade-in">
        <div class="srv-emoji">🔥</div>
        <div class="srv-name">Fire Alarm Systems</div>
        <p class="srv-desc">Addressable and conventional fire detection installed to international safety standards.</p>
        <span class="srv-arrow">→</span>
      </div>
      <div class="srv-mini fade-in">
        <div class="srv-emoji">🔔</div>
        <div class="srv-name">Intercom Solutions</div>
        <p class="srv-desc">Audio and video intercom systems for seamless access control and communication.</p>
        <span class="srv-arrow">→</span>
      </div>
      <div class="srv-mini fade-in">
        <div class="srv-emoji">⚡</div>
        <div class="srv-name">Electrical Works</div>
        <p class="srv-desc">Full wiring, panel upgrades, and compliance inspections for all property types.</p>
        <span class="srv-arrow">→</span>
      </div>
    </div>
  </section>

  <!-- CTA Strip -->
  <div class="cta-strip">
    <h2>Ready to secure and power your property?</h2>
    <button class="btn-white" onclick="goto('contact')">Get a Free Quote →</button>
  </div>

  <!-- Footer -->
  <footer class="footer">
    <div class="footer-top">
      <div>
        <div class="footer-brand">HB<span>WAHEED</span></div>
        <p class="footer-tagline">Professional electrical and ICT installation services you can trust — for homes and businesses across Nigeria.</p>
      </div>
      <div>
        <div class="footer-col-title">Pages</div>
        <ul class="footer-links">
          <li><button onclick="goto('home')">Home</button></li>
          <li><button onclick="goto('services')">Services</button></li>
          <li><button onclick="goto('about')">About Us</button></li>
          <li><button onclick="goto('gallery')">Gallery</button></li>
          <li><button onclick="goto('contact')">Contact</button></li>
        </ul>
      </div>
      <div>
        <div class="footer-col-title">Contact</div>
        <ul class="footer-links">
          <li><a href="tel:+2347067612107" style="color:var(--muted); font-size:14px;">+234 706 761 2107</a></li>
          <li><a href="mailto:hbabduwaheed@gmail.com" style="color:var(--muted); font-size:14px;">hbabduwaheed@gmail.com</a></li>
          <li style="color:var(--muted); font-size:14px; padding-top:4px;">Available 7 days a week</li>
        </ul>
      </div>
    </div>
    <div class="footer-bottom">
      <span>© 2024 HBWAHEED Electrical ICT Solution. All rights reserved.</span>
      <span>Quality installations you can trust.</span>
    </div>
  </footer>
</div>

<!-- ═══════════════════════════════════════════
     PAGE: SERVICES
═══════════════════════════════════════════ -->
<div class="page" id="page-services">
  <section class="services-hero">
    <div class="section-tag">Our Expertise</div>
    <h1 class="section-title">Professional<br><em>installation services</em><br>built to last.</h1>
    <p class="section-sub">Every job is handled by experienced technicians using quality-grade equipment — from small residential setups to large commercial projects.</p>
  </section>

  <section class="section" style="padding:60px 80px 80px; background:var(--navy);">
    <div class="services-grid-full">
      <div class="srv-card fade-in">
        <span class="srv-card-num">01</span>
        <div class="srv-card-icon ic-orange">📹</div>
        <div class="srv-card-title">CCTV & Surveillance</div>
        <p class="srv-card-desc">We design and install complete IP camera systems with NVR/DVR recording, remote mobile viewing, and night-vision coverage. Whether you need 4 cameras or 64, we handle the full setup.</p>
        <div class="srv-card-tags">
          <span class="tag">IP Cameras</span><span class="tag">NVR / DVR</span><span class="tag">Night Vision</span><span class="tag">Remote Viewing</span><span class="tag">PTZ Cameras</span>
        </div>
      </div>
      <div class="srv-card fade-in">
        <span class="srv-card-num">02</span>
        <div class="srv-card-icon ic-blue">🌐</div>
        <div class="srv-card-title">Network Infrastructure</div>
        <p class="srv-card-desc">From cat6 structured cabling to enterprise-grade wireless access points, we build networks that are fast, stable, and future-ready. We handle both new builds and upgrades to existing systems.</p>
        <div class="srv-card-tags">
          <span class="tag">Cat6 Cabling</span><span class="tag">Switches</span><span class="tag">Wi-Fi AP</span><span class="tag">Server Rack</span><span class="tag">Fibre Optic</span>
        </div>
      </div>
      <div class="srv-card fade-in">
        <span class="srv-card-num">03</span>
        <div class="srv-card-icon ic-yellow">☀️</div>
        <div class="srv-card-title">Solar Installations</div>
        <p class="srv-card-desc">End-to-end solar energy solutions — from site assessment and panel mounting to inverter installation and battery storage. We install systems that run reliably through load shedding and outages.</p>
        <div class="srv-card-tags">
          <span class="tag">Solar Panels</span><span class="tag">Inverters</span><span class="tag">Battery Storage</span><span class="tag">Hybrid Systems</span>
        </div>
      </div>
      <div class="srv-card fade-in">
        <span class="srv-card-num">04</span>
        <div class="srv-card-icon ic-cyan">🔥</div>
        <div class="srv-card-title">Fire Alarm Systems</div>
        <p class="srv-card-desc">We install addressable and conventional fire alarm systems for offices, warehouses, hotels, schools, and homes. All installations comply with international fire safety standards and local regulations.</p>
        <div class="srv-card-tags">
          <span class="tag">Smoke Detectors</span><span class="tag">Heat Sensors</span><span class="tag">Control Panels</span><span class="tag">Sprinkler Integration</span>
        </div>
      </div>
      <div class="srv-card fade-in">
        <span class="srv-card-num">05</span>
        <div class="srv-card-icon ic-green">🔔</div>
        <div class="srv-card-title">Intercom Solutions</div>
        <p class="srv-card-desc">Audio and video intercom systems for apartment buildings, offices, and gated properties. We integrate with existing access control systems for a seamless, secure entry experience.</p>
        <div class="srv-card-tags">
          <span class="tag">Video Intercom</span><span class="tag">Audio Units</span><span class="tag">Access Control</span><span class="tag">Multi-Unit</span>
        </div>
      </div>
      <div class="srv-card fade-in">
        <span class="srv-card-num">06</span>
        <div class="srv-card-icon ic-purple">⚡</div>
        <div class="srv-card-title">Electrical Works</div>
        <p class="srv-card-desc">Complete electrical installations for residential and commercial properties. From consumer unit upgrades and wiring to outdoor lighting and generator connections — done safely and cleanly.</p>
        <div class="srv-card-tags">
          <span class="tag">Wiring</span><span class="tag">Panel Upgrades</span><span class="tag">Lighting</span><span class="tag">Generator</span><span class="tag">Inspection</span>
        </div>
      </div>
    </div>
  </section>

  <!-- Process -->
  <section class="process-section">
    <div class="section-tag">How We Work</div>
    <h2 class="section-title">Our <em>simple</em> process</h2>
    <div class="process-steps">
      <div class="process-step fade-in">
        <span class="step-num">01</span>
        <div class="srv-emoji">📞</div>
        <div class="step-title">Consultation</div>
        <p class="step-desc">We discuss your needs, property size, and budget. Call us or fill out the quote form — no obligation.</p>
      </div>
      <div class="process-step fade-in">
        <span class="step-num">02</span>
        <div class="srv-emoji">📐</div>
        <div class="step-title">Site Assessment</div>
        <p class="step-desc">Our team visits the site to assess the space, plan cable routes, and identify the best equipment placement.</p>
      </div>
      <div class="process-step fade-in">
        <span class="step-num">03</span>
        <div class="srv-emoji">🔧</div>
        <div class="step-title">Installation</div>
        <p class="step-desc">We install everything neatly and professionally, with minimal disruption to your home or business operations.</p>
      </div>
      <div class="process-step fade-in">
        <span class="step-num">04</span>
        <div class="srv-emoji">✅</div>
        <div class="step-title">Handover & Support</div>
        <p class="step-desc">We test everything, walk you through how it works, and provide ongoing support after the job is done.</p>
      </div>
    </div>
  </section>

  <!-- CTA -->
  <div class="cta-strip">
    <h2>Need any of these services?<br>Let's talk today.</h2>
    <button class="btn-white" onclick="goto('contact')">Get a Free Quote →</button>
  </div>

  <footer class="footer">
    <div class="footer-top">
      <div>
        <div class="footer-brand">HB<span>WAHEED</span></div>
        <p class="footer-tagline">Professional electrical and ICT installation services you can trust — for homes and businesses across Nigeria.</p>
      </div>
      <div>
        <div class="footer-col-title">Pages</div>
        <ul class="footer-links">
          <li><button onclick="goto('home')">Home</button></li>
          <li><button onclick="goto('services')">Services</button></li>
          <li><button onclick="goto('about')">About Us</button></li>
          <li><button onclick="goto('gallery')">Gallery</button></li>
          <li><button onclick="goto('contact')">Contact</button></li>
        </ul>
      </div>
      <div>
        <div class="footer-col-title">Contact</div>
        <ul class="footer-links">
          <li><a href="tel:+2347067612107" style="color:var(--muted);font-size:14px;">+234 706 761 2107</a></li>
          <li><a href="mailto:hbabduwaheed@gmail.com" style="color:var(--muted);font-size:14px;">hbabduwaheed@gmail.com</a></li>
        </ul>
      </div>
    </div>
    <div class="footer-bottom">
      <span>© 2024 HBWAHEED Electrical ICT Solution.</span>
      <span>Quality installations you can trust.</span>
    </div>
  </footer>
</div>

<!-- ═══════════════════════════════════════════
     PAGE: ABOUT
═══════════════════════════════════════════ -->
<div class="page" id="page-about">
  <section class="about-hero">
    <div class="about-visual">
      <div class="about-big-num">10+</div>
      <div class="about-card">
        <div class="about-card-title">Why clients choose us</div>
        <ul class="value-list">
          <li>Licensed and experienced installation team</li>
          <li>Transparent pricing — no hidden charges</li>
          <li>Clean, professional cable management</li>
          <li>On-time project delivery, every time</li>
          <li>Post-installation support and maintenance</li>
          <li>Both residential and commercial expertise</li>
        </ul>
      </div>
    </div>
    <div class="about-text fade-in">
      <div class="section-tag">Our Story</div>
      <h1 class="section-title">We don't just install.<br><em>We build systems</em><br>you can rely on.</h1>
      <p>HBWAHEED Electrical ICT Solution was founded with one mission: to bring professional, high-quality electrical and ICT installations to homes and businesses at a fair price. Over a decade in, that mission hasn't changed.</p>
      <p>From a single CCTV camera installation to a full commercial network rollout, we bring the same level of care and precision to every job. Our team stays updated on the latest technologies so you always get solutions that work — today and years from now.</p>
      <p>We've built our reputation job by job, and our clients keep coming back. That's the only metric that matters to us.</p>
      <div style="margin-top:32px; display:flex; gap:14px; flex-wrap:wrap;">
        <button class="btn btn-orange" onclick="goto('contact')">Work With Us</button>
        <button class="btn btn-outline" onclick="goto('gallery')">See Our Work</button>
      </div>
    </div>
  </section>

  <!-- Trust cards -->
  <section class="trust-section">
    <div class="section-tag">What Drives Us</div>
    <h2 class="section-title">Built on <em>three pillars</em></h2>
    <div class="trust-grid">
      <div class="trust-card fade-in">
        <span class="trust-icon">🎯</span>
        <div class="trust-title">Precision</div>
        <p class="trust-desc">Every cable routed neatly. Every camera positioned precisely. We take pride in the details most companies overlook.</p>
      </div>
      <div class="trust-card fade-in">
        <span class="trust-icon">🛡️</span>
        <div class="trust-title">Reliability</div>
        <p class="trust-desc">We use quality-grade equipment that lasts. Our installations are built to perform for years with minimal maintenance.</p>
      </div>
      <div class="trust-card fade-in">
        <span class="trust-icon">🤝</span>
        <div class="trust-title">Integrity</div>
        <p class="trust-desc">Honest quotes, clear timelines, no surprises. We say what we'll do and do what we say — every single time.</p>
      </div>
    </div>
  </section>

  <!-- Numbers -->
  <div class="creds-section">
    <div class="cred-item fade-in">
      <div class="cred-num">10+</div>
      <div class="cred-label">Years in Business</div>
    </div>
    <div class="cred-item fade-in">
      <div class="cred-num">500+</div>
      <div class="cred-label">Projects Completed</div>
    </div>
    <div class="cred-item fade-in">
      <div class="cred-num">6</div>
      <div class="cred-label">Core Services</div>
    </div>
    <div class="cred-item fade-in">
      <div class="cred-num">100%</div>
      <div class="cred-label">Client Satisfaction</div>
    </div>
  </div>

  <div class="cta-strip">
    <h2>Let's talk about your next project.</h2>
    <button class="btn-white" onclick="goto('contact')">Contact Us →</button>
  </div>

  <footer class="footer">
    <div class="footer-top">
      <div>
        <div class="footer-brand">HB<span>WAHEED</span></div>
        <p class="footer-tagline">Professional electrical and ICT installation services you can trust — for homes and businesses across Nigeria.</p>
      </div>
      <div>
        <div class="footer-col-title">Pages</div>
        <ul class="footer-links">
          <li><button onclick="goto('home')">Home</button></li>
          <li><button onclick="goto('services')">Services</button></li>
          <li><button onclick="goto('about')">About Us</button></li>
          <li><button onclick="goto('gallery')">Gallery</button></li>
          <li><button onclick="goto('contact')">Contact</button></li>
        </ul>
      </div>
      <div>
        <div class="footer-col-title">Contact</div>
        <ul class="footer-links">
          <li><a href="tel:+2347067612107" style="color:var(--muted);font-size:14px;">+234 706 761 2107</a></li>
          <li><a href="mailto:hbabduwaheed@gmail.com" style="color:var(--muted);font-size:14px;">hbabduwaheed@gmail.com</a></li>
        </ul>
      </div>
    </div>
    <div class="footer-bottom">
      <span>© 2024 HBWAHEED Electrical ICT Solution.</span>
      <span>Quality installations you can trust.</span>
    </div>
  </footer>
</div>

<!-- ═══════════════════════════════════════════
     PAGE: GALLERY
═══════════════════════════════════════════ -->
<div class="page" id="page-gallery">
  <section class="gallery-hero">
    <div class="section-tag">Our Work</div>
    <h1 class="section-title">Projects we're<br><em>proud to show.</em></h1>
    <p class="section-sub">A selection of completed installations across residential and commercial properties.</p>
    <div class="gallery-filters">
      <button class="filter-btn active" onclick="filterGallery('all', this)">All Projects</button>
      <button class="filter-btn" onclick="filterGallery('cctv', this)">CCTV</button>
      <button class="filter-btn" onclick="filterGallery('network', this)">Networking</button>
      <button class="filter-btn" onclick="filterGallery('solar', this)">Solar</button>
      <button class="filter-btn" onclick="filterGallery('fire', this)">Fire Alarm</button>
      <button class="filter-btn" onclick="filterGallery('electrical', this)">Electrical</button>
    </div>
  </section>

  <div class="gallery-grid">
    <div class="gallery-item gi-bg-1 fade-in" data-cat="cctv">
      <div class="gi-inner">
        <span class="gi-icon">📹</span>
        <span style="font-family:var(--heading);font-size:15px;color:var(--muted);letter-spacing:1px;">CCTV PROJECT</span>
      </div>
      <div class="gi-overlay">
        <div><div class="gi-label">Commercial Tower — 32 Cameras</div><div class="gi-sub">Full IP CCTV System · Al Wakra</div></div>
      </div>
    </div>
    <div class="gallery-item gi-bg-2 fade-in" data-cat="network">
      <div class="gi-inner">
        <span class="gi-icon">🌐</span>
        <span style="font-family:var(--heading);font-size:15px;color:var(--muted);letter-spacing:1px;">NETWORK PROJECT</span>
      </div>
      <div class="gi-overlay">
        <div><div class="gi-label">Office Network Rollout</div><div class="gi-sub">Cat6 + 12 Access Points · Lagos</div></div>
      </div>
    </div>
    <div class="gallery-item gi-bg-3 fade-in" data-cat="solar">
      <div class="gi-inner">
        <span class="gi-icon">☀️</span>
        <span style="font-family:var(--heading);font-size:15px;color:var(--muted);letter-spacing:1px;">SOLAR PROJECT</span>
      </div>
      <div class="gi-overlay">
        <div><div class="gi-label">Villa Solar System — 10kW</div><div class="gi-sub">Hybrid Inverter + Battery · Abuja</div></div>
      </div>
    </div>
    <div class="gallery-item gi-bg-4 fade-in" data-cat="fire">
      <div class="gi-inner">
        <span class="gi-icon">🔥</span>
        <span style="font-family:var(--heading);font-size:15px;color:var(--muted);letter-spacing:1px;">FIRE ALARM PROJECT</span>
      </div>
      <div class="gi-overlay">
        <div><div class="gi-label">Hotel Fire Alarm System</div><div class="gi-sub">48-Zone Addressable · Port Harcourt</div></div>
      </div>
    </div>
    <div class="gallery-item gi-bg-5 fade-in" data-cat="cctv">
      <div class="gi-inner">
        <span class="gi-icon">🔔</span>
        <span style="font-family:var(--heading);font-size:15px;color:var(--muted);letter-spacing:1px;">INTERCOM PROJECT</span>
      </div>
      <div class="gi-overlay">
        <div><div class="gi-label">Apartment Block Intercom</div><div class="gi-sub">Video + Access Control · Kano</div></div>
      </div>
    </div>
    <div class="gallery-item gi-bg-6 fade-in" data-cat="electrical">
      <div class="gi-inner">
        <span class="gi-icon">⚡</span>
        <span style="font-family:var(--heading);font-size:15px;color:var(--muted);letter-spacing:1px;">ELECTRICAL PROJECT</span>
      </div>
      <div class="gi-overlay">
        <div><div class="gi-label">Full Rewire — 5-Bedroom House</div><div class="gi-sub">Panel Upgrade + Lighting · Lagos</div></div>
      </div>
    </div>
  </div>

  <div class="cta-strip">
    <h2>Want results like these<br>for your property?</h2>
    <button class="btn-white" onclick="goto('contact')">Get a Free Quote →</button>
  </div>

  <footer class="footer">
    <div class="footer-top">
      <div>
        <div class="footer-brand">HB<span>WAHEED</span></div>
        <p class="footer-tagline">Professional electrical and ICT installation services you can trust — for homes and businesses across Nigeria.</p>
      </div>
      <div>
        <div class="footer-col-title">Pages</div>
        <ul class="footer-links">
          <li><button onclick="goto('home')">Home</button></li>
          <li><button onclick="goto('services')">Services</button></li>
          <li><button onclick="goto('about')">About Us</button></li>
          <li><button onclick="goto('gallery')">Gallery</button></li>
          <li><button onclick="goto('contact')">Contact</button></li>
        </ul>
      </div>
      <div>
        <div class="footer-col-title">Contact</div>
        <ul class="footer-links">
          <li><a href="tel:+2347067612107" style="color:var(--muted);font-size:14px;">+234 706 761 2107</a></li>
          <li><a href="mailto:hbabduwaheed@gmail.com" style="color:var(--muted);font-size:14px;">hbabduwaheed@gmail.com</a></li>
        </ul>
      </div>
    </div>
    <div class="footer-bottom">
      <span>© 2024 HBWAHEED Electrical ICT Solution.</span>
      <span>Quality installations you can trust.</span>
    </div>
  </footer>
</div>

<!-- ═══════════════════════════════════════════
     PAGE: CONTACT
═══════════════════════════════════════════ -->
<div class="page" id="page-contact">
  <div class="contact-page">
    <div class="contact-info fade-in">
      <div class="section-tag">Reach Out</div>
      <h1>Let's talk about<br><em>your project.</em></h1>
      <p>Fill in the quote form and we'll get back to you within 24 hours. Or reach us directly — we're available 7 days a week.</p>

      <div class="contact-method">
        <div class="cm-icon">📞</div>
        <div>
          <div class="cm-label">Phone / WhatsApp</div>
          <div class="cm-value"><a href="tel:+2347067612107">+234 706 761 2107</a></div>
        </div>
      </div>
      <div class="contact-method">
        <div class="cm-icon">✉️</div>
        <div>
          <div class="cm-label">Email</div>
          <div class="cm-value"><a href="mailto:hbabduwaheed@gmail.com">hbabduwaheed@gmail.com</a></div>
        </div>
      </div>
      <div class="contact-method">
        <div class="cm-icon">🕐</div>
        <div>
          <div class="cm-label">Availability</div>
          <div class="cm-value">7 Days a Week</div>
        </div>
      </div>

      <div class="contact-note">
        <strong>⚡ Fast Response Guaranteed</strong>
        We typically respond to quote requests within a few hours. For urgent jobs, call or WhatsApp us directly.
      </div>
    </div>

    <div class="quote-form fade-in">
      <div id="form-content">
        <div class="form-title">Request a Free Quote</div>
        <div class="form-subtitle">Tell us about your project and we'll get back to you with a detailed quote.</div>

        <div class="form-row">
          <div class="form-group">
            <label>Your Name *</label>
            <input type="text" id="f-name" placeholder="e.g. Ahmed Yusuf" required>
          </div>
          <div class="form-group">
            <label>Phone Number *</label>
            <input type="tel" id="f-phone" placeholder="+234 xxx xxx xxxx" required>
          </div>
        </div>
        <div class="form-group">
          <label>Email Address</label>
          <input type="email" id="f-email" placeholder="your@email.com">
        </div>
        <div class="form-group">
          <label>Service Required *</label>
          <select id="f-service">
            <option value="">Select a service...</option>
            <option>CCTV & Surveillance</option>
            <option>Network Infrastructure</option>
            <option>Solar Installation</option>
            <option>Fire Alarm System</option>
            <option>Intercom Solution</option>
            <option>Electrical Works</option>
            <option>Multiple Services</option>
          </select>
        </div>
        <div class="form-group">
          <label>Property Type</label>
          <select id="f-property">
            <option value="">Select property type...</option>
            <option>Residential — Single Home</option>
            <option>Residential — Apartment Block</option>
            <option>Commercial — Office</option>
            <option>Commercial — Warehouse / Factory</option>
            <option>Commercial — Hotel / Hospitality</option>
            <option>Other</option>
          </select>
        </div>
        <div class="form-group">
          <label>Project Details</label>
          <textarea id="f-details" placeholder="Briefly describe your project — number of cameras, building size, location, any specific requirements..."></textarea>
        </div>
        <button class="form-submit" onclick="submitForm()">Send My Request →</button>
      </div>
      <div class="form-success" id="form-success">
        <div class="success-icon">✅</div>
        <h3>Request Sent!</h3>
        <p>Thank you for reaching out. We'll review your project details and get back to you within 24 hours.<br><br>For urgent enquiries, call us on<br><strong style="color:var(--orange);">+234 706 761 2107</strong></p>
        <button class="btn btn-orange" style="margin-top:24px;" onclick="resetForm()">Send Another Request</button>
      </div>
    </div>
  </div>

  <footer class="footer" style="margin-top:0;">
    <div class="footer-top">
      <div>
        <div class="footer-brand">HB<span>WAHEED</span></div>
        <p class="footer-tagline">Professional electrical and ICT installation services you can trust — for homes and businesses across Nigeria.</p>
      </div>
      <div>
        <div class="footer-col-title">Pages</div>
        <ul class="footer-links">
          <li><button onclick="goto('home')">Home</button></li>
          <li><button onclick="goto('services')">Services</button></li>
          <li><button onclick="goto('about')">About Us</button></li>
          <li><button onclick="goto('gallery')">Gallery</button></li>
          <li><button onclick="goto('contact')">Contact</button></li>
        </ul>
      </div>
      <div>
        <div class="footer-col-title">Contact</div>
        <ul class="footer-links">
          <li><a href="tel:+2347067612107" style="color:var(--muted);font-size:14px;">+234 706 761 2107</a></li>
          <li><a href="mailto:hbabduwaheed@gmail.com" style="color:var(--muted);font-size:14px;">hbabduwaheed@gmail.com</a></li>
        </ul>
      </div>
    </div>
    <div class="footer-bottom">
      <span>© 2024 HBWAHEED Electrical ICT Solution.</span>
      <span>Quality installations you can trust.</span>
    </div>
  </footer>
</div>

<!-- ═══════════════════════════════════════════
     JAVASCRIPT
═══════════════════════════════════════════ -->
<script>
/* ── Navigation ── */
function goto(id) {
  document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
  document.getElementById('page-' + id).classList.add('active');
  window.scrollTo({ top: 0, behavior: 'smooth' });

  // Update nav buttons
  ['home','services','about','gallery','contact'].forEach(p => {
    const nb = document.getElementById('nb-' + p);
    const mb = document.getElementById('mb-' + p);
    if (nb) nb.classList.toggle('active', p === id);
    if (mb) mb.classList.toggle('active', p === id);
  });

  // Trigger fade-ins
  setTimeout(triggerFades, 50);
}

/* ── Mobile menu ── */
let mobileOpen = false;
function toggleMobile() {
  mobileOpen = !mobileOpen;
  document.getElementById('mobileMenu').classList.toggle('open', mobileOpen);
}

/* ── Fade-in observer ── */
function triggerFades() {
  const observer = new IntersectionObserver((entries) => {
    entries.forEach((e, i) => {
      if (e.isIntersecting) {
        setTimeout(() => e.target.classList.add('visible'), i * 80);
        observer.unobserve(e.target);
      }
    });
  }, { threshold: 0.1 });
  document.querySelectorAll('.page.active .fade-in:not(.visible)').forEach(el => observer.observe(el));
}

/* ── Gallery filter ── */
function filterGallery(cat, btn) {
  document.querySelectorAll('.filter-btn').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
  document.querySelectorAll('.gallery-item').forEach(item => {
    const match = cat === 'all' || item.dataset.cat === cat;
    item.style.display = match ? 'block' : 'none';
  });
}

/* ── Quote form ── */
function submitForm() {
  const name = document.getElementById('f-name').value.trim();
  const phone = document.getElementById('f-phone').value.trim();
  const service = document.getElementById('f-service').value;
  if (!name || !phone || !service) {
    alert('Please fill in your name, phone number, and select a service.');
    return;
  }
  document.getElementById('form-content').style.display = 'none';
  document.getElementById('form-success').style.display = 'block';
}
function resetForm() {
  ['f-name','f-phone','f-email','f-details'].forEach(id => document.getElementById(id).value = '');
  ['f-service','f-property'].forEach(id => document.getElementById(id).selectedIndex = 0);
  document.getElementById('form-content').style.display = 'block';
  document.getElementById('form-success').style.display = 'none';
}

/* ── Init ── */
triggerFades();
</script>
</body>
</html>
