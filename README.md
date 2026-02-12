<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>GRAPESINO Vehicles | Future of Driving</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;600;700;900&family=DM+Sans:wght@400;500;700&display=swap" rel="stylesheet">
<style>
  /* ---------- Global & Reset ---------- */
  * {margin:0; padding:0; box-sizing:border-box;}
  body {
    font-family:'DM Sans', sans-serif; 
    background-color:#08080a; 
    color:#fff; 
    line-height:1.6; 
    overflow-x: hidden;
    background-image: 
      radial-gradient(ellipse at 20% 0%, rgba(0, 200, 170, 0.08) 0%, transparent 50%),
      radial-gradient(ellipse at 80% 100%, rgba(200, 120, 50, 0.06) 0%, transparent 50%);
  }
  a {text-decoration:none; color:inherit; transition:0.3s;}
  ul {list-style:none;}

  /* Scrollbar Styling */
  ::-webkit-scrollbar {width: 6px;}
  ::-webkit-scrollbar-track {background: #0d0d0f;}
  ::-webkit-scrollbar-thumb {background: #00c8aa; border-radius: 3px;}

  /* ---------- Header - HIDDEN FOR PUBLIC VIEW ---------- */
  header {
    display: none;
  }

  /* ---------- Layout Utilities ---------- */
  .container {max-width:1200px; margin:auto; padding:5rem 2rem;}
  .section-title {
    font-family: 'Space Grotesk', sans-serif;
    font-size:clamp(2rem, 5vw, 2.8rem); 
    font-weight:700; 
    text-align:center; 
    margin-bottom:3.5rem; 
    color: #f5f5f5;
    letter-spacing: -1px;
    position: relative;
  }
  .section-title::after {
    content: ''; display: block; width: 60px; height: 3px; 
    background: linear-gradient(90deg, #00c8aa, #c87830); margin: 1rem auto 0; border-radius: 2px;
  }

  /* ---------- Hero Section ---------- */
  .hero {
    min-height: 60vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding: 6rem 2rem;
    position: relative;
    overflow: hidden;
  }
  .hero::before {
    content: '';
    position: absolute;
    width: 600px;
    height: 600px;
    background: radial-gradient(circle, rgba(0,200,170,0.15) 0%, transparent 70%);
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    pointer-events: none;
    animation: heroPulse 8s ease-in-out infinite;
  }
  @keyframes heroPulse {
    0%, 100% { opacity: 0.5; transform: translate(-50%, -50%) scale(1); }
    50% { opacity: 0.8; transform: translate(-50%, -50%) scale(1.1); }
  }
  .hero-logo {
    font-family: 'Space Grotesk', sans-serif;
    font-size: clamp(2.5rem, 8vw, 4.5rem);
    font-weight: 900;
    letter-spacing: 4px;
    color: #fff;
    text-transform: uppercase;
    margin-bottom: 1rem;
    position: relative;
    z-index: 2;
  }
  .hero-logo span { color: #00c8aa; }
  .hero-sub {
    font-size: 1.1rem;
    color: #888;
    text-transform: uppercase;
    letter-spacing: 6px;
    margin-bottom: 2.5rem;
    position: relative;
    z-index: 2;
  }
  .hero-cta {
    display: inline-flex;
    gap: 1rem;
    position: relative;
    z-index: 2;
  }
  .cta-btn {
    padding: 1rem 2.5rem;
    border-radius: 8px;
    font-weight: 700;
    font-size: 0.9rem;
    text-transform: uppercase;
    letter-spacing: 1px;
    cursor: pointer;
    transition: all 0.3s cubic-bezier(0.25, 0.46, 0.45, 0.94);
  }
  .cta-primary {
    background: linear-gradient(135deg, #00c8aa, #00a88a);
    color: #000;
    border: none;
  }
  .cta-primary:hover {
    transform: translateY(-3px);
    box-shadow: 0 15px 35px rgba(0, 200, 170, 0.3);
  }
  .cta-secondary {
    background: transparent;
    color: #fff;
    border: 1px solid rgba(255,255,255,0.2);
  }
  .cta-secondary:hover {
    border-color: #00c8aa;
    color: #00c8aa;
  }

  /* ---------- Car Grid ---------- */
  .car-grid {display:grid; grid-template-columns:repeat(auto-fit, minmax(320px,1fr)); gap:2rem;}
  
  .car-card {
    background: linear-gradient(165deg, #131315, #0a0a0c); 
    border: 1px solid rgba(255,255,255,0.06);
    border-radius:16px; 
    overflow:hidden; 
    cursor:pointer;
    transition: all 0.4s cubic-bezier(0.25, 0.46, 0.45, 0.94);
    position: relative;
    opacity: 0; 
    animation: fadeInUp 0.8s forwards;
  }
  
  .car-card:hover {
    transform: translateY(-8px); 
    border-color: rgba(0, 200, 170, 0.4);
    box-shadow: 0 25px 50px rgba(0, 0, 0, 0.4), 0 0 0 1px rgba(0, 200, 170, 0.1);
  }
  .car-card:hover .img-wrapper img {transform: scale(1.05);}

  .img-wrapper {width: 100%; height: 200px; overflow: hidden; position: relative;}
  .img-wrapper img {width:100%; height:100%; object-fit:cover; transition:0.6s cubic-bezier(0.25, 0.46, 0.45, 0.94);}
  .img-wrapper::after {
    content:''; position: absolute; bottom:0; left:0; width:100%; height:50%;
    background: linear-gradient(to top, #131315, transparent);
  }

  .car-info {padding:1.5rem;}
  
  .series-badge {
    display: inline-block;
    font-family: 'Space Grotesk', sans-serif;
    font-size: 0.65rem; font-weight: 700; letter-spacing: 1.5px;
    color: #000; background: linear-gradient(135deg, #00c8aa, #00a88a);
    padding: 5px 10px; border-radius: 4px;
    margin-bottom: 0.8rem;
    text-transform: uppercase;
  }

  .car-info h3 {
    font-family: 'Space Grotesk', sans-serif;
    font-size:1.6rem; margin-bottom:0.3rem; 
    font-weight: 700;
    color: #f5f5f5;
  }

  .price {
    font-family: 'Space Grotesk', sans-serif;
    font-size:1.2rem; font-weight:600; color:#c87830; display:block; margin-bottom: 1.5rem;
  }

  .card-stats {
    display: grid; grid-template-columns: 1fr 1fr 1fr;
    border-top: 1px solid rgba(255,255,255,0.08);
    padding-top: 1rem;
    gap: 0.5rem;
  }
  .stat {text-align: center;}
  .stat small {display: block; color: #555; font-size: 0.7rem; text-transform: uppercase; margin-bottom: 2px;}
  .stat span {display: block; color: #ccc; font-size: 0.9rem; font-weight: 700;}


  /* ---------- Detail View ---------- */
  #detailView {
    position: fixed; top: 0; left: 0; width: 100%; height: 100vh;
    background: #08080a; z-index: 200;
    overflow-y: auto;
    transform: translateY(100%);
    transition: transform 0.6s cubic-bezier(0.8, 0, 0.1, 1);
    display: flex; flex-direction: column;
  }
  #detailView.active {transform: translateY(0);}

  .detail-hero {width: 100%; height: 50vh; position: relative;}
  .detail-hero img {width: 100%; height: 100%; object-fit: cover;}
  .detail-gradient {
    position: absolute; bottom: 0; left: 0; width: 100%; height: 100%;
    background: linear-gradient(to top, #08080a 5%, transparent 60%);
  }

  .detail-content {
    max-width: 900px; margin: -80px auto 0; padding: 2rem; position: relative; z-index: 2;
    opacity: 0; transform: translateY(30px); transition: 0.5s 0.4s;
  }
  #detailView.active .detail-content {opacity: 1; transform: translateY(0);}

  .detail-header {
    display: flex; justify-content: space-between; align-items: flex-end; margin-bottom: 2.5rem; flex-wrap: wrap; gap: 1rem;
    border-bottom: 1px solid rgba(255,255,255,0.08); padding-bottom: 1.5rem;
  }
  .detail-title h2 {font-family: 'Space Grotesk', sans-serif; font-size: clamp(2rem, 6vw, 3rem); line-height: 1; color: #fff; text-transform: uppercase; letter-spacing: -1px;}
  .detail-title span {font-size: 0.9rem; color: #00c8aa; letter-spacing: 3px; font-weight: 700;}
  .detail-price {font-family: 'Space Grotesk', sans-serif; font-size: 2rem; font-weight: 700; color: #c87830;}

  .specs-box-container {
    display: flex; gap: 1rem; margin-bottom: 2.5rem; flex-wrap: wrap;
  }
  .hud-box {
    flex: 1; min-width: 120px;
    background: rgba(255,255,255,0.02); border: 1px solid rgba(255,255,255,0.08);
    padding: 1.2rem; border-radius: 10px; 
    transition: 0.3s; position: relative; overflow: hidden;
  }
  .hud-box:hover {background: rgba(0,200,170,0.05); border-color: rgba(0,200,170,0.3); transform: translateY(-3px);}
  .hud-box::before {
    content: ''; position: absolute; top: 0; left: 0; width: 2px; height: 100%; background: #00c8aa;
  }
  .hud-box h4 {font-family: 'Space Grotesk', sans-serif; color: #666; font-size: 0.7rem; margin-bottom: 0.5rem; text-transform: uppercase; letter-spacing: 1px;}
  .hud-box p {font-family: 'Space Grotesk', sans-serif; color: #fff; font-size: 1.5rem; font-weight: 700;}

  .detail-desc {
    font-size: 1rem; color: #aaa; margin-bottom: 2.5rem; max-width: 700px; line-height: 1.8;
  }

  .close-btn {
    position: fixed; top: 1.5rem; right: 1.5rem; width: 44px; height: 44px;
    background: rgba(0,0,0,0.6); backdrop-filter: blur(10px); border: 1px solid rgba(255,255,255,0.15);
    color: #fff; border-radius: 50%; font-size: 1.3rem; cursor: pointer; z-index: 210;
    display: flex; align-items: center; justify-content: center; transition: 0.3s;
  }
  .close-btn:hover {background: #00c8aa; color: #000; transform: rotate(90deg);}

  /* ---------- Showrooms ---------- */
  .showroom-wrapper {display: flex; flex-wrap: wrap; justify-content: center; gap: 1.5rem;}
  
  .showroom-card {
    background-color: #111;
    background-size: cover;
    background-position: center;
    padding: 2.5rem 1.5rem; border-radius: 16px; width: 300px; text-align: center;
    border: 1px solid rgba(255,255,255,0.08); position: relative; overflow: hidden;
    transition: 0.4s;
    box-shadow: 0 15px 40px rgba(0,0,0,0.3);
    cursor: pointer;
  }

  .showroom-card.sl { background-image: linear-gradient(rgba(8,8,10,0.88), rgba(8,8,10,0.95)), url('https://flagcdn.com/w320/lk.png'); }
  .showroom-card.usa { background-image: linear-gradient(rgba(8,8,10,0.88), rgba(8,8,10,0.95)), url('https://flagcdn.com/w320/us.png'); }
  .showroom-card.th { background-image: linear-gradient(rgba(8,8,10,0.88), rgba(8,8,10,0.95)), url('https://flagcdn.com/w320/th.png'); }

  .showroom-card:hover {transform: translateY(-8px); border-color: rgba(0,200,170,0.4);}
  .showroom-card h3 {font-family: 'Space Grotesk', sans-serif; color: #fff; font-size: 1.5rem; margin-bottom: 0.5rem; position: relative; z-index: 2;}
  .showroom-card .country {color: #00c8aa; font-size: 0.75rem; font-weight: 700; text-transform: uppercase; margin-bottom: 1rem; display: block; letter-spacing: 2px;}
  .showroom-card p {color: #999; font-size: 0.9rem; margin-bottom: 0.3rem; position: relative; z-index: 2;}
  
  .locate-hint {
    display: inline-block; margin-top: 1.2rem; padding: 0.5rem 1rem;
    border: 1px solid rgba(255,255,255,0.15); border-radius: 20px;
    font-size: 0.7rem; color: #fff; text-transform: uppercase; letter-spacing: 1px;
    background: rgba(0,0,0,0.3); transition: 0.3s;
  }
  .showroom-card:hover .locate-hint {
    background: linear-gradient(135deg, #00c8aa, #00a88a); color: #000; border-color: #00c8aa;
  }

  /* ---------- Location Map Modal ---------- */
  #locationModal {
    position: fixed; top: 0; left: 0; width: 100%; height: 100vh;
    background: rgba(8,8,10,0.95); backdrop-filter: blur(20px); z-index: 300;
    display: flex; justify-content: center; align-items: center;
    opacity: 0; visibility: hidden; transition: 0.4s;
  }
  #locationModal.active { opacity: 1; visibility: visible; }
  
  .map-content {
    width: 92%; max-width: 900px; height: 75vh;
    background: #0d0d0f; border-radius: 16px; border: 1px solid #1a1a1c;
    display: flex; flex-direction: column; overflow: hidden;
    position: relative; transform: scale(0.9); transition: 0.4s;
    box-shadow: 0 40px 80px rgba(0,0,0,0.6);
  }
  #locationModal.active .map-content { transform: scale(1); }

  .map-header {
    padding: 1.2rem 1.5rem; border-bottom: 1px solid #1a1a1c; display: flex; justify-content: space-between; align-items: center;
    background: #0a0a0c;
  }
  .map-header h3 { font-family: 'Space Grotesk', sans-serif; font-size: 1.3rem; color: #fff; }
  .map-header h3 span { color: #00c8aa; font-size: 0.7rem; display: block; text-transform: uppercase; letter-spacing: 2px; }

  .map-body { flex: 1; display: flex; flex-direction: column; }
  .map-iframe-box { flex: 1; position: relative; min-height: 280px; }
  .map-iframe-box iframe { width: 100%; height: 100%; border: 0; position: absolute; top: 0; left: 0; }

  .map-info-panel {
    padding: 1.2rem 1.5rem; background: #08080a; border-top: 1px solid #1a1a1c;
    display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 1rem;
  }
  .address-block { flex: 1; min-width: 200px; }
  .address-block p { color: #888; font-size: 0.85rem; margin-bottom: 0.2rem; }
  .address-block strong { font-family: 'Space Grotesk', sans-serif; color: #fff; font-size: 1rem; }

  .action-buttons { display: flex; gap: 0.8rem; }
  .action-btn {
    padding: 0.7rem 1.2rem; border-radius: 6px; font-weight: 700; font-size: 0.8rem;
    border: none; cursor: pointer; transition: 0.3s; text-transform: uppercase; display: flex; align-items: center; gap: 0.5rem;
  }
  .btn-call { background: transparent; border: 1px solid #00c8aa; color: #00c8aa; }
  .btn-call:hover { background: #00c8aa; color: #000; }
  .btn-dir { background: linear-gradient(135deg, #c87830, #a86020); color: #fff; }
  .btn-dir:hover { transform: translateY(-2px); }

  /* ---------- Contact ---------- */
  .contact-section {background: #0a0a0c; margin-top: 4rem; padding: 5rem 2rem; border-top: 1px solid #151517;}
  .form-box {max-width: 550px; margin: auto;}
  
  input, textarea {
    width: 100%; background: #111114; border: 1px solid #1e1e22; padding: 1rem; margin-bottom: 1rem;
    color: #fff; font-family: 'DM Sans', sans-serif; border-radius: 8px; transition: 0.3s;
  }
  input:focus, textarea:focus {outline: none; border-color: #00c8aa; background: #131316;}
  
  button.submit-btn {
    width: 100%; padding: 1rem; background: linear-gradient(135deg, #00c8aa, #00a88a); 
    color: #000; border: none; font-family: 'Space Grotesk', sans-serif;
    font-weight: 700; font-size: 0.9rem;
    border-radius: 8px; cursor: pointer; transition: 0.3s; text-transform: uppercase; letter-spacing: 1px;
  }
  button.submit-btn:hover {transform: translateY(-2px); box-shadow: 0 15px 35px rgba(0,200,170,0.25);}

  /* ---------- Footer ---------- */
  footer {
    text-align: center; 
    padding: 4rem 2rem; 
    border-top: 1px solid #111; 
    background: #050507;
  }

  .footer-brand {
    font-family: 'Space Grotesk', sans-serif;
    font-size: 2rem; font-weight: 900; letter-spacing: 3px; color: #fff; text-transform: uppercase; 
    margin-bottom: 1.5rem;
  }
  .footer-brand span { color: #00c8aa; }

  .footer-socials {
    display: flex; justify-content: center; gap: 1.5rem; 
    margin: 2rem 0;
  }

  .social-icon {
    width: 44px; height: 44px; border-radius: 50%;
    background: rgba(255,255,255,0.03);
    border: 1px solid #222;
    display: flex; align-items: center; justify-content: center;
    color: #888;
    transition: 0.3s;
  }

  .social-icon svg { width: 20px; height: 20px; fill: currentColor; }

  .social-icon:hover {
    background: #00c8aa; border-color: #00c8aa;
    color: #000; transform: translateY(-5px);
  }

  .footer-text {
    color: #444; font-size: 0.8rem; text-transform: uppercase; 
    letter-spacing: 2px;
    margin-top: 1.5rem;
  }

  /* ---------- Floating Particles ---------- */
  .particles {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    pointer-events: none;
    z-index: 0;
    overflow: hidden;
  }
  .particle {
    position: absolute;
    width: 3px;
    height: 3px;
    background: rgba(0, 200, 170, 0.4);
    border-radius: 50%;
    animation: float 15s infinite ease-in-out;
  }

  @keyframes float {
    0%, 100% { transform: translateY(100vh) translateX(0); opacity: 0; }
    10% { opacity: 1; }
    90% { opacity: 1; }
    100% { transform: translateY(-10vh) translateX(50px); opacity: 0; }
  }

  @keyframes fadeInUp {
    from {opacity:0; transform:translateY(30px);}
    to {opacity:1; transform:translateY(0);}
  }

  /* ---------- Responsive ---------- */
  @media (max-width: 768px) {
    .hero { min-height: 50vh; padding: 4rem 1.5rem; }
    .hero-cta { flex-direction: column; width: 100%; }
    .cta-btn { width: 100%; text-align: center; justify-content: center; }
    .container { padding: 3rem 1.5rem; }
    .car-grid { gap: 1.5rem; }
    .detail-hero { height: 40vh; }
    .detail-header { flex-direction: column; align-items: flex-start; }
    .map-content { height: 85vh; border-radius: 12px; }
    .map-info-panel { flex-direction: column; text-align: center; }
    .action-buttons { width: 100%; justify-content: center; }
  }

  /* Reduced motion */
  @media (prefers-reduced-motion: reduce) {
    *, *::before, *::after {
      animation-duration: 0.01ms !important;
      animation-iteration-count: 1 !important;
      transition-duration: 0.01ms !important;
    }
  }
</style>
</head>
<body>

<!-- Floating Particles Background -->
<div class="particles" id="particles"></div>

<!-- Detail View Overlay -->
<div id="detailView">
  <button class="close-btn" onclick="closeDetails()" aria-label="Close detail view">×</button>
  <div class="detail-hero">
    <img id="d-img" src="" alt="Vehicle">
    <div class="detail-gradient"></div>
  </div>
  <div class="detail-content">
    <div class="detail-header">
      <div class="detail-title">
        <span id="d-series">SERIES NAME</span>
        <h2 id="d-name">Model Name</h2>
      </div>
      <div class="detail-price" id="d-price">$00,000</div>
    </div>

    <div class="specs-box-container">
      <div class="hud-box">
        <h4>Max Range</h4>
        <p id="d-range">0 KM</p>
      </div>
      <div class="hud-box">
        <h4>Top Speed</h4>
        <p id="d-speed">0 km/h</p>
      </div>
      <div class="hud-box">
        <h4>Horsepower</h4>
        <p id="d-power">0 HP</p>
      </div>
    </div>

    <div class="detail-desc">
      <p id="d-desc">Vehicle description...</p>
    </div>
    
    <button class="submit-btn" style="width:auto; padding: 1rem 3rem;">Reserve Configuration</button>
  </div>
</div>

<!-- Location Map Modal -->
<div id="locationModal">
  <div class="map-content">
    <div class="map-header">
      <div>
        <h3 id="map-title">Location Name</h3>
        <span id="map-country">Country</span>
      </div>
      <button class="close-btn" style="position:relative; top:0; right:0; transform:none;" onclick="closeLocationModal()" aria-label="Close map">×</button>
    </div>
    <div class="map-body">
      <div class="map-iframe-box" id="mapContainer"></div>
      <div class="map-info-panel">
        <div class="address-block">
          <p id="map-address">123 Street Name</p>
          <p id="map-city">City, State</p>
          <strong id="map-phone" style="margin-top:0.5rem; display:block;">+00 000 000</strong>
        </div>
        <div class="action-buttons">
          <a href="#" id="call-btn" class="action-btn btn-call">
            <svg style="width:14px; height:14px; fill:currentColor;" viewBox="0 0 24 24"><path d="M6.62 10.79c1.44 2.83 3.76 5.14 6.59 6.59l2.2-2.2c.27-.27.67-.36 1.02-.24 1.12.37 2.33.57 3.57.57.55 0 1 .45 1 1V20c0 .55-.45 1-1 1-9.39 0-17-7.61-17-17 0-.55.45-1 1-1h3.5c.55 0 1 .45 1 1 0 1.25.2 2.45.57 3.57.11.35.03.74-.25 1.02l-2.2 2.2z"/></svg>
            Call
          </a>
          <a href="#" id="dir-btn" class="action-btn btn-dir" target="_blank" rel="noopener">
            <svg style="width:14px; height:14px; fill:currentColor;" viewBox="0 0 24 24"><path d="M12 2C8.13 2 5 5.13 5 9c0 5.25 7 13 7 13s7-7.75 7-13c0-3.87-3.13-7-7-7zm0 9.5c-1.38 0-2.5-1.12-2.5-2.5s1.12-2.5 2.5-2.5 2.5 1.12 2.5 2.5-1.12 2.5-2.5 2.5z"/></svg>
            Directions
          </a>
        </div>
      </div>
    </div>
  </div>
</div>

<!-- Header Hidden for Public View -->
<header>
  <h1>GRAPE<span>SINO</span></h1>
  <nav>
    <a href="#cars">Models</a>
    <a href="#showrooms">Locations</a>
    <a href="#contact">Contact</a>
  </nav>
</header>

<!-- Hero Section -->
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
    <div class="showroom-card sl" onclick="openLocation('Colombo', 'Sri Lanka', 'Level 04, Lotus Tower Precinct, Colombo 01', '+94 11 234 5678', 'Lotus+Tower+Colombo')">
      <span class="country">Sri Lanka</span>
      <h3>Colombo</h3>
      <p>Level 04, Lotus Tower Precinct</p>
      <p>Colombo 01</p>
      <p style="margin-top:1rem; color:#fff; font-weight:600;">+94 11 234 5678</p>
      <div class="locate-hint">View on Map</div>
    </div>

    <div class="showroom-card usa" onclick="openLocation('New York', 'United States', '456 Broadway, SoHo, New York, NY 10013', '+1 212 555 0123', '456+Broadway+New+York')">
      <span class="country">United States</span>
      <h3>New York</h3>
      <p>456 Broadway, SoHo</p>
      <p>New York, NY 10013</p>
      <p style="margin-top:1rem; color:#fff; font-weight:600;">+1 212 555 0123</p>
      <div class="locate-hint">View on Map</div>
    </div>

    <div class="showroom-card th" onclick="openLocation('Bangkok', 'Thailand', 'Icon Siam, 299 Charoen Nakhon Rd, Khlong San, Bangkok 10600', '+66 2 8888 9999', 'Icon+Siam+Bangkok')">
      <span class="country">Thailand</span>
      <h3>Bangkok</h3>
      <p>Icon Siam, 299 Charoen Nakhon Rd</p>
      <p>Khlong San, Bangkok 10600</p>
      <p style="margin-top:1rem; color:#fff; font-weight:600;">+66 2 8888 9999</p>
      <div class="locate-hint">View on Map</div>
    </div>
  </div>
</div>

<div class="contact-section" id="contact">
  <div class="container" style="padding:0;">
    <h2 class="section-title">Get in Touch</h2>
    <div class="form-box">
      <form action="#" method="post">
        <input type="text" name="name" placeholder="Your Name" required aria-label="Your name">
        <input type="email" name="email" placeholder="Your Email" required aria-label="Your email">
        <textarea name="message" rows="4" placeholder="Your Message" required aria-label="Your message"></textarea>
        <button type="submit" class="submit-btn">Send Message</button>
      </form>
    </div>
  </div>
</div>

<footer>
  <div class="footer-brand">GRAPE<span>SINO</span></div>
  
  <div class="footer-socials">
    <a href="https://www.youtube.com" target="_blank" rel="noopener" class="social-icon" title="YouTube" aria-label="YouTube">
      <svg viewBox="0 0 24 24"><path d="M19.615 3.184c-3.604-.246-11.631-.245-15.23 0-3.897.266-4.356 2.62-4.385 8.816.029 6.185.484 8.549 4.385 8.816 3.6.245 11.626.246 15.23 0 3.897-.266 4.356-2.62 4.385-8.816-.029-6.185-.484-8.549-4.385-8.816zm-10.615 12.816v-8l8 3.993-8 4.007z"/></svg>
    </a>
    
    <a href="https://www.facebook.com" target="_blank" rel="noopener" class="social-icon" title="Facebook" aria-label="Facebook">
      <svg viewBox="0 0 24 24"><path d="M9 8h-3v4h3v12h5v-12h3.642l.358-4h-4v-1.667c0-.955.192-1.333 1.115-1.333h2.885v-5h-3.808c-3.596 0-5.192 1.583-5.192 4.615v3.385z"/></svg>
    </a>

    <a href="https://www.instagram.com" target="_blank" rel="noopener" class="social-icon" title="Instagram" aria-label="Instagram">
      <svg viewBox="0 0 24 24"><path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"/></svg>
    </a>
  </div>

  <p class="footer-text">2026 GRAPESINO Automotive. All Rights Reserved.</p>
</footer>

<script>
/* ----- Car Data (Original Images Restored) ----- */
const carData = [
  { 
    name: "LSGMAXI", 
    series: "COMFORT", 
    price: 77000, 
    range: "850 KM", 
    speed: 280, 
    power: 620, 
    img: "https://images.unsplash.com/photo-1770297345804-e6af74ee764d?w=600&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHx0b3BpYy1mZWVkfDExfHhIeFlUTUhMZ09jfHxlbnwwfHx8fHw%3D",
    desc: "The LSGMAXI redefines executive travel. Featuring active noise cancellation and a suspension system that reads the road 500 times per second, this vehicle offers a sanctuary of silence and smoothness."
  },
  { 
    name: "GFANCY", 
    series: "LUXURY", 
    price: 45000, 
    range: "420 KM", 
    speed: 210, 
    power: 310, 
    img: "https://images.unsplash.com/photo-1618418721668-0d1f72aa4bab?w=600&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTF8fGx1eHVyeSUyMGNhcnxlbnwwfHwwfHx8MA%3D%3D",
    desc: "Designed for the urban elite, the GFANCY combines compact agility with opulent interior finishes. Hand-stitched leather and ambient lighting make every commute an event."
  },
  { 
    name: "DIOMANDLG", 
    series: "VELOCITY", 
    price: 125000, 
    range: "600 KM", 
    speed: 350, 
    power: 1200, 
    img: "https://images.unsplash.com/photo-1628519592419-bf288f08cef5?w=600&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8M3x8c3BvcnRzJTIwY2FyfGVufDB8fDB8fHww",
    desc: "A masterpiece of aerodynamics. The DIOMANDLG isn't just a car; it's a land-based rocket. With carbon-fiber monocoque construction and quad-motor setup delivering 1200HP."
  },
  { 
    name: "GRAPE-4x4", 
    series: "HILL SIDE", 
    price: 92000, 
    range: "1200 KM", 
    speed: 190, 
    power: 800, 
    img: "https://images.unsplash.com/photo-1667374268462-4e6bee52fffe?w=600&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTZ8fGhpbGwlMjBzaWRlJTIwbXVkZHklMjB0cmFja3MlMjBjYXIlMjByYWNpbmd8ZW58MHx8MHx8fDA%3D",
    desc: "Where the road ends, the GRAPE-4x4 begins. Equipped with military-grade tires and AI-assisted traction control that adapts to mud, snow, and sand instantly."
  },
  { 
    name: "SHADOW-X", 
    series: "SPORT", 
    price: 150000, 
    range: "750 KM", 
    speed: 310, 
    power: 900, 
    img: "https://plus.unsplash.com/premium_photo-1686730540277-c7e3a5571553?w=600&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MXx8c3BvcnRzJTIwY2FyfGVufDB8fDB8fHww",
    desc: "Stealth meets aggression. The SHADOW-X features a matte finish coating and a cockpit designed around the driver, delivering visceral feedback and precision handling."
  },
  { 
    name: "LocalG", 
    series: "SL-origin", 
    price: 19500, 
    range: "1500 KM", 
    speed: 160, 
    power: 2000, 
    img: "https://images.unsplash.com/photo-1628832908835-814f799db7c5?w=600&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTl8fGNhcnMlMjBsdXh1cnl8ZW58MHx8MHx8fDA%3D",
    desc: "The pride of domestic engineering. The LocalG is built for efficiency and endurance, designed to cross the country on a single charge."
  }
];

const carGrid = document.getElementById("carGrid");
const detailView = document.getElementById("detailView");

// Render Grid
carData.forEach((car, index) => {
  const carCard = document.createElement("div");
  carCard.classList.add("car-card");
  carCard.style.animationDelay = `${index * 0.12}s`;
  carCard.onclick = () => openDetails(index);
  carCard.setAttribute('role', 'button');
  carCard.setAttribute('tabindex', '0');
  carCard.setAttribute('aria-label', `View details for ${car.name}`);
  
  carCard.innerHTML = `
    <div class="img-wrapper">
      <img src="${car.img}" alt="${car.name}" loading="lazy">
    </div>
    <div class="car-info">
      <span class="series-badge">${car.series}</span>
      <h3>${car.name}</h3>
      <span class="price">$${car.price.toLocaleString()}</span>
      
      <div class="card-stats">
        <div class="stat">
          <small>Range</small>
          <span>${car.range}</span>
        </div>
        <div class="stat">
          <small>Speed</small>
          <span>${car.speed}</span>
        </div>
        <div class="stat">
          <small>Power</small>
          <span>${car.power}</span>
        </div>
      </div>
    </div>
  `;
  carGrid.appendChild(carCard);
});

// Keyboard accessibility for cards
document.querySelectorAll('.car-card').forEach((card, i) => {
  card.addEventListener('keydown', (e) => {
    if (e.key === 'Enter' || e.key === ' ') {
      e.preventDefault();
      openDetails(i);
    }
  });
});

function openDetails(index) {
  const car = carData[index];
  document.getElementById('d-img').src = car.img;
  document.getElementById('d-name').textContent = car.name;
  document.getElementById('d-series').textContent = car.series + " SERIES";
  document.getElementById('d-price').textContent = "$" + car.price.toLocaleString();
  document.getElementById('d-range').textContent = car.range;
  document.getElementById('d-speed').textContent = car.speed + " km/h";
  document.getElementById('d-power').textContent = car.power + " HP";
  document.getElementById('d-desc').textContent = car.desc;

  detailView.classList.add('active');
  document.body.style.overflow = 'hidden';
}

function closeDetails() {
  detailView.classList.remove('active');
  document.body.style.overflow = 'auto';
}

/* ----- Location Logic ----- */
function openLocation(city, country, address, phone, query) {
  const modal = document.getElementById('locationModal');
  
  document.getElementById('map-title').textContent = city + " Experience Center";
  document.getElementById('map-country').textContent = country;
  document.getElementById('map-address').textContent = address.split(',').slice(0, 2).join(', ');
  document.getElementById('map-city').textContent = address.split(',').slice(2).join(', ').trim();
  document.getElementById('map-phone').textContent = phone;

  document.getElementById('call-btn').href = "tel:" + phone.replace(/ /g, '');
  document.getElementById('dir-btn').href = "https://www.google.com/maps/search/?api=1&query=" + query;

  const mapContainer = document.getElementById('mapContainer');
  mapContainer.innerHTML = `
    <div style="width:100%;height:100%;display:flex;flex-direction:column;align-items:center;justify-content:center;background:#111;color:#888;">
      <svg style="width:48px;height:48px;margin-bottom:1rem;fill:#00c8aa;" viewBox="0 0 24 24"><path d="M12 2C8.13 2 5 5.13 5 9c0 5.25 7 13 7 13s7-7.75 7-13c0-3.87-3.13-7-7-7zm0 9.5c-1.38 0-2.5-1.12-2.5-2.5s1.12-2.5 2.5-2.5 2.5 1.12 2.5 2.5-1.12 2.5-2.5 2.5z"/></svg>
      <p style="font-size:1rem;margin-bottom:0.5rem;">Location Preview</p>
      <p style="font-size:0.8rem;">Click "Directions" to open in Google Maps</p>
    </div>
  `;

  modal.classList.add('active');
  document.body.style.overflow = 'hidden';
}

function closeLocationModal() {
  const modal = document.getElementById('locationModal');
  modal.classList.remove('active');
  document.body.style.overflow = 'auto';
  setTimeout(() => {
    document.getElementById('mapContainer').innerHTML = "";
  }, 400);
}

// Close modals on escape key
window.addEventListener('keydown', (e) => {
  if (e.key === 'Escape') {
    closeDetails();
    closeLocationModal();
  }
});

// Create floating particles
function createParticles() {
  const container = document.getElementById('particles');
  const particleCount = 15;
  
  for (let i = 0; i < particleCount; i++) {
    const particle = document.createElement('div');
    particle.classList.add('particle');
    particle.style.left = Math.random() * 100 + '%';
    particle.style.animationDelay = Math.random() * 15 + 's';
    particle.style.animationDuration = (15 + Math.random() * 10) + 's';
    particle.style.width = (2 + Math.random() * 3) + 'px';
    particle.style.height = particle.style.width;
    particle.style.opacity = 0.2 + Math.random() * 0.4;
    container.appendChild(particle);
  }
}

createParticles();

// Smooth scroll for anchor links
document.querySelectorAll('a[href^="#"]').forEach(anchor => {
  anchor.addEventListener('click', function (e) {
    e.preventDefault();
    const target = document.querySelector(this.getAttribute('href'));
    if (target) {
      target.scrollIntoView({ behavior: 'smooth', block: 'start' });
    }
  });
});
</script>

</body>
</html>
