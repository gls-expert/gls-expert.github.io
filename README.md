
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>GRAPESINO | THE FINAL APEX</title>
  <link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;700&family=Orbitron:wght@400;900&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
  <style>
    :root {
      --p: #bc13fe; --s: #00f2ff; --bg: #000;
      --glass: rgba(255, 255, 255, 0.04);
      --neon-glow: 0 0 20px var(--s), 0 0 40px var(--p);
      --text-glow: 0 0 10px rgba(0, 242, 255, 0.4);
    }
    * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Space Grotesk', sans-serif; -webkit-font-smoothing: antialiased; }
    body {
      background: var(--bg); color: #fff; overflow-x: hidden;
      background-image:
        radial-gradient(circle at 5% 5%, rgba(188, 19, 254, 0.15) 0%, transparent 40%),
        radial-gradient(circle at 95% 95%, rgba(0, 242, 255, 0.15) 0%, transparent 40%);
      background-attachment: fixed;
    }
    #bg-glow {
      position: fixed; inset: 0; z-index: -1; pointer-events: none;
      background: radial-gradient(circle at 20% 80%, rgba(188, 19, 254, 0.1) 0%, transparent 50%),
                  radial-gradient(circle at 80% 20%, rgba(0, 242, 255, 0.1) 0%, transparent 50%);
      animation: nebulaPulse 8s ease-in-out infinite alternate;
    }
    @keyframes nebulaPulse { 0% { opacity: 0.8; transform: scale(1); } 100% { opacity: 1; transform: scale(1.05); } }
    .particle {
      position: fixed; width: 4px; height: 4px; background: var(--s); border-radius: 50%;
      pointer-events: none; z-index: -1; animation: float 20s linear infinite;
    }
    @keyframes float { 0% { transform: translateY(100vh) rotate(0deg); opacity: 0; } 10% { opacity: 1; } 90% { opacity: 1; } 100% { transform: translateY(-100vh) rotate(360deg); opacity: 0; } }
    header {
      position: relative;
      min-height: 100vh;
      background: linear-gradient(rgba(0,0,0,0.65), rgba(0,0,0,0.75)),
                  url('https://thumbs.dreamstime.com/b/vibrant-futuristic-sports-car-neon-lit-setting-smoke-adds-to-atmosphere-futuristic-sports-car-neon-nightscape-351035810.jpg') center/cover no-repeat;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      text-align: center;
      overflow: hidden;
    }
    header::before {
      content: ''; position: absolute; inset: 0;
      background: radial-gradient(circle at center, transparent 30%, rgba(0,0,0,0.6));
      pointer-events: none;
    }
    .hero-content { position: relative; z-index: 2; max-width: 90%; }
    .logo {
      font-family: 'Orbitron'; font-size: clamp(4rem, 20vw, 10rem); font-weight: 900;
      letter-spacing: -8px; line-height: 0.9;
      background: linear-gradient(to bottom, #fff 30%, var(--s));
      -webkit-background-clip: text; -webkit-text-fill-color: transparent;
      filter: drop-shadow(var(--neon-glow));
      animation: logoScan 4s linear infinite;
      margin-bottom: 20px;
    }
    .status {
      font-size: 0.8rem; letter-spacing: 8px; color: var(--p); text-transform: uppercase; margin-bottom: 60px; font-weight: 700;
      animation: statusFlicker 2s ease-in-out infinite alternate;
    }
    .hero-search {
      position: relative; max-width: 600px; margin: 0 auto 60px;
    }
    .hero-search input {
      width: 100%; background: rgba(255,255,255,0.05); border: 2px solid var(--s);
      padding: 20px 60px 20px 25px; border-radius: 50px; color: #fff; font-size: 1.1rem;
      outline: none; transition: 0.4s; backdrop-filter: blur(10px);
    }
    .hero-search input:focus { border-color: var(--p); box-shadow: var(--neon-glow); }
    .hero-search i { position: absolute; right: 25px; top: 50%; transform: translateY(-50%); font-size: 1.4rem; color: var(--s); }
    .hero-cta {
      padding: 22px 50px; font-size: 1.2rem; letter-spacing: 6px;
    }
    .hero-cta:hover { animation: pulseGlow 1.5s infinite; }
    @keyframes pulseGlow { 0%, 100% { box-shadow: var(--neon-glow); } 50% { box-shadow: 0 0 60px var(--s), 0 0 100px var(--p); } }
    nav {
      position: fixed; top: 0; left: 0; right: 0; z-index: 1000;
      background: rgba(0,0,0,0.7); backdrop-filter: blur(15px);
      padding: 20px 0; border-bottom: 1px solid rgba(0,242,255,0.2);
    }
    .nav-container {
      max-width: 1400px; margin: auto; padding: 0 25px;
      display: flex; justify-content: space-between; align-items: center;
    }
    .nav-logo { font-family: 'Orbitron'; font-size: 1.8rem; color: var(--s); text-shadow: var(--neon-glow); }
    .nav-links {
      display: flex; gap: 40px;
    }
    .nav-links a {
      color: #fff; font-size: 1rem; letter-spacing: 2px; text-transform: uppercase;
      transition: 0.3s; position: relative;
    }
    .nav-links a:hover {
      color: var(--s); text-shadow: var(--neon-glow);
    }
    .nav-links a::after {
      content: ''; position: absolute; bottom: -8px; left: 0; width: 0; height: 2px; background: var(--s);
      transition: width 0.3s;
    }
    .nav-links a:hover::after { width: 100%; }
    .container { max-width: 1400px; margin: auto; padding: 0 25px; padding-top: 120px; }
    .section-title {
      font-family: 'Orbitron'; font-size: 2.5rem; text-align: center; margin: 100px 0 60px;
      color: var(--s); text-shadow: var(--neon-glow); position: relative;
    }
    .section-title::after {
      content: ''; position: absolute; bottom: -20px; left: 50%; transform: translateX(-50%);
      width: 200px; height: 4px; background: linear-gradient(90deg, transparent, var(--p), var(--s), transparent);
    }
    .grid {
      display: grid; grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
      gap: 40px; padding: 40px 0;
    }
    .card {
      background: var(--glass); border-radius: 28px; border: 1px solid rgba(255,255,255,0.1);
      overflow: hidden; cursor: pointer; transition: 0.5s;
      box-shadow: inset 0 0 30px rgba(0, 242, 255, 0.05);
    }
    .card:hover {
      border-color: var(--s); transform: translateY(-25px) scale(1.05);
      box-shadow: 0 50px 100px rgba(0,0,0,0.8), var(--neon-glow);
    }
    .card img { width: 100%; aspect-ratio: 1/1; object-fit: cover; filter: brightness(0.7); transition: 0.6s; }
    .card:hover img { filter: brightness(1.2) hue-rotate(12deg); transform: scale(1.1); }
    .card-meta { 
      padding: 30px; 
      background: linear-gradient(transparent, rgba(0,0,0,0.95)); 
      display: flex;
      flex-direction: column;
      gap: 12px;
    }
    .card-meta h3 { 
      font-size: 1.8rem; 
      letter-spacing: 4px; 
      color: var(--s);
      text-shadow: var(--text-glow);
    }
    .card-specs {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 10px;
      font-size: 0.95rem;
    }
    .card-specs div {
      display: flex;
      justify-content: space-between;
    }
    .card-specs label {
      color: var(--p);
      letter-spacing: 2px;
      font-weight: bold;
    }
    .card-meta .units {
      font-size: 1rem;
      color: #ff3366;
      font-weight: bold;
      letter-spacing: 2px;
      align-self: flex-end;
    }
    .about-section {
      padding: 120px 0; text-align: center; background: rgba(188, 19, 254, 0.06);
    }
    .about-section p {
      max-width: 1000px; margin: 0 auto 30px; font-size: 1.2rem; line-height: 2; opacity: 0.95;
    }
    .services-grid {
      display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 40px; margin: 80px 0;
    }
    .service-card {
      background: var(--glass); border-radius: 28px; padding: 50px 30px; text-align: center;
      border: 1px solid rgba(255,255,255,0.05); transition: 0.4s;
    }
    .service-card:hover {
      border-color: var(--p); transform: translateY(-15px); box-shadow: var(--neon-glow);
    }
    .service-card i { font-size: 3.5rem; color: var(--s); margin-bottom: 30px; text-shadow: var(--neon-glow); }
    .service-card h4 { font-family: 'Orbitron'; font-size: 1.6rem; margin-bottom: 20px; }
    .testimonials {
      padding: 100px 0; background: rgba(0,0,0,0.4);
    }
    .testimonial-grid {
      display: grid; grid-template-columns: repeat(auto-fit, minmax(320px, 1fr)); gap: 40px;
    }
    .testimonial-card {
      background: var(--glass); border-radius: 24px; padding: 40px; border-left: 5px solid var(--s);
      font-style: italic; position: relative;
    }
    .testimonial-card::before {
      content: '“'; font-size: 6rem; color: var(--p); opacity: 0.2; position: absolute; top: -20px; left: 20px;
    }
    .testimonial-author { margin-top: 30px; font-weight: bold; color: var(--s); }
    .hub-grid { 
      display: grid; 
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); 
      gap: 40px; 
    }
    .hub-card { padding: 60px; text-align: center; }
    .uplink { 
      padding: 120px 0; 
      text-align: center; 
    }
    .uplink form {
      max-width: 700px;
      margin: 60px auto 0;
      display: flex;
      flex-direction: column;
      gap: 30px;
    }
    .uplink .form-group {
      display: flex;
      flex-direction: column;
      text-align: left;
    }
    .uplink .form-group label {
      font-size: 1rem;
      letter-spacing: 3px;
      color: var(--p);
      margin-bottom: 10px;
    }
    .uplink input,
    .uplink textarea {
      width: 100%;
      background: rgba(255,255,255,0.05);
      border: 2px solid var(--s);
      padding: 20px 25px;
      border-radius: 50px;
      color: #fff;
      font-size: 1.1rem;
      outline: none;
      transition: 0.4s;
      backdrop-filter: blur(10px);
    }
    .uplink textarea {
      border-radius: 30px;
      min-height: 180px;
      resize: vertical;
    }
    .uplink input:focus,
    .uplink textarea:focus {
      border-color: var(--p);
      box-shadow: var(--neon-glow);
    }
    .uplink .success-message {
      margin-top: 30px;
      font-size: 1.4rem;
      color: var(--s);
      text-shadow: var(--text-glow);
      display: none;
      animation: fadeIn 1s ease-out;
    }
    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(20px); }
      to { opacity: 1; transform: translateY(0); }
    }
    .footer {
      padding: 120px 0; text-align: center; background: rgba(0,0,0,0.6);
    }
    .social-links { 
      gap: 70px; 
      margin-bottom: 0; 
      display: flex; 
      justify-content: center; 
      align-items: center; 
    }
    .social-links a i { font-size: 3.5rem; }
    .btn-glow {
      background: linear-gradient(90deg, var(--p), var(--s));
      border: none; border-radius: 18px; color: #fff; font-family: 'Orbitron';
      font-weight: 900; letter-spacing: 4px; cursor: pointer; transition: 0.4s;
      text-transform: uppercase; padding: 20px 50px; font-size: 1.2rem;
    }
    .btn-glow:hover { transform: scale(1.05); filter: brightness(1.3); box-shadow: var(--neon-glow); }

    /* SUPREME PREMIUM DETAIL PAGE (PORTAL) */
    #portal {
      display: none;
      position: fixed;
      inset: 0;
      background: var(--bg);
      z-index: 9999;
      overflow-y: auto;
    }
    .portal-header {
      position: fixed;
      top: 0;
      left: 0;
      right: 0;
      height: 90px;
      background: rgba(0,0,0,0.8);
      backdrop-filter: blur(20px);
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 0 50px;
      border-bottom: 2px solid var(--s);
      z-index: 10000;
    }
    .portal-header span {
      font-family: 'Orbitron';
      font-size: 1.4rem;
      letter-spacing: 6px;
      color: var(--s);
      text-shadow: var(--neon-glow);
    }
    .portal-header strong {
      color: #fff;
      font-size: 1.6rem;
    }
    .portal-back {
      background: linear-gradient(90deg, var(--p), var(--s));
      border: none;
      padding: 12px 40px;
      border-radius: 50px;
      color: #fff;
      font-family: 'Orbitron';
      font-weight: 900;
      letter-spacing: 4px;
      cursor: pointer;
      font-size: 1rem;
    }
    .portal-back:hover {
      transform: scale(1.05);
      box-shadow: var(--neon-glow);
    }
    .portal-body {
      min-height: 100vh;
      padding-top: 120px;
      text-align: center;
    }
    .portal-body .container {
      padding-top: 0;
    }
  </style>
</head>
<body>
<div id="bg-glow"></div>
<script>for(let i=0; i<70; i++){const p=document.createElement('div');p.className='particle';p.style.left=Math.random()*100+'%';p.style.animationDelay=Math.random()*20+'s';p.style.animationDuration=(15+Math.random()*15)+'s';document.body.appendChild(p);}</script>
<nav>
  <div class="nav-container">
    <div class="nav-logo">GRAPESINO</div>
    <div class="nav-links">
      <a href="#hero">Home</a>
      <a href="#fleet">Apex Fleet</a>
      <a href="#about">About</a>
      <a href="#services">Services</a>
      <a href="#testimonials">Testimonials</a>
      <a href="#hubs">Global Hubs</a>
      <a href="#uplink">Contact</a>
    </div>
  </div>
</nav>
<header id="hero">
  <div class="hero-content">
    <div class="logo">GRAPE<span>SINO</span></div>
    <div class="status">APEX PROTOCOL // QUANTUM LINK ESTABLISHED // 2026</div>
   
    <div class="hero-search">
      <input type="text" id="modelSearch" placeholder="SEARCH APEX MODELS..." oninput="filterModels(this.value.trim().toLowerCase())">
      <i class="fas fa-search"></i>
    </div>
   
    <button class="btn-glow hero-cta" onclick="document.getElementById('fleet').scrollIntoView({behavior: 'smooth'})">DISCOVER THE APEX FLEET</button>
  </div>
</header>
<div class="container">
  <h2 class="section-title" id="fleet">APEX FLEET</h2>
  <div class="grid" id="mainGrid"></div>
  <section class="about-section" id="about">
    <h3 class="section-title">DRIVING PASSION. REDEFINING LUXURY.</h3>
    <p>Grapesino Corp is the world's most trusted futuristic automobile dealership, delivering quantum-era engineering fused with timeless design excellence.</p>
    <p>We curate only the finest apex vehicles — from mind-linked hypercraft to cloaked stealth machines and bio-fused industrial titans. Every model represents the pinnacle of performance, exclusivity, and innovation.</p>
    <p>With global experience hubs, bespoke customization, and eternal warranty protocols, Grapesino is where tomorrow's elite secure their mobility legacy.</p>
  </section>
  <h2 class="section-title" id="services">EXCLUSIVE SERVICES</h2>
  <div class="services-grid">
    <div class="service-card">
      <i class="fas fa-car"></i>
      <h4>Elite Sales</h4>
      <p>Hand-selected apex vehicles with limited units and pre-order access for VIP clients.</p>
    </div>
    <div class="service-card">
      <i class="fas fa-coins"></i>
      <h4>Quantum Financing</h4>
      <p>Flexible neural-linked payment plans and instant approval for qualified pilots.</p>
    </div>
    <div class="service-card">
      <i class="fas fa-shield-alt"></i>
      <h4>Eternal Warranty</h4>
      <p>Lifetime coverage including self-repair activation and quantum upgrades.</p>
    </div>
    <div class="service-card">
      <i class="fas fa-tools"></i>
      <h4>Apex Maintenance</h4>
      <p>Certified neural technicians and on-demand holographic diagnostics.</p>
    </div>
    <div class="service-card">
      <i class="fas fa-cogs"></i>
      <h4>Bespoke Customization</h4>
      <p>Full matrix personalization — from nanocoats to core overclocks.</p>
    </div>
    <div class="service-card">
      <i class="fas fa-exchange-alt"></i>
      <h4>Elite Trade-In</h4>
      <p>Maximum value for legacy vehicles toward your next apex acquisition.</p>
    </div>
  </div>
  <section class="testimonials" id="testimonials">
    <h2 class="section-title">CLIENT TRANSMISSIONS</h2>
    <div class="testimonial-grid">
      <div class="testimonial-card">
        <p>"The SHADOW-X with full cloak is beyond anything on the grid. Grapesino delivered perfection."</p>
        <div class="testimonial-author">— Executive Pilot, New York Hub</div>
      </div>
      <div class="testimonial-card">
        <p>"Neural sync on the LSGMAXI changed everything. Instant response, infinite range. Elite experience."</p>
        <div class="testimonial-author">— Global Entrepreneur</div>
      </div>
      <div class="testimonial-card">
        <p>"LocalG handled planetary haulage like nothing else. Bio-fusion engine never fails."</p>
        <div class="testimonial-author">— Industrial Titan, Colombo</div>
      </div>
      <div class="testimonial-card">
        <p>"Customization matrix allowed me to build my dream DIOMANDLG. Truly bespoke."</p>
        <div class="testimonial-author">— Apex Collector</div>
      </div>
    </div>
  </section>
  <h2 class="section-title" id="hubs">GLOBAL EXPERIENCE HUBS</h2>
  <div class="hub-grid">
    <div class="hub-card">
      <i class="fas fa-map-marker-alt"></i>
      <h4><span class="flag">🇱🇰</span>COLOMBO</h4>
      <p>Headquarters • Lotus Tower, Level 42 • Sri Lanka • Neural Interface R&D Center</p>
    </div>
    <div class="hub-card">
      <i class="fas fa-map-marker-alt"></i>
      <h4><span class="flag">🇺🇸</span>NEW YORK</h4>
      <p>Premium Showroom • Hudson Yards, Manhattan • USA • Holographic Display Suites</p>
    </div>
    <div class="hub-card">
      <i class="fas fa-map-marker-alt"></i>
      <h4><span class="flag">🇹🇭</span>BANGKOK</h4>
      <p>Production Lab & Manufacturing • Icon Siam, Riverside • Thailand • Quantum Assembly Lines</p>
    </div>
  </div>
  <section class="uplink" id="uplink">
    <h2 class="section-title">UPLINK MESSAGE</h2>
    <form onsubmit="event.preventDefault(); submitForm();">
      <div class="form-group">
        <label for="citizen">CITIZEN ID / NAME</label>
        <input type="text" id="citizen" placeholder="Enter your Citizen ID or Name" required>
      </div>
      <div class="form-group">
        <label for="email">UPLINK EMAIL</label>
        <input type="email" id="email" placeholder="Enter your email address" required>
      </div>
      <div class="form-group">
        <label for="message">MESSAGE CONTENTS</label>
        <textarea id="message" rows="6" placeholder="Describe Your Apex Vision" required></textarea>
      </div>
      <button type="submit" class="btn-glow">EXECUTE TRANSMISSION</button>
      <div id="success-message" class="success-message">
        Transmission Successful. Quantum Sync Complete.
      </div>
    </form>
  </section>
</div>
<div class="footer">
  <div class="social-links">
    <a href="#" target="_blank"><i class="fab fa-facebook-f"></i></a>
    <a href="#" target="_blank"><i class="fab fa-youtube"></i></a>
    <a href="#" target="_blank"><i class="fab fa-instagram"></i></a>
  </div>
</div>
<div id="portal">
  <div class="portal-header">
    <span>SUPREME PREMIUM ACCESS // APEX MODEL: <strong id="premium-model"></strong></span>
    <button class="btn-glow portal-back" onclick="closePortal()">BACK TO FLEET</button>
  </div>
  <div class="portal-body">
    <div class="container">
      <div class="img-frame">
        <img id="p-img" src="" style="width:100%; display:block; border-radius: 28px;">
        <div class="exclusive-badge">GRAPESINO EXCLUSIVE</div>
      </div>
      <h1 id="p-name" style="font-family:'Orbitron'; font-size:3.5rem; margin:40px 0 20px; text-shadow:var(--neon-glow);"></h1>
      <div class="spec-grid" style="display:grid; grid-template-columns:repeat(auto-fit,minmax(220px,1fr)); gap:30px; margin:60px 0; font-size:1.2rem;">
        <div class="spec-item"><label>DRIVE_RANGE</label><b id="p-range"></b></div>
        <div class="spec-item"><label>MAX_VELOCITY</label><b id="p-speed"></b></div>
        <div class="spec-item"><label>CORE_OUTPUT</label><b id="p-power"></b></div>
        <div class="spec-item"><label>ACQUISITION</label><b id="p-price"></b></div>
      </div>
      <p id="p-desc" style="max-width:1000px; margin:0 auto 60px; font-size:1.3rem; line-height:2;"></p>
     
      <div class="custom-options" style="max-width:1000px; margin:0 auto;">
        <h3 style="font-size:2rem; margin-bottom:40px;">GRAPESINO CUSTOMIZATION MATRIX</h3>
        <ul class="custom-list" id="customList" style="display:grid; grid-template-columns:repeat(auto-fit,minmax(300px,1fr)); gap:20px; list-style:none;"></ul>
        <div id="build-summary" style="margin-top:60px;">
          <h4 style="font-size:1.8rem; margin-bottom:30px;">YOUR APEX BUILD SUMMARY</h4>
          <ul id="summary-list" style="text-align:left; font-size:1.1rem;"></ul>
        </div>
      </div>
     
      <button class="btn-glow" style="margin:80px auto 40px; width:80%; max-width:600px; padding:25px;" onclick="reserveBuild()">CONFIGURE & RESERVE YOUR APEX</button>
    </div>
  </div>
</div>
<script>
const data = [
  {
    n: "LSGMAXI", r: "850 KM", s: "280 KM/H", p: "620 HP", c: "$77,000",
    i: "https://images.unsplash.com/photo-1708019868640-864307aff6b9?w=900&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8N3x8c3VwZXIlMjBjYXIlMjBpbWFnZXN8ZW58MHx8MHx8fDA%3D",
    d: "A masterclass in executive mobility. Features active liquid-cooling for long-distance cruising. <strong>Exclusive Grapesino Features:</strong> <br>• Neural Pilot Sync – Mind-controlled navigation <br>• Vortex Energy Harvest – Atmospheric drag conversion <br>• Phantom Aura Cloak – Environmental camouflage",
    custom: [
      {name: "Neural Interface Level", opts: ["Basic", "Advanced", "Quantum Direct"]},
      {name: "Exterior Nanocoat", opts: ["Iridescent Void", "Mirror Plasma", "Adaptive Chameleon"]},
      {name: "Interior Material", opts: ["Graphene Leather", "Bioluminescent Weave", "Memory Alloy Trim"]},
      {name: "Power Augment", opts: ["Standard Flux", "Overclock Pulse", "Singularity Boost"]},
      {name: "HUD Theme", opts: ["Neon Grid", "Starfield", "Personal Constellation"]},
      {name: "Audio Ecosystem", opts: ["Spatial Harmonic", "Neural Resonance", "Silence Protocol"]}
    ],
    u: "4 UNITS REMAINING"
  },
  {
    n: "GFANCY", r: "420 KM", s: "210 KM/H", p: "310 HP", c: "$45,000",
    i: "https://plus.unsplash.com/premium_photo-1737597230788-21c5a56d5d8a?w=900&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTd8fGx1eHVyeSUyMGNhcnxlbnwwfHwwfHx8MA%3D%3D",
    d: "Ultra-maneuverable urban craft. <strong>Exclusive Grapesino Features:</strong> <br>• Holo-Display HUD – AR overlays <br>• Swarm Intelligence – Route optimization <br>• Nano-Repair Veil – Self-healing exterior",
    custom: [
      {name: "Sky-Dock Mode", opts: ["Auto", "Manual", "Swarm Assisted"]},
      {name: "Urban Camo Package", opts: ["Holo-Shift", "Neon Pulse", "Stealth Matte"]},
      {name: "Cabin Atmosphere", opts: ["Ozone Fresh", "Aroma Diffusion", "Zero-G Relax"]},
      {name: "Mobility Augment", opts: ["Hover Assist", "Vertical Leap", "Glide Wings"]},
      {name: "Light Signature", opts: ["Hexa-Scan", "Ribbon Trail", "Ghost Echo"]},
      {name: "AI Companion", opts: ["Sarcastic", "Loyal", "Oracle Mode"]}
    ],
    u: "12 UNITS REMAINING"
  },
  {
    n: "DIOMANDLG", r: "600 KM", s: "350 KM/H", p: "1200 HP", c: "$125,000",
    i: "https://images.unsplash.com/photo-1759493464674-aadfffcd786a?w=900&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTh8fGZhc3Rlc3QlMjBtb2Rlcm4lMjB0ZWNoJTIwY2FyfGVufDB8fDB8fHww",
    d: "Pure kinetic art with graphene core. <strong>Exclusive Grapesino Features:</strong> <br>• Quantum Shield Armor <br>• Chrono-Flux Drive <br>• Echo Resonance Core",
    custom: [
      {name: "Energy Core Tuning", opts: ["Balanced", "Aggressive", "Overdrive"]},
      {name: "Armor Hue", opts: ["Diamond Refract", "Obsidian Void", "Plasma Glow"]},
      {name: "Kinetic Trim", opts: ["Carbon Nano", "Iridium Weave", "Crystal Lattice"]},
      {name: "Acceleration Profile", opts: ["Linear", "Exponential", "Temporal Burst"]},
      {name: "Signature Sound", opts: ["Silent Void", "Harmonic Thunder", "Synthwave Pulse"]},
      {name: "Cockpit Layout", opts: ["Pilot Focus", "Co-Pilot", "Immersive Dome"]}
    ],
    u: "ONLY 2 LEFT"
  },
  {
    n: "GRAPE-4x4", r: "1200 KM", s: "190 KM/H", p: "800 HP", c: "$92,000",
    i: "https://images.unsplash.com/photo-1533473359331-0135ef1b58bf?w=800",
    d: "Heavy-duty explorer. <strong>Exclusive Grapesino Features:</strong> <br>• Adaptive Terrain Morph <br>• Geo-Spectral Scanner <br>• Titan Forge Plating",
    custom: [
      {name: "Chassis Extension", opts: ["Standard", "Long Range", "Expedition"]},
      {name: "Surface Adaptation", opts: ["Rock", "Sand", "Liquid", "Zero-G"]},
      {name: "Utility Modules", opts: ["Drone Bay", "Winch Array", "Habitat Pod"]},
      {name: "Suspension Type", opts: ["Magnetic Lev", "Hydraulic Titan", "Adaptive Morph"]},
      {name: "Exterior Armor", opts: ["Ceramic Plate", "Reactive Nano", "Energy Field"]},
      {name: "Exploration HUD", opts: ["Topographic", "Thermal", "Quantum Map"]}
    ],
    u: "8 UNITS REMAINING"
  },
  {
    n: "SHADOW-X", r: "750 KM", s: "310 KM/H", p: "900 HP", c: "$150,000",
    i: "https://media.istockphoto.com/id/156784761/photo/car-race.jpg?s=612x612&w=0&k=20&c=bjOiWi_rsZXcODfxuNTEbGXmvYJs4dIexxyCTtBia-M=",
    d: "Vantablack stealth machine. <strong>Exclusive Grapesino Features:</strong> <br>• Stealth Cloak Mode <br>• Shadow Realm Link <br>• Null-Signature Emitters",
    custom: [
      {name: "Cloak Level", opts: ["Visual", "Thermal", "Full Spectrum"]},
      {name: "Signature Suppress", opts: ["Basic", "Advanced", "Absolute Zero"]},
      {name: "Interior Mode", opts: ["Dark Void", "Red Alert", "Ghost Blue"]},
      {name: "Evasion Package", opts: ["Smoke Veil", "Chaff Burst", "Phantom Decoy"]},
      {name: "Encryption Layer", opts: ["Quantum", "Neural", "Eternal"]},
      {name: "Pilot Interface", opts: ["Standard", "Ghost Link", "Mind Merge"]}
    ],
    u: "PRE-ORDER ONLY"
  },
  {
    n: "LocalG", r: "1500 KM", s: "160 KM/H", p: "2000 HP", c: "$19,500",
    i: "https://images.unsplash.com/photo-1544896478-d5b709d413c5?w=900&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8M3x8dmludGFnZSUyMGNhcnxlbnwwfHwwfHx8MA%3D%3D",
    d: "Indestructible legend. <strong>Exclusive Grapesino Features:</strong> <br>• Bio-Fusion Engine <br>• Terra-Link Symbiosis <br>• Colossus Overload Surge",
    custom: [
      {name: "Haul Capacity", opts: ["Industrial", "Mega", "Planetary"]},
      {name: "Powertrain Fusion", opts: ["Organic", "Hybrid", "Eternal Core"]},
      {name: "Durability Coating", opts: ["Ablative", "Regenerative", "Immortal"]},
      {name: "Overload Duration", opts: ["Short Burst", "Sustained", "Infinite"]},
      {name: "Terrain Mastery", opts: ["Mud", "Rock", "Void", "Multi-Planet"]},
      {name: "Utility Suite", opts: ["Crane Arm", "Cargo Forge", "Mobile Base"]}
    ],
    u: "IN STOCK"
  }
];

const grid = document.getElementById('mainGrid');
data.forEach((car, i) => {
  grid.innerHTML += `
    <div class="card" onclick="openPortal(${i})">
      <img src="${car.i}">
      <div class="card-meta">
        <h3>${car.n}</h3>
        <div class="card-specs">
          <div><label>RANGE</label><span>${car.r}</span></div>
          <div><label>SPEED</label><span>${car.s}</span></div>
          <div><label>POWER</label><span>${car.p}</span></div>
          <div><label>PRICE</label><span>${car.c}</span></div>
        </div>
        <div class="units">${car.u}</div>
      </div>
    </div>`;
});

let currentSelections = {};
function openPortal(i) {
  const c = data[i];
  document.getElementById('premium-model').innerText = c.n;
  document.getElementById('p-name').innerText = c.n;
  document.getElementById('p-img').src = c.i;
  document.getElementById('p-range').innerText = c.r;
  document.getElementById('p-speed').innerText = c.s;
  document.getElementById('p-power').innerText = c.p;
  document.getElementById('p-price').innerText = c.c;
  document.getElementById('p-desc').innerHTML = c.d;
  currentSelections = {};
  const customList = document.getElementById('customList');
  customList.innerHTML = '';
  c.custom.forEach((item, idx) => {
    const id = `custom-${idx}`;
    currentSelections[id] = item.opts[0];
    let optionsHtml = '';
    item.opts.forEach(opt => {
      optionsHtml += `<option value="${opt}">${opt}</option>`;
    });
    customList.innerHTML += `
      <li class="custom-item">
        <label for="${id}">${item.name}</label>
        <select id="${id}" onchange="updateSummary()">
          ${optionsHtml}
        </select>
      </li>`;
  });
  updateSummary();
  document.getElementById('portal').style.display = 'block';
  document.body.style.overflow = 'hidden';
}
function updateSummary() {
  const summaryList = document.getElementById('summary-list');
  summaryList.innerHTML = '';
  Object.keys(currentSelections).forEach(id => {
    const select = document.getElementById(id);
    if (select) {
      currentSelections[id] = select.value;
      const label = document.querySelector(`label[for="${id}"]`).innerText;
      summaryList.innerHTML += `<li><strong>${label}:</strong> ${currentSelections[id]}</li>`;
    }
  });
}
function reserveBuild() {
  let configStr = 'Your Custom Apex Build:\n';
  Object.keys(currentSelections).forEach(id => {
    const label = document.querySelector(`label[for="${id}"]`).innerText;
    configStr += `${label}: ${currentSelections[id]}\n`;
  });
  alert(`Configuration Profile Synced. ${configStr}Quantum Fabrication Queued.`);
}
function closePortal() {
  document.getElementById('portal').style.display = 'none';
  document.body.style.overflow = 'auto';
}
function filterModels(query) {
  const cards = document.querySelectorAll('#mainGrid .card');
  cards.forEach(card => {
    const name = card.querySelector('h3').innerText.toLowerCase();
    card.style.display = query === '' || name.includes(query) ? '' : 'none';
  });
}
document.querySelectorAll('.nav-links a').forEach(link => {
  link.addEventListener('click', e => {
    e.preventDefault();
    document.querySelector(link.getAttribute('href')).scrollIntoView({ behavior: 'smooth' });
  });
});
window.addEventListener('mousemove', (e) => {
  const x = (e.clientX / window.innerWidth - 0.5) * 40;
  const y = (e.clientY / window.innerHeight - 0.5) * 40;
  document.querySelector('header').style.backgroundPosition = `calc(50% + ${x}px) calc(50% + ${y}px)`;
});
function submitForm() {
  const form = document.querySelector('.uplink form');
  const successMsg = document.getElementById('success-message');
  if (form.checkValidity()) {
    successMsg.style.display = 'block';
    form.reset();
    setTimeout(() => {
      successMsg.style.display = 'none';
    }, 6000);
  } else {
    successMsg.style.display = 'block';
    successMsg.textContent = 'Please complete all fields.';
    successMsg.style.color = '#ff0066';
    setTimeout(() => {
      successMsg.style.display = 'none';
      successMsg.textContent = 'Transmission Successful. Quantum Sync Complete.';
      successMsg.style.color = 'var(--s)';
    }, 4000);
  }
}
</script>
</body>
</html>
