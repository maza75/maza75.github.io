---
layout: home
title: Home
order: 1
---

<style>
  @import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@500;700;900&family=Rajdhani:wght@400;600&family=JetBrains+Mono:wght@400;700&display=swap');

  /* --- 🌌 SYSTEM PALETTE (Not Black, but Deep Space) --- */
  :root {
    --bg-deep: #0f172a;
    --bg-gradient: linear-gradient(135deg, #0f172a 0%, #1e1b4b 100%);
    --glass-surface: rgba(30, 41, 59, 0.7);
    --glass-border: rgba(124, 58, 237, 0.3);
    --neon-cyan: #22d3ee;
    --neon-purple: #c084fc;
    --neon-alert: #f472b6;
    --text-main: #cbd5e1;
  }

  /* --- 🚀 GLOBAL PHYSICS --- */
  html, body {
    margin: 0; padding: 0;
    width: 100%; min-height: 100vh;
    font-family: 'Rajdhani', sans-serif;
    background: var(--bg-gradient);
    color: var(--text-main);
    overflow-x: hidden;
  }

  /* --- 🌐 MOVING WARP GRID BACKGROUND --- */
  body::before {
    content: "";
    position: fixed; top: 0; left: 0; width: 200%; height: 200%;
    background-image: 
      linear-gradient(rgba(56, 189, 248, 0.07) 1px, transparent 1px),
      linear-gradient(90deg, rgba(56, 189, 248, 0.07) 1px, transparent 1px);
    background-size: 60px 60px;
    transform: perspective(500px) rotateX(60deg) translateY(-100px) translateZ(-200px);
    animation: grid-move 20s linear infinite;
    z-index: -2;
    pointer-events: none;
  }

  @keyframes grid-move { 0% { transform: perspective(500px) rotateX(60deg) translateY(0); } 100% { transform: perspective(500px) rotateX(60deg) translateY(60px); } }

  /* --- 🧬 LAYOUT CONTAINER --- */
  .wrapper {
    max-width: 1300px;
    margin: 0 auto;
    padding: 20px;
    position: relative;
    z-index: 2;
  }

  /* --- 🧪 TYPOGRAPHY --- */
  h1, h2, h3 { font-family: 'Orbitron', sans-serif; text-transform: uppercase; letter-spacing: 2px; }
  
  h2 { 
    border-bottom: 2px solid var(--neon-purple); 
    display: inline-block; 
    padding-bottom: 5px; 
    color: #fff;
    margin-top: 60px;
    font-size: 2rem;
    text-shadow: 0 0 15px rgba(192, 132, 252, 0.5);
  }

  p { font-size: 1.2rem; line-height: 1.6; }
  strong { color: var(--neon-cyan); }

  /* --- 🛸 HERO INTERFACE --- */
  .hero-grid {
    display: grid;
    grid-template-columns: 1fr;
    gap: 40px;
    background: var(--glass-surface);
    backdrop-filter: blur(12px);
    border: 1px solid var(--glass-border);
    border-radius: 20px;
    padding: 40px;
    margin-top: 40px;
    box-shadow: 0 20px 50px rgba(0,0,0,0.5);
    position: relative;
    overflow: hidden;
  }

  /* Glowing Top Bar */
  .hero-grid::before {
    content: ""; position: absolute; top: 0; left: 0; width: 100%; height: 4px;
    background: linear-gradient(90deg, var(--neon-cyan), var(--neon-purple));
  }

  @media screen and (min-width: 900px) {
    .hero-grid { 
      grid-template-columns: 300px 1fr; /* Image Left, Text Right */
      align-items: center;
      text-align: left;
    }
  }

  /* --- 🤡 HEXAGON PROFILE IMAGE --- */
  .hex-container {
    width: 250px; height: 250px;
    margin: 0 auto;
    position: relative;
    clip-path: polygon(50% 0%, 100% 25%, 100% 75%, 50% 100%, 0% 75%, 0% 25%);
    background: var(--neon-cyan);
    padding: 4px; /* Border thickness */
    transition: transform 0.5s;
  }
  
  .hex-container:hover { transform: scale(1.05) rotate(5deg); }

  .profile-pic {
    width: 100%; height: 100%;
    object-fit: cover;
    clip-path: polygon(50% 0%, 100% 25%, 100% 75%, 50% 100%, 0% 75%, 0% 25%);
    background: #000;
    filter: contrast(1.1) saturate(1.2); /* Comic Book Style */
  }

  /* --- 📜 TYPEWRITER TEXT --- */
  .typewriter {
    font-family: 'JetBrains Mono', monospace;
    color: var(--neon-purple);
    font-size: 1.1rem;
    background: rgba(0,0,0,0.3);
    padding: 10px;
    border-radius: 5px;
    display: inline-block;
    border-left: 3px solid var(--neon-cyan);
  }

  /* --- 📂 INFO MODULES (Cards) --- */
  .module-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 25px;
    margin-top: 30px;
  }

  .data-module {
    background: rgba(255,255,255,0.03);
    border: 1px solid rgba(255,255,255,0.1);
    border-radius: 12px;
    padding: 25px;
    transition: 0.3s;
    position: relative;
  }

  .data-module:hover {
    background: rgba(255,255,255,0.06);
    border-color: var(--neon-cyan);
    transform: translateY(-5px);
    box-shadow: 0 10px 30px rgba(34, 211, 238, 0.15);
  }

  .module-header {
    font-family: 'JetBrains Mono';
    font-size: 0.8rem;
    color: #666;
    letter-spacing: 2px;
    margin-bottom: 10px;
    display: block;
  }

  /* --- 🛠 TECH CHIPS --- */
  .chip-container { display: flex; flex-wrap: wrap; gap: 10px; justify-content: center; }
  .tech-chip {
    background: rgba(192, 132, 252, 0.1);
    border: 1px solid var(--neon-purple);
    color: var(--neon-purple);
    padding: 5px 15px;
    border-radius: 20px;
    font-size: 0.9rem;
    font-family: 'JetBrains Mono';
    cursor: default;
    transition: 0.2s;
  }
  .tech-chip:hover { background: var(--neon-purple); color: #fff; box-shadow: 0 0 15px var(--neon-purple); }

  /* --- 🕹️ BUTTONS --- */
  .cyber-btn {
    display: inline-block;
    background: transparent;
    color: #fff;
    font-family: 'Orbitron';
    padding: 15px 30px;
    border: 2px solid var(--neon-cyan);
    text-decoration: none;
    text-transform: uppercase;
    letter-spacing: 2px;
    position: relative;
    overflow: hidden;
    transition: 0.3s;
    margin-top: 20px;
    z-index: 1;
  }
  
  .cyber-btn::before {
    content: ""; position: absolute; top: 0; left: -100%; width: 100%; height: 100%;
    background: var(--neon-cyan); z-index: -1; transition: 0.3s;
  }
  
  .cyber-btn:hover::before { left: 0; }
  .cyber-btn:hover { color: #000; box-shadow: 0 0 30px var(--neon-cyan); }

  /* --- 🤣 SYSTEM ERROR BOX --- */
  .error-box {
    background: #2a0a18;
    border: 2px dashed var(--neon-alert);
    color: var(--neon-alert);
    padding: 30px;
    text-align: center;
    border-radius: 10px;
    margin-top: 60px;
    position: relative;
  }
  .error-box::after {
    content: "⚠ CRITICAL HUMOR FAILURE ⚠";
    position: absolute; top: -12px; left: 50%; transform: translateX(-50%);
    background: var(--neon-alert); color: #000; padding: 2px 10px; font-weight: bold; font-family: 'Orbitron';
  }

  /* --- 📡 EMAIL ORB --- */
  .email-orb {
    position: fixed; bottom: 30px; right: 30px;
    width: 60px; height: 60px;
    background: linear-gradient(135deg, var(--neon-purple), var(--neon-cyan));
    border-radius: 50%;
    display: flex; justify-content: center; align-items: center;
    box-shadow: 0 0 20px var(--neon-purple);
    z-index: 999;
    transition: 0.3s;
  }
  .email-orb:hover { transform: scale(1.1) rotate(360deg); }
  .email-orb svg { width: 30px; fill: white; }

</style>

<div class="wrapper">

  <div class="hero-grid">
    <div class="hex-container">
      <img src="Mazaharul-Abedin.webp" alt="Mazaharul Abedin" class="profile-pic">
    </div>

    <div style="text-align: center; @media (min-width: 900px) { text-align: left; }">
      <h1 style="color: #fff; margin: 0;">MAZAHARUL</h1>
      <h1 style="color: var(--neon-cyan); margin: 0; font-size: 2rem;">ABEDIN</h1>
      
      <br>
      <div class="typewriter">
        > SYSTEM STATUS: PhD Scholar | Dark Energy Detective
      </div>

      <p style="margin-top: 20px;">
        Operating from <strong>Presidency University, Kolkata</strong>. <br>
        I specialize in asking the Universe uncomfortable questions about its expansion history.
        (Usually, the Universe refuses to answer, so I use Python instead).
      </p>
    </div>
  </div>

  <section>
    <h2>01. MISSION OBJECTIVES</h2>
    <p>My primary directive is **Observational Cosmology**. Using a blend of rigorous math and "letting the data speak for itself."</p>
    

[Image of cosmic expansion timeline]


    <div class="module-grid">
      <div class="data-module">
        <span class="module-header">TARGET: DARK_ENERGY</span>
        <h3 style="color:#fff; margin-top:0;">Cosmic Acceleration</h3>
        <p style="font-size: 0.95rem;">Reconstructing the Hubble parameter to figure out why galaxies are ghosting us at increasing speeds.</p>
      </div>

      <div class="data-module">
        <span class="module-header">METHOD: NON_PARAMETRIC</span>
        <h3 style="color:#fff; margin-top:0;">Machine Learning</h3>
        <p style="font-size: 0.95rem;">Using <strong>Gaussian Processes</strong> and <strong>ANNs</strong> because assuming a model is too mainstream.</p>
      </div>

      <div class="data-module">
        <span class="module-header">PROTOCOL: STRESS_TEST</span>
        <h3 style="color:#fff; margin-top:0;">Testing ΛCDM</h3>
        <p style="font-size: 0.95rem;">Checking if the Standard Model holds up against new SNe Ia and DESI-BAO data, or if it needs a software update.</p>
      </div>
    </div>
  </section>

  <section style="text-align: center;">
    <h2>02. THE ARSENAL</h2>
    <p style="margin: 0 auto 30px auto;">The computational weaponry I use to fight bad data.</p>
    
    <div class="chip-container">
      <span class="tech-chip">Python</span>
      <span class="tech-chip">JAX</span>
      <span class="tech-chip">MCMC</span>
      <span class="tech-chip">Gaussian Processes</span>
      <span class="tech-chip">CLASS</span>
      <span class="tech-chip">MontePython</span>
      <span class="tech-chip">Cobaya</span>
      <span class="tech-chip">NumPyro</span>
    </div>
  </section>

  <section style="text-align: center; margin-top: 80px;">
    <div style="background: var(--glass-surface); padding: 40px; border-radius: 20px; border: 1px solid var(--glass-border);">
      <h3 style="color: #fff; margin-bottom: 20px;">ACCESS CLASSIFIED DATA</h3>
      
      <div style="display: flex; gap: 20px; justify-content: center; flex-wrap: wrap;">
        <a href="/publications/" class="cyber-btn">
          📂 Research Logs
        </a>
        <a href="/gallery/" class="cyber-btn" style="border-color: var(--neon-purple); color: var(--neon-purple);">
          🎭 Life.exe (Gallery)
        </a>
      </div>
    </div>
  </section>

  <div class="error-box">
    <p style="font-size: 1.1rem; color: #fce7f3;">
      "I believe Physics explains <em>how</em> the world works, but <strong>Charlie Chaplin</strong> explains <em>why</em> we bother putting up with it."
      <br><br>
      <span style="font-size: 0.9rem; opacity: 0.8;">(Also, if you find the missing mass of the universe, please email me. I lost it somewhere.)</span>
    </p>
  </div>

  <a href="mailto:mazaharul.rs@presiuniv.ac.in" class="email-orb" title="Send Signal">
    <svg viewBox="0 0 24 24">
      <path d="M20,4H4C2.9,4,2,4.9,2,6v12c0,1.1,0.9,2,2,2h16c1.1,0,2-0.9,2-2V6C22,4.9,21.1,4,20,4z M20,8l-8,5L4,8V6l8,5l8-5V8z"/>
    </svg>
  </a>

</div>
