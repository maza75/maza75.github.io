---
layout: home
title: Home
order: 1
---

<style>
  /* --- GLOBAL PAGE BACKGROUND --- */
  body {
    /* Subtle geometric constellation pattern */
    background-image: url('https://www.transparenttextures.com/patterns/connected.png');
    background-color: #fcfcfc; /* Very light grey fallback */
  }

  /* --- GLOBAL COLORS --- */
  h1, h2, h3 { color: #003366; } 
  strong { color: #005b96; } 
  a { color: #d35400; text-decoration: none; } 
  a:hover { text-decoration: underline; }

  /* --- HERO BANNER (The Image Section) --- */
  .hero-banner {
    /* Space Image with Dark Blue Overlay */
    background-image: linear-gradient(rgba(0, 15, 50, 0.7), rgba(0, 15, 50, 0.7)), url('https://images.unsplash.com/photo-1462331940025-496dfa712568?q=80&w=2560&auto=format&fit=crop');
    background-size: cover;
    background-position: center;
    padding: 60px 30px;
    text-align: center;
    border-radius: 10px;
    margin-bottom: 40px;
    color: white; 
    box-shadow: 0 10px 20px rgba(0,0,0,0.2);
  }

  /* Force white text inside the banner */
  .hero-banner h1 {
    color: white !important;
    font-size: 2.2em;
    margin-bottom: 15px;
    text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
  }
  .hero-banner p {
    font-size: 1.1em;
    line-height: 1.6;
    max-width: 800px;
    margin: 0 auto;
    color: #f0f0f0;
  }
  .hero-banner strong { color: #82cfff !important; } /* Light blue accents */

  /* --- RESEARCH BOX --- */
  /* Added white background so text remains readable over the pattern */
  .box {
    background-color: #ffffff;
    border-left: 5px solid #003366;
    padding: 15px;
    margin-bottom: 20px;
    box-shadow: 0 2px 5px rgba(0,0,0,0.05); /* Slight shadow to pop out */
  }

  /* --- TECH TAGS (Skills) --- */
  .tech-tag {
    background-color: #f0f5f9;
    padding: 3px 8px;
    border-radius: 4px;
    font-family: monospace;
    font-size: 0.9em;
    color: #333;
    border: 1px solid #d1e2eb;
    margin-right: 5px;
    display: inline-block;
    margin-bottom: 5px;
  }

  /* --- BUTTON STYLE --- */
  .btn-container { text-align: center; margin: 30px 0; }
  .btn-pub {
    display: inline-block;
    padding: 12px 24px;
    background-color: #003366; 
    color: white !important; 
    border-radius: 5px;
    font-weight: bold;
    font-size: 1.1em;
    text-decoration: none !important;
    transition: background-color 0.3s ease;
    border: 2px solid #003366;
  }
  .btn-pub:hover {
    background-color: #d35400; 
    border-color: #d35400;
    color: white !important;
  }
</style>

<div class="hero-banner">
  <h1>Hi, I'm Mazaharul Abedin 👋</h1>
  <p>
    <strong>PhD Research Scholar | Department of Mathematics | Presidency University, Kolkata</strong><br><br>
    I am a cosmological researcher working under the guidance of <strong>Dr. Supriya Pan</strong>. My work sits at the intersection of <strong>theoretical physics</strong> and <strong>astronomical observations</strong>. I specialize in using data-driven techniques to investigate the mystery of <strong>Dark Energy</strong>.
  </p>
</div>

---

###  Research Domain
My primary focus is **Observational Cosmology**. I employ both parametric and non-parametric methodologies to understand the origin, dynamics, and ultimate fate of the Universe.

<div class="box">
<strong>Key Focus Areas:</strong>
<ul>
  <li><strong>Dark Energy & Cosmic Acceleration:</strong> Reconstructing the Hubble and deceleration parameters to understand late-time acceleration.</li>
  <li><strong>Model-Independent Reconstructions:</strong> Letting the data speak for itself using Machine Learning and Gaussian Processes.</li>
  <li><strong>Testing ΛCDM:</strong> Identifying potential deviations from standard cosmological frameworks using datasets like SNe Ia, DESI-BAO, and CMB.</li>
</ul>
</div>

---

###  Publications
I have authored papers on dark energy interactions and model-independent reconstructions.

<div class="btn-container">
  <a href="/publications/" class="btn-pub">View Full List of Publications →</a>
</div>

---

###  Methodological Framework & Tools

I blend rigorous mathematics with modern computation. My workflow involves Bayesian inference, MCMC sampling, and Machine Learning.

**Statistical & ML Libraries:**
<span class="tech-tag">Gaussian Processes</span> <span class="tech-tag">Gapp</span> <span class="tech-tag">tinygp</span> <span class="tech-tag">GPyTorch</span> <span class="tech-tag">JAX</span> <span class="tech-tag">NumPyro</span> <span class="tech-tag">ANNs</span>

**Cosmological Packages:**
<span class="tech-tag">CLASS</span> <span class="tech-tag">MontePython</span> <span class="tech-tag">Cobaya</span> <span class="tech-tag">Colfi</span> <span class="tech-tag">emcee</span>

---

