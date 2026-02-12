<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>GRAPESINO Vehicles | Future of Driving</title>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700;900&display=swap" rel="stylesheet">
<style>
  /* ---------- Global & Reset ---------- */
  * {margin:0; padding:0; box-sizing:border-box;}
  body {
    font-family:'Inter', sans-serif; 
    background-color:#050505; 
    color:#fff; 
    line-height:1.6; 
    overflow-x: hidden;
    background-image: 
      radial-gradient(circle at 10% 20%, rgba(0, 255, 234, 0.03) 0%, transparent 40%),
      radial-gradient(circle at 90% 80%, rgba(100, 100, 255, 0.03) 0%, transparent 40%);
  }
  a {text-decoration:none; color:inherit; transition:0.3s;}
  ul {list-style:none;}

  /* Scrollbar Styling */
  ::-webkit-scrollbar {width: 8px;}
  ::-webkit-scrollbar-track {background: #111;}
  ::-webkit-scrollbar-thumb {background: #00ffea; border-radius: 4px;}

  /* ---------- Header ---------- */
  header {
    padding:1.5rem 2rem; 
    display:flex; 
    justify-content:space-between; 
    align-items:center; 
    background:rgba(5,5,5,0.8); 
    backdrop-filter:blur(20px); 
    -webkit-backdrop-filter: blur(20px);
    position:sticky; 
    top:0; 
    z-index:100; 
    border-bottom: 1px solid rgba(255,255,255,0.05);
  }
  header h1 {font-size:2rem; font-weight:900; letter-spacing:1px; color:#fff; text-transform: uppercase; text-shadow: 0 0 20px rgba(0,255,234,0.3);}
  header h1 span {color:#00ffea;}
  
  nav {display:flex; gap:2rem;}
  nav a {font-weight:600; font-size:0.95rem; opacity:0.7; position:relative;}
  nav a:hover {opacity:1; color:#00ffea; text-shadow: 0 0 10px rgba(0,255,234,0.5);}
  nav a::after {content:""; position:absolute; width:0; height:2px; bottom:-4px; left:0; background:#00ffea; transition:0.3s cubic-bezier(0.4, 0, 0.2, 1);}
  nav a:hover::after {width:100%;}

  /* ---------- Layout Utilities ---------- */
  .container {max-width:1200px; margin:auto; padding:5rem 2rem;}
  .section-title {
    font-size:2.5rem; 
    font-weight:800; 
    text-align:center; 
    margin-bottom:3.5rem; 
    background:linear-gradient(to bottom, #fff, #666); 
    -webkit-background-clip:text; 
    -webkit-text-fill-color:transparent;
    letter-spacing: -1px;
    position: relative;
  }
  .section-title::after {
    content: ''; display: block; width: 60px; height: 4px; 
    background: #00ffea; margin: 1rem auto 0; border-radius: 2px;
    box-shadow: 0 0 10px #00ffea;
  }

  /* ---------- Car Grid (Revamped) ---------- */
  .car-grid {display:grid; grid-template-columns:repeat(auto-fit, minmax(320px,1fr)); gap:2.5rem;}
  
  .car-card {
    background: linear-gradient(145deg, #111, #0a0a0a); 
    border: 1px solid rgba(255,255,255,0.08);
    border-radius:20px; 
    overflow:hidden; 
    cursor:pointer;
    transition: all 0.4s cubic-bezier(0.25, 0.46, 0.45, 0.94);
    position: relative;
    opacity: 0; 
    animation: fadeInUp 0.8s forwards;
    box-shadow: 0 10px 30px rgba(0,0,0,0.5);
  }
  
  .car-card:hover {
    transform: translateY(-10px) scale(1.01); 
    box-shadow: 0 20px 50px rgba(0, 255, 234, 0.15);
    border-color: #00ffea;
  }
  .car-card:hover .img-wrapper img {transform: scale(1.1);}
  .car-card::before {
    content: ''; position: absolute; top: 0; left: 0; width: 100%; height: 100%;
    border-radius: 20px; padding: 1px;
    background: linear-gradient(45deg, transparent, #00ffea, transparent);
    -webkit-mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
    mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
    -webkit-mask-composite: xor; mask-composite: exclude;
    opacity: 0; transition: 0.4s;
  }
  .car-card:hover::before { opacity: 1; }

  .img-wrapper {width: 100%; height: 220px; overflow: hidden; position: relative;}
  .img-wrapper img {width:100%; height:100%; object-fit:cover; transition:0.6s cubic-bezier(0.25, 0.46, 0.45, 0.94); filter: saturate(0.8);}
  .car-card:hover .img-wrapper img { filter: saturate(1.2); }
  .img-wrapper::after {
    content:''; position: absolute; bottom:0; left:0; width:100%; height:50%;
    background: linear-gradient(to top, #111, transparent);
  }

  .car-info {padding:1.5rem;}
  
  .series-badge {
    display: inline-block;
    font-size: 0.7rem; font-weight: 800; letter-spacing: 1px;
    color: #000; background: #00ffea;
    padding: 4px 8px; border-radius: 4px;
    margin-bottom: 0.8rem;
    text-transform: uppercase;
    box-shadow: 0 0 10px rgba(0,255,234,0.4);
  }

  .car-info h3 {
    font-size:1.8rem; margin-bottom:0.2rem; 
    font-weight: 900;
    background: linear-gradient(90deg, #fff, #aaa);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
  }

  .price {font-size:1.3rem; font-weight:600; color:#00ffea; display:block; margin-bottom: 1.5rem; text-shadow: 0 0 10px rgba(0,255,234,0.3);}

  .card-stats {
    display: grid; grid-template-columns: 1fr 1fr 1fr;
    border-top: 1px solid rgba(255,255,255,0.1);
    padding-top: 1rem;
    gap: 0.5rem;
  }
  .stat {text-align: center;}
  .stat small {display: block; color: #666; font-size: 0.7rem; text-transform: uppercase; margin-bottom: 2px;}
  .stat span {display: block; color: #eee; font-size: 0.95rem; font-weight: 700;}


  /* ---------- Detail View (HUD Style) ---------- */
  #detailView {
    position: fixed; top: 0; left: 0; width: 100%; height: 100vh;
    background: #050505; z-index: 200;
    overflow-y: auto;
    transform: translateY(100%);
    transition: transform 0.6s cubic-bezier(0.8, 0, 0.1, 1);
    display: flex; flex-direction: column;
  }
  #detailView.active {transform: translateY(0);}

  .detail-hero {width: 100%; height: 55vh; position: relative;}
  .detail-hero img {width: 100%; height: 100%; object-fit: cover;}
  .detail-gradient {
    position: absolute; bottom: 0; left: 0; width: 100%; height: 100%;
    background: linear-gradient(to top, #050505 5%, transparent 60%);
  }

  .detail-content {
    max-width: 1100px; margin: -100px auto 0; padding: 2rem; position: relative; z-index: 2;
    opacity: 0; transform: translateY(30px); transition: 0.5s 0.4s;
  }
  #detailView.active .detail-content {opacity: 1; transform: translateY(0);}

  .detail-header {
    display: flex; justify-content: space-between; align-items: flex-end; margin-bottom: 3rem; flex-wrap: wrap; gap: 1rem;
    border-bottom: 1px solid rgba(255,255,255,0.1); padding-bottom: 2rem;
  }
  .detail-title h2 {font-size: 3.5rem; line-height: 1; color: #fff; text-transform: uppercase; letter-spacing: -2px;}
  .detail-title span {font-size: 1.2rem; color: #00ffea; letter-spacing: 4px; font-weight: 700;}
  .detail-price {font-size: 3rem; font-weight: 700; color: #fff; text-shadow: 0 0 20px rgba(255,255,255,0.2);}

  .specs-box-container {
    display: flex; gap: 1.5rem; margin-bottom: 3rem; flex-wrap: wrap;
  }
  .hud-box {
    flex: 1; min-width: 140px;
    background: rgba(255,255,255,0.03); border: 1px solid rgba(255,255,255,0.1);
    padding: 1.5rem; border-radius: 12px; backdrop-filter: blur(10px);
    transition: 0.3s; position: relative; overflow: hidden;
  }
  .hud-box:hover {background: rgba(0,255,234,0.05); border-color: #00ffea; transform: translateY(-5px);}
  .hud-box::before {
    content: ''; position: absolute; top: 0; left: 0; width: 3px; height: 100%; background: #00ffea; opacity: 0.5;
  }
  .hud-box h4 {color: #888; font-size: 0.8rem; margin-bottom: 0.5rem; text-transform: uppercase; letter-spacing: 1px;}
  .hud-box p {color: #fff; font-size: 1.8rem; font-weight: 700;}

  .detail-desc {
    font-size: 1.1rem; color: #ccc; margin-bottom: 3rem; max-width: 800px; line-height: 1.8;
  }

  .close-btn {
    position: fixed; top: 2rem; right: 2rem; width: 50px; height: 50px;
    background: rgba(0,0,0,0.5); backdrop-filter: blur(10px); border: 1px solid rgba(255,255,255,0.2);
    color: #fff; border-radius: 50%; font-size: 1.5rem; cursor: pointer; z-index: 210;
    display: flex; align-items: center; justify-content: center; transition: 0.3s;
  }
  .close-btn:hover {background: #00ffea; color: #000; transform: rotate(90deg);}

  /* ---------- Showrooms with Faded Flags ---------- */
  .showroom-wrapper {display: flex; flex-wrap: wrap; justify-content: center; gap: 2rem;}
  
  .showroom-card {
    background-color: #111;
    background-size: cover;
    background-position: center;
    padding: 3rem 2rem; border-radius: 20px; width: 320px; text-align: center;
    border: 1px solid rgba(255,255,255,0.1); position: relative; overflow: hidden;
    transition: 0.4s;
    box-shadow: 0 10px 30px rgba(0,0,0,0.3);
    cursor: pointer; /* Added cursor pointer */
  }

  /* Specific Flag Backgrounds with Dark Overlay */
  .showroom-card.sl { background-image: linear-gradient(rgba(10,10,10,0.85), rgba(10,10,10,0.95)), url('https://flagcdn.com/w640/lk.png'); }
  .showroom-card.usa { background-image: linear-gradient(rgba(10,10,10,0.85), rgba(10,10,10,0.95)), url('https://flagcdn.com/w640/us.png'); }
  .showroom-card.th { background-image: linear-gradient(rgba(10,10,10,0.85), rgba(10,10,10,0.95)), url('https://flagcdn.com/w640/th.png'); }

  .showroom-card:hover {transform: translateY(-10px); border-color: #00ffea;}
  .showroom-card h3 {color: #fff; font-size: 1.8rem; margin-bottom: 0.5rem; position: relative; z-index: 2;}
  .showroom-card .country {color: #00ffea; font-size: 0.9rem; font-weight: 800; text-transform: uppercase; margin-bottom: 1rem; display: block; letter-spacing: 2px;}
  .showroom-card p {color: #ccc; font-size: 1rem; margin-bottom: 0.4rem; position: relative; z-index: 2;}
  
  /* "Click to Locate" Hint */
  .locate-hint {
    display: inline-block; margin-top: 1.5rem; padding: 0.5rem 1rem;
    border: 1px solid rgba(255,255,255,0.2); border-radius: 20px;
    font-size: 0.8rem; color: #fff; text-transform: uppercase; letter-spacing: 1px;
    background: rgba(0,0,0,0.3); transition: 0.3s;
  }
  .showroom-card:hover .locate-hint {
    background: #00ffea; color: #000; border-color: #00ffea;
  }

  /* ---------- NEW: Location Map Modal ---------- */
  #locationModal {
    position: fixed; top: 0; left: 0; width: 100%; height: 100vh;
    background: rgba(5,5,5,0.95); backdrop-filter: blur(20px); z-index: 300;
    display: flex; justify-content: center; align-items: center;
    opacity: 0; visibility: hidden; transition: 0.4s;
  }
  #locationModal.active { opacity: 1; visibility: visible; }
  
  .map-content {
    width: 90%; max-width: 1000px; height: 80vh;
    background: #111; border-radius: 20px; border: 1px solid #333;
    display: flex; flex-direction: column; overflow: hidden;
    position: relative; transform: scale(0.9); transition: 0.4s;
    box-shadow: 0 0 50px rgba(0,0,0,0.5);
  }
  #locationModal.active .map-content { transform: scale(1); }

  .map-header {
    padding: 1.5rem; border-bottom: 1px solid #222; display: flex; justify-content: space-between; align-items: center;
    background: #0a0a0a;
  }
  .map-header h3 { font-size: 1.5rem; color: #fff; }
  .map-header h3 span { color: #00ffea; font-size: 0.8rem; display: block; text-transform: uppercase; letter-spacing: 2px; }

  .map-body {
    flex: 1; display: flex; flex-direction: column;
  }
  
  /* Responsive Map & Info */
  .map-iframe-box { flex: 1; position: relative; min-height: 300px; }
  .map-iframe-box iframe { width: 100%; height: 100%; border: 0; position: absolute; top: 0; left: 0; }

  .map-info-panel {
    padding: 1.5rem; background: #050505; border-top: 1px solid #222;
    display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 1rem;
  }
  .address-block { flex: 1; min-width: 200px; }
  .address-block p { color: #ccc; font-size: 0.95rem; margin-bottom: 0.3rem; }
  .address-block strong { color: #fff; font-size: 1.1rem; }

  .action-buttons { display: flex; gap: 1rem; }
  .action-btn {
    padding: 0.8rem 1.5rem; border-radius: 8px; font-weight: 700; font-size: 0.9rem;
    border: none; cursor: pointer; transition: 0.3s; text-transform: uppercase; display: flex; align-items: center; gap: 0.5rem;
  }
  .btn-call { background: transparent; border: 1px solid #00ffea; color: #00ffea; }
  .btn-call:hover { background: #00ffea; color: #000; }
  .btn-dir { background: #fff; color: #000; }
  .btn-dir:hover { background: #ccc; }

  /* ---------- Contact ---------- */
  .contact-section {background: #0a0a0a; margin-top: 4rem; padding: 6rem 2rem; border-top: 1px solid #222;}
  .form-box {max-width: 600px; margin: auto;}
  
  input, textarea {
    width: 100%; background: #161616; border: 1px solid #333; padding: 1.2rem; margin-bottom: 1.2rem;
    color: #fff; font-family: 'Inter', sans-serif; border-radius: 12px; transition: 0.3s;
  }
  input:focus, textarea:focus {outline: none; border-color: #00ffea; background: #1a1a1a; box-shadow: 0 0 15px rgba(0,255,234,0.1);}
  
  button.submit-btn {
    width: 100%; padding: 1.2rem; background: linear-gradient(45deg, #00ffea, #00c3b3); 
    color: #000; border: none; font-weight: 800; font-size: 1rem;
    border-radius: 12px; cursor: pointer; transition: 0.3s; text-transform: uppercase; letter-spacing: 1px;
    position: relative; overflow: hidden;
  }
  button.submit-btn::after {
    content: ''; position: absolute; top: -50%; left: -50%; width: 200%; height: 200%;
    background: linear-gradient(transparent, rgba(255,255,255,0.4), transparent);
    transform: rotate(45deg) translateY(-100%);
    transition: 0.5s;
  }
  button.submit-btn:hover::after { transform: rotate(45deg) translateY(100%); }
  button.submit-btn:hover {transform: scale(1.02); box-shadow: 0 0 30px rgba(0,255,234,0.4);}

  /* ---------- Footer ---------- */
  footer {
    text-align: center; 
    padding: 5rem 2rem; 
    border-top: 1px solid #111; 
    background: #030303;
    position: relative;
  }
  footer::before {
    content: '';
    position: absolute; top: 0; left: 0; width: 100%; height: 100%;
    background-image: 
      linear-gradient(rgba(255,255,255,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(255,255,255,0.03) 1px, transparent 1px);
    background-size: 40px 40px;
    opacity: 0.2;
    pointer-events: none;
  }

  .footer-brand {
    font-size: 2.5rem; font-weight: 900; letter-spacing: 1px; color: #fff; text-transform: uppercase; 
    margin-bottom: 1rem; position: relative; z-index: 2;
    text-shadow: 0 0 20px rgba(255,255,255,0.1);
  }
  .footer-brand span { color: #00ffea; }

  .footer-socials {
    display: flex; justify-content: center; gap: 2.5rem; 
    margin: 2.5rem 0; position: relative; z-index: 2;
  }

  .social-icon {
    width: 50px; height: 50px; border-radius: 50%;
    background: rgba(255,255,255,0.05);
    border: 1px solid #333;
    display: flex; align-items: center; justify-content: center;
    color: #ccc;
    transition: 0.4s cubic-bezier(0.25, 0.46, 0.45, 0.94);
    position: relative;
  }

  .social-icon svg {
    width: 24px; height: 24px; fill: currentColor;
    transition: 0.3s;
  }

  .social-icon:hover {
    background: #00ffea; border-color: #00ffea;
    color: #000; transform: translateY(-8px) rotate(360deg);
    box-shadow: 0 10px 25px rgba(0,255,234,0.4);
  }

  .footer-text {
    color: #444; font-size: 0.85rem; text-transform: uppercase; 
    letter-spacing: 2px; position: relative; z-index: 2;
    margin-top: 2rem;
  }

  @keyframes fadeInUp {
    from {opacity:0; transform:translateY(40px);}
    to {opacity:1; transform:translateY(0);}
  }
</style>
</head>
<body>

<!-- Detail View Overlay -->
<div id="detailView">
  <button class="close-btn" onclick="closeDetails()">&times;</button>
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
    
    <button class="submit-btn" style="width:auto; padding: 1rem 4rem;">Reserve Configuration</button>
  </div>
</div>

<!-- NEW: Location Map Modal -->
<div id="locationModal">
  <div class="map-content">
    <div class="map-header">
      <div>
        <h3 id="map-title">Location Name</h3>
        <span id="map-country">Country</span>
      </div>
      <button class="close-btn" style="position:relative; top:0; right:0; transform:none;" onclick="closeLocationModal()">&times;</button>
    </div>
    <div class="map-body">
      <div class="map-iframe-box" id="mapContainer">
         <!-- Iframe Injected Here -->
      </div>
      <div class="map-info-panel">
        <div class="address-block">
          <p id="map-address">123 Street Name</p>
          <p id="map-city">City, State</p>
          <strong id="map-phone" style="margin-top:0.5rem; display:block;">+00 000 000</strong>
        </div>
        <div class="action-buttons">
          <a href="#" id="call-btn" class="action-btn btn-call">
            <!-- Phone Icon SVG -->
            <svg style="width:16px; height:16px; fill:currentColor;" viewBox="0 0 24 24"><path d="M6.62 10.79c1.44 2.83 3.76 5.14 6.59 6.59l2.2-2.2c.27-.27.67-.36 1.02-.24 1.12.37 2.33.57 3.57.57.55 0 1 .45 1 1V20c0 .55-.45 1-1 1-9.39 0-17-7.61-17-17 0-.55.45-1 1-1h3.5c.55 0 1 .45 1 1 0 1.25.2 2.45.57 3.57.11.35.03.74-.25 1.02l-2.2 2.2z"/></svg>
            Call Supplier
          </a>
          <a href="#" id="dir-btn" class="action-btn btn-dir" target="_blank">
            <!-- Map Marker Icon SVG -->
            <svg style="width:16px; height:16px; fill:currentColor;" viewBox="0 0 24 24"><path d="M12 2C8.13 2 5 5.13 5 9c0 5.25 7 13 7 13s7-7.75 7-13c0-3.87-3.13-7-7-7zm0 9.5c-1.38 0-2.5-1.12-2.5-2.5s1.12-2.5 2.5-2.5 2.5 1.12 2.5 2.5-1.12 2.5-2.5 2.5z"/></svg>
            Get Directions
          </a>
        </div>
      </div>
    </div>
  </div>
</div>

<header>
  <h1>GRAPE<span>SINO</span></h1>
  <nav>
    <a href="#cars">Models</a>
    <a href="#showrooms">Locations</a>
    <a href="#contact">Contact</a>
  </nav>
</header>

<div class="container" id="cars">
  <h2 class="section-title">The Collection</h2>
  <div class="car-grid" id="carGrid">
    <!-- JS Injection -->
  </div>
</div>

<div class="container" id="showrooms">
  <h2 class="section-title">Global Experience Centers</h2>
  <div class="showroom-wrapper">
    
    <!-- Added onclick events and location data attributes -->
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
    <h2 class="section-title">Initiate Contact</h2>
    <div class="form-box">
      <form action="mailto:youremail@gmail.com" method="post" enctype="text/plain">
        <input type="text" name="name" placeholder="Name" required>
        <input type="email" name="email" placeholder="Email" required>
        <textarea name="message" rows="4" placeholder="Message" required></textarea>
        <button type="submit" class="submit-btn">Transmit Message</button>
      </form>
    </div>
  </div>
</div>

<footer>
  <div class="footer-brand">GRAPE<span>SINO</span></div>
  
  <div class="footer-socials">
    <a href="https://www.youtube.com" target="_blank" class="social-icon" title="YouTube">
      <svg viewBox="0 0 24 24">
        <path d="M19.615 3.184c-3.604-.246-11.631-.245-15.23 0-3.897.266-4.356 2.62-4.385 8.816.029 6.185.484 8.549 4.385 8.816 3.6.245 11.626.246 15.23 0 3.897-.266 4.356-2.62 4.385-8.816-.029-6.185-.484-8.549-4.385-8.816zm-10.615 12.816v-8l8 3.993-8 4.007z"/>
      </svg>
    </a>
    
    <a href="https://www.facebook.com" target="_blank" class="social-icon" title="Facebook">
      <svg viewBox="0 0 24 24">
        <path d="M9 8h-3v4h3v12h5v-12h3.642l.358-4h-4v-1.667c0-.955.192-1.333 1.115-1.333h2.885v-5h-3.808c-3.596 0-5.192 1.583-5.192 4.615v3.385z"/>
      </svg>
    </a>

    <a href="https://www.instagram.com" target="_blank" class="social-icon" title="Instagram">
      <svg viewBox="0 0 24 24">
        <path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"/>
      </svg>
    </a>
  </div>

  <p class="footer-text">&copy; 2026 GRAPESINO Automotive. Engineering the Unknown.</p>
</footer>

<script>
/* ----- Car Data & Logic (Preserved) ----- */
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
    desc: "Designed for the urban elite, the GFANCY combines compact agility with opulent interior finishes. Hand-stitched leather, ambient lighting, and a panoramic glass roof make every commute an event."
  },
  { 
    name: "DIOMANDLG", 
    series: "VELOCITY", 
    price: 125000, 
    range: "600 KM", 
    speed: 350, 
    power: 1200, 
    img: "https://images.unsplash.com/photo-1628519592419-bf288f08cef5?w=600&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8M3x8c3BvcnRzJTIwY2FyfGVufDB8fDB8fHww",
    desc: "A masterpiece of aerodynamics. The DIOMANDLG isn't just a car; it's a land-based rocket. With carbon-fiber monocoque construction and a quad-motor setup delivering 1200HP."
  },
  { 
    name: "GRAPE-4x4", 
    series: "HILL SIDE", 
    price: 92000, 
    range: "1200 KM", 
    speed: 190, 
    power: 800, 
    img: "https://images.unsplash.com/photo-1667374268462-4e6bee52fffe?w=600&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTZ8fGhpbGwlMjBzaWRlJTIwbXVkZHklMjB0cmFja3MlMjBjYXIlMjByYWNpbmd8ZW58MHx8MHx8fDA%3D",
    desc: "Where the road ends, the GRAPE-4x4 begins. Equipped with military-grade tires, water-sealed batteries, and an AI-assisted traction control system that adapts to mud, snow, and sand instantly."
  },
  { 
    name: "SHADOW-X", 
    series: "SPORT", 
    price: 150000, 
    range: "750 KM", 
    speed: 310, 
    power: 900, 
    img: "https://plus.unsplash.com/premium_photo-1686730540277-c7e3a5571553?w=600&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MXx8c3BvcnRzJTIwY2FyfGVufDB8fDB8fHww",
    desc: "Stealth meets aggression. The SHADOW-X features a matte finish radar-absorbent coating and a cockpit designed around the driver, delivering visceral feedback and precision handling."
  },
  { 
    name: "LocalG", 
    series: "SL-origin", 
    price: 19500, 
    range: "1500 KM", 
    speed: 160, 
    power: 2000, 
    img: "https://images.unsplash.com/photo-1628832908835-814f799db7c5?w=600&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTl8fGNhcnMlMjBsdXh1cnl8ZW58MHx8MHx8fDA%3D",
    desc: "The pride of domestic engineering. The LocalG is built for efficiency and endurance, designed to cross the country on a single charge while carrying heavy loads with its surprising 2000HP torque output."
  }
];

const carGrid = document.getElementById("carGrid");
const detailView = document.getElementById("detailView");

// Render Grid
carData.forEach((car, index) => {
  const carCard = document.createElement("div");
  carCard.classList.add("car-card");
  carCard.style.animationDelay = `${index * 0.1}s`;
  carCard.onclick = () => openDetails(index); 
  
  carCard.innerHTML = `
    <div class="img-wrapper">
      <img src="${car.img}" alt="${car.name}">
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

function openDetails(index) {
  const car = carData[index];
  document.getElementById('d-img').src = car.img;
  document.getElementById('d-name').innerText = car.name;
  document.getElementById('d-series').innerText = car.series + " SERIES";
  document.getElementById('d-price').innerText = "$" + car.price.toLocaleString();
  document.getElementById('d-range').innerText = car.range;
  document.getElementById('d-speed').innerText = car.speed + " km/h";
  document.getElementById('d-power').innerText = car.power + " HP";
  document.getElementById('d-desc').innerText = car.desc;

  detailView.classList.add('active');
  document.body.style.overflow = 'hidden';
}

function closeDetails() {
  detailView.classList.remove('active');
  document.body.style.overflow = 'auto';
}

/* ----- NEW: Location Logic ----- */
function openLocation(city, country, address, phone, query) {
  const modal = document.getElementById('locationModal');
  
  // Update Text Content
  document.getElementById('map-title').innerText = city + " Experience Center";
  document.getElementById('map-country').innerText = country;
  document.getElementById('map-address').innerText = address.split(',').slice(0, 2).join(', '); // First two lines
  document.getElementById('map-city').innerText = address.split(',').slice(2).join(', ').trim(); // Rest
  document.getElementById('map-phone').innerText = phone;

  // Update Buttons
  document.getElementById('call-btn').href = "tel:" + phone.replace(/ /g, '');
  document.getElementById('dir-btn').href = "https://www.google.com/maps/search/?api=1&query=" + query;

  // Inject Map Iframe
  const mapContainer = document.getElementById('mapContainer');
  mapContainer.innerHTML = `<iframe allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade" src="https://www.google.com/maps/embed/v1/place?key=AIzaSyBFw0Qbyq9zTFTd-tUY6dZWTgaQzuU17R8&q=${query}&zoom=14"></iframe>`;
  // Note: The key used is a general demo key for embeds, strictly for functional demo purposes in this environment. 
  // It might show watermarks or limits. Ideally, replace with your own Google Maps API key.

  // Activate Modal
  modal.classList.add('active');
  document.body.style.overflow = 'hidden';
}

function closeLocationModal() {
  const modal = document.getElementById('locationModal');
  modal.classList.remove('active');
  document.body.style.overflow = 'auto';
  
  // Clear map to stop loading
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
</script>

</body>
</html>
