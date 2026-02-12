
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>GRAPESINO ULTRA | 2026</title>

    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;900&family=Inter:wght@300;400;700;800&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
    
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.5/gsap.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.5/ScrollTrigger.min.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/@studio-freight/lenis@1.0.27/bundled/lenis.min.js"></script>

    <style>
        :root {
            --apple-blue: #0071e3;
            --bg: #000000;
            --glass: rgba(255, 255, 255, 0.05);
            --gold: #d4af37;
        }

        * { margin: 0; padding: 0; box-sizing: border-box; -webkit-font-smoothing: antialiased; }
        body { background: var(--bg); color: white; font-family: 'Inter', sans-serif; overflow-x: hidden; }

        nav { 
            position: fixed; top: 0; width: 100%; padding: 20px 8%; 
            display: flex; justify-content: space-between; align-items: center; 
            z-index: 1000; background: rgba(0,0,0,0.8); backdrop-filter: blur(20px);
            border-bottom: 0.5px solid rgba(255,255,255,0.1);
        }
        .logo { font-family: 'Orbitron'; font-size: 1.4rem; font-weight: 900; letter-spacing: 4px; color: #fff; text-decoration: none; }

        .hero { 
            height: 100vh; display: flex; align-items: center; justify-content: center; 
            position: relative; text-align: center; overflow: hidden;
        }
        .hero-video {
            position: absolute; top: 0; left: 0; width: 100%; height: 100%; object-fit: cover; z-index: -1;
            filter: brightness(0.4);
        }
        .hero h1 { 
            font-size: clamp(3.5rem, 10vw, 7rem); font-weight: 800; letter-spacing: -4px;
            background: linear-gradient(180deg, #fff 40%, #555 100%);
            -webkit-background-clip: text; -webkit-text-fill-color: transparent;
        }

        .grid-container { 
            display: grid; grid-template-columns: repeat(auto-fit, minmax(400px, 1fr)); 
            gap: 40px; padding: 120px 8%; background: #000;
        }
        .car-card { 
            background: var(--glass); border: 1px solid rgba(255,255,255,0.1); 
            border-radius: 32px; padding: 40px; cursor: pointer; 
            transition: all 0.6s cubic-bezier(0.15, 1, 0.3, 1);
        }
        .car-card:hover { border-color: var(--apple-blue); transform: translateY(-10px); background: rgba(255,255,255,0.1); }
        
        .car-title { font-size: 3rem; font-weight: 800; letter-spacing: -2px; margin-bottom: 5px; }
        .car-series { font-family: 'Orbitron'; color: var(--apple-blue); font-size: 0.7rem; letter-spacing: 3px; margin-bottom: 25px; }

        .visible-details {
            display: grid; grid-template-columns: 1fr 1fr 1fr;
            background: rgba(255,255,255,0.03);
            border-radius: 15px; padding: 20px; margin-bottom: 25px;
            border: 0.5px solid rgba(255,255,255,0.05);
        }
        .spec-unit { text-align: center; }
        .spec-unit label { display: block; font-size: 0.6rem; opacity: 0.4; font-family: 'Orbitron'; margin-bottom: 5px; }
        .spec-unit span { font-weight: 700; font-size: 0.9rem; color: #fff; }

        .img-wrap { width: 100%; height: 250px; border-radius: 20px; overflow: hidden; margin-bottom: 25px; }
        .car-img { width: 100%; height: 100%; object-fit: cover; filter: brightness(1.2); transition: 1.5s; }
        
        #mainOverlay {
            position: fixed; inset: 0; background: rgba(0,0,0,0.99); backdrop-filter: blur(50px);
            z-index: 2000; display: none; padding: 80px 8%; overflow-y: auto;
        }
        .overlay-flex { display: flex; gap: 60px; align-items: flex-start; flex-wrap: wrap; padding-bottom: 100px; }
        .close-btn { position: absolute; top: 40px; right: 8%; width: 50px; height: 50px; background: #222; border-radius: 50%; display: flex; align-items: center; justify-content: center; cursor: pointer; font-size: 1.5rem; z-index: 2100; }

        .config-block { background: rgba(255,255,255,0.03); padding: 25px; border-radius: 24px; border: 1px solid rgba(255,255,255,0.05); margin-bottom: 20px; }
        .config-label { font-family: 'Orbitron'; font-size: 0.65rem; opacity: 0.4; letter-spacing: 2px; display: block; margin-bottom: 15px; }
        
        .btn-action {
            width: 100%; padding: 20px; border-radius: 50px; font-family: 'Orbitron'; font-weight: 900; cursor: pointer; border: none; transition: 0.4s; margin-top: 10px;
        }
        .btn-order { background: white; color: black; }
        .btn-negotiate { background: transparent; border: 1px solid var(--apple-blue); color: var(--apple-blue); }

        .color-dot { width: 35px; height: 35px; border-radius: 50%; cursor: pointer; border: 3px solid transparent; transition: 0.3s; }
        .color-dot.active { border-color: #fff; transform: scale(1.1); }

        #interior-view {
            position: absolute; inset: 0; background: url = ('https://dribbble.com/shots/5899231-Car-interior-infographic-element') center/cover;
            display: none; align-items: center; justify-content: center; z-index: 10; border-radius: 30px;
        }
        .interior-overlay { inset: 0; position: absolute; background: radial-gradient(circle, transparent 20%, rgba(0,0,0,0.8) 100%); }

        #toast {
            position: fixed; bottom: 40px; left: 50%; transform: translateX(-50%);
            background: var(--apple-blue); color: white; padding: 15px 30px; 
            border-radius: 50px; font-family: 'Orbitron'; font-size: 0.8rem; z-index: 3000; display: none;
        }

        .showroom-wrap { padding: 100px 8%; background: #050505; }
        .section-title { font-size: 4rem; font-weight: 800; text-align: center; margin-bottom: 80px; letter-spacing: -3px; }
        .loc-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 30px; }
        .loc-card { height: 350px; border-radius: 35px; position: relative; overflow: hidden; display: flex; flex-direction: column; justify-content: flex-end; padding: 40px; border: 1px solid rgba(255,255,255,0.08); cursor: pointer; }
        
        /* FLAG STYLES - 0.25 OPACITY */
        .loc-flag { 
            position: absolute; 
            inset: 0; 
            background-size: cover; 
            background-position: center; 
            opacity: 0.25; 
            filter: brightness(1.2); 
            transition: 0.5s; 
        }
        .loc-card:hover .loc-flag { 
            opacity: 0.8; 
            filter: brightness(1.4); 
        }
        
        /* MAP STYLE */
        .map-frame {
            width: 100%; height: 300px; border-radius: 20px; border: 1px solid rgba(255,255,255,0.1);
            filter: invert(90%) hue-rotate(180deg) brightness(0.8) contrast(1.2);
            margin-top: 15px;
        }

        .footer { text-align: center; padding: 100px 8% 40px; border-top: 1px solid rgba(255,255,255,0.1); }
        .social-row { display: flex; justify-content: center; gap: 25px; }
        .social-btn { width: 60px; height: 60px; border-radius: 50%; background: #111; display: flex; align-items: center; justify-content: center; color: #fff; font-size: 1.5rem; text-decoration: none; border: 1px solid rgba(255,255,255,0.05); transition: 0.3s; }
        .social-btn:hover { background: var(--apple-blue); transform: translateY(-5px); border-color: white; }

        .showroom-details { width: 100%; animation: slideIn 0.5s ease forwards; }
        @keyframes slideIn { from { opacity: 0; transform: translateY(20px); } to { opacity: 1; transform: translateY(0); } }
     /* ============================= */
/* DESKTOP SCREEN OPTIMIZATION  */
/* ============================= */

/* Ultra-wide screen improvement */
@media (min-width: 1400px) {

    .grid-container {
        max-width: 1800px;
        margin: 0 auto;
        grid-template-columns: repeat(auto-fit, minmax(500px, 1fr));
        gap: 60px;
        padding: 160px 6%;
    }

    .showroom-wrap {
        max-width: 1800px;
        margin: 0 auto;
        padding: 160px 6%;
    }

    .loc-grid {
        grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
        gap: 50px;
    }

    .section-title {
        font-size: 5.5rem;
    }

    .hero h1 {
        font-size: clamp(4rem, 7vw, 9rem);
    }
}

/* Large laptop optimization */
@media (min-width: 1100px) and (max-width: 1399px) {

    .grid-container {
        grid-template-columns: repeat(auto-fit, minmax(450px, 1fr));
        gap: 50px;
        padding: 140px 7%;
    }

    .loc-grid {
        grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
    }

    .hero h1 {
        font-size: clamp(3.5rem, 6vw, 7rem);
    }
}

         
    </style>
</head>
<body>

<nav><a href="#" class="logo">GRAPESINO</a></nav>

<section class="hero">
    <video class="hero-video" autoplay muted loop playsinline>
        <source src="https://assets.mixkit.co/videos/preview/mixkit-futuristic-driving-in-a-neon-city-vibe-43572-large.mp4" type="video/mp4">
    </video>
    <h1>Built for<br>The 1%.</h1>
</section>

<div id="toast">SYSTEM UPDATED</div>
<div class="grid-container" id="carGrid"></div>

<section class="showroom-wrap">
    <h2 class="section-title">The Network.</h2>
    <div class="loc-grid">
        <div class="loc-card" onclick="openLocation(event, 'SRI LANKA', 'Colombo & Wallawaya HQ')">
            <div class="loc-flag" style="background-image: url('https://upload.wikimedia.org/wikipedia/commons/1/11/Flag_of_Sri_Lanka.svg')"></div>
            <h3>Sri Lanka</h3><p>Global HQ</p>
        </div>
        <div class="loc-card" onclick="openLocation(event, 'AMERICA', 'New York Manhattan Hub')">
            <div class="loc-flag" style="background-image: url('https://upload.wikimedia.org/wikipedia/en/a/a4/Flag_of_the_United_States.svg')"></div>
            <h3>USA</h3><p>Design Center</p>
        </div>
        <div class="loc-card" onclick="openLocation(event, 'CHINA', 'Shanghai Tech District')">
            <div class="loc-flag" style="background-image: url('https://upload.wikimedia.org/wikipedia/commons/f/fa/Flag_of_the_People%27s_Republic_of_China.svg')"></div>
            <h3>China</h3><p>Production Lab</p>
        </div>
    </div>
</section>

<footer class="footer">
    <a href="mailto:grapesinomobiles@gmail.com" style="color:rgba(255,255,255,0.4); text-decoration:none; margin-bottom:40px; display:block;">grapesinomobiles@gmail.com</a>
    <div class="social-row">
        <a href="https://www.youtube.com/@MasterGring" target="_blank" class="social-btn"><i class="fab fa-youtube"></i></a>
        <a href="https://www.facebook.com/profile.php?id=61565261314945" target="_blank" class="social-btn"><i class="fab fa-facebook-f"></i></a>
        <a href="https://www.instagram.com/grapesino_mobiles" target="_blank" class="social-btn"><i class="fab fa-instagram"></i></a>
    </div>
</footer>

<div id="mainOverlay">
    <div class="close-btn" onclick="closeOverlay()">×</div>
    <div id="overlayContent" class="overlay-flex"></div>
</div>

<script>
    const carData = [
        { name: "LSG", series: "ORBITRON", price: 77000, range: "850 KM", speed: 280, power: 620, img: "https://images.unsplash.com/photo-1614162692292-7ac56d7f7f1e?auto=format&fit=crop&w=800" },
        { name: "GFANCY", series: "METRO", price: 45000, range: "420 KM", speed: 210, power: 310, img: "https://images.unsplash.com/photo-1544636331-e26879cd4d9b?auto=format&fit=crop&w=800" },
        { name: "DIOMANDLG", series: "VELOCITY", price: 125000, range: "600 KM", speed: 350, power: 1200, img: "https://images.unsplash.com/photo-1618843479313-40f8afb4b4d8?auto=format&fit=crop&w=800" },
        { name: "GRAPE-4x4", series: "TERRAIN", price: 92000, range: "1200 KM", speed: 190, power: 800, img: "https://images.unsplash.com/photo-1533473359331-0135ef1b58bf?auto=format&fit=crop&w=800" },
        { name: "SHADOW-X", series: "STEALTH", price: 150000, range: "750 KM", speed: 310, power: 900, img: "https://images.unsplash.com/photo-1503376780353-7e6692767b70?auto=format&fit=crop&w=800" },
        { name: "LocalG", series: "HEAVY", price: 195000, range: "1500 KM", speed: 160, power: 2000, img: "https://images.unsplash.com/photo-1552519507-da3b142c6e3d?auto=format&fit=crop&w=800" }
    ];

    const showroomDetails = {
        'SRI LANKA': { 
            desc: 'Global Headquarters & Engine Foundry', 
            address: 'Wallawaya Industrial Zone / Colombo 03', 
            tech: 'Quantum Assembly Line v4.0', 
            phone: '+94 11 2026 000',
            coords: '6.9271° N, 79.8612° E',
            map: 'https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d126743.58272213753!2d79.8612!3d6.9271!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x3ae253d10f7a70ad%3A0x2db2e198f0efca5!2sColombo!5e0!3m2!1sen!2slk!4v1700000000000'
        },
        'AMERICA': { 
            desc: 'Primary Design & Marketing Studio', 
            address: '5th Ave, Manhattan, New York City', 
            tech: 'AI Styling Lab & VR Showroom', 
            phone: '+1 212 900 8888',
            coords: '40.7831° N, 73.9712° W',
            map: 'https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3022.142293761308!2d-73.9732!3d40.7831!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x89c2589a018531ad%3A0x34553a5c20d77562!2s5th%20Ave%2C%20New%20York%2C%20NY!5e0!3m2!1sen!2sus!4v1700000000000'
        },
        'CHINA': { 
            desc: 'Advanced Production & Battery Research', 
            address: 'Pudong Tech District, Shanghai', 
            tech: 'Carbon-Fiber Weaving Wing', 
            phone: '+86 21 555 1234',
            coords: '31.2244° N, 121.5376° E',
            map: 'https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3412.06450!2d121.5376!3d31.2244!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x35b270406191c951%3A0x442658e388c3a12!2sPudong%2C%20Shanghai%2C%20China!5e0!3m2!1sen!2scn!4v1700000000000'
        }
    };

    let state = { color: 'Titanium', wheel: 'Aero-Blade', mode: 'Cruising', price: 0 };

    const grid = document.getElementById('carGrid');
    carData.forEach((car, i) => {
        grid.innerHTML += `
            <div class="car-card" onclick="openCar(${i})">
                <div class="car-series">${car.series} SERIES</div>
                <div class="car-title">${car.name}</div>
                <div class="visible-details">
                    <div class="spec-unit"><label>RANGE</label><span>${car.range}</span></div>
                    <div class="spec-unit"><label>SPEED</label><span>${car.speed} KM/H</span></div>
                    <div class="spec-unit"><label>POWER</label><span>${car.power} HP</span></div>
                </div>
                <div class="img-wrap"><img src="${car.img}" class="car-img"></div>
                <button class="btn-action btn-order" style="padding:10px; font-size:0.7rem;">Configure Build</button>
            </div>
        `;
    });

    function openLocation(event, loc, title) {
        event.stopPropagation();
        const info = showroomDetails[loc];
        document.getElementById('overlayContent').innerHTML = `
            <div class="showroom-details">
                <span class="config-label" style="color:var(--apple-blue)">GRAPESINO GLOBAL NETWORK</span>
                <h1 style="font-size:4.5rem; letter-spacing:-4px; margin-bottom:20px;">${loc}</h1>
                <div class="config-block">
                    <p style="font-size:1.2rem; font-weight:700; margin-bottom:10px;">${info.desc}</p>
                    <p style="opacity:0.6;">Primary Hub: ${title}</p>
                </div>
                <div style="display:grid; grid-template-columns:1fr 1fr; gap:20px;">
                    <div class="config-block">
                        <span class="config-label">FACILITY TECHNOLOGY</span>
                        <p>${info.tech}</p>
                    </div>
                    <div class="config-block">
                        <span class="config-label">CONTACT DIRECT</span>
                        <p>${info.phone}</p>
                    </div>
                </div>
                <div class="config-block">
                    <span class="config-label">GEO-COORDINATES</span>
                    <p style="font-family:'Orbitron'; font-size:1.1rem; color:var(--apple-blue);">${info.coords}</p>
                    <p style="opacity:0.4; font-size:0.8rem; margin-top:5px;">${info.address}</p>
                    <iframe class="map-frame" src="${info.map}" allowfullscreen="" loading="lazy"></iframe>
                </div>
                <button class="btn-action btn-order" style="width:auto; padding:20px 50px;" onclick="showToast('TOUR REQUEST SENT')">BOOK PRIVATE VIEWING</button>
            </div>
        `;
        toggleModal(true);
    }

    function toggleInterior(show) {
        const view = document.getElementById('interior-view');
        view.style.display = show ? 'flex' : 'none';
        if(show) gsap.from(view, {opacity: 0, scale: 1.1, duration: 0.8});
    }

    function negotiate() {
        showToast("OPENING SECURE NEGOTIATION CHANNEL...");
        setTimeout(() => {
            const discount = 1500;
            state.price -= discount;
            document.getElementById('live-price').innerText = state.price.toLocaleString() + " IMDAN";
            showToast(`DEAL OPTIMIZED: -${discount} IMDAN REMOVED`);
        }, 1500);
    }

    function updateColor(color, hex) {
        state.color = color;
        document.querySelectorAll('.color-dot').forEach(d => d.classList.remove('active'));
        if (event) event.target.classList.add('active');
        document.getElementById('car-main-img').style.filter = `drop-shadow(0 0 40px ${hex})`;
        showToast(`EXTERIOR: ${color}`);
    }

    function openCar(i) {
        const car = carData[i];
        state.price = car.price;
        document.getElementById('overlayContent').innerHTML = `
            <div style="flex:1.4; min-width:350px; position:relative;">
                <div id="interior-view">
                    <div class="interior-overlay"></div>
                    <div style="z-index:11; text-align:center;">
                        <h2 style="font-family:'Orbitron'; font-size:2rem;">COCKPIT VIEW</h2>
                        <button onclick="toggleInterior(false)" class="btn-action" style="width:auto; padding:10px 30px; margin-top:20px;">BACK TO EXTERIOR</button>
                    </div>
                </div>
                <img id="car-main-img" src="${car.img}" style="width:100%; border-radius:30px; transition:0.8s;">
                <div style="display:grid; grid-template-columns:1fr 1fr; gap:20px; margin-top:20px;">
                    <div class="config-block">
                        <span class="config-label">FINISH</span>
                        <div style="display:flex; gap:10px;">
                            <div class="color-dot active" style="background:#444;" onclick="updateColor('Titanium', '#444')"></div>
                            <div class="color-dot" style="background:#0071e3;" onclick="updateColor('Blue', '#0071e3')"></div>
                            <div class="color-dot" style="background:#800;" onclick="updateColor('Red', '#800')"></div>
                        </div>
                    </div>
                    <div class="config-block" style="cursor:pointer;" onclick="toggleInterior(true)">
                        <span class="config-label">INTERIOR</span>
                        <p style="font-size:0.8rem; font-weight:700;"><i class="fas fa-expand"></i> ENTER CABIN</p>
                    </div>
                </div>
            </div>
            <div style="flex:1; min-width:350px;">
                <h1 style="font-size:4.5rem; font-weight:800; letter-spacing:-4px; line-height:0.9;">${car.name}</h1>
                <div class="config-block">
                    <div style="display:flex; justify-content:space-between; font-size:1.5rem;">
                        <span style="font-weight:300;">PRICE</span>
                        <b id="live-price">${car.price.toLocaleString()} IMDAN</b>
                    </div>
                </div>
                <button class="btn-action btn-negotiate" onclick="negotiate()">OPTIMIZE DEAL (NEGOTIATE)</button>
                <button class="btn-action btn-order" onclick="showToast('ORDER SENT TO HQ')">PLACE SECURE ORDER</button>
            </div>
        `;
        toggleModal(true);
    }

    function showToast(msg) {
        const t = document.getElementById('toast');
        t.innerText = msg; t.style.display = 'block';
        gsap.fromTo(t, {y: 50, opacity: 0}, {y: 0, opacity: 1, duration: 0.4});
        setTimeout(() => gsap.to(t, {opacity:0, onComplete:()=>t.style.display='none'}), 2500);
    }

    function toggleModal(show) {
        const modal = document.getElementById('mainOverlay');
        modal.style.display = show ? 'block' : 'none';
        if(show) gsap.from("#overlayContent > *", {opacity: 0, y: 30, stagger: 0.1, duration: 0.6});
    }

    function closeOverlay() { toggleModal(false); }
    const lenis = new Lenis();
    function raf(time) { lenis.raf(time); requestAnimationFrame(raf); }
    requestAnimationFrame(raf);
</script>
</body>

</html>
