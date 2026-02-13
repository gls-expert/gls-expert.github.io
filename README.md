<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
  <title>GRAPESINO Vehicles | Future of Driving</title>
  <link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;600;700;900&family=DM+Sans:wght@400;500;700&display=swap" rel="stylesheet">
  <style>
    /* ALL YOUR ORIGINAL STYLES PRESERVED */
    :root {
      --spacing-xs: 0.8rem;
      --spacing-sm: 1.2rem;
      --spacing-md: 1.8rem;
      --spacing-lg: 3rem;
      --accent: #00c8aa;
      --accent-dark: #00a88a;
      --highlight: #c87830;
    }

    * { margin: 0; padding: 0; box-sizing: border-box; -webkit-tap-highlight-color: transparent; }

    body {
      font-family: 'DM Sans', sans-serif;
      background-color: #08080a;
      color: #fff;
      line-height: 1.6;
      overflow-x: hidden;
      font-size: 16px;
      background-image: 
        radial-gradient(ellipse at 20% 0%, rgba(0,200,170,0.08) 0%, transparent 50%),
        radial-gradient(ellipse at 80% 100%, rgba(200,120,50,0.06) 0%, transparent 50%);
    }

    a { text-decoration: none; color: inherit; transition: 0.3s; }
    ul { list-style: none; }

    header { display: none; }

    .container {
      max-width: 1280px;
      margin: auto;
      padding: var(--spacing-md) var(--spacing-sm);
      padding-top: max(var(--spacing-lg), env(safe-area-inset-top));
    }

    .section-title {
      font-family: 'Space Grotesk', sans-serif;
      font-size: clamp(1.7rem, 7vw, 2.6rem);
      font-weight: 700;
      text-align: center;
      margin-bottom: var(--spacing-md);
      color: #f5f5f5;
      letter-spacing: -0.4px;
      position: relative;
    }
    .section-title::after {
      content: '';
      display: block;
      width: 60px;
      height: 4px;
      background: linear-gradient(90deg, var(--accent), var(--highlight));
      margin: 1rem auto 0;
      border-radius: 2px;
    }

    /* Hero Section */
    .hero {
      min-height: 70vh;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      text-align: center;
      padding: 5rem 1.25rem 6rem;
      position: relative;
      overflow: hidden;
    }

    .hero-logo {
      font-family: 'Space Grotesk', sans-serif;
      font-size: clamp(3rem, 15vw, 6rem);
      font-weight: 900;
      letter-spacing: 4px;
      color: #fff;
      text-transform: uppercase;
      margin-bottom: 1rem;
    }
    .hero-logo span { color: var(--accent); }

    .hero-sub {
      font-size: clamp(0.95rem, 4vw, 1.2rem);
      color: #999;
      text-transform: uppercase;
      letter-spacing: 5px;
      margin-bottom: 2.5rem;
    }

    .hero-cta {
      display: flex;
      flex-direction: column;
      gap: 1rem;
      width: 100%;
      max-width: 300px;
    }

    .cta-btn {
      padding: 1.1rem 1.8rem;
      border-radius: 10px;
      font-weight: 700;
      font-size: 0.98rem;
      text-transform: uppercase;
      letter-spacing: 1.2px;
      cursor: pointer;
      transition: all 0.22s;
      min-height: 52px;
      display: flex;
      align-items: center;
      justify-content: center;
    }
    .cta-primary { background: linear-gradient(135deg, var(--accent), var(--accent-dark)); color: #000; border: none; }
    .cta-secondary { background: transparent; color: #fff; border: 1px solid rgba(255,255,255,0.18); }

    /* Car Grid */
    .car-grid { display: grid; grid-template-columns: 1fr; gap: 1.6rem; }

    .car-card {
      background: linear-gradient(165deg, #131315, #0a0a0c);
      border: 1px solid rgba(255,255,255,0.07);
      border-radius: 14px;
      overflow: hidden;
      cursor: pointer;
      transition: transform 0.25s, border-color 0.25s;
    }

    .img-wrapper { width: 100%; height: 210px; overflow: hidden; position: relative; }
    .img-wrapper img { width: 100%; height: 100%; object-fit: cover; transition: transform 0.4s; }
    .car-info { padding: 1.4rem 1.2rem; }

    .series-badge {
      display: inline-block;
      font-family: 'Space Grotesk', sans-serif;
      font-size: 0.74rem;
      font-weight: 700;
      letter-spacing: 1.6px;
      color: #000;
      background: linear-gradient(135deg, var(--accent), var(--accent-dark));
      padding: 5px 11px;
      border-radius: 5px;
      margin-bottom: 0.7rem;
      text-transform: uppercase;
    }

    .price { font-family: 'Space Grotesk', sans-serif; font-size: 1.18rem; font-weight: 600; color: var(--highlight); display: block; margin-bottom: 1.1rem; }

    .card-stats { display: grid; grid-template-columns: repeat(3, 1fr); border-top: 1px solid rgba(255,255,255,0.09); padding-top: 1.1rem; }
    .stat { text-align: center; }
    .stat small { display: block; color: #666; font-size: 0.7rem; text-transform: uppercase; }
    .stat span { display: block; color: #ddd; font-size: 0.92rem; font-weight: 700; }

    /* Detail Overlay */
    #detailView {
      position: fixed; inset: 0; background: #08080a; z-index: 200; overflow-y: auto;
      transform: translateY(100%); transition: transform 0.5s cubic-bezier(0.77,0,0.18,1);
      display: flex; flex-direction: column;
    }
    #detailView.active { transform: translateY(0); }

    .detail-hero { width: 100%; height: 38vh; min-height: 260px; position: relative; }
    .detail-hero img { width: 100%; height: 100%; object-fit: cover; }
    .detail-content { max-width: 960px; margin: -60px auto 0; padding: 0 1.4rem 2.5rem; position: relative; z-index: 2; }
    .hud-box { flex: 1; min-width: 110px; background: rgba(255,255,255,0.025); border: 1px solid rgba(255,255,255,0.09); padding: 1.1rem 0.9rem; border-radius: 10px; position: relative; }
    .hud-box::before { content: ''; position: absolute; top: 0; left: 0; width: 3px; height: 100%; background: var(--accent); }
    .specs-box-container { display: flex; gap: 0.7rem; margin-bottom: 1.8rem; flex-wrap: wrap; }

    .close-btn {
      position: fixed; top: 1.2rem; right: 1.2rem; width: 48px; height: 48px;
      background: rgba(0,0,0,0.65); backdrop-filter: blur(10px); border: 1px solid rgba(255,255,255,0.16);
      color: #fff; border-radius: 50%; font-size: 1.4rem; z-index: 210; display: flex; align-items: center; justify-content: center;
    }

    /* Showrooms */
    .showroom-wrapper { display: flex; flex-direction: column; gap: 1.6rem; align-items: center; }
    .showroom-card { 
      width: 100%; max-width: 420px; background-size: cover; background-position: center; padding: 2rem 1.4rem; 
      border-radius: 14px; text-align: center; border: 1px solid rgba(255,255,255,0.09); position: relative; overflow: hidden;
      min-height: 190px; display: flex; flex-direction: column; justify-content: center; cursor: pointer;
    }
    .showroom-card.sl { background-image: linear-gradient(rgba(8,8,10,0.9), rgba(8,8,10,0.96)), url('https://flagcdn.com/w320/lk.png'); }
    .showroom-card.usa { background-image: linear-gradient(rgba(8,8,10,0.9), rgba(8,8,10,0.96)), url('https://flagcdn.com/w320/us.png'); }
    .showroom-card.th { background-image: linear-gradient(rgba(8,8,10,0.9), rgba(8,8,10,0.96)), url('https://flagcdn.com/w320/th.png'); }

    /* Location Modal */
    #locationModal { position: fixed; inset: 0; background: rgba(8,8,10,0.98); z-index: 300; display: flex; justify-content: center; align-items: center; opacity: 0; visibility: hidden; transition: 0.4s; }
    #locationModal.active { opacity: 1; visibility: visible; }
    .map-content { width: 100%; height: 100%; background: #0d0d0f; display: flex; flex-direction: column; position: relative; }
    .map-header { padding: 1.2rem 1.4rem; border-bottom: 1px solid #1a1a1c; background: #0a0a0c; padding-top: max(1.2rem, env(safe-area-inset-top)); }

    /* Contact Section */
    .contact-section { background: #0a0a0c; margin-top: 4rem; padding: 4rem 1.25rem; border-top: 1px solid #151517; }
    input, textarea { width: 100%; background: #111114; border: 1px solid #1e1e22; padding: 1.15rem; margin-bottom: 1.2rem; color: #fff; border-radius: 10px; }
    .submit-btn { width: 100%; padding: 1.15rem; background: linear-gradient(135deg, var(--accent), var(--accent-dark)); font-family: 'Space Grotesk'; font-weight: 700; border-radius: 10px; border: none; cursor: pointer; text-transform: uppercase; }

    /* Particles */
    .particles { position: fixed; inset: 0; pointer-events: none; z-index: 0; overflow: hidden; }
    .particle { position: absolute; width: 2px; height: 2px; background: rgba(0,200,170,0.3); border-radius: 50%; animation: float 22s infinite ease-in-out; }

    @keyframes float { 0%,100% { transform: translateY(100vh) translateX(0); opacity: 0; } 10% { opacity: 1; } 100% { transform: translateY(-15vh) translateX(30px); opacity: 0; } }

    /* Responsive */
    @media (min-width: 560px) {
      .hero-cta { flex-direction: row; width: auto; max-width: none; }
      .car-grid { grid-template-columns: repeat(2, 1fr); }
      .showroom-wrapper { flex-direction: row; flex-wrap: wrap; justify-content: center; }
    }
    @media (min-width: 960px) {
      .car-grid { grid-template-columns: repeat(3, 1fr); }
    }
  </style>
</head>
<body>

<div class="particles" id="particles"></div>

<div id="detailView">
  <button class="close-btn" onclick="closeDetails()" aria-label="Close">×</button>
  <div class="detail-hero">
    <img id="d-img" src="" alt="Vehicle">
    <div style="position: absolute; inset: 0; background: linear-gradient(to top, #08080a 8%, transparent 65%);"></div>
  </div>
  <div class="detail-content">
    <div style="margin-bottom: 1.6rem;">
        <span id="d-series" class="series-badge" style="background: var(--accent); color: #000;">SERIES</span>
        <h2 id="d-name" style="font-family: 'Space Grotesk'; font-size: 2.5rem; text-transform: uppercase;">Model</h2>
        <div id="d-price" style="font-family: 'Space Grotesk'; font-size: 1.5rem; color: var(--highlight); font-weight: 700;">$0</div>
    </div>
    <div class="specs-box-container">
      <div class="hud-box"><h4>Max Range</h4><p id="d-range">—</p></div>
      <div class="hud-box"><h4>Top Speed</h4><p id="d-speed">—</p></div>
      <div class="hud-box"><h4>Horsepower</h4><p id="d-power">—</p></div>
    </div>
    <p id="d-desc" style="color: #bbb; margin-bottom: 2rem;"></p>
    <button class="submit-btn" onclick="this.innerText='CONFIGURATION SAVED'">Reserve Configuration</button>
  </div>
</div>

<div id="locationModal">
  <div class="map-content">
    <div class="map-header">
      <h3 id="map-title" style="color: #fff;">Center</h3>
      <span id="map-country" style="color: var(--accent); font-size: 0.8rem; font-weight: 700; text-transform: uppercase;"></span>
      <button class="close-btn" onclick="closeLocationModal()">×</button>
    </div>
    <div style="flex: 1; display: flex; flex-direction: column; background: #0d0d0f;">
      <div id="mapContainer" style="flex: 1; display: flex; align-items: center; justify-content: center; flex-direction: column;">
          </div>
      <div style="padding: 1.6rem; background: #08080a; border-top: 1px solid #1a1a1c; text-align: center;">
          <p id="map-address" style="color: #888;"></p>
          <strong id="map-phone" style="display: block; margin: 0.5rem 0 1.5rem; color: #fff;"></strong>
          <div style="display: flex; gap: 1rem; justify-content: center;">
              <a href="#" id="call-btn" style="flex:1; border: 1px solid var(--accent); color: var(--accent); padding: 1rem; border-radius: 8px; font-weight: 700;">CALL</a>
              <a href="#" id="dir-btn" target="_blank" style="flex:1; background: var(--highlight); color: #fff; padding: 1rem; border-radius: 8px; font-weight: 700;">DIRECTIONS</a>
          </div>
      </div>
    </div>
  </div>
</div>

<section class="hero">
  <h1 class="hero-logo">GRAPE<span>SINO</span></h1>
  <p class="hero-sub">Engineering the Future</p>
  <div class="hero-cta">
    <a href="#cars" class="cta-btn cta-primary">Explore Models</a>
    <a href="#contact" class="cta-btn cta-secondary">Contact Us</a>
  </div>
</section>

<div class="container" id="cars">
  <h2 class="section-title">The Collection</h2>
  <div class="car-grid" id="carGrid"></div>
</div>

<div class="container" id="showrooms">
  <h2 class="section-title">Global Experience Centers</h2>
  <div class="showroom-wrapper">
    <div class="showroom-card sl" onclick="openLocation('Colombo', 'Sri Lanka', 'Lotus Tower Precinct, Colombo 01', '+94 11 234 5678', 'Lotus Tower Colombo')">
      <span class="country" style="color: var(--accent); font-weight: 700; font-size: 0.8rem; letter-spacing: 2px;">SRI LANKA</span>
      <h3 style="font-family: 'Space Grotesk'; font-size: 1.5rem;">Colombo</h3>
      <p style="color: #aaa; font-size: 0.9rem;">Lotus Tower Precinct</p>
      <div style="margin-top: 1rem; padding: 0.5rem; border: 1px solid rgba(255,255,255,0.2); border-radius: 20px; font-size: 0.7rem;">VIEW ON MAP</div>
    </div>

    <div class="showroom-card usa" onclick="openLocation('New York', 'United States', '456 Broadway, SoHo, NY 10013', '+1 212 555 0123', '456 Broadway New York')">
      <span class="country" style="color: var(--accent); font-weight: 700; font-size: 0.8rem; letter-spacing: 2px;">UNITED STATES</span>
      <h3 style="font-family: 'Space Grotesk'; font-size: 1.5rem;">New York</h3>
      <p style="color: #aaa; font-size: 0.9rem;">456 Broadway, SoHo</p>
      <div style="margin-top: 1rem; padding: 0.5rem; border: 1px solid rgba(255,255,255,0.2); border-radius: 20px; font-size: 0.7rem;">VIEW ON MAP</div>
    </div>

    <div class="showroom-card th" onclick="openLocation('Bangkok', 'Thailand', 'Icon Siam, Bangkok 10600', '+66 2 8888 9999', 'Icon Siam Bangkok')">
      <span class="country" style="color: var(--accent); font-weight: 700; font-size: 0.8rem; letter-spacing: 2px;">THAILAND</span>
      <h3 style="font-family: 'Space Grotesk'; font-size: 1.5rem;">Bangkok</h3>
      <p style="color: #aaa; font-size: 0.9rem;">Icon Siam Shopping Mall</p>
      <div style="margin-top: 1rem; padding: 0.5rem; border: 1px solid rgba(255,255,255,0.2); border-radius: 20px; font-size: 0.7rem;">VIEW ON MAP</div>
    </div>
  </div>
</div>

<div class="contact-section" id="contact">
  <div class="container" style="padding:0;">
    <h2 class="section-title">Get in Touch</h2>
    <div style="max-width: 520px; margin: auto;">
      <form onsubmit="event.preventDefault(); this.querySelector('button').innerText='MESSAGE SENT';">
        <input type="text" placeholder="Your Name" required>
        <input type="email" placeholder="Your Email" required>
        <textarea rows="5" placeholder="Your Message" required></textarea>
        <button type="submit" class="submit-btn">Send Message</button>
      </form>
    </div>
  </div>
</div>

<footer style="text-align: center; padding: 4rem 1.5rem; background: #050507; border-top: 1px solid #111;">
  <div style="font-family: 'Space Grotesk'; font-weight: 900; color: #fff; letter-spacing: 3px; margin-bottom: 1rem;">GRAPE<span style="color: var(--accent);">SINO</span></div>
  <p style="color: #555; font-size: 0.8rem;">2026 GRAPESINO AUTOMOTIVE. ALL RIGHTS RESERVED.</p>
</footer>

<script>
// ALL ORIGINAL DATA PRESERVED
const carData = [
  { name: "LSGMAXI", series: "COMFORT", price: 77000, range: "850 KM", speed: 280, power: 620, img: "https://images.unsplash.com/photo-1502877338535-766e3a6052c0?w=800", desc: "Executive-class comfort with intelligent road-adaptive suspension." },
  { name: "GFANCY", series: "LUXURY", price: 45000, range: "420 KM", speed: 210, power: 310, img: "https://images.unsplash.com/photo-1552519507-da3b142c6e3d?w=800", desc: "Urban luxury in a compact, agile package." },
  { name: "DIOMANDLG", series: "VELOCITY", price: 125000, range: "600 KM", speed: 350, power: 1200, img: "https://images.unsplash.com/photo-1494905998402-395d579af36f?w=800", desc: "Aerodynamic perfection. Pure performance." },
  { name: "GRAPE-4x4", series: "HILL SIDE", price: 92000, range: "1200 KM", speed: 190, power: 800, img: "https://images.unsplash.com/photo-1502489597346-d8389a6b1f2a?w=800", desc: "Off-road dominance with extreme endurance." },
  { name: "SHADOW-X", series: "SPORT", price: 150000, range: "750 KM", speed: 310, power: 900, img: "https://images.unsplash.com/photo-1617814076369-7a78d158798f?w=800", desc: "Stealth design meets brutal acceleration." },
  { name: "LocalG", series: "SL-origin", price: 19500, range: "1500 KM", speed: 160, power: 2000, img: "https://images.unsplash.com/photo-1553440569-bcc63803a83d?w=800", desc: "Proudly local. Built to last." }
];

const carGrid = document.getElementById("carGrid");

carData.forEach((car, i) => {
  const card = document.createElement("div");
  card.className = "car-card";
  card.onclick = () => openDetails(i);
  card.innerHTML = `
    <div class="img-wrapper"><img src="${car.img}" alt="${car.name}"></div>
    <div class="car-info">
      <span class="series-badge">${car.series}</span>
      <h3>${car.name}</h3>
      <span class="price">$${car.price.toLocaleString()}</span>
      <div class="card-stats">
        <div class="stat"><small>Range</small><span>${car.range}</span></div>
        <div class="stat"><small>Speed</small><span>${car.speed} km/h</span></div>
        <div class="stat"><small>Power</small><span>${car.power} HP</span></div>
      </div>
    </div>`;
  carGrid.appendChild(card);
});

function openDetails(i) {
  const car = carData[i];
  document.getElementById("d-img").src = car.img;
  document.getElementById("d-series").textContent = car.series + " SERIES";
  document.getElementById("d-name").textContent = car.name;
  document.getElementById("d-price").textContent = "$" + car.price.toLocaleString();
  document.getElementById("d-range").textContent = car.range;
  document.getElementById("d-speed").textContent = car.speed + " km/h";
  document.getElementById("d-power").textContent = car.power + " HP";
  document.getElementById("d-desc").textContent = car.desc;
  document.getElementById("detailView").classList.add("active");
  document.body.style.overflow = "hidden";
}

function closeDetails() {
  document.getElementById("detailView").classList.remove("active");
  document.body.style.overflow = "";
}

function openLocation(city, country, address, phone, query) {
  document.getElementById("map-title").textContent = city + " Center";
  document.getElementById("map-country").textContent = country;
  document.getElementById("map-address").textContent = address;
  document.getElementById("map-phone").textContent = phone;
  document.getElementById("call-btn").href = "tel:" + phone;
  document.getElementById("dir-btn").href = "https://www.google.com/maps/search/?api=1&query=" + encodeURIComponent(query);
  
  document.getElementById("mapContainer").innerHTML = `
    <div style="text-align:center;">
        <div style="width:60px; height:60px; background:var(--accent); border-radius:50%; margin:0 auto 1rem; display:flex; align-items:center; justify-content:center; color:#000; font-weight:900;">GO</div>
        <p style="color:#fff;">GPS coordinates locked for ${city}.</p>
    </div>`;
    
  document.getElementById("locationModal").classList.add("active");
}

function closeLocationModal() {
  document.getElementById("locationModal").classList.remove("active");
}

// Particle Gen
const container = document.getElementById("particles");
for (let i = 0; i < 15; i++) {
  const p = document.createElement("div");
  p.className = "particle";
  p.style.left = Math.random() * 100 + "%";
  p.style.animationDelay = Math.random() * 20 + "s";
  container.appendChild(p);
}
</script>
</body>
</html>
