---
layout: home
title: Home
order: 1
---

<style>
  /* --- 🌌 IMPORT FONTS 🌌 --- */
  @import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&family=Space+Mono:ital,wght@0,400;0,700;1,400&display=swap');

  /* --- 🚀 CORE SYSTEM SETTINGS --- */
  :root {
    --neon-blue: #00d2ff;
    --neon-pink: #ff00ff;
    --dark-bg: #050505;
    --panel-bg: #0d0d12;
    --border: #1f1f2e;
  }

  html, body {
    overflow-x: hidden;
    max-width: 100%;
    background-color: var(--dark-bg);
    background: radial-gradient(circle at center, #1a1a2e 0%, #000000 100%);
    color: #a8b2d1;
    font-family: 'Space Mono', monospace;
    cursor: crosshair; /* Sci-Fi Cursor */
  }

  /* --- 📺 CRT SCANLINE OVERLAY --- */
  body::before {
    content: " ";
    display: block;
    position: fixed; top: 0; left: 0; bottom: 0; right: 0;
    background: linear-gradient(rgba(18, 16, 16, 0) 50%, rgba(0, 0, 0, 0.25) 50%), 
                linear-gradient(90deg, rgba(255, 0, 0, 0.06), rgba(0, 255, 0, 0.02), rgba(0, 0, 255, 0.06));
    z-index: 9999;
    background-size: 100% 2px, 3px 100%;
    pointer-events: none;
  }

  /* --- 📐 LAYOUT WRAPPER --- */
  .wrapper { 
    max-width: 1000px; 
    margin: 0 auto; 
    padding: 0 20px; 
    position: relative;
    z-index: 1;
  }

  /* --- 🎛️ HUD TOP BAR --- */
  .hud-bar {
    border: 1px solid #333;
    background: rgba(0,0,0,0.6);
    padding: 10px 15px;
    margin-bottom: 40px;
    display: flex;
    justify-content: space-between;
    font-family: 'Orbitron', sans-serif;
    font-size: 0.8em;
    color: #777;
    text-transform: uppercase;
    letter-spacing: 1px;
  }
  .hud-status { color: #0f0; text-shadow: 0 0 5px #0f0; }
  .hud-critical { color: red; animation: blink 2s infinite; }
  @keyframes blink { 0% {opacity: 1;} 50% {opacity: 0.4;} 100% {opacity: 1;} }

  /* --- ✒️ TYPOGRAPHY --- */
  h1, h2, h3 { 
    font-family: 'Orbitron', sans-serif; 
    text-transform: uppercase;
    letter-spacing: 2px;
  }
  
  h1 { 
    font-weight: 900; 
    font-size: 2.5em;
    background: -webkit-linear-gradient(var(--neon-blue), #3a7bd5);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    filter: drop-shadow(0 0 10px rgba(0,210,255,0.5));
    margin-bottom: 10px;
  }

  h2 {
    font-size: 1.4em;
    color: #fff;
    margin: 0;
  }

  strong { color: var(--neon-blue); }
  a { color: var(--neon-pink); text-decoration: none; border-bottom: 1px dashed var(--neon-pink); transition: 0.3s; }
  a:hover { background: var(--neon-pink); color: #000; text-decoration: none; border-bottom: none; }

  /* --- 🛸 HERO PANEL --- */
  .hero-panel {
    background: rgba(10, 10, 15, 0.8);
    border: 1px solid #333;
    padding: 40px;
    border-radius: 10px;
    position: relative;
    box-shadow: 0 0 30px rgba(0, 210, 255, 0.05);
    margin-bottom: 50px;
  }
  .hero-panel::after {
    content: ''; position: absolute; top: -2px; left: -2px; right: -2px; bottom: -2px;
    background: linear-gradient(45deg, var(--neon-pink), #000, var(--neon-blue), #000);
    z-index: -1;
    border-radius: 12px;
    background-size: 400%;
    animation: glowing 20s linear infinite;
  }
  @keyframes glowing { 0% { background-position: 0 0; } 50% { background-position: 400% 0; } 100% { background-position: 0 0; } }

  /* --- 📂 SECTION HEADERS --- */
  .section-header {
    display: flex;
    align-items: center;
    gap: 15px;
    margin-bottom: 20px;
    margin-top: 50px;
    border-bottom: 1px solid #333;
    padding-bottom: 10px;
  }
  .section-header .icon {
    font-size: 1.5em;
    filter: drop-shadow(0 0 5px var(--neon-blue));
  }

  /* --- 📦 CONTENT BOXES --- */
  .box, .content-box {
    background: var(--panel-bg);
    border: 1px solid var(--border);
    border-left: 4px solid var(--neon-blue);
    padding: 25px;
    margin-bottom: 30px;
    position: relative;
    transition: 0.3s;
  }
  .box:hover, .content-box:hover {
    border-color: var(--neon-blue);
    box-shadow: -5px 5px 0 rgba(0, 210, 255, 0.1);
    transform: translateX(5px);
  }
  .box::after, .content-box::after {
    content: " [SECURE]";
    position: absolute; top: 10px; right: 10px;
    font-size: 0.7em; color: #444; font-family: 'Orbitron';
  }

  /* --- 🏷️ TECH TAGS --- */
  .tech-grid {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    margin-top: 10px;
  }
  .tech-tag {
    background-color: rgba(0, 210, 255, 0.05);
    padding: 5px 10px;
    border: 1px solid rgba(0, 210, 255, 0.3);
    color: var(--neon-blue);
    font-size: 0.85em;
    font-family: 'Space Mono', monospace;
  }
  .tech-tag:hover {
    background-color: var(--neon-blue);
    color: #000;
  }

  /* --- 🎭 WARNING / COMEDY BOX --- */
  .warning-box {
    background: repeating-linear-gradient(45deg, #131313, #131313 10px, #1a1a1a 10px, #1a1a1a 20px);
    border: 2px solid #ff9f43;
    color: #ff9f43;
    padding: 25px;
    margin-top: 40px;
    position: relative;
  }
  .warning-label {
    background: #ff9f43;
    color: #000;
    padding: 2px 8px;
    font-weight: bold;
    font-family: 'Orbitron';
    position: absolute;
    top: -15px;
    left: 20px;
  }

  /* --- 📡 SIGNAL BEACON (FLOATING ICON) --- */
  .signal-beacon {
    position: fixed; bottom: 30px; right: 30px;
    width: 50px; height: 50px;
    background: radial-gradient(circle, #ff55ff 10%, #ff00ff 100%);
    border-radius: 50%;
    display: flex; justify-content: center; align-items: center;
    box-shadow: 0 0 20px #ff00ff;
    z-index: 100;
    animation: bounce 3s infinite ease-in-out;
    text-decoration: none;
    border: 2px solid #fff;
  }
  .signal-beacon::before {
    content: ''; position: absolute; top: 0; left: 0; right: 0; bottom: 0;
    border-radius: 50%; border: 2px solid #ff00ff;
    animation: ripple 1.5s infinite ease-out; z-index: -1;
  }
  @keyframes ripple { 0% { transform: scale(1); opacity: 1; } 100% { transform: scale(2.5); opacity: 0; } }
  @keyframes bounce { 0%, 100% { transform: translateY(0); } 50% { transform: translateY(-10px); } }

  /* --- 📱 MOBILE --- */
  @media screen and (max-width: 768px) {
    .hud-bar { flex-direction: column; text-align: center; gap: 5px; }
    h1 { font-size: 1.8em; }
    .hero-panel { padding: 20px; }
  }
</style>

<div class="wrapper">

  <div class="hud-bar">
    <span>System: <span class="hud-status">ONLINE</span></span>
    <span>Loc: EARTH-982</span>
    <span>Caffeine: <span class="hud-critical">CRITICAL</span></span>
  </div>

  <div class="hero-panel">
    <h1>MAZAHARUL ABEDIN</h1>
    <p>
      <strong>Greetings, Observer.</strong> 👋 <br>
      I am a PhD Research Scholar at <strong>Presidency University, Kolkata</strong>, investigating the underlying fabric of the cosmos.
    </p>
    <p>
      My goal? To figure out if <strong>Dark Energy</strong> is real, or if the Universe is just pranking us.
    </p>
  </div>

  <div class="section-header">
    <span class="icon">📂</span>
    <h2>Case File: Cosmology</h2>
  </div>

  <div class="content-box">
    <p>
      I employ both <strong>parametric</strong> (testing theories) and <strong>non-parametric</strong> (letting data speak) methodologies. 
      I combine rigorous math with data from distant galaxies and CMB radiation to answer one question: <em>What is the ultimate fate of the Universe?</em>
    </p>
    
    <div style="margin-top: 20px; border-top: 1px dashed #333; padding-top: 15px;">
      <strong>Key Objectives:</strong>
      <ul>
        <li><strong>Dark Energy Forensics:</strong> Reconstructing Hubble parameters to understand late-time acceleration.</li>
        <li><strong>Testing ΛCDM:</strong> The "Standard Model" is robust, but I look for the cracks using datasets like SNe Ia and DESI-BAO.</li>
        <li><strong>Model-Independent Recon:</strong> Using Machine Learning to extract cosmic signals without theoretical bias.</li>
      </ul>
    </div>
  </div>

  <div class="section-header">
    <span class="icon">🛠</span>
    <h2>The Arsenal (Methodology)</h2>
  </div>

  <div class="content-box">
    <p>
      To model the Universe, I rely on Bayesian inference and modern computation.
    </p>
    
    <div style="margin-top: 15px;">
      <span style="font-family: 'Orbitron'; font-size: 0.8em; color: #666;">// MACHINE LEARNING & STATS</span>
      <div class="tech-grid">
        <span class="tech-tag">Gaussian Processes</span>
        <span class="tech-tag">Gapp</span>
        <span class="tech-tag">tinygp</span>
        <span class="tech-tag">JAX</span>
        <span class="tech-tag">NumPyro</span>
        <span class="tech-tag">ANNs</span>
      </div>
    </div>

    <div style="margin-top: 20px;">
      <span style="font-family: 'Orbitron'; font-size: 0.8em; color: #666;">// COSMOLOGY PACKAGES</span>
      <div class="tech-grid">
        <span class="tech-tag">CLASS</span>
        <span class="tech-tag">MontePython</span>
        <span class="tech-tag">Cobaya</span>
        <span class="tech-tag">Colfi</span>
        <span class="tech-tag">emcee</span>
      </div>
    </div>
  </div>

  <div class="section-header">
    <span class="icon">🎭</span>
    <h2>Human Simulation Mode</h2>
  </div>

  <div class="warning-box">
    <span class="warning-label">STATUS: OFFLINE</span>
    <p>
      <strong>Balance is key.</strong> When the code compiles (or crashes), I switch contexts.
    </p>
    <p>
      I thrive on creativity, movement, and laughter. Inspired by the timeless humor of <strong>Charlie Chaplin</strong> and <strong>Mr. Bean</strong>, I believe that a little absurdity is necessary to understand a chaotic Universe.
    </p>
    <p>
      <strong>Current Activities:</strong><br>
      🏏 <strong>Sports:</strong> Keeping the kinetic energy high.<br>
      🎬 <strong>Cinema:</strong> From thought-provoking dramas to light-hearted comedies.<br>
      🎨 <strong>Digital Content:</strong> Blending storytelling with imagination.
    </p>
  </div>

  <div style="text-align: center; margin: 50px 0;">
    <a href="mailto:mazaharul.rs@presiuniv.ac.in" style="font-family: 'Orbitron'; border: 2px solid var(--neon-pink); padding: 10px 20px;">
      INITIATE CONTACT PROTOCOL
    </a>
  </div>

  <a href="https://github.com/maza75" class="signal-beacon" title="Github Uplink">
    <span style="color:white; font-weight:bold;">GH</span>
  </a>

</div>
