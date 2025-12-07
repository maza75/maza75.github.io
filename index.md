---
layout: home
title: Home
order: 1
---

<style>
  /* --- 🌌 FONTS & IMPORTS --- */
  @import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&family=Share+Tech+Mono&family=Rajdhani:wght@300;500;700&display=swap');

  /* --- ⚙️ SYSTEM CORE VARIABLES --- */
  :root {
    --neon-cyan: #00f3ff;
    --neon-pink: #bc13fe;
    --neon-green: #0aff0a;
    --void-bg: #050505;
    --glass-panel: rgba(13, 13, 18, 0.85); /* Slightly darker for readability */
    --border-color: rgba(255, 255, 255, 0.15);
  }

  /* --- 🚀 GLOBAL PHYSICS & RESET --- */
  * {
    box-sizing: border-box; /* Fixes sizing issues */
  }

  html {
    height: 100%;
  }

  body {
    margin: 0; padding: 0;
    width: 100%; 
    min-height: 100vh; /* Forces background to cover full screen */
    overflow-x: hidden; /* Prevents side scrolling */
    background-color: var(--void-bg);
    color: #a8b2d1;
    font-family: 'Share Tech Mono', monospace;
    
    /* 🌐 MOVING 3D GRID BACKGROUND */
    background-image: 
      linear-gradient(rgba(0, 243, 255, 0.04) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0, 243, 255, 0.04) 1px, transparent 1px);
    background-size: 50px 50px;
    background-position: center top;
  }

  /* --- 📺 CRT INTERFACE OVERLAY --- */
  body::after {
    content: " ";
    display: block;
    position: fixed; top: 0; left: 0; bottom: 0; right: 0;
    background: linear-gradient(rgba(18, 16, 16, 0) 50%, rgba(0, 0, 0, 0.1) 50%), 
                linear-gradient(90deg, rgba(255, 0, 0, 0.03), rgba(0, 255, 0, 0.01), rgba(0, 0, 255, 0.03));
    z-index: 9999;
    background-size: 100% 3px, 3px 100%;
    pointer-events: none;
  }

  /* --- 📐 DYNAMIC WRAPPER (FULL SCREEN ENGINE) --- */
  .wrapper {
    width: 96%;        /* Covers 96% of the screen width */
    max-width: 1600px; /* Cap it at 1600px for ultra-wide monitors */
    margin: 0 auto;    /* Centers it */
    padding: 0;
    position: relative;
    z-index: 2;
    padding-bottom: 100px; /* Space for footer */
  }

  /* --- 🎛️ HUD STATUS BAR (Stretches Full Width) --- */
  .hud-bar {
    display: flex;
    justify-content: space-between;
    padding: 15px 20px;
    border-bottom: 1px solid var(--border-color);
    background: rgba(0,0,0,0.6);
    backdrop-filter: blur(5px);
    font-family: 'Orbitron', sans-serif;
    font-size: 0.8rem;
    letter-spacing: 2px;
    color: #777;
    margin-bottom: 50px;
    width: 100%;
  }
  .hud-item { display: flex; align-items: center; gap: 10px; }
  .status-dot { width: 8px; height: 8px; background: var(--neon-green); border-radius: 50%; box-shadow: 0 0 10px var(--neon-green); }
  .status-alert { width: 8px; height: 8px; background: red; border-radius: 50%; animation: blink 1s infinite; }

  /* --- 🧪 TYPOGRAPHY --- */
  h1 {
    font-family: 'Orbitron', sans-serif;
    font-weight: 900;
    /* DYNAMIC FONT SIZING: Fits any screen */
    font-size: clamp(2.5rem, 6vw, 5.5rem); 
    line-height: 0.9;
    margin-bottom: 15px;
    color: #fff;
    text-transform: uppercase;
    position: relative;
    text-shadow: 3px 3px 0px var(--neon-pink);
    letter-spacing: -2px;
  }

  h2 {
    font-family: 'Rajdhani', sans-serif;
    font-size: clamp(1.8rem, 4vw, 2.5rem);
    color: #fff;
    border-bottom: 2px solid var(--neon-cyan);
    display: inline-block;
    padding-bottom: 5px;
    margin-top: 60px;
    margin-bottom: 30px;
    text-transform: uppercase;
  }

  p { font-size: 1.15rem; line-height: 1.7; color: #b4c0d6; max-width: 900px; /* Keeps text readable on wide screens */ }
  strong { color: var(--neon-cyan); }
  a { color: var(--neon-pink); text-decoration: none; border-bottom: 1px dashed var(--neon-pink); transition: 0.3s; }
  a:hover { background: var(--neon-pink); color: #fff; border-bottom: none; box-shadow: 0 0 15px var(--neon-pink); }

  /* --- ⚡ GLITCH EFFECT --- */
  .glitch { position: relative; color: white; }
  .glitch::before, .glitch::after {
    content: attr(data-text); position: absolute; top: 0; left: 0; width: 100%; height: 100%; background: var(--void-bg);
  }
  .glitch::before { left: 2px; text-shadow: -1px 0 red; clip: rect(24px, 550px, 90px, 0); animation: glitch-anim-2 3s infinite linear alternate-reverse; }
  .glitch::after { left: -2px; text-shadow: -1px 0 blue; clip: rect(85px, 550px, 140px, 0); animation: glitch-anim 2.5s infinite linear alternate-reverse; }
  @keyframes glitch-anim { 0% { clip: rect(14px, 9999px, 121px, 0); } 100% { clip: rect(69px, 9999px, 34px, 0); } }
  @keyframes glitch-anim-2 { 0% { clip: rect(129px, 9999px, 36px, 0); } 100% { clip: rect(2px, 9999px, 86px, 0); } }

  /* --- 📂 HOLOGRAPHIC PANELS (Full Width) --- */
  .holo-card {
    background: var(--glass-panel);
    border: 1px solid var(--border-color);
    padding: 40px;
    border-radius: 6px;
    position: relative;
    backdrop-filter: blur(12px);
    box-shadow: 0 0 30px rgba(0,0,0,0.6);
    transition: transform 0.3s, border-color 0.3s;
    overflow: hidden;
    width: 100%; /* Ensures it fills the wrapper */
  }
  .holo-card:hover { transform: translateY(-3px); border-color: rgba(0, 243, 255, 0.4); box-shadow: 0 10px 40px rgba(0, 243, 255, 0.15); }
  
  /* Corner Accents */
  .holo-card::before { content: ''; position: absolute; top: 0; left: 0; width: 30px; height: 30px; border-top: 3px solid var(--neon-cyan); border-left: 3px solid var(--neon-cyan); }
  .holo-card::after { content: ''; position: absolute; bottom: 0; right: 0; width: 30px; height: 30px; border-bottom: 3px solid var(--neon-cyan); border-right: 3px solid var(--neon-cyan); }

  /* --- 🧬 TECH GRID --- */
  .tech-wrapper { display: grid; grid-template-columns: repeat(auto-fit, minmax(140px, 1fr)); gap: 15px; margin-top: 25px; }
  .tech-node { background: rgba(255,255,255,0.03); border: 1px solid #333; padding: 12px; text-align: center; font-size: 1rem; color: var(--neon-cyan); transition: 0.2s; cursor: crosshair; }
  .tech-node:hover { background: var(--neon-cyan); color: #000; box-shadow: 0 0 20px var(--neon-cyan); }

  /* --- 🤣 HAZARD ZONE --- */
  .hazard-zone {
    background: repeating-linear-gradient(45deg, #1a1a1a, #1a1a1a 10px, #222 10px, #222 20px);
    border: 2px dashed #ff9f43; padding: 40px; margin-top: 60px; text-align: center; position: relative;
  }
  .hazard-title { background: #ff9f43; color: #000; padding: 5px 20px; font-family: 'Orbitron'; font-weight: bold; position: absolute; top: -18px; left: 50%; transform: translateX(-50%); letter-spacing: 2px; }

  /* --- 🕹️ BUTTONS --- */
  .btn-container { display: flex; gap: 30px; justify-content: center; flex-wrap: wrap; margin-top: 40px; }
  
  .btn-main {
    display: inline-block;
    padding: 20px 40px;
    border: 2px solid var(--neon-pink);
    color: var(--neon-pink);
    font-family: 'Orbitron';
    text-transform: uppercase;
    letter-spacing: 2px;
    font-size: 1rem;
    font-weight: bold;
    position: relative;
    overflow: hidden;
    z-index: 1;
    transition: 0.3s;
    text-decoration: none;
    border-bottom: 4px solid var(--neon-pink);
    background: rgba(0,0,0,0.6);
  }
  .btn-main:hover { color: #fff; background: var(--neon-pink); box-shadow: 0 0 40px var(--neon-pink); transform: translateY(-2px); }
  
  .btn-blue { border-color: var(--neon-cyan); color: var(--neon-cyan); border-bottom: 4px solid var(--neon-cyan); }
  .btn-blue:hover { background: var(--neon-cyan); color: #000; box-shadow: 0 0 40px var(--neon-cyan); }

  /* --- 🔮 BLING BLING EMAIL ORB --- */
  .email-orb {
    position: fixed;
    bottom: 40px; right: 40px;
    width: 80px; height: 80px;
    border-radius: 50%;
    background: radial-gradient(circle at 30% 30%, #ff55ff, #ff00ff, #aa00aa);
    border: 3px solid #fff;
    display: flex; align-items: center; justify-content: center;
    box-shadow: 0 0 30px #ff00ff, inset 0 0 10px #fff;
    z-index: 9999;
    animation: orb-pulse 2s infinite ease-in-out;
    transition: transform 0.3s;
  }
  .email-orb:hover { transform: scale(1.15) rotate(10deg); cursor: pointer; }
  .email-orb svg { width: 40px; height: 40px; fill: white; filter: drop-shadow(0 0 5px rgba(0,0,0,0.5)); }
  .email-orb::before {
    content: ''; position: absolute; top: -15px; left: -15px; right: -15px; bottom: -15px;
    border-radius: 50%; border: 2px solid #ff00ff;
    animation: ripple-wave 1.5s infinite linear; opacity: 0;
  }

  @keyframes orb-pulse { 0%, 100% { box-shadow: 0 0 20px #ff00ff; } 50% { box-shadow: 0 0 60px #ff00ff, 0 0 15px #fff; } }
  @keyframes ripple-wave { 0% { transform: scale(0.5); opacity: 1; } 100% { transform: scale(1.5); opacity: 0; } }

  /* --- 📱 MOBILE OPTIMIZATION --- */
  @media screen and (max-width: 768px) {
    .wrapper { width: 92%; padding-bottom: 80px; } /* More width on mobile */
    .hud-bar { padding: 10px; font-size: 0.6rem; flex-wrap: wrap; justify-content: center; gap: 10px; text-align: center; }
    .holo-card { padding: 20px; }
    .btn-container { flex-direction: column; width: 100%; gap: 15px; }
    .btn-main { width: 100%; text-align: center; padding: 15px; }
    .email-orb { bottom: 20px; right: 20px; width: 60px; height: 60px; }
    .email-orb svg { width: 30px; height: 30px; }
    h1 { margin-top: 10px; }
  }
  @keyframes blink { 0%, 100% { opacity: 1; } 50% { opacity: 0; } }
</style>

<div class="wrapper">

  <div class="hud-bar">
    <div class="hud-item"><div class="status-dot"></div> SYSTEM: ONLINE</div>
    <div class="hud-item">LOC: EARTH-982 (Kolkata)</div>
    <div class="hud-item"><div class="status-alert"></div> CAFFEINE: CRITICAL</div>
  </div>

  <div style="margin-bottom: 80px;">
    <h1 class="glitch" data-text="MAZAHARUL ABEDIN">MAZAHARUL ABEDIN</h1>
    
    <p style="border-left: 4px solid var(--neon-pink); padding-left: 20px; font-size: clamp(1rem, 2vw, 1.4rem); color: #fff; margin-top: 20px;">
      > PhD Research Scholar | Cosmetic Architect | Void Stare-er<br>
      > Investigating <strong>Dark Energy</strong> & <strong>Cosmic Expansion</strong>
    </p>

    <div class="holo-card" style="margin-top: 40px;">
      <p style="margin: 0;">
        <strong>// INITIALIZING GREETING PROTOCOL...</strong><br><br>
        Operating out of the <strong>Department of Mathematics, Presidency University</strong> under the command of <strong>Dr. Supriya Pan</strong>. 
        I combine Theoretical Physics with Astronomical Observations to ask the Universe why it is running away from us so fast.
      </p>
    </div>
  </div>

  <section>
    <h2><span style="color:var(--neon-cyan)">01.</span> CASE FILE: COSMOLOGY</h2>
    
    <div class="holo-card">
      <p>
        I employ both <strong>parametric</strong> (testing theories) and <strong>non-parametric</strong> (letting data speak) methodologies.
        

[Image of cosmic expansion timeline]

      </p>
      
      <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 30px; margin-top: 30px;">
        <div style="border: 1px dashed #444; padding: 20px; background: rgba(0,0,0,0.3);">
          <strong style="color:var(--neon-pink); font-size: 1.2rem;">TARGET: Dark Energy</strong>
          <p style="font-size: 1rem; margin-top: 10px;">Reconstructing Hubble parameters to understand late-time acceleration.</p>
        </div>
        <div style="border: 1px dashed #444; padding: 20px; background: rgba(0,0,0,0.3);">
          <strong style="color:var(--neon-pink); font-size: 1.2rem;">TARGET: ΛCDM</strong>
          <p style="font-size: 1rem; margin-top: 10px;">Hunting for cracks in the standard model using SNe Ia & DESI-BAO data.</p>
        </div>
      </div>
    </div>
  </section>

  <section>
    <h2><span style="color:var(--neon-cyan)">02.</span> THE ARSENAL</h2>
    <div class="holo-card">
      <p style="font-family: 'Orbitron'; color: #888; font-size: 0.9rem; margin-bottom: 5px;">// LOAD MODULE: MACHINE_LEARNING</p>
      <div class="tech-wrapper">
        <div class="tech-node">Gaussian Proc</div>
        <div class="tech-node">Gapp</div>
        <div class="tech-node">JAX</div>
        <div class="tech-node">NumPyro</div>
        <div class="tech-node">ANNs</div>
        <div class="tech-node">tinygp</div>
      </div>
      <div style="height: 30px;"></div>
      <p style="font-family: 'Orbitron'; color: #888; font-size: 0.9rem; margin-bottom: 5px;">// LOAD MODULE: COSMOLOGY_SIMS</p>
      <div class="tech-wrapper">
        <div class="tech-node">CLASS</div>
        <div class="tech-node">MontePython</div>
        <div class="tech-node">Cobaya</div>
        <div class="tech-node">emcee</div>
        <div class="tech-node">Colfi</div>
      </div>
    </div>
  </section>

  <section>
    <div class="hazard-zone">
      <span class="hazard-title">⚠ HUMAN SIMULATION MODE ⚠</span>
      <p style="color: #ff9f43; font-size: 1.2rem; margin-bottom: 20px;">
        <strong>System Warning:</strong> Prolonged exposure to Friedmann equations may cause hallucinations.
      </p>
      <div style="margin-top: 30px; display: flex; justify-content: center; gap: 20px; flex-wrap: wrap;">
        <span style="border: 1px solid #ff9f43; padding: 8px 20px; color: #ff9f43; letter-spacing: 1px;">🏏 CRICKET</span>
        <span style="border: 1px solid #ff9f43; padding: 8px 20px; color: #ff9f43; letter-spacing: 1px;">🎬 CINEMA</span>
        <span style="border: 1px solid #ff9f43; padding: 8px 20px; color: #ff9f43; letter-spacing: 1px;">🎨 DESIGN</span>
      </div>
    </div>
  </section>

  <div style="text-align: center; margin: 100px 0;">
    <p style="font-family: 'Orbitron'; margin-bottom: 10px; color: #666; letter-spacing: 3px;">// SYSTEM NAVIGATION //</p>
    
    <div class="btn-container">
      <a href="/publications/" class="btn-main">
        ACCESS PUBLICATIONS
      </a>
      <a href="/gallery/" class="btn-main btn-blue">
        VISUAL DATA (GALLERY)
      </a>
    </div>

    <br><br>
    <p style="font-size: 0.8rem; color: #444; margin-top: 40px;">// END OF TRANSMISSION //</p>
  </div>

  <a href="mailto:mazaharul.rs@presiuniv.ac.in" class="email-orb" title="Initiate Contact">
    <svg viewBox="0 0 24 24">
      <path d="M20,4H4C2.9,4,2,4.9,2,6v12c0,1.1,0.9,2,2,2h16c1.1,0,2-0.9,2-2V6C22,4.9,21.1,4,20,4z M20,8l-8,5L4,8V6l8,5l8-5V8z"/>
    </svg>
  </a>

</div>
