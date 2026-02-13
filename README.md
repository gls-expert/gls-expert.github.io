
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
  <title>GRAPESINO Vehicles | Future of Driving</title>
  <link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;600;700;900&family=DM+Sans:wght@400;500;700&display=swap" rel="stylesheet">
  <style>
    :root {
      --spacing-xs: 0.8rem;
      --spacing-sm: 1.2rem;
      --spacing-md: 1.8rem;
      --spacing-lg: 3rem;
      --accent: #00c8aa;
      --accent-dark: #00a88a;
      --highlight: #c87830;
    }

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      -webkit-tap-highlight-color: transparent;
    }

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

    ::-webkit-scrollbar { width: 5px; }
    ::-webkit-scrollbar-track { background: #0d0d0f; }
    ::-webkit-scrollbar-thumb { background: var(--accent); border-radius: 3px; }

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

    /* Hero */
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
    .hero::before {
      content: '';
      position: absolute;
      width: 140vw;
      height: 140vw;
      background: radial-gradient(circle, rgba(0,200,170,0.14) 0%, transparent 60%);
      top: 50%; left: 50%;
      transform: translate(-50%, -50%);
      pointer-events: none;
      animation: heroPulse 10s ease-in-out infinite;
    }
    @keyframes heroPulse {
      0%,100% { opacity: 0.5; transform: translate(-50%,-50%) scale(1); }
      50%     { opacity: 0.75; transform: translate(-50%,-50%) scale(1.08); }
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
    .cta-primary {
      background: linear-gradient(135deg, var(--accent), var(--accent-dark));
      color: #000;
      border: none;
    }
    .cta-primary:active { transform: scale(0.97); opacity: 0.92; }

    .cta-secondary {
      background: transparent;
      color: #fff;
      border: 1px solid rgba(255,255,255,0.18);
    }
    .cta-secondary:active { border-color: var(--accent); color: var(--accent); }

    /* Car Grid */
    .car-grid {
      display: grid;
      grid-template-columns: 1fr;
      gap: 1.6rem;
    }

    .car-card {
      background: linear-gradient(165deg, #131315, #0a0a0c);
      border: 1px solid rgba(255,255,255,0.07);
      border-radius: 14px;
      overflow: hidden;
      cursor: pointer;
      transition: transform 0.25s, border-color 0.25s;
      opacity: 0;
      animation: fadeInUp 0.7s forwards;
      min-height: 320px;
    }
    .car-card:active {
      transform: scale(0.98);
      border-color: rgba(0,200,170,0.55);
    }

    .img-wrapper {
      width: 100%;
      height: 210px;
      overflow: hidden;
      position: relative;
    }
    .img-wrapper img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      transition: transform 0.4s;
    }
    .car-card:active .img-wrapper img { transform: scale(1.06); }

    .img-wrapper::after {
      content: '';
      position: absolute;
      bottom: 0; left: 0;
      width: 100%; height: 55%;
      background: linear-gradient(to top, #131315, transparent);
    }

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

    .car-info h3 {
      font-family: 'Space Grotesk', sans-serif;
      font-size: 1.38rem;
      margin-bottom: 0.3rem;
      font-weight: 700;
      color: #f5f5f5;
    }

    .price {
      font-family: 'Space Grotesk', sans-serif;
      font-size: 1.18rem;
      font-weight: 600;
      color: var(--highlight);
      display: block;
      margin-bottom: 1.1rem;
    }

    .card-stats {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      border-top: 1px solid rgba(255,255,255,0.09);
      padding-top: 1.1rem;
    }
    .stat { text-align: center; }
    .stat small {
      display: block;
      color: #666;
      font-size: 0.7rem;
      text-transform: uppercase;
    }
    .stat span {
      display: block;
      color: #ddd;
      font-size: 0.92rem;
      font-weight: 700;
    }

    /* Detail View */
    #detailView {
      position: fixed;
      inset: 0;
      background: #08080a;
      z-index: 200;
      overflow-y: auto;
      transform: translateY(100%);
      transition: transform 0.55s cubic-bezier(0.77,0,0.18,1);
      display: flex;
      flex-direction: column;
      -webkit-overflow-scrolling: touch;
    }
    #detailView.active { transform: translateY(0); }

    .detail-hero {
      width: 100%;
      height: 38vh;
      min-height: 260px;
      position: relative;
      flex-shrink: 0;
    }
    .detail-hero img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }
    .detail-gradient {
      position: absolute;
      inset: 0;
      background: linear-gradient(to top, #08080a 8%, transparent 65%);
      pointer-events: none;
    }

    .detail-content {
      max-width: 960px;
      margin: -60px auto 0;
      padding: 0 1.4rem 2.5rem;
      position: relative;
      z-index: 2;
      opacity: 0;
      transform: translateY(30px);
      transition: all 0.5s 0.25s;
    }
    #detailView.active .detail-content {
      opacity: 1;
      transform: translateY(0);
    }

    .detail-header {
      display: flex;
      flex-direction: column;
      align-items: flex-start;
      margin-bottom: 1.6rem;
      gap: 0.6rem;
    }
    .detail-title h2 {
      font-family: 'Space Grotesk', sans-serif;
      font-size: clamp(1.9rem, 7vw, 2.8rem);
      line-height: 1.05;
      color: #fff;
      text-transform: uppercase;
    }
    .detail-title span {
      font-size: 0.82rem;
      color: var(--accent);
      letter-spacing: 2.5px;
      font-weight: 700;
    }
    .detail-price {
      font-family: 'Space Grotesk', sans-serif;
      font-size: 1.55rem;
      font-weight: 700;
      color: var(--highlight);
    }

    .specs-box-container {
      display: flex;
      gap: 0.7rem;
      margin-bottom: 1.8rem;
      flex-wrap: wrap;
    }
    .hud-box {
      flex: 1;
      min-width: 110px;
      background: rgba(255,255,255,0.025);
      border: 1px solid rgba(255,255,255,0.09);
      padding: 1.1rem 0.9rem;
      border-radius: 10px;
      position: relative;
    }
    .hud-box::before {
      content: '';
      position: absolute;
      top: 0; left: 0;
      width: 3px;
      height: 100%;
      background: var(--accent);
    }
    .hud-box h4 {
      color: #777;
      font-size: 0.72rem;
      margin-bottom: 0.4rem;
      text-transform: uppercase;
    }
    .hud-box p {
      color: #fff;
      font-size: 1.15rem;
      font-weight: 700;
    }

    .detail-desc {
      font-size: 0.94rem;
      color: #bbb;
      margin-bottom: 2.2rem;
      line-height: 1.65;
    }

    .close-btn {
      position: fixed;
      top: 1.2rem;
      right: 1.2rem;
      width: 48px;
      height: 48px;
      background: rgba(0,0,0,0.65);
      backdrop-filter: blur(10px);
      border: 1px solid rgba(255,255,255,0.16);
      color: #fff;
      border-radius: 50%;
      font-size: 1.4rem;
      cursor: pointer;
      z-index: 210;
      display: flex;
      align-items: center;
      justify-content: center;
      transition: 0.25s;
    }
    .close-btn:active { background: var(--accent); color: #000; }

    /* Showrooms */
    .showroom-wrapper {
      display: flex;
      flex-direction: column;
      gap: 1.6rem;
      align-items: center;
    }

    .showroom-card {
      width: 100%;
      max-width: 420px;
      background-size: cover;
      background-position: center;
      padding: 2rem 1.4rem;
      border-radius: 14px;
      text-align: center;
      border: 1px solid rgba(255,255,255,0.09);
      position: relative;
      overflow: hidden;
      transition: 0.25s;
      cursor: pointer;
      min-height: 190px;
      display: flex;
      flex-direction: column;
      justify-content: center;
    }
    .showroom-card:active {
      transform: scale(0.98);
      border-color: rgba(0,200,170,0.45);
    }

    .showroom-card.sl { background-image: linear-gradient(rgba(8,8,10,0.9), rgba(8,8,10,0.96)), url('https://flagcdn.com/w320/lk.png'); }
    .showroom-card.usa { background-image: linear-gradient(rgba(8,8,10,0.9), rgba(8,8,10,0.96)), url('https://flagcdn.com/w320/us.png'); }
    .showroom-card.th { background-image: linear-gradient(rgba(8,8,10,0.9), rgba(8,8,10,0.96)), url('https://flagcdn.com/w320/th.png'); }

    .showroom-card h3 {
      font-family: 'Space Grotesk', sans-serif;
      color: #fff;
      font-size: 1.4rem;
      margin-bottom: 0.5rem;
      position: relative;
      z-index: 2;
    }
    .showroom-card .country {
      color: var(--accent);
      font-size: 0.82rem;
      font-weight: 700;
      text-transform: uppercase;
      margin-bottom: 1rem;
      display: block;
      letter-spacing: 2.2px;
    }
    .showroom-card p {
      color: #aaa;
      font-size: 0.9rem;
      margin-bottom: 0.3rem;
      position: relative;
      z-index: 2;
    }

    .locate-hint {
      display: inline-block;
      margin-top: 1.3rem;
      padding: 0.7rem 1.3rem;
      border: 1px solid rgba(255,255,255,0.22);
      border-radius: 30px;
      font-size: 0.78rem;
      color: #fff;
      text-transform: uppercase;
      letter-spacing: 1.2px;
      background: rgba(0,0,0,0.45);
      transition: 0.25s;
    }

    /* Location Modal */
    #locationModal {
      position: fixed;
      inset: 0;
      background: rgba(8,8,10,0.98);
      z-index: 300;
      display: flex;
      justify-content: center;
      align-items: center;
      opacity: 0;
      visibility: hidden;
      transition: 0.4s;
    }
    #locationModal.active {
      opacity: 1;
      visibility: visible;
    }

    .map-content {
      width: 100%;
      height: 100%;
      background: #0d0d0f;
      display: flex;
      flex-direction: column;
      overflow: hidden;
      position: relative;
    }

    .map-header {
      padding: 1.2rem 1.4rem;
      border-bottom: 1px solid #1a1a1c;
      display: flex;
      justify-content: space-between;
      align-items: center;
      background: #0a0a0c;
      flex-shrink: 0;
      padding-top: max(1.2rem, env(safe-area-inset-top));
    }
    .map-header h3 { font-size: 1.2rem; color: #fff; }
    .map-header span { font-size: 0.72rem; color: #aaa; }

    .map-body { flex: 1; display: flex; flex-direction: column; }
    .map-iframe-box { flex: 1; position: relative; min-height: 220px; }

    .map-info-panel {
      padding: 1.6rem;
      background: #08080a;
      border-top: 1px solid #1a1a1c;
      flex-shrink: 0;
      padding-bottom: calc(1.6rem + env(safe-area-inset-bottom));
    }
    .address-block { text-align: center; }
    .address-block p { color: #888; font-size: 0.9rem; margin-bottom: 0.3rem; }
    .address-block strong { color: #fff; font-size: 1.05rem; display: block; margin-top: 0.6rem; }

    .action-buttons {
      display: flex;
      gap: 1rem;
      justify-content: center;
      margin-top: 1.5rem;
    }
    .action-btn {
      padding: 1rem 1.6rem;
      border-radius: 8px;
      font-weight: 700;
      font-size: 0.9rem;
      text-transform: uppercase;
      min-height: 52px;
      flex: 1;
      max-width: 180px;
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 0.6rem;
      transition: 0.25s;
    }
    .btn-call {
      background: transparent;
      border: 1px solid var(--accent);
      color: var(--accent);
    }
    .btn-call:active { background: var(--accent); color: #000; }
    .btn-dir {
      background: linear-gradient(135deg, var(--highlight), #a86020);
      color: #fff;
      border: none;
    }

    /* Contact */
    .contact-section {
      background: #0a0a0c;
      margin-top: 4rem;
      padding: 4rem 1.25rem;
      border-top: 1px solid #151517;
    }
    .form-box { max-width: 520px; margin: auto; }

    input, textarea {
      width: 100%;
      background: #111114;
      border: 1px solid #1e1e22;
      padding: 1.15rem;
      margin-bottom: 1.2rem;
      color: #fff;
      font-family: 'DM Sans', sans-serif;
      border-radius: 10px;
      font-size: 1rem;
      transition: border-color 0.3s;
    }
    input:focus, textarea:focus {
      outline: none;
      border-color: var(--accent);
    }

    .submit-btn {
      width: 100%;
      padding: 1.15rem;
      background: linear-gradient(135deg, var(--accent), var(--accent-dark));
      color: #000;
      border: none;
      font-family: 'Space Grotesk', sans-serif;
      font-weight: 700;
      font-size: 1.05rem;
      border-radius: 10px;
      cursor: pointer;
      text-transform: uppercase;
      min-height: 54px;
      transition: 0.25s;
    }
    .submit-btn:active { opacity: 0.88; }

    /* Footer */
    footer {
      text-align: center;
      padding: 4rem 1.5rem 5rem;
      border-top: 1px solid #111;
      background: #050507;
      padding-bottom: calc(4rem + env(safe-area-inset-bottom));
    }
    .footer-brand {
      font-family: 'Space Grotesk', sans-serif;
      font-size: 1.8rem;
      font-weight: 900;
      letter-spacing: 3px;
      color: #fff;
      text-transform: uppercase;
      margin-bottom: 1.5rem;
    }
    .footer-brand span { color: var(--accent); }

    .footer-socials {
      display: flex;
      justify-content: center;
      gap: 1.6rem;
      margin: 1.8rem 0;
    }
    .social-icon {
      width: 52px;
      height: 52px;
      border-radius: 50%;
      background: rgba(255,255,255,0.04);
      border: 1px solid #222;
      display: flex;
      align-items: center;
      justify-content: center;
      color: #888;
      transition: 0.25s;
    }
    .social-icon svg { width: 22px; height: 22px; fill: currentColor; }
    .social-icon:active {
      background: var(--accent);
      border-color: var(--accent);
      color: #000;
      transform: scale(0.94);
    }

    .footer-text {
      color: #555;
      font-size: 0.8rem;
      text-transform: uppercase;
      letter-spacing: 1px;
    }

    /* Particles */
    .particles {
      position: fixed;
      inset: 0;
      pointer-events: none;
      z-index: 0;
      overflow: hidden;
    }
    .particle {
      position: absolute;
      width: 2px;
      height: 2px;
      background: rgba(0,200,170,0.3);
      border-radius: 50%;
      animation: float 22s infinite ease-in-out;
    }
    @keyframes float {
      0%,100% { transform: translateY(100vh) translateX(0); opacity: 0; }
      10%     { opacity: 1; }
      90%     { opacity: 1; }
      100%    { transform: translateY(-15vh) translateX(30px); opacity: 0; }
    }
    @keyframes fadeInUp {
      from { opacity: 0; transform: translateY(35px); }
      to   { opacity: 1; transform: translateY(0); }
    }

    /* ────────────────────────────────────────────────
       RESPONSIVE
    ───────────────────────────────────────────────── */

    @media (min-width: 560px) {
      .container { padding: 4rem 2.2rem; }
      .hero { min-height: 65vh; padding: 7rem 2.5rem 8rem; }
      .hero-cta { flex-direction: row; width: auto; max-width: none; }
      .cta-btn { width: auto; padding: 1.15rem 2.2rem; }
      .car-grid { grid-template-columns: repeat(2, 1fr); gap: 2rem; }
      .img-wrapper { height: 240px; }
      .showroom-wrapper { flex-direction: row; flex-wrap: wrap; justify-content: center; gap: 1.8rem; }
      .showroom-card { width: 48%; min-width: 300px; }
    }

    @media (min-width: 960px) {
      .container { padding: 6rem 3.5rem; }
      .hero { min-height: 85vh; }
      .car-grid { grid-template-columns: repeat(3, 1fr); gap: 2.4rem; }
      .img-wrapper { height: 270px; }
      .showroom-card { width: 340px; }
      .detail-hero { height: 55vh; min-height: 380px; }
      .detail-content { padding: 0 4rem 3.5rem; margin-top: -110px; }
      .detail-title h2 { font-size: 3.4rem; }
      .hud-box p { font-size: 1.35rem; }
      .map-info-panel { flex-direction: row; justify-content: space-between; text-align: left; }
      .address-block { text-align: left; }
      .action-buttons { justify-content: flex-end; margin-top: 0; }
    }
  </style>
</head>
<body>

<div class="particles" id="particles"></div>

<!-- Detail Overlay -->
<div id="detailView">
  <button class="close-btn" onclick="closeDetails()" aria-label="Close">×</button>
  <div class="detail-hero">
    <img id="d-img" src="" alt="Vehicle">
    <div class="detail-gradient"></div>
  </div>
  <div class="detail-content">
    <div class="detail-header">
      <div class="detail-title">
        <span id="d-series">SERIES</span>
        <h2 id="d-name">Model</h2>
      </div>
      <div class="detail-price" id="d-price">$0</div>
    </div>

    <div class="specs-box-container">
      <div class="hud-box"><h4>Max Range</h4><p id="d-range">—</p></div>
      <div class="hud-box"><h4>Top Speed</h4><p id="d-speed">—</p></div>
      <div class="hud-box"><h4>Horsepower</h4><p id="d-power">—</p></div>
    </div>

    <div class="detail-desc">
      <p id="d-desc">...</p>
    </div>

    <button class="submit-btn">Reserve Configuration</button>
  </div>
</div>

<!-- Location Modal -->
<div id="locationModal">
  <div class="map-content">
    <div class="map-header">
      <div>
        <h3 id="map-title">Center</h3>
        <span id="map-country"></span>
      </div>
      <button class="close-btn" onclick="closeLocationModal()" aria-label="Close">×</button>
    </div>
    <div class="map-body">
      <div class="map-iframe-box" id="mapContainer">
        <!-- Placeholder until real map integration -->
      </div>
      <div class="map-info-panel">
        <div class="address-block">
          <p id="map-address"></p>
          <p id="map-city"></p>
          <strong id="map-phone"></strong>
        </div>
        <div class="action-buttons">
          <a href="#" id="call-btn" class="action-btn btn-call">
            <svg viewBox="0 0 24 24" width="18" height="18" fill="currentColor"><path d="M6.62 10.79c1.44 2.83 3.76 5.14 6.59 6.59l2.2-2.2c.27-.27.67-.36 1.02-.24 1.12.37 2.33.57 3.57.57.55 0 1 .45 1 1V20c0 .55-.45 1-1 1-9.39 0-17-7.61-17-17 0-.55.45-1 1-1h3.5c.55 0 1 .45 1 1 0 1.25.2 2.45.57 3.57.11.35.03.74-.25 1.02l-2.2 2.2z"/></svg>
            Call
          </a>
          <a href="#" id="dir-btn" class="action-btn btn-dir" target="_blank">
            <svg viewBox="0 0 24 24" width="18" height="18" fill="currentColor"><path d="M12 2C8.13 2 5 5.13 5 9c0 5.25 7 13 7 13s7-7.75 7-13c0-3.87-3.13-7-7-7zm0 9.5c-1.38 0-2.5-1.12-2.5-2.5s1.12-2.5 2.5-2.5 2.5 1.12 2.5 2.5-1.12 2.5-2.5 2.5z"/></svg>
            Directions
          </a>
        </div>
      </div>
    </div>
  </div>
</div>

<!-- Hero -->
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
    <div class="showroom-card sl" onclick="openLocation('Colombo', 'Sri Lanka', 'Level 04, Lotus Tower Precinct, Colombo 01', '+94 11 234 5678', 'Lotus Tower Colombo')">
      <span class="country">Sri Lanka</span>
      <h3>Colombo</h3>
      <p>Level 04, Lotus Tower Precinct</p>
      <p>Colombo 01</p>
      <p style="margin-top:0.9rem; color:#fff; font-weight:600;">+94 11 234 5678</p>
      <div class="locate-hint">View on Map</div>
    </div>

    <div class="showroom-card usa" onclick="openLocation('New York', 'United States', '456 Broadway, SoHo, New York, NY 10013', '+1 212 555 0123', '456 Broadway New York')">
      <span class="country">United States</span>
      <h3>New York</h3>
      <p>456 Broadway, SoHo</p>
      <p>New York, NY 10013</p>
      <p style="margin-top:0.9rem; color:#fff; font-weight:600;">+1 212 555 0123</p>
      <div class="locate-hint">View on Map</div>
    </div>

    <div class="showroom-card th" onclick="openLocation('Bangkok', 'Thailand', 'Icon Siam, 299 Charoen Nakhon Rd, Khlong San, Bangkok 10600', '+66 2 8888 9999', 'Icon Siam Bangkok')">
      <span class="country">Thailand</span>
      <h3>Bangkok</h3>
      <p>Icon Siam, 299 Charoen Nakhon Rd</p>
      <p>Khlong San, Bangkok 10600</p>
      <p style="margin-top:0.9rem; color:#fff; font-weight:600;">+66 2 8888 9999</p>
      <div class="locate-hint">View on Map</div>
    </div>
  </div>
</div>

<div class="contact-section" id="contact">
  <div class="container" style="padding:0;">
    <h2 class="section-title">Get in Touch</h2>
    <div class="form-box">
      <form action="#" method="post">
        <input type="text" name="name" placeholder="Your Name" required>
        <input type="email" name="email" placeholder="Your Email" required>
        <textarea name="message" rows="5" placeholder="Your Message" required></textarea>
        <button type="submit" class="submit-btn">Send Message</button>
      </form>
    </div>
  </div>
</div>

<footer>
  <div class="footer-brand">GRAPE<span>SINO</span></div>
  <div class="footer-socials">
    <a href="https://youtube.com" target="_blank" class="social-icon"><svg viewBox="0 0 24 24"><path d="M19.615 3.184c-3.604-.246-11.631-.245-15.23 0-3.897.266-4.356 2.62-4.385 8.816.029 6.185.484 8.549 4.385 8.816 3.6.245 11.626.246 15.23 0 3.897-.266 4.356-2.62 4.385-8.816-.029-6.185-.484-8.549-4.385-8.816zm-10.615 12.816v-8l8 3.993-8 4.007z"/></svg></a>
    <a href="https://facebook.com" target="_blank" class="social-icon"><svg viewBox="0 0 24 24"><path d="M9 8h-3v4h3v12h5v-12h3.642l.358-4h-4v-1.667c0-.955.192-1.333 1.115-1.333h2.885v-5h-3.808c-3.596 0-5.192 1.583-5.192 4.615v3.385z"/></svg></a>
    <a href="https://instagram.com" target="_blank" class="social-icon"><svg viewBox="0 0 24 24"><path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069z"/></svg></a>
  </div>
  <p class="footer-text">2026 GRAPESINO Automotive. All Rights Reserved.</p>
</footer>

<script>
// ────────────────────────────────────────────────
// CAR DATA
// ────────────────────────────────────────────────
const carData = [
  { name: "LSGMAXI",    series: "COMFORT",  price: 77000,  range: "850 KM", speed: 280, power: 620,  img: "https://images.unsplash.com/photo-1502877338535-766e3a6052c0?w=800", desc: "Executive-class comfort with intelligent road-adaptive suspension." },
  { name: "GFANCY",     series: "LUXURY",   price: 45000,  range: "420 KM", speed: 210, power: 310,  img: "https://images.unsplash.com/photo-1552519507-da3b142c6e3d?w=800", desc: "Urban luxury in a compact, agile package." },
  { name: "DIOMANDLG",  series: "VELOCITY", price: 125000, range: "600 KM", speed: 350, power: 1200, img: "https://images.unsplash.com/photo-1494905998402-395d579af36f?w=800", desc: "Aerodynamic perfection. Pure performance." },
  { name: "GRAPE-4x4",  series: "HILL SIDE",price: 92000,  range: "1200 KM",speed: 190, power: 800,  img: "https://images.unsplash.com/photo-1502489597346-d8389a6b1f2a?w=800", desc: "Off-road dominance with extreme endurance." },
  { name: "SHADOW-X",   series: "SPORT",    price: 150000, range: "750 KM", speed: 310, power: 900,  img: "https://images.unsplash.com/photo-1617814076369-7a78d158798f?w=800", desc: "Stealth design meets brutal acceleration." },
  { name: "LocalG",     series: "SL-origin",price: 19500,  range: "1500 KM",speed: 160, power: 2000, img: "https://images.unsplash.com/photo-1553440569-bcc63803a83d?w=800", desc: "Proudly local. Built to last." }
];

const carGrid = document.getElementById("carGrid");
const detailView = document.getElementById("detailView");

// Render cars
carData.forEach((car, i) => {
  const card = document.createElement("div");
  card.className = "car-card";
  card.style.animationDelay = `${i * 0.08}s`;
  card.onclick = () => openDetails(i);
  card.setAttribute("role", "button");
  card.tabIndex = 0;

  card.innerHTML = `
    <div class="img-wrapper">
      <img src="${car.img}" alt="${car.name}" loading="lazy">
    </div>
    <div class="car-info">
      <span class="series-badge">${car.series}</span>
      <h3>${car.name}</h3>
      <span class="price">$${car.price.toLocaleString()}</span>
      <div class="card-stats">
        <div class="stat"><small>Range</small><span>${car.range}</span></div>
        <div class="stat"><small>Speed</small><span>${car.speed} km/h</span></div>
        <div class="stat"><small>Power</small><span>${car.power} HP</span></div>
      </div>
    </div>
  `;
  carGrid.appendChild(card);
});

function openDetails(i) {
  const car = carData[i];
  Object.assign(document.getElementById("d-img"), { src: car.img, alt: car.name });
  document.getElementById("d-series").textContent = car.series + " SERIES";
  document.getElementById("d-name").textContent = car.name;
  document.getElementById("d-price").textContent = "$" + car.price.toLocaleString();
  document.getElementById("d-range").textContent = car.range;
  document.getElementById("d-speed").textContent = car.speed + " km/h";
  document.getElementById("d-power").textContent = car.power + " HP";
  document.getElementById("d-desc").textContent = car.desc;

  detailView.classList.add("active");
  document.body.style.overflow = "hidden";
}

function closeDetails() {
  detailView.classList.remove("active");
  document.body.style.overflow = "";
}

// ────────────────────────────────────────────────
// SHOWROOM LOCATIONS
// ────────────────────────────────────────────────
function openLocation(city, country, address, phone, mapQuery) {
  document.getElementById("map-title").textContent = city + " Center";
  document.getElementById("map-country").textContent = country;
  document.getElementById("map-address").textContent = address.split(',').slice(0,2).join(', ');
  document.getElementById("map-city").textContent = address.split(',').slice(2).join(', ').trim();
  document.getElementById("map-phone").textContent = phone;

  document.getElementById("call-btn").href = `tel:${phone.replace(/\s/g,'')}`;
  document.getElementById("dir-btn").href = `https://www.google.com/maps/search/?api=1&query=${encodeURIComponent(mapQuery)}`;

  document.getElementById("mapContainer").innerHTML = `
    <div style="height:100%;display:flex;align-items:center;justify-content:center;background:#111;color:#888;flex-direction:column;">
      <svg width="64" height="64" viewBox="0 0 24 24" fill="var(--accent)"><path d="M12 2C8.13 2 5 5.13 5 9c0 5.25 7 13 7 13s7-7.75 7-13c0-3.87-3.13-7-7-7zm0 9.5c-1.38 0-2.5-1.12-2.5-2.5s1.12-2.5 2.5-2.5 2.5 1.12 2.5 2.5-1.12 2.5-2.5 2.5z"/></svg>
      <p style="margin:1rem 0 0.4rem;font-size:1.1rem;">Location ready</p>
      <p style="font-size:0.9rem;">Tap Directions to navigate</p>
    </div>
  `;

  document.getElementById("locationModal").classList.add("active");
  document.body.style.overflow = "hidden";
}

function closeLocationModal() {
  document.getElementById("locationModal").classList.remove("active");
  document.body.style.overflow = "";
  setTimeout(() => {
    document.getElementById("mapContainer").innerHTML = "";
  }, 500);
}

// ────────────────────────────────────────────────
// HELPERS
// ────────────────────────────────────────────────
window.addEventListener("keydown", e => {
  if (e.key === "Escape") {
    closeDetails();
    closeLocationModal();
  }
});

// Floating particles
function createParticles() {
  const container = document.getElementById("particles");
  const count = window.innerWidth < 600 ? 7 : 14;
  for (let i = 0; i < count; i++) {
    const p = document.createElement("div");
    p.className = "particle";
    p.style.left = Math.random() * 100 + "%";
    p.style.animationDelay = Math.random() * 18 + "s";
    container.appendChild(p);
  }
}
createParticles();

// Smooth scroll for anchor links
document.querySelectorAll('a[href^="#"]').forEach(a => {
  a.addEventListener("click", e => {
    e.preventDefault();
    document.querySelector(a.getAttribute("href"))?.scrollIntoView({ behavior: "smooth", block: "start" });
  });
});
</script>
</body>
</html>
