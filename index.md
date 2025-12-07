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
    --void-bg: #0f172a; /* Deep blue-grey instead of black */
    --glass-panel: rgba(15, 23, 42, 0.6); /* Adjusted for new bg */
    --border-color: rgba(255, 255, 255, 0.1);
    --bg-gradient-start: #0f172a;
    --bg-gradient-end: #1e1b4b; /* Indigo */
  }

  /* --- 🚀 GLOBAL PHYSICS --- */
  * { box-sizing: border-box; }
  
  html, body {
    margin: 0; padding: 0;
    width: 100%; min-height: 100vh;
    overflow-x: hidden;
    background: linear-gradient(135deg, var(--bg-gradient-start) 0%, var(--bg-gradient-end) 100%);
    color: #cbd5e1; /* Lighter text for contrast */
    font-family: 'Share Tech Mono', monospace;
  }

  /* --- 🌐 MOVING 3D GRID BACKGROUND --- */
  body::before {
    content: "";
    position: fixed; top: 0; left: 0; width: 200%; height: 200%;
    background-image: 
      linear-gradient(rgba(0, 243, 255, 0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0, 243, 255, 0.03) 1px, transparent 1px);
    background-size: 60px 60px;
    transform: perspective(500px) rotateX(60deg) translateY(-100px) translateZ(-200px);
    animation: grid-move 20s linear infinite;
    z-index: -2;
    pointer-events: none;
  }

  @keyframes grid-move { 
    0% { transform: perspective(500px) rotateX(60deg) translateY(0); } 
    100% { transform: perspective(500px) rotateX(60deg) translateY(60px); } 
  }

  /* --- 📺 CRT INTERFACE OVERLAY (Subtler) --- */
  body::after {
    content: " ";
    display: block;
    position: fixed; top: 0; left: 0; bottom: 0; right: 0;
    background: linear-gradient(rgba(18, 16, 16, 0) 50%, rgba(0, 0, 0, 0.05) 50%), 
                linear-gradient(90deg, rgba(255, 0, 0, 0.03), rgba(0, 255, 0, 0.01), rgba(0, 0, 255, 0.03));
    z-index: 9999;
    background-size: 100% 3px, 3px 100%;
    pointer-events: none;
  }

  /* --- 📐 DYNAMIC WRAPPER --- */
  .wrapper {
    width: 94%;
    max-width: 1400px;
    margin: 0 auto;
    padding: 20px 0 100px 0;
    position: relative;
    z-index: 2;
  }

  /* --- 🎛️ HUD STATUS BAR --- */
  .hud-bar {
    display: flex;
    justify-content: space-between;
    padding: 12px 20px;
    border-bottom: 1px solid var(--border-color);
    background: rgba(15, 23, 42, 0.8);
    backdrop-filter: blur(8px);
    font-family: 'Orbitron', sans-serif;
    font-size: 0.75rem;
    color: #94a3b8;
    margin-bottom: 60px;
    border-radius: 0 0 10px 10px;
  }
  .hud-item { display: flex; align-items: center; gap: 8px; }
  .status-dot { width: 6px; height: 6px; background: var(--neon-green); border-radius: 50%; box-shadow: 0 0 8px var(--neon-green); }
  .status-alert { width: 6px; height: 6px; background: #ef4444; border-radius: 50%; animation: blink 1.5s infinite; }

  /* --- 🧪 TYPOGRAPHY --- */
  h1 {
    font-family: 'Orbitron', sans-serif;
    font-weight: 900;
    font-size: clamp(2.5rem, 5vw, 4.5rem); 
    line-height: 1.1;
    margin-bottom: 10px;
    color: #f8fafc;
    text-transform: uppercase;
    text-shadow: 0 0 20px rgba(188, 19, 254, 0.4);
  }

  h2 {
    font-family: 'Rajdhani', sans-serif;
    font-size: clamp(1.8rem, 3.5vw, 2.5rem);
    color: #e2e8f0;
    border-bottom: 2px solid var(--neon-cyan);
    display: inline-block;
    padding-bottom: 5px;
    margin-top: 80px;
    margin-bottom: 40px;
    letter-spacing: 1px;
  }

  p { font-size: 1.1rem; line-height: 1.8; color: #cbd5e1; max-width: 800px; }
  strong { color: var(--neon-cyan); }
  a { color: var(--neon-pink); text-decoration: none; border-bottom: 1px dashed var(--neon-pink); transition: 0.3s; }
  a:hover { background: var(--neon-pink); color: #fff; border-bottom: none; }

  /* --- ⚡ GLITCH EFFECT --- */
  .glitch { position: relative; color: white; }
  .glitch::before, .glitch::after {
    content: attr(data-text); position: absolute; top: 0; left: 0; width: 100%; height: 100%; background: transparent;
  }
  .glitch::before { left: 2px; text-shadow: -1px 0 #ef4444; clip: rect(24px, 550px, 90px, 0); animation: glitch-anim-2 4s infinite linear alternate-reverse; }
  .glitch::after { left: -2px; text-shadow: -1px 0 #3b82f6; clip: rect(85px, 550px, 140px, 0); animation: glitch-anim 3s infinite linear alternate-reverse; }
  @keyframes glitch-anim { 0% { clip: rect(14px, 9999px, 121px, 0); } 100% { clip: rect(69px, 9999px, 34px, 0); } }
  @keyframes glitch-anim-2 { 0% { clip: rect(129px, 9999px, 36px, 0); } 100% { clip: rect(2px, 9999px, 86px, 0); } }

  /* --- 📂 HOLOGRAPHIC PANELS --- */
  .holo-card {
    background: var(--glass-panel);
    border: 1px solid var(--border-color);
    padding: 35px;
    border-radius: 12px;
    position: relative;
    backdrop-filter: blur(16px);
    box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
    transition: transform 0.3s ease, border-color 0.3s ease;
    width: 100%;
  }
  .holo-card:hover { 
    transform: translateY(-5px); 
    border-color: rgba(0, 243, 255, 0.5); 
    box-shadow: 0 10px 40px rgba(0, 243, 255, 0.1); 
  }
  .holo-card::before { content: ''; position: absolute; top: 0; left: 0; width: 20px; height: 20px; border-top: 2px solid var(--neon-cyan); border-left: 2px solid var(--neon-cyan); border-radius: 12px 0 0 0; }
  .holo-card::after { content: ''; position: absolute; bottom: 0; right: 0; width: 20px; height: 20px; border-bottom: 2px solid var(--neon-cyan); border-right: 2px solid var(--neon-cyan); border-radius: 0 0 12px 0; }

  /* --- 🤡 PROFILE IMAGE --- */
  .profile-container {
    width: 200px; height: 200px;
    margin: 0 auto 30px auto;
    position: relative;
    border-radius: 50%; 
    border: 3px solid var(--neon-cyan);
    box-shadow: 0 0 25px rgba(0, 243, 255, 0.3);
    overflow: hidden;
    background: #0f172a;
    animation: float 6s ease-in-out infinite;
  }
  .profile-pic {
    width: 100%; height: 100%;
    object-fit: cover;
    filter: contrast(1.1) saturate(1.2);
    transition: transform 0.6s cubic-bezier(0.34, 1.56, 0.64, 1);
  }
  .profile-container:hover .profile-pic { transform: rotate(10deg) scale(1.1); filter: hue-rotate(15deg); }
  @keyframes float { 0%, 100% { transform: translateY(0); } 50% { transform: translateY(-10px); } }

  /* --- 🧬 TECH GRID --- */
  .tech-wrapper { display: flex; flex-wrap: wrap; gap: 12px; margin-top: 25px; }
  .tech-node { 
    background: rgba(30, 41, 59, 0.5); 
    border: 1px solid rgba(255,255,255,0.1); 
    padding: 8px 16px; 
    text-align: center; 
    font-size: 0.9rem; 
    color: var(--neon-cyan); 
    transition: 0.2s; 
    cursor: default;
    border-radius: 4px;
  }
  .tech-node:hover { background: rgba(0, 243, 255, 0.1); border-color: var(--neon-cyan); color: #fff; box-shadow: 0 0 15px rgba(0, 243, 255, 0.2); }

  /* --- 🤣 HAZARD ZONE --- */
  .hazard-zone {
    background: repeating-linear-gradient(45deg, rgba(30, 41, 59, 0.5), rgba(30, 41, 59, 0.5) 10px, rgba(15, 23, 42, 0.5) 10px, rgba(15, 23, 42, 0.5) 20px);
    border: 1px dashed #ff9f43; padding: 40px; margin-top: 80px; text-align: center; position: relative; border-radius: 8px;
  }
  .hazard-title { background: #ff9f43; color: #0f172a; padding: 4px 16px; font-family: 'Orbitron'; font-weight: bold; font-size: 0.8rem; position: absolute; top: -14px; left: 50%; transform: translateX(-50%); letter-spacing: 1px; border-radius: 4px; }

  /* --- 🕹️ NAV BUTTONS --- */
  .nav-deck { text-align: center; margin: 100px 0 50px 0; }
  .btn-container { display: flex; gap: 20px; justify-content: center; flex-wrap: wrap; margin-top: 30px; }
  
  .btn-main {
    display: inline-block;
    padding: 16px 32px;
    border: 1px solid var(--neon-pink);
    color: var(--neon-pink);
    font-family: 'Orbitron';
    text-transform: uppercase;
    letter-spacing: 1px;
    font-size: 0.9rem;
    font-weight: bold;
    position: relative;
    overflow: hidden;
    z-index: 1;
    transition: 0.3s;
    text-decoration: none;
    background: rgba(15, 23, 42, 0.8);
    border-radius: 4px;
  }
  .btn-main:hover { color: #fff; background: var(--neon-pink); box-shadow: 0 0 25px rgba(188, 19, 254, 0.4); transform: translateY(-2px); border-color: var(--neon-pink); }
  
  .btn-blue { border-color: var(--neon-cyan); color: var(--neon-cyan); }
  .btn-blue:hover { background: var(--neon-cyan); color: #0f172a; box-shadow: 0 0 25px rgba(0, 243, 255, 0.4); border-color: var(--neon-cyan); }

  /* --- 🔮 EMAIL ORB --- */
  .email-orb {
    position: fixed; bottom: 30px; right: 30px;
    width: 60px; height: 60px;
    border-radius: 50%;
    background: linear-gradient(135deg, var(--neon-pink), #a855f7);
    display: flex; align-items: center; justify-content: center;
    box-shadow: 0 4px 20px rgba(188, 19, 254, 0.4);
    z-index: 9999;
    animation: float-orb 4s ease-in-out infinite;
    transition: transform 0.3s;
    border: 2px solid rgba(255,255,255,0.2);
  }
  .email-orb:hover { transform: scale(1.1) rotate(15deg); cursor: pointer; }
  .email-orb svg { width: 28px; height: 28px; fill: white; }
  @keyframes float-orb { 0%, 100% { transform: translateY(0); } 50% { transform: translateY(-8px); } }

  /* --- 📱 MOBILE OPTIMIZATION --- */
  @media screen and (max-width: 768px) {
    .hud-bar { flex-direction: column; gap: 8px; text-align: center; }
    .holo-card { padding: 25px; }
    .btn-container { flex-direction: column; width: 100%; gap: 15px; }
    .btn-main { width: 100%; text-align: center; }
    h1 { font-size: 2.2rem; }
    h2 { margin-top: 60px; font-size: 1.8rem; }
  }
  @keyframes blink { 0%, 100% { opacity: 1; } 50% { opacity: 0.5; } }
</style>

<div class="wrapper">

  <div class="hud-bar">
    <div class="hud-item"><div class="status-dot"></div> SYSTEM: ONLINE</div>
    <div class="hud-item">LOC: EARTH-982 (Kolkata)</div>
    <div class="hud-item"><div class="status-alert"></div> CAFFEINE: CRITICAL</div>
  </div>

  <div style="margin-bottom: 80px; text-align: center;">
    
    <div class="profile-container">
      <img src="Mazaharul-Abedin.png" alt="Mazaharul Abedin" class="profile-pic">
    </div>

    <h1 class="glitch" data-text="MAZAHARUL ABEDIN">MAZAHARUL ABEDIN</h1>
    
    <div style="display: inline-block; border-left: 3px solid var(--neon-pink); padding-left: 15px; margin-top: 20px; text-align: left;">
      <p style="margin: 0; color: #e2e8f0; font-size: 1.1rem;">
        > PhD Research Scholar | Cosmetic Architect | Void Stare-er<br>
        > Investigating <strong>Dark Energy</strong> & <strong>Cosmic Expansion</strong>
      </p>
    </div>

    <div class="holo-card" style="margin-top: 50px; text-align: left;">
      <p style="margin: 0;">
        <strong style="font-family: 'Orbitron'; letter-spacing: 1px;">// INITIALIZING GREETING PROTOCOL...</strong><br><br>
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
      </p>
      

[Image of cosmic expansion timeline]

      
      <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 20px; margin-top: 30px;">
        <div style="border: 1px dashed rgba(255,255,255,0.2); padding: 20px; background: rgba(15, 23, 42, 0.4); border-radius: 8px;">
          <strong style="color:var(--neon-pink); font-family: 'Orbitron'; font-size: 0.9rem; letter-spacing: 1px;">TARGET: Dark Energy</strong>
          <p style="font-size: 0.95rem; margin-top: 10px; color: #cbd5e1;">Reconstructing Hubble parameters to understand late-time acceleration.</p>
        </div>
        <div style="border: 1px dashed rgba(255,255,255,0.2); padding: 20px; background: rgba(15, 23, 42, 0.4); border-radius: 8px;">
          <strong style="color:var(--neon-pink); font-family: 'Orbitron'; font-size: 0.9rem; letter-spacing: 1px;">TARGET: ΛCDM</strong>
          <p style="font-size: 0.95rem; margin-top: 10px; color: #cbd5e1;">Hunting for cracks in the standard model using SNe Ia & DESI-BAO data.</p>
        </div>
      </div>
    </div>
  </section>

  <section>
    <h2><span style="color:var(--neon-cyan)">02.</span> THE ARSENAL</h2>
    <div class="holo-card">
      <p style="font-family: 'Orbitron'; color: #64748b; font-size: 0.8rem; margin-bottom: 10px;">// LOAD MODULE: MACHINE_LEARNING</p>
      <div class="tech-wrapper">
        <div class="tech-node">Gaussian Proc</div>
        <div class="tech-node">Gapp</div>
        <div class="tech-node">JAX</div>
        <div class="tech-node">NumPyro</div>
        <div class="tech-node">ANNs</div>
        <div class="tech-node">tinygp</div>
      </div>
      <div style="height: 30px;"></div>
      <p style="font-family: 'Orbitron'; color: #64748b; font-size: 0.8rem; margin-bottom: 10px;">// LOAD MODULE: COSMOLOGY_SIMS</p>
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
      <p style="color: #ff9f43; font-size: 1.1rem; margin-bottom: 20px;">
        <strong>System Warning:</strong> Prolonged exposure to Friedmann equations may cause hallucinations.
      </p>
      <div style="margin-top: 20px; display: flex; justify-content: center; gap: 15px; flex-wrap: wrap;">
        <span style="border: 1px solid #ff9f43; padding: 6px 16px; color: #ff9f43; letter-spacing: 1px; font-size: 0.9rem; border-radius: 4px;">🏏 CRICKET</span>
        <span style="border: 1px solid #ff9f43; padding: 6px 16px; color: #ff9f43; letter-spacing: 1px; font-size: 0.9rem; border-radius: 4px;">🎬 CINEMA</span>
        <span style="border: 1px solid #ff9f43; padding: 6px 16px; color: #ff9f43; letter-spacing: 1px; font-size: 0.9rem; border-radius: 4px;">🎨 DESIGN</span>
      </div>
    </div>
  </section>

  <div class="nav-deck">
    <p style="font-family: 'Orbitron'; margin-bottom: 10px; color: #64748b; letter-spacing: 3px; font-size: 0.8rem;">// SYSTEM NAVIGATION //</p>
    
    <div class="btn-container">
      <a href="/publications/" class="btn-main">
        ACCESS PUBLICATIONS
      </a>
      
      <a href="/gallery/" class="btn-main btn-blue">
        VISUAL DATA (GALLERY)
      </a>
    </div>

    <p style="font-size: 0.8rem; color: #475569; margin-top: 50px;">// END OF TRANSMISSION //</p>
  </div>

  <a href="mailto:mazaharul.rs@presiuniv.ac.in" class="email-orb" title="Initiate Contact">
    <svg viewBox="0 0 24 24">
      <path d="M20,4H4C2.9,4,2,4.9,2,6v12c0,1.1,0.9,2,2,2h16c1.1,0,2-0.9,2-2V6C22,4.9,21.1,4,20,4z M20,8l-8,5L4,8V6l8,5l8-5V8z"/>
    </svg>
  </a>

</div>
