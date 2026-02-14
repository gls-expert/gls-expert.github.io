
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>GRAPESINO | THE FINAL APEX</title>
  <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@300;500;800&family=Orbitron:wght@400;900&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
  <style>
    :root {
      --p: #bc13fe; --s: #00f2ff; --bg: #030303;
      --glass: rgba(255, 255, 255, 0.03);
      --border: rgba(255, 255, 255, 0.1);
      --neon-glow: 0 8px 32px rgba(0, 242, 255, 0.2);
    }

    * { margin: 0; padding: 0; box-sizing: border-box; }
    
    body {
      background: var(--bg);
      color: #fff;
      font-family: 'Plus Jakarta Sans', sans-serif;
      overflow-x: hidden;
      line-height: 1.6;
    }

    /* Animated Grainy Background */
    body::before {
      content: "";
      position: fixed; top: 0; left: 0; width: 100%; height: 100%;
      background: radial-gradient(circle at 50% 50%, rgba(188, 19, 254, 0.05), transparent);
      z-index: -1;
    }

    /* Navigation */
    nav {
      position: fixed; top: 0; width: 100%; z-index: 1000;
      padding: 25px 0; transition: 0.4s;
      background: rgba(3, 3, 3, 0.8);
      backdrop-filter: blur(20px);
      border-bottom: 1px solid var(--border);
    }
    .nav-container {
      max-width: 1300px; margin: auto; padding: 0 40px;
      display: flex; justify-content: space-between; align-items: center;
    }
    .nav-logo { font-family: 'Orbitron'; font-weight: 900; letter-spacing: 4px; color: var(--s); font-size: 1.4rem; }
    .nav-links { display: flex; gap: 30px; }
    .nav-links a { color: rgba(255,255,255,0.7); text-decoration: none; font-size: 0.8rem; font-weight: 600; text-transform: uppercase; letter-spacing: 2px; transition: 0.3s; }
    .nav-links a:hover { color: var(--s); }

    /* Hero Section */
    header {
      height: 100vh;
      display: flex; align-items: center; justify-content: center;
      background: linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.8)), 
                  url('https://thumbs.dreamstime.com/b/vibrant-futuristic-sports-car-neon-lit-setting-smoke-adds-to-atmosphere-futuristic-sports-car-neon-nightscape-351035810.jpg') center/cover;
      text-align: center;
      padding: 0 20px;
    }
    .logo { 
        font-family: 'Orbitron'; font-size: clamp(3rem, 12vw, 8rem); font-weight: 900; 
        letter-spacing: -2px; margin-bottom: 10px;
        background: linear-gradient(to bottom, #fff, #666);
        -webkit-background-clip: text; -webkit-text-fill-color: transparent;
    }
    .status { font-size: 0.7rem; letter-spacing: 10px; color: var(--s); margin-bottom: 40px; opacity: 0.8; }
    
    .hero-search {
      position: relative; max-width: 500px; margin: 0 auto 40px;
    }
    .hero-search input {
      width: 100%; background: var(--glass); border: 1px solid var(--border);
      padding: 18px 30px; border-radius: 100px; color: #fff; border-bottom: 2px solid var(--s);
      backdrop-filter: blur(10px); outline: none; transition: 0.3s;
    }
    .hero-search input:focus { background: rgba(255,255,255,0.08); box-shadow: var(--neon-glow); }

    /* Buttons */
    .btn-glow {
      background: #fff; color: #000; border: none; padding: 18px 40px;
      font-family: 'Orbitron'; font-weight: 900; font-size: 0.9rem;
      letter-spacing: 3px; cursor: pointer; transition: 0.4s; border-radius: 4px;
    }
    .btn-glow:hover { background: var(--s); transform: translateY(-3px); box-shadow: var(--neon-glow); }

    /* Grid Layout */
    .container { max-width: 1300px; margin: auto; padding: 80px 40px; }
    .section-title { font-family: 'Orbitron'; font-size: 2rem; margin-bottom: 60px; letter-spacing: 5px; text-align: center; }
    
    .grid {
      display: grid; grid-template-columns: repeat(auto-fit, minmax(350px, 1fr)); gap: 30px;
    }
    .card {
      background: var(--glass); border: 1px solid var(--border); border-radius: 12px;
      overflow: hidden; transition: 0.5s cubic-bezier(0.23, 1, 0.32, 1);
      position: relative;
    }
    .card:hover { border-color: var(--s); transform: translateY(-10px); background: rgba(255,255,255,0.06); }
    
    .card img { width: 100%; aspect-ratio: 16/10; object-fit: cover; opacity: 0.8; transition: 0.5s; }
    .card:hover img { opacity: 1; transform: scale(1.05); }

    .card-meta { padding: 30px; }
    .card-meta h3 { font-family: 'Orbitron'; font-size: 1.4rem; margin-bottom: 20px; letter-spacing: 2px; }
    .card-specs { display: grid; grid-template-columns: 1fr 1fr; gap: 15px; font-size: 0.8rem; opacity: 0.8; }
    .card-specs b { color: var(--s); }
    .units { margin-top: 20px; font-weight: 800; font-size: 0.7rem; color: var(--p); letter-spacing: 2px; }

    /* Services */
    .services-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 20px; }
    .service-card { 
        padding: 40px; background: var(--glass); border: 1px solid var(--border); 
        border-radius: 12px; transition: 0.3s;
    }
    .service-card:hover { background: #fff; color: #000; }
    .service-card i { font-size: 2rem; margin-bottom: 20px; color: var(--s); }
    .service-card h4 { font-family: 'Orbitron'; margin-bottom: 10px; font-size: 0.9rem; }
    .service-card p { font-size: 0.85rem; opacity: 0.7; }
    .service-card:hover i, .service-card:hover p { color: #000; opacity: 1; }

    /* Portal Overlay */
    #portal {
      display: none; position: fixed; inset: 0; background: #000; z-index: 2000;
      overflow-y: auto; padding: 100px 20px;
    }
    .portal-header {
        position: fixed; top: 0; left: 0; width: 100%; padding: 20px 40px;
        display: flex; justify-content: space-between; align-items: center;
        background: rgba(0,0,0,0.9); border-bottom: 1px solid var(--border);
    }
    .spec-item { background: var(--glass); padding: 20px; border-radius: 8px; border-left: 3px solid var(--s); }
    
    /* Responsive */
    @media (max-width: 768px) {
      .nav-links { display: none; }
      .grid { grid-template-columns: 1fr; }
    }
  </style>
</head>
<body>

<nav id="navbar">
  <div class="nav-container">
    <div class="nav-logo">GRAPESINO</div>
    <div class="nav-links">
      <a href="#hero">Home</a>
      <a href="#fleet">Fleet</a>
      <a href="#about">About</a>
      <a href="#services">Services</a>
      <a href="#uplink">Contact</a>
    </div>
  </div>
</nav>

<header id="hero">
  <div class="hero-content">
    <div class="status">SYSTEMS ONLINE // APEX v2.6</div>
    <div class="logo">GRAPESINO</div>
    <div class="hero-search">
      <input type="text" id="modelSearch" placeholder="FIND YOUR APEX..." oninput="filterModels(this.value.trim().toLowerCase())">
    </div>
    <button class="btn-glow" onclick="document.getElementById('fleet').scrollIntoView({behavior: 'smooth'})">EXPLORE FLEET</button>
  </div>
</header>

<div class="container">
  <h2 class="section-title" id="fleet">THE APEX FLEET</h2>
  <div class="grid" id="mainGrid"></div>

  <section id="about" style="padding: 100px 0; text-align: center; max-width: 800px; margin: auto;">
    <h3 style="font-family: 'Orbitron'; color: var(--s); margin-bottom: 30px;">FUTURE OF MOBILITY</h3>
    <p style="font-size: 1.1rem; opacity: 0.8;">Grapesino Corp curates mind-linked hypercraft and bio-fused titans. We provide tomorrow's elite with the pinnacle of engineering, exclusivity, and quantum-era performance.</p>
  </section>

  <h2 class="section-title" id="services">SERVICES</h2>
  <div class="services-grid">
    <div class="service-card"><i class="fas fa-car"></i><h4>ELITE SALES</h4><p>Hand-selected apex vehicles for VIP clients.</p></div>
    <div class="service-card"><i class="fas fa-coins"></i><h4>QUANTUM FINANCING</h4><p>Neural-linked payment plans.</p></div>
    <div class="service-card"><i class="fas fa-shield-alt"></i><h4>ETERNAL WARRANTY</h4><p>Lifetime self-repair activation.</p></div>
    <div class="service-card"><i class="fas fa-tools"></i><h4>APEX CARE</h4><p>Certified neural technician support.</p></div>
  </div>

  <section id="uplink" style="margin-top: 100px; background: var(--glass); padding: 60px; border-radius: 20px;">
    <h2 class="section-title">UPLINK</h2>
    <form style="max-width: 600px; margin: auto; display: grid; gap: 20px;" onsubmit="event.preventDefault(); submitForm();">
        <input type="text" placeholder="CITIZEN NAME" style="background: transparent; border: none; border-bottom: 1px solid var(--border); padding: 15px; color: #fff; outline: none;" required>
        <input type="email" placeholder="UPLINK EMAIL" style="background: transparent; border: none; border-bottom: 1px solid var(--border); padding: 15px; color: #fff; outline: none;" required>
        <textarea placeholder="MESSAGE" rows="4" style="background: transparent; border: none; border-bottom: 1px solid var(--border); padding: 15px; color: #fff; outline: none;" required></textarea>
        <button class="btn-glow">SEND TRANSMISSION</button>
        <div id="success-message" style="display:none; color: var(--s); margin-top: 20px;">Transmission Synced.</div>
    </form>
  </section>
</div>

<div id="portal">
  <div class="portal-header">
    <span style="font-family: 'Orbitron'; font-size: 0.8rem; letter-spacing: 2px;">MODEL: <strong id="premium-model" style="color:var(--s)"></strong></span>
    <button class="btn-glow" style="padding: 10px 20px; font-size: 0.7rem;" onclick="closePortal()">CLOSE</button>
  </div>
  <div class="container" style="padding-top: 40px;">
    <img id="p-img" src="" style="width:100%; border-radius: 12px; margin-bottom: 40px;">
    <h1 id="p-name" style="font-family:'Orbitron'; font-size: 3rem; margin-bottom: 20px;"></h1>
    <div class="grid" style="grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); margin-bottom: 40px;">
        <div class="spec-item"><small>RANGE</small><h3 id="p-range"></h3></div>
        <div class="spec-item"><small>VELOCITY</small><h3 id="p-speed"></h3></div>
        <div class="spec-item"><small>POWER</small><h3 id="p-power"></h3></div>
        <div class="spec-item"><small>PRICE</small><h3 id="p-price"></h3></div>
    </div>
    <p id="p-desc" style="font-size: 1.2rem; opacity: 0.8; margin-bottom: 50px; text-align: left;"></p>
    
    <div style="background: var(--glass); padding: 40px; border-radius: 12px;">
        <h3 style="font-family: 'Orbitron'; margin-bottom: 30px;">CUSTOMIZATION MATRIX</h3>
        <div id="customList" style="display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 20px; text-align: left;"></div>
    </div>
    <button class="btn-glow" style="margin-top: 50px; width: 100%;" onclick="reserveBuild()">RESERVE APEX BUILD</button>
  </div>
</div>

<style>
  /* Updated Footer Styling */
  .main-footer {
    padding: 80px 20px;
    background: linear-gradient(to top, rgba(188, 19, 254, 0.05), transparent);
    border-top: 1px solid var(--border);
    text-align: center;
  }

  .social-container {
    display: flex;
    justify-content: center;
    gap: 40px;
    margin-bottom: 40px;
  }

  .social-icon {
    font-size: 2rem;
    color: rgba(255, 255, 255, 0.6);
    transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
    position: relative;
    text-decoration: none;
  }

  /* Brand Specific Hover Effects */
  .social-icon.facebook:hover {
    color: #1877F2;
    transform: translateY(-10px) scale(1.2);
    filter: drop-shadow(0 0 15px rgba(24, 119, 242, 0.8));
  }

  .social-icon.youtube:hover {
    color: #FF0000;
    transform: translateY(-10px) scale(1.2);
    filter: drop-shadow(0 0 15px rgba(255, 0, 0, 0.8));
  }

  .social-icon.instagram:hover {
    background: radial-gradient(circle at 30% 107%, #fdf497 0%, #fdf497 5%, #fd5949 45%, #d6249f 60%, #285AEB 90%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    transform: translateY(-10px) scale(1.2);
    filter: drop-shadow(0 0 15px rgba(214, 36, 159, 0.8));
  }

  .footer-copyright {
    font-family: 'Orbitron';
    font-size: 0.7rem;
    letter-spacing: 5px;
    opacity: 0.4;
    text-transform: uppercase;
  }
</style>

<footer class="main-footer">
  <div class="social-container">
    <a href="https://www.facebook.com" target="_blank" class="social-icon facebook" title="Follow us on Facebook">
      <i class="fab fa-facebook-f"></i>
    </a>
    
    <a href="https://www.youtube.com" target="_blank" class="social-icon youtube" title="Watch on YouTube">
      <i class="fab fa-youtube"></i>
    </a>
    
    <a href="https://www.instagram.com" target="_blank" class="social-icon instagram" title="Follow us on Instagram">
      <i class="fab fa-instagram"></i>
    </a>
  </div>
  
  <div class="footer-copyright">
    GRAPESINO CORP © 2026 // APEX PROTOCOL SECURED
  </div>
</footer>

<script>
const data = [
  { n: "LSGMAXI", r: "850 KM", s: "280 KM/H", p: "620 HP", c: "$77,000", i: "https://images.unsplash.com/photo-1708019868640-864307aff6b9?w=900&auto=format&fit=crop&q=60", d: "Executive mobility masterclass. Features active liquid-cooling. <br><br><b>Exclusive:</b> Neural Pilot Sync, Vortex Energy Harvest.", u: "4 UNITS REMAINING", custom: [{name: "Interface", opts: ["Basic", "Quantum"]}, {name: "Coat", opts: ["Void", "Plasma"]}] },
  { n: "GFANCY", r: "420 KM", s: "210 KM/H", p: "310 HP", c: "$45,000", i: "https://plus.unsplash.com/premium_photo-1737597230788-21c5a56d5d8a?w=900&auto=format&fit=crop&q=60", d: "Ultra-maneuverable urban craft. <br><br><b>Exclusive:</b> Holo-Display HUD, Nano-Repair Veil.", u: "12 UNITS REMAINING", custom: [{name: "Mode", opts: ["Auto", "Manual"]}, {name: "AI", opts: ["Loyal", "Oracle"]}] },
  { n: "DIOMANDLG", r: "600 KM", s: "350 KM/H", p: "1200 HP", c: "$125,000", i: "https://images.unsplash.com/photo-1759493464674-aadfffcd786a?w=900&auto=format&fit=crop&q=60", d: "Kinetic art with graphene core. <br><br><b>Exclusive:</b> Quantum Shielding, Chrono-Flux Drive.", u: "ONLY 2 LEFT", custom: [{name: "Core", opts: ["Balanced", "Overdrive"]}] },
  { n: "GRAPE-4x4", r: "1200 KM", s: "190 KM/H", p: "800 HP", c: "$92,000", i: "https://images.unsplash.com/photo-1764053000942-80ec3553fa78?w=900&auto=format&fit=crop&q=60", d: "Heavy-duty explorer. <br><br><b>Exclusive:</b> Terrain Morphing, Geo-Spectral Scanner.", u: "8 UNITS REMAINING", custom: [{name: "Chassis", opts: ["Standard", "Expedition"]}] },
  { n: "SHADOW-X", r: "750 KM", s: "310 KM/H", p: "900 HP", c: "$150,000", i: "https://media.istockphoto.com/id/156784761/photo/car-race.jpg?s=612x612&w=0&k=20&c=bjOiWi_rsZXcODfxuNTEbGXmvYJs4dIexxyCTtBia-M=", d: "Vantablack stealth machine. <br><br><b>Exclusive:</b> Stealth Cloak Mode, Shadow Realm Link.", u: "PRE-ORDER ONLY", custom: [{name: "Cloak", opts: ["Visual", "Full"]}] },
  { n: "LocalG", r: "1500 KM", s: "160 KM/H", p: "2000 HP", c: "$19,500", i: "https://images.unsplash.com/photo-1544896478-d5b709d413c5?w=900&auto=format&fit=crop&q=60", d: "Indestructible legend. <br><br><b>Exclusive:</b> Bio-Fusion Engine, Terra-Link Symbiosis.", u: "IN STOCK", custom: [{name: "Haul", opts: ["Mega", "Planetary"]}] }
];

const grid = document.getElementById('mainGrid');
data.forEach((car, i) => {
  grid.innerHTML += `
    <div class="card" onclick="openPortal(${i})">
      <img src="${car.i}">
      <div class="card-meta">
        <h3>${car.n}</h3>
        <div class="card-specs">
          <span>RANGE <b>${car.r}</b></span>
          <span>SPEED <b>${car.s}</b></span>
          <span>POWER <b>${car.p}</b></span>
          <span>PRICE <b>${car.c}</b></span>
        </div>
        <div class="units">${car.u}</div>
      </div>
    </div>`;
});

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
  
  const customList = document.getElementById('customList');
  customList.innerHTML = '';
  c.custom.forEach(item => {
    customList.innerHTML += `<div style="display:flex; flex-direction:column; gap:8px;">
        <label style="font-size:0.7rem; letter-spacing:2px; opacity:0.6;">${item.name.toUpperCase()}</label>
        <select style="background:rgba(255,255,255,0.05); color:#fff; border:1px solid var(--border); padding:10px; border-radius:4px;">
            ${item.opts.map(o => `<option>${o}</option>`).join('')}
        </select>
    </div>`;
  });

  document.getElementById('portal').style.display = 'block';
  document.body.style.overflow = 'hidden';
}

function closePortal() {
  document.getElementById('portal').style.display = 'none';
  document.body.style.overflow = 'auto';
}

function filterModels(q) {
  const cards = document.querySelectorAll('.card');
  cards.forEach(card => {
    const name = card.querySelector('h3').innerText.toLowerCase();
    card.style.display = name.includes(q) ? '' : 'none';
  });
}

function submitForm() {
    document.getElementById('success-message').style.display = 'block';
    setTimeout(() => document.getElementById('success-message').style.display = 'none', 3000);
}

function reserveBuild() {
    alert("APEX Sync Complete. Quantum Fabrication Queued.");
}

// Nav Scroll Effect
window.onscroll = () => {
    const nav = document.getElementById('navbar');
    if (window.scrollY > 50) nav.style.padding = "15px 0";
    else nav.style.padding = "25px 0";
}
</script>
</body>
</html>
