---
layout: home
title: Home
order: 1
---

<style>
  @import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700&family=Space+Mono&display=swap');

  /* --- 🌌 DEEP SPACE ANIMATED BACKGROUND 🌌 --- */
  body {
    background: radial-gradient(ellipse at bottom, #1b2735 0%, #090a0f 100%);
    color: #e0e6ed;
    font-family: 'Space Mono', monospace; /* Coding font */
    overflow-x: hidden;
  }

  /* Animated Stars */
  .stars {
    position: fixed; top: 0; left: 0; width: 100%; height: 100%;
    background: transparent;
    z-index: -1;
  }
  .stars::after {
    content: " "; position: absolute; top: 2000px; width: 1px; height: 1px;
    background: transparent;
    box-shadow: 
      100px 200px #FFF, 230px 400px #FFF, 500px 100px #FFF, 
      900px 1000px #FFF, 50px 800px #FFF, 300px 1200px #FFF,
      800px 500px #FFF, 1200px 200px #FFF, 400px 900px #FFF;
    animation: animStar 50s linear infinite;
  }
  @keyframes animStar { from { transform: translateY(-2000px); } to { transform: translateY(0px); } }

  /* --- WIDE LAYOUT FIX (Laptop Mode) --- */
  @media screen and (min-width: 1000px) {
    .wrapper { max-width: 1400px !important; width: 92% !important; padding: 0 !important; }
  }

  /* --- TYPOGRAPHY --- */
  h1, h2, h3 { 
    font-family: 'Orbitron', sans-serif; /* Sci-Fi Font */
    color: #00d2ff; /* Cyan Neon */
    text-transform: uppercase;
    letter-spacing: 2px;
  }
  strong { color: #ff00ff; } /* Hot Pink Neon */
  a { color: #ff00ff; text-decoration: none; transition: 0.3s; }
  a:hover { color: #00d2ff; text-shadow: 0 0 8px #00d2ff; text-decoration: none; }

  /* --- 🛸 HOLOGRAPHIC HERO SECTION 🛸 --- */
  .hero-panel {
    background: rgba(255, 255, 255, 0.03);
    backdrop-filter: blur(10px); /* Glass effect */
    border: 1px solid rgba(255, 255, 255, 0.1);
    border-top: 4px solid #00d2ff;
    border-radius: 15px;
    padding: 60px 40px;
    text-align: center;
    margin-bottom: 50px;
    box-shadow: 0 0 20px rgba(0, 210, 255, 0.1);
    position: relative;
  }

  /* Glitch Effect on Name */
  .glitch-name {
    font-size: 3.5em;
    color: #fff;
    position: relative;
    animation: glitch 3s infinite;
  }
  @keyframes glitch {
    0% { text-shadow: 2px 2px #ff00ff, -2px -2px #00d2ff; }
    2% { text-shadow: -2px -2px #ff00ff, 2px 2px #00d2ff; }
    4% { text-shadow: 0 0 0; }
    100% { text-shadow: 0 0 0; }
  }

  /* --- 🧪 DATA CARDS (Research) --- */
  .data-card {
    background: linear-gradient(145deg, rgba(20,20,30,0.9), rgba(10,10,20,0.9));
    border: 1px solid #333;
    border-left: 5px solid #ff00ff;
    padding: 25px;
    margin-bottom: 25px;
    border-radius: 10px;
    transition: transform 0.3s, box-shadow 0.3s;
    position: relative;
    overflow: hidden;
  }
  .data-card:hover {
    transform: translateY(-5px) scale(1.01);
    box-shadow: 0 10px 30px rgba(255, 0, 255, 0.2);
    border-color: #ff00ff;
  }
  .data-card::before {
    content: "SYSTEM_ACTIVE";
    position: absolute; top: 10px; right: 10px;
    font-size: 0.6em; color: #00d2ff; opacity: 0.5;
  }

  /* --- 💾 TECH CHIPS --- */
  .tech-chip {
    background: rgba(0, 210, 255, 0.1);
    border: 1px solid #00d2ff;
    color: #00d2ff;
    padding: 6px 14px;
    border-radius: 4px;
    font-size: 0.85em;
    display: inline-block;
    margin: 5px;
    text-transform: uppercase;
    transition: 0.3s;
  }
  .tech-chip:hover {
    background: #00d2ff; color: #000;
    box-shadow: 0 0 15px #00d2ff;
    cursor: crosshair;
  }

  /* --- 🚀 BUTTONS --- */
  .btn-container { text-align: center; margin: 40px 0; }
  .sci-fi-btn {
    display: inline-block;
    padding: 15px 40px;
    border: 2px solid #ff00ff;
    color: #ff00ff;
    font-family: 'Orbitron', sans-serif;
    font-weight: bold;
    text-transform: uppercase;
    letter-spacing: 2px;
    text-decoration: none;
    transition: 0.3s;
    background: transparent;
    position: relative;
    z-index: 1;
  }
  .sci-fi-btn::before {
    content: "";
    position: absolute; top: 0; left: 0; width: 0%; height: 100%;
    background: #ff00ff; z-index: -1; transition: 0.3s;
  }
  .sci-fi-btn:hover::before { width: 100%; }
  .sci-fi-btn:hover { color: #fff; box-shadow: 0 0 20px #ff00ff; }

  /* --- 👾 COMEDY SECTION --- */
  .comedy-zone {
    text-align: center;
    border: 2px dashed #444;
    padding: 30px;
    border-radius: 20px;
    margin-top: 50px;
  }
  .comedy-zone:hover { border-color: #ff9f43; } /* Turns orange */
  
  /* --- 📡 FLOATING BEACON --- */
  .signal-beacon {
    position: fixed; bottom: 30px; right: 30px;
    width: 70px; height: 70px;
    background: #00d2ff;
    border-radius: 50%;
    display: flex; justify-content: center; align-items: center;
    box-shadow: 0 0 0 0 rgba(0, 210, 255, 0.7);
    animation: pulse-blue 2s infinite;
    z-index: 999;
  }
  @keyframes pulse-blue {
    0% { box-shadow: 0 0 0 0 rgba(0, 210, 255, 0.7); }
    70% { box-shadow: 0 0 0 20px rgba(0, 210, 255, 0); }
    100% { box-shadow: 0 0 0 0 rgba(0, 210, 255, 0); }
  }
  .icon-svg { width: 35px; height: 35px; fill: #000; }

</style>

<div class="stars"></div>

<div class="hero-panel">
  <h1 class="glitch-name">MAZAHARUL</h1>
  <p style="color: #00d2ff; letter-spacing: 3px; font-weight: bold;">PHD RESEARCH SCHOLAR</p>
  <p style="font-size: 1.1em; margin-top: 20px; line-height: 1.6;">
    <strong>Location:</strong> Presidency University, Kolkata (Earth, Milky Way)<br>
    <strong>Mission:</strong> Investigating why the Universe is running away from us.<br>
    <strong>Specialty:</strong> Dark Energy, Python, and aggressive debugging.
  </p>
</div>

---

### 🔭 Mission Control (Research)
I use data as a flashlight to look into the dark corners of the Universe.

<div class="data-card">
  <h3>⚡ The Big Questions</h3>
  <ul>
    <li><strong>Dark Energy:</strong> Is it a constant? A fluid? Or just a math error? (I'm betting on the first two).</li>
    <li><strong>Model-Independent Recon:</strong> Using <strong>Machine Learning</strong> to let the data speak for itself, because theoretical models talk too much.</li>
    <li><strong>Stress-Testing ΛCDM:</strong> Checking if the standard model needs an update or a reboot.</li>
  </ul>
</div>

---

### 📜 The Archives (Publications)
Documenting the expansion history of the universe (and my caffeine intake).

<div class="btn-container">
  <a href="/publications/" class="sci-fi-btn">Decryt Data Logs</a>
</div>

---

### 💻 The Toolkit (Weaponry)
I don't just do math; I force computers to do it for me.

<div style="text-align: center;">
  <span class="tech-chip">Gaussian Processes</span>
  <span class="tech-chip">JAX</span>
  <span class="tech-chip">NumPyro</span>
  <span class="tech-chip">Neural Networks</span>
  <span class="tech-chip">CLASS</span>
  <span class="tech-chip">MontePython</span>
  <span class="tech-chip">MCMC</span>
</div>

---

### 🎭 The "Human" Side
**Warning:** This researcher also contains traces of comedy and cinema.

I believe Physics explains *how* the world works, but Comedy explains *why* we bother putting up with it. Inspired by **Charlie Chaplin** and **Mr. Bean**, I try to keep my research rigorous but my attitude ridiculous.

<div class="btn-container">
  <a href="/gallery/" class="sci-fi-btn" style="border-color: #ff9f43; color: #ff9f43;">View Life Gallery</a>
</div>

<div class="comedy-zone">
  <em>"I am interested in the Universe for the same reason I am interested in comedy: neither of them makes any sense, but both are beautiful."</em>
</div>

<br><br>

<a href="mailto:mazaharul.rs@presiuniv.ac.in" class="signal-beacon" title="Send Distress Signal">
  <svg class="icon-svg" viewBox="0 0 24 24">
    <path d="M20 4H4c-1.1 0-1.99.9-1.99 2L2 18c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm0 4l-8 5-8-5V6l8 5 8-5v2z"/>
  </svg>
</a>
