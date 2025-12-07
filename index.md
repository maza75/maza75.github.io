---
layout: home
title: Home
order: 1
---

<style>
  @import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&family=Space+Mono&family=vt323&display=swap');

  /* --- 🌌 GLOBAL SYSTEM SETTINGS 🌌 --- */
  body {
    background-color: #050505;
    background: radial-gradient(circle at center, #1a1a2e 0%, #000000 100%);
    color: #a8b2d1;
    font-family: 'Space Mono', monospace;
    overflow-x: hidden;
    cursor: crosshair; /* Sci-Fi Cursor */
  }

  /* --- CRT SCANLINE OVERLAY (Retro Monitor Effect) --- */
  body::before {
    content: " ";
    display: block;
    position: fixed; top: 0; left: 0; bottom: 0; right: 0;
    background: linear-gradient(rgba(18, 16, 16, 0) 50%, rgba(0, 0, 0, 0.25) 50%), linear-gradient(90deg, rgba(255, 0, 0, 0.06), rgba(0, 255, 0, 0.02), rgba(0, 0, 255, 0.06));
    z-index: 9999;
    background-size: 100% 2px, 3px 100%;
    pointer-events: none; /* Lets you click through it */
  }

  /* --- WIDE LAYOUT FIX --- */
  @media screen and (min-width: 1000px) {
    .wrapper { max-width: 1400px !important; width: 92% !important; padding: 0 !important; }
  }

  /* --- HUD (Heads Up Display) TOP BAR --- */
  .hud-bar {
    border-bottom: 1px solid #333;
    padding: 10px 0;
    margin-bottom: 40px;
    display: flex;
    justify-content: space-between;
    font-family: 'Orbitron', sans-serif;
    font-size: 0.8em;
    color: #555;
    text-transform: uppercase;
  }
  .hud-status { color: #0f0; text-shadow: 0 0 5px #0f0; } /* Glowing Green */

  /* --- TYPOGRAPHY --- */
  h1, h2, h3 { 
    font-family: 'Orbitron', sans-serif; 
    text-transform: uppercase;
    letter-spacing: 3px;
  }
  
  h1 { 
    font-weight: 900; 
    background: -webkit-linear-gradient(#00d2ff, #3a7bd5);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    filter: drop-shadow(0 0 10px rgba(0,210,255,0.5));
  }

  h3 { color: #ff00ff; border-left: 5px solid #00d2ff; padding-left: 15px; }

  strong { color: #00d2ff; }
  a { color: #ff00ff; text-decoration: none; border-bottom: 1px dashed #ff00ff; transition: 0.3s; }
  a:hover { background: #ff00ff; color: #000; text-decoration: none; border-bottom: none; }

  /* --- 🛸 HERO SECTION --- */
  .hero-panel {
    background: rgba(10, 10, 15, 0.8);
    border: 1px solid #333;
    padding: 50px;
    border-radius: 20px;
    text-align: center;
    position: relative;
    box-shadow: 0 0 50px rgba(0, 210, 255, 0.05);
    margin-bottom: 60px;
  }

  /* Rotating Border Effect */
  .hero-panel::before {
    content: ''; position: absolute; top: -2px; left: -2px; right: -2px; bottom: -2px;
    background: linear-gradient(45deg, #ff00ff, #000, #00d2ff, #000);
    z-index: -1;
    border-radius: 22px;
    background-size: 400%;
    animation: glowing 20s linear infinite;
  }
  @keyframes glowing { 0% { background-position: 0 0; } 50% { background-position: 400% 0; } 100% { background-position: 0 0; } }

  /* Typewriter Effect Container */
  .typewriter {
    display: inline-block;
    overflow: hidden; 
    white-space: nowrap; 
    margin: 0 auto;
    letter-spacing: .15em;
    animation: typing 3.5s steps(40, end);
    border-right: .15em solid orange; /* The cursor */
  }
  @keyframes typing { from { width: 0 } to { width: 100% } }

  /* --- 🧪 DATA MODULES --- */
  .box {
    background: #0d0d12;
    border: 1px solid #1f1f2e;
    padding: 25px;
    margin-bottom: 30px;
    transition: 0.3s;
    position: relative;
  }
  .box:hover {
    border-color: #00d2ff;
    box-shadow: 0 0 20px rgba(0, 210, 255, 0.2);
    transform: scale(1.01);
  }
  .box::after {
    content: " [SECURE]";
    position: absolute; top: 10px; right: 10px;
    font-size: 0.7em; color: #333; font-family: 'Orbitron';
  }

  /* --- 🕹️ BUTTONS --- */
  .btn-container { text-align: center; margin: 50px 0; }
  
  .cyber-btn {
    background: transparent;
    color: #00d2ff;
    font-family: 'Orbitron';
    font-size: 1.1em;
    padding: 15px 30px;
    border: 2px solid #00d2ff;
    text-transform: uppercase;
    letter-spacing: 2px;
    position: relative;
    transition: 0.3s;
    text-decoration: none;
    border-bottom: 2px solid #00d2ff; /* Override default link style */
  }
  .cyber-btn:hover {
    background: #00d2ff;
    color: #000;
    box-shadow: 0 0 30px #00d2ff;
  }

  /* --- 🤣 COMEDY WARNING BOX --- */
  .warning-box {
    background: repeating-linear-gradient(
      45deg,
      #1a1a1a,
      #1a1a1a 10px,
      #222 10px,
      #222 20px
    );
    border: 2px solid #ff9f43;
    color: #ff9f43;
    padding: 20px;
    text-align: center;
    font-style: italic;
    margin-top: 50px;
    position: relative;
  }
  .warning-icon { font-size: 2em; display: block; margin-bottom: 10px; }

  /* --- 📡 BEACON --- */
  .signal-beacon {
    position: fixed; bottom: 30px; right: 30px;
    width: 60px; height: 60px;
    background: #ff00ff;
    border-radius: 50%;
    display: flex; justify-content: center; align-items: center;
    box-shadow: 0 0 20px #ff00ff;
    z-index: 10000; /* Above scanlines */
    border: none;
  }
  .signal-beacon:hover { transform: scale(1.1); background: #fff; }
  .icon-svg { width: 30px; fill: #000; }

</style>

<div class="hud-bar">
  <span>System: <span class="hud-status">ONLINE</span></span>
  <span>Location: EARTH-982</span>
  <span>Caffeine Level: <span style="color:red">CRITICAL</span></span>
</div>

<div class="hero-panel">
  <h1 style="font-size: 3em; margin-bottom: 0;">MAZAHARUL</h1>
  <p style="color: #666; font-size: 0.9em; margin-top: 5px;">IDENT CODE: PHD-SCHOLAR-75</p>
  
  <br>
  
  <div class="typewriter">
    <p style="font-size: 1.2em; color: #fff;">"Parsing the Universe, one error at a time."</p>
  </div>

  <p style="margin-top: 30px; line-height: 1.7; font-size: 1.1em;">
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
  <span style="border: 1px solid #333; padding: 5px 10px; margin: 5px; display: inline-block; color: #00d2ff;">PYTHON</span>
  <span style="border: 1px solid #333; padding: 5px 10px; margin: 5px; display: inline-block; color: #00d2ff;">JAX</span>
  <span style="border: 1px solid #333; padding: 5px 10px; margin: 5px; display: inline-block; color: #00d2ff;">MCMC</span>
  <span style="border: 1px solid #333; padding: 5px 10px; margin: 5px; display: inline-block; color: #00d2ff;">Gaussian Processes</span>
  <span style="border: 1px solid #333; padding: 5px 10px; margin: 5px; display: inline-block; color: #00d2ff;">CLASS</span>
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
</a>
