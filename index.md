---
layout: home
title: Home
order: 1
---

<style>
  @import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&family=Space+Mono&family=vt323&display=swap');

  /* --- 🌌 GLOBAL SYSTEM SETTINGS 🌌 --- */
  html, body {
    overflow-x: hidden;
    max-width: 100%;
  }

  body {
    background-color: #050505;
    background: radial-gradient(circle at center, #1a1a2e 0%, #000000 100%);
    color: #a8b2d1;
    font-family: 'Space Mono', monospace;
    cursor: crosshair;
  }

  /* --- CRT SCANLINE OVERLAY --- */
  body::before {
    content: " ";
    display: block;
    position: fixed; top: 0; left: 0; bottom: 0; right: 0;
    background: linear-gradient(rgba(18, 16, 16, 0) 50%, rgba(0, 0, 0, 0.25) 50%), linear-gradient(90deg, rgba(255, 0, 0, 0.06), rgba(0, 255, 0, 0.02), rgba(0, 0, 255, 0.06));
    z-index: 9999;
    background-size: 100% 2px, 3px 100%;
    pointer-events: none;
  }

  /* --- 📱 RESPONSIVE LAYOUT LOGIC 📱 --- */
  .wrapper { 
    width: 95% !important; 
    padding: 0 10px !important; 
    max-width: 100% !important;
  }

  @media screen and (min-width: 1000px) {
    .wrapper { 
      max-width: 1400px !important; 
      width: 92% !important; 
      padding: 0 !important; 
    }
  }

  /* --- HUD TOP BAR --- */
  .hud-bar {
    border-bottom: 1px solid #333;
    padding: 10px 0;
    margin-bottom: 30px;
    display: flex;
    justify-content: space-between;
    font-family: 'Orbitron', sans-serif;
    font-size: 0.8em;
    color: #555;
    text-transform: uppercase;
  }
  .hud-status { color: #0f0; text-shadow: 0 0 5px #0f0; }

  /* --- TYPOGRAPHY --- */
  h1, h2, h3 { 
    font-family: 'Orbitron', sans-serif; 
    text-transform: uppercase;
    letter-spacing: 2px;
  }
  
  h1 { 
    font-weight: 900; 
    background: -webkit-linear-gradient(#00d2ff, #3a7bd5);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    filter: drop-shadow(0 0 10px rgba(0,210,255,0.5));
    font-size: 2em;
    line-height: 1.2;
  }

  h3 { color: #ff00ff; border-left: 5px solid #00d2ff; padding-left: 15px; font-size: 1.2em; }

  strong { color: #00d2ff; }
  a { color: #ff00ff; text-decoration: none; border-bottom: 1px dashed #ff00ff; transition: 0.3s; }
  a:hover { background: #ff00ff; color: #000; text-decoration: none; border-bottom: none; }

  /* --- 🛸 HERO SECTION --- */
  .hero-panel {
    background: rgba(10, 10, 15, 0.8);
    border: 1px solid #333;
    padding: 30px 15px;
    border-radius: 20px;
    text-align: center;
    position: relative;
    box-shadow: 0 0 30px rgba(0, 210, 255, 0.05);
    margin-bottom: 40px;
  }

  .hero-panel::before {
    content: ''; position: absolute; top: -2px; left: -2px; right: -2px; bottom: -2px;
    background: linear-gradient(45deg, #ff00ff, #000, #00d2ff, #000);
    z-index: -1;
    border-radius: 22px;
    background-size: 400%;
    animation: glowing 20s linear infinite;
  }
  @keyframes glowing { 0% { background-position: 0 0; } 50% { background-position: 400% 0; } 100% { background-position: 0 0; } }

  .typewriter {
    display: inline-block;
    margin: 0 auto;
  }
  .typewriter p {
    font-size: 1em; 
    color: #fff;
    margin: 0;
  }

  /* --- 🧪 DATA MODULES --- */
  .box {
    background: #0d0d12;
    border: 1px solid #1f1f2e;
    padding: 20px;
    margin-bottom: 30px;
    transition: 0.3s;
    position: relative;
  }
  .box:hover {
    border-color: #00d2ff;
    box-shadow: 0 0 20px rgba(0, 210, 255, 0.2);
  }
  .box::after {
    content: " [SECURE]";
    position: absolute; top: 10px; right: 10px;
    font-size: 0.7em; color: #333; font-family: 'Orbitron';
  }

  /* --- 🕹️ BUTTONS --- */
  .btn-container { text-align: center; margin: 40px 0; }
  
  .cyber-btn {
    background: transparent;
    color: #00d2ff;
    font-family: 'Orbitron';
    font-size: 1em;
    padding: 12px 20px;
    border: 2px solid #00d2ff;
    text-transform: uppercase;
    letter-spacing: 1px;
    position: relative;
    transition: 0.3s;
    text-decoration: none;
    border-bottom: 2px solid #00d2ff;
    display: inline-block;
    margin-top: 10px;
  }
  .cyber-btn:hover {
    background: #00d2ff;
    color: #000;
    box-shadow: 0 0 30px #00d2ff;
  }

  /* --- 🤣 COMEDY WARNING BOX --- */
  .warning-box {
    background: repeating-linear-gradient(45deg, #1a1a1a, #1a1a1a 10px, #222 10px, #222 20px);
    border: 2px solid #ff9f43;
    color: #ff9f43;
    padding: 20px;
    text-align: center;
    font-style: italic;
    margin-top: 50px;
  }
  .warning-icon { font-size: 2em; display: block; margin-bottom: 10px; }

  /* --- 📡 BLING BLING SIGNAL BEACON --- */
  .signal-beacon {
    position: fixed; bottom: 20px; right: 20px;
    width: 60px; height: 60px;
    background: radial-gradient(circle, #ff55ff 10%, #ff00ff 100%); /* Shiny Gradient */
    border-radius: 50%;
    display: flex; justify-content: center; align-items: center;
    box-shadow: 0 0 20px #ff00ff, 0 0 40px rgba(255, 0, 255, 0.4);
    z-index: 10000;
    border: 2px solid white;
    animation: bounce 2s infinite ease-in-out;
  }
  
  /* The Ripple Effect (Radar Ping) */
  .signal-beacon::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0; bottom: 0;
    border-radius: 50%;
    border: 2px solid #ff00ff;
    animation: ripple 1.5s infinite ease-out;
    z-index: -1;
  }

  .signal-beacon:hover { 
    transform: scale(1.1); 
    background: #fff; 
    border-color: #ff00ff;
  }
  .signal-beacon:hover .icon-svg { fill: #ff00ff; }
  
  .icon-svg { width: 30px; fill: #fff; transition: 0.3s; }

  /* --- ANIMATIONS --- */
  @keyframes ripple {
    0% { transform: scale(1); opacity: 1; }
    100% { transform: scale(2.5); opacity: 0; }
  }
  
  @keyframes bounce {
    0%, 100% { transform: translateY(0); }
    50% { transform: translateY(-5px); }
  }

  /* --- 📱 MOBILE SPECIFIC --- */
  @media screen and (max-width: 768px) {
    .hud-bar { flex-direction: column; text-align: center; gap: 5px; }
    h1 { font-size: 1.8em; }
    .hero-panel p { font-size: 0.95em; }
    .typewriter p { white-space: normal; border: none; animation: none; }
    .toolkit-span { display: block !important; margin: 5px auto !important; width: 80%; }
  }

  @media screen and (min-width: 1000px) {
    .hero-panel { padding: 50px; }
    h1 { font-size: 3em; }
    .typewriter {
      overflow: hidden; white-space: nowrap; animation: typing 3.5s steps(40, end); border-right: .15em solid orange;
    }
    @keyframes typing { from { width: 0 } to { width: 100% } }
  }

</style>

<div class="hud-bar">
  <span>System: <span class="hud-status">ONLINE</span></span>
  <span>Loc: EARTH-982</span>
  <span>Caffeine: <span style="color:red">CRITICAL</span></span>
</div>

<div class="hero-panel">
  <h1 style="margin-bottom: 0;">MAZAHARUL</h1>
  <p style="color: #666; font-size: 0.9em; margin-top: 5px;">IDENT CODE: PHD-SCHOLAR-75</p>
  
  <br>
  
  <div class="typewriter">
    <p>"Parsing the Universe, one error at a time."</p>
  </div>

  <p style="margin-top: 30px; line-height: 1.7;">
    I am a <strong>Cosmological Detective</strong> at Presidency University. <br>
    I stare at data until it confesses why the Universe is accelerating. <br>
    (Spoiler: It's mostly Dark Energy, or my code is broken).
  </p>
</div>

---

### 📂 CASE FILE: RESEARCH
*Accessing classified documents on the fate of the cosmos...*

<div class="box">
  <h3>⚡ The Big Mysteries</h3>
  <ul>
    <li><strong>Dark Energy:</strong> The thing pushing the universe apart. I'm trying to figure out what it is before it pushes us all away.</li>
    <li><strong>Model-Independent Recon:</strong> I use <strong>Machine Learning</strong> to analyze data without human bias. (Robots are better at math than us anyway).</li>
    <li><strong>Testing ΛCDM:</strong> The "Standard Model" of cosmology. It's like an old car; it works, but it makes weird noises sometimes.</li>
  </ul>
</div>

---

### 💾 DATA LOGS (Publications)
Proof that I actually do work and don't just watch Sci-Fi movies.

<div class="btn-container">
  <a href="/publications/" class="cyber-btn">Decrypt Archives</a>
</div>

---

### 🛠 WEAPONRY (Toolkit)
Tools I use to fight entropy and bad data.

<div style="text-align: center; margin-top: 20px;">
  <span class="toolkit-span" style="border: 1px solid #333; padding: 5px 10px; margin: 5px; display: inline-block; color: #00d2ff;">PYTHON</span>
  <span class="toolkit-span" style="border: 1px solid #333; padding: 5px 10px; margin: 5px; display: inline-block; color: #00d2ff;">JAX</span>
  <span class="toolkit-span" style="border: 1px solid #333; padding: 5px 10px; margin: 5px; display: inline-block; color: #00d2ff;">MCMC</span>
  <span class="toolkit-span" style="border: 1px solid #333; padding: 5px 10px; margin: 5px; display: inline-block; color: #00d2ff;">Gaussian Processes</span>
  <span class="toolkit-span" style="border: 1px solid #333; padding: 5px 10px; margin: 5px; display: inline-block; color: #00d2ff;">CLASS</span>
</div>

---

### 🎭 HUMAN SIMULATION MODE
**Warning:** Serious scientist detected. Deploying countermeasures.

I believe the Universe is a giant joke, and Physics is the punchline. Inspired by **Charlie Chaplin**, I try to find the rhythm in the chaos. When not calculating cosmic expansion, I am usually expanding my knowledge of cinema and cricket.

<div class="btn-container">
  <a href="/gallery/" class="cyber-btn" style="border-color: #ff9f43; color: #ff9f43;">View Life.exe</a>
</div>

<div class="warning-box">
  <span class="warning-icon">⚠️</span>
  <strong>SYSTEM ALERT:</strong><br>
  "I am not saying it was Aliens... but have you seen my Dark Energy plots?"
</div>

<br><br>

<a href="mailto:mazaharul.rs@presiuniv.ac.in" class="signal-beacon" title="Send Distress Signal">
  <svg class="icon-svg" viewBox="0 0 24 24">
    <path d="M20 4H4c-1.1 0-1.99.9-1.99 2L2 18c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm0 4l-8 5-8-5V6l8 5 8-5v2z"/>
  </svg>
<!-- </a> -->
