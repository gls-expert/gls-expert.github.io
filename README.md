
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
      --active-glow: 0 0 20px rgba(0, 242, 255, 0.5);
    }

    * { margin: 0; padding: 0; box-sizing: border-box; }
    body { background: var(--bg); color: #fff; font-family: 'Plus Jakarta Sans', sans-serif; overflow-x: hidden; line-height: 1.6; }
    .container, .nav-container { width: 92%; max-width: 2400px; margin: auto; }

    /* Restoration: Navigation & Search */
    nav { position: fixed; top: 0; width: 100%; z-index: 1000; padding: 25px 0; background: rgba(3, 3, 3, 0.95); backdrop-filter: blur(15px); border-bottom: 1px solid var(--border); }
    .nav-container { display: flex; justify-content: space-between; align-items: center; }
    .nav-logo { font-family: 'Orbitron'; font-weight: 900; letter-spacing: 4px; color: var(--s); font-size: 1.4rem; }
    .nav-links a { color: rgba(255,255,255,0.7); text-decoration: none; font-size: 0.8rem; margin-left: 2vw; text-transform: uppercase; letter-spacing: 2px; }

    header { height: 100vh; display: flex; align-items: center; justify-content: center; background: linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.9)), url('https://thumbs.dreamstime.com/b/vibrant-futuristic-sports-car-neon-lit-setting-smoke-adds-to-atmosphere-futuristic-sports-car-neon-nightscape-351035810.jpg') center/cover; text-align: center; }
    .logo { font-family: 'Orbitron'; font-size: clamp(3rem, 10vw, 8rem); font-weight: 900; background: linear-gradient(to bottom, #fff, #666); -webkit-background-clip: text; -webkit-text-fill-color: transparent; }
    .hero-search input { width: 100%; max-width: 600px; background: var(--glass); border: 1px solid var(--border); padding: 18px 30px; border-radius: 50px; color: #fff; border-bottom: 2px solid var(--s); outline: none; margin-top: 30px; font-size: 1rem; }

    /* Fleet Grid */
    .grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(380px, 1fr)); gap: 30px; padding: 80px 0; }
    .card { background: var(--glass); border: 1px solid var(--border); border-radius: 15px; overflow: hidden; cursor: pointer; transition: 0.4s; }
    .card:hover { border-color: var(--s); transform: translateY(-10px); }
    .card img { width: 100%; aspect-ratio: 16/10; object-fit: cover; }
    .card-meta { padding: 25px; }

    /* ADVANCED CONFIGURATION LAB */
    #portal { display: none; position: fixed; inset: 0; background: #050505; z-index: 2000; overflow-y: auto; }
    .portal-hero { position: relative; height: 50vh; width: 100%; background-size: cover; background-position: center; display: flex; flex-direction: column; justify-content: flex-end; padding: 5% 8%; }
    .portal-hero::before { content: ""; position: absolute; inset: 0; background: linear-gradient(to top, #050505, transparent); }
    
    .sync-status { width: 300px; height: 4px; background: rgba(255,255,255,0.1); border-radius: 10px; margin-top: 20px; position: relative; overflow: hidden; }
    .sync-bar { position: absolute; left: 0; top: 0; height: 100%; width: 0%; background: var(--s); box-shadow: 0 0 15px var(--s); transition: 0.6s; }

    .lab-content { padding: 0 8% 100px; display: grid; grid-template-columns: 1fr 350px; gap: 40px; }
    
    /* Config Categories */
    .config-group { margin-bottom: 40px; }
    .group-label { font-family: 'Orbitron'; font-size: 0.75rem; color: var(--s); letter-spacing: 3px; margin-bottom: 20px; display: block; opacity: 0.7; }
    
    .choice-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(180px, 1fr)); gap: 15px; }
    .choice-btn { background: #111; border: 1px solid var(--border); padding: 15px; border-radius: 10px; cursor: pointer; transition: 0.3s; color: #888; text-align: left; position: relative; overflow: hidden; }
    .choice-btn:hover { border-color: rgba(255,255,255,0.3); color: #fff; }
    .choice-btn.selected { border-color: var(--s); background: rgba(0,242,255,0.05); color: var(--s); box-shadow: var(--active-glow); }
    .choice-btn.selected::after { content: "✓"; position: absolute; right: 10px; top: 10px; font-size: 0.7rem; }

    /* Sidebar Summary */
    .summary-box { background: #0a0a0a; border: 1px solid var(--border); padding: 30px; border-radius: 20px; height: fit-content; position: sticky; top: 100px; }
    .summary-box h3 { font-family: 'Orbitron'; font-size: 0.8rem; margin-bottom: 20px; letter-spacing: 2px; }
    .price-total { font-family: 'Orbitron'; font-size: 1.8rem; color: #fff; margin-bottom: 10px; }

    /* Restoration: Feedback & Socials */
    .feedback-section { padding: 80px 0; background: #030303; border-top: 1px solid var(--border); }
    .social-icons { padding: 60px 0; text-align: center; }
    .social-icons a { color: #fff; font-size: 1.8rem; margin: 0 20px; opacity: 0.4; transition: 0.3s; }
    .social-icons a:hover { opacity: 1; color: var(--s); transform: scale(1.2); display: inline-block; }
  </style>
</head>
<body>

<nav>
  <div class="nav-container">
    <div class="nav-logo">GRAPESINO</div>
    <div class="nav-links">
      <a href="#">Home</a><a href="#fleet">Fleet</a><a href="#feedback">Feedback</a>
    </div>
  </div>
</nav>

<header>
  <div>
    <div class="logo">GRAPESINO</div>
    <div class="hero-search">
        <input type="text" placeholder="QUERY VEHICLE DATABASE..." oninput="filterModels(this.value.toLowerCase())">
    </div>
  </div>
</header>

<div class="container">
  <h2 id="fleet" style="font-family:'Orbitron'; text-align:center; margin-top:80px; letter-spacing:10px;">THE APEX FLEET</h2>
  <div class="grid" id="mainGrid"></div>
</div>

<div id="portal">
  <div class="portal-hero" id="p-hero-bg">
    <div style="position: absolute; top: 40px; left: 8%; cursor: pointer;" onclick="closePortal()"><i class="fas fa-arrow-left"></i> EXIT LAB</div>
    <div class="portal-hero-content">
      <h1 id="p-name" style="font-family:'Orbitron';"></h1>
      <div class="sync-status"><div class="sync-bar" id="syncBar"></div></div>
    </div>
  </div>

  <div class="lab-content">
    <div id="config-panel">
        <div class="config-group">
            <span class="group-label">EXTERNAL FINISH</span>
            <div class="choice-grid">
                <div class="choice-btn selected" onclick="toggleChoice(this)">Void Black</div>
                <div class="choice-btn" onclick="toggleChoice(this)">Neon Chrome</div>
                <div class="choice-btn" onclick="toggleChoice(this)">Matte Ghost</div>
            </div>
        </div>

        <div class="config-group">
            <span class="group-label">PERFORMANCE CORE</span>
            <div class="choice-grid">
                <div class="choice-btn selected" onclick="toggleChoice(this)">Standard Fusion</div>
                <div class="choice-btn" onclick="toggleChoice(this)">Quantum Overclock</div>
                <div class="choice-btn" onclick="toggleChoice(this)">Stealth Silent</div>
            </div>
        </div>

        <div class="config-group">
            <span class="group-label">DRIVING PREFERENCES</span>
            <div class="choice-grid">
                <div class="choice-btn selected" onclick="toggleChoice(this)">Neural-Sync (AI)</div>
                <div class="choice-btn" onclick="toggleChoice(this)">Manual Drift Mode</div>
                <div class="choice-btn" onclick="toggleChoice(this)">Eco-Cruising</div>
            </div>
        </div>

        <div class="config-group">
            <span class="group-label">ACCESSIBILITY</span>
            <div class="choice-grid">
                <div class="choice-btn selected" onclick="toggleChoice(this)">Voice Command</div>
                <div class="choice-btn" onclick="toggleChoice(this)">Haptic Steering</div>
                <div class="choice-btn" onclick="toggleChoice(this)">Auto-Entry Proximity</div>
            </div>
        </div>

        <div class="config-group">
            <span class="group-label">PURCHASING STORE / HUB</span>
            <div class="choice-grid">
                <div class="choice-btn selected" onclick="toggleChoice(this)">Apex Central Hub</div>
                <div class="choice-btn" onclick="toggleChoice(this)">Neo-Tokyo Distro</div>
                <div class="choice-btn" onclick="toggleChoice(this)">London Underground</div>
            </div>
        </div>
    </div>

    <div class="summary-box">
        <h3>CONFIG SUMMARY</h3>
        <div class="price-total" id="p-price"></div>
        <p style="font-size: 0.7rem; color: #555; margin-bottom: 20px;">Ready for deployment at selected store.</p>
        <button onclick="alert('Config Synced')" style="width:100%; background:#fff; color:#000; border:none; padding:15px; border-radius:8px; font-family:'Orbitron'; font-weight:800; cursor:pointer;">CONFIRM & UPLINK</button>
    </div>
  </div>
</div>

<section class="feedback-section" id="feedback">
  <div class="container">
    <div style="background:#0a0a0a; padding:40px; border-radius:15px; border:1px solid var(--border); max-width:800px; margin:auto;">
        <h2 style="font-family:'Orbitron'; letter-spacing:5px; text-align: center; margin-bottom: 30px;">USER FEEDBACK</h2>
        <textarea rows="4" placeholder="TRANSMISSION DATA..." style="width:100%; background:#111; border:1px solid var(--border); padding:20px; color:#fff; border-radius:8px; outline:none; margin-bottom:20px;"></textarea>
        <button onclick="alert('Sent')" style="background: #fff; color: #000; border: none; padding: 18px; width: 100%; font-family: 'Orbitron'; font-weight: 800; cursor: pointer; border-radius: 8px;">SUBMIT UPLINK</button>
    </div>
  </div>
</section>

<footer>
  <div class="social-icons">
    <a href="#"><i class="fab fa-facebook-f"></i></a>
    <a href="#"><i class="fab fa-instagram"></i></a>
    <a href="#"><i class="fab fa-youtube"></i></a>
    <a href="#"><i class="fab fa-twitter"></i></a>
  </div>
  <p style="text-align: center; font-size: 0.7rem; opacity: 0.3; font-family: 'Orbitron';">GRAPESINO CORP // 2026</p>
</footer>

<script>
const data = [
  { n: "LSGMAXI", c: "$77,000", i: "https://images.unsplash.com/photo-1708019868640-864307aff6b9?w=1200" },
  { n: "GFANCY", c: "$45,000", i: "https://plus.unsplash.com/premium_photo-1737597230788-21c5a56d5d8a?w=1200" },
  { n: "DIOMANDLG", c: "$125,000", i: "https://images.unsplash.com/photo-1759493464674-aadfffcd786a?w=1200" },
  { n: "GRAPE-4x4", c: "$92,000", i: "https://images.unsplash.com/photo-1764053000942-80ec3553fa78?w=1200" },
  { n: "SHADOW-X", c: "$150,000", i: "https://media.istockphoto.com/id/156784761/photo/car-race.jpg?s=1024" },
  { n: "LocalG", c: "$19,500", i: "https://images.unsplash.com/photo-1544896478-d5b709d413c5?w=1200" }
];

const mainGrid = document.getElementById('mainGrid');
data.forEach((car, i) => {
  mainGrid.innerHTML += `
    <div class="card" onclick="openPortal(${i})">
      <img src="${car.i}">
      <div class="card-meta">
        <h3 style="font-family:'Orbitron';">${car.n}</h3>
        <p style="font-size:0.8rem; opacity:0.5;">${car.c}</p>
      </div>
    </div>`;
});

function openPortal(i) {
  const c = data[i];
  document.getElementById('p-name').innerText = c.n;
  document.getElementById('p-price').innerText = c.c;
  document.getElementById('p-hero-bg').style.backgroundImage = `url('${c.i}')`;
  document.getElementById('portal').style.display = 'block';
  document.body.style.overflow = 'hidden';
  updateSync();
}

function toggleChoice(btn) {
    const parent = btn.parentElement;
    parent.querySelectorAll('.choice-btn').forEach(b => b.classList.remove('selected'));
    btn.classList.add('selected');
    updateSync();
}

function updateSync() {
    const totalGroups = document.querySelectorAll('.config-group').length;
    const selected = document.querySelectorAll('.choice-btn.selected').length;
    document.getElementById('syncBar').style.width = (selected / totalGroups) * 100 + "%";
}

function closePortal() {
  document.getElementById('portal').style.display = 'none';
  document.body.style.overflow = 'auto';
}

function filterModels(q) {
  document.querySelectorAll('.card').forEach(card => {
    const name = card.querySelector('h3').innerText.toLowerCase();
    card.style.display = name.includes(q) ? '' : 'none';
  });
}
</script>
</body>
</html>
