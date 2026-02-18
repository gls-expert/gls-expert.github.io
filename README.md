
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>The Private Island of Grapesino | Where Luxury Lives</title>

<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;600;700&family=Montserrat:wght@300;400;500&display=swap" rel="stylesheet">

<style>

/* ================= GLOBAL ================= */

*{margin:0;padding:0;box-sizing:border-box}
html{scroll-behavior:smooth}
body{
  font-family:'Montserrat',sans-serif;
  background:#0C1B2A;
  color:#E8D8C3;
  overflow-x:hidden;
  line-height:1.8;
}

h1,h2,h3{
  font-family:'Playfair Display',serif;
  letter-spacing:1px;
}

section{
  padding:120px 10%;
  position:relative;
}

.gold{color:#C6A75E}
.center{text-align:center}

/* ================= HERO ================= */

.hero{
  height:100vh;
  background:
  linear-gradient(rgba(12,27,42,.6),rgba(12,27,42,.85)),
  url('https://images.unsplash.com/photo-1507525428034-b723cf961d3e') center/cover no-repeat;
  display:flex;
  justify-content:center;
  align-items:center;
  text-align:center;
}

.hero h1{
  font-size:70px;
  margin-bottom:20px;
}

.hero p{
  font-size:22px;
  font-weight:300;
}

.btn{
  display:inline-block;
  margin-top:40px;
  padding:15px 35px;
  border:1px solid #C6A75E;
  color:#C6A75E;
  text-decoration:none;
  transition:.4s;
}

.btn:hover{
  background:#C6A75E;
  color:#0C1B2A;
}

/* ================= STORY ================= */

.story{
  display:flex;
  gap:60px;
  align-items:center;
  flex-wrap:wrap;
}

.story img{
  width:100%;
  border-radius:10px;
}

.story div{flex:1}

/* ================= PARALLAX ================= */

.parallax{
  height:60vh;
  background:
  linear-gradient(rgba(12,27,42,.6),rgba(12,27,42,.8)),
  url('https://images.unsplash.com/photo-1493558103817-58b2924bce98') center/cover fixed no-repeat;
  display:flex;
  justify-content:center;
  align-items:center;
  text-align:center;
}

/* ================= EXPERIENCES ================= */

.grid{
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(280px,1fr));
  gap:40px;
  margin-top:60px;
}

.card{
  background:#11273A;
  padding:50px;
  border:1px solid rgba(198,167,94,.2);
  transition:.4s;
}

.card:hover{
  transform:translateY(-10px);
  border-color:#C6A75E;
}

/* ================= SEA GALLERY ================= */

.gallery{
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(300px,1fr));
  gap:30px;
  margin-top:60px;
}

.gallery img{
  width:100%;
  height:400px;
  object-fit:cover;
  border-radius:10px;
  transition:.6s;
}

.gallery img:hover{
  transform:scale(1.05);
}

/* ================= VILLAS ================= */

.villas{
  display:flex;
  gap:60px;
  align-items:center;
  flex-wrap:wrap;
}

.villas img{width:100%;border-radius:10px}
.villas div{flex:1}

/* ================= MEMBERSHIP ================= */

.membership-tier{
  background:#11273A;
  padding:60px;
  border:1px solid rgba(198,167,94,.3);
}

/* ================= ACCESS FORM ================= */

form{
  max-width:700px;
  margin:auto;
  display:flex;
  flex-direction:column;
  gap:20px;
}

input,textarea{
  padding:15px;
  background:transparent;
  border:1px solid #C6A75E;
  color:#E8D8C3;
}

textarea{height:120px}

button{
  padding:15px;
  background:transparent;
  border:1px solid #C6A75E;
  color:#C6A75E;
  cursor:pointer;
  transition:.4s;
}

button:hover{
  background:#C6A75E;
  color:#0C1B2A;
}

/* ================= FOOTER ================= */

footer{
  text-align:center;
  padding:50px;
  background:#0C1B2A;
  font-size:14px;
  color:#C6A75E;
}

/* ================= RESPONSIVE ================= */

@media(max-width:768px){
  .hero h1{font-size:42px}
  section{padding:80px 8%}
}

</style>
</head>
<body>

<!-- HERO -->
<section class="hero">
  <div>
    <h1 class="gold">The Private Island of Grapesino</h1>
    <p>Beyond luxury… lies privacy.</p>
    <a href="#access" class="btn">Request Private Access</a>
  </div>
</section>

<!-- STORY -->
<section>
  <div class="story">
    <div>
      <h2 class="gold">A Sanctuary Reserved for the Few</h2>
      <p>
        Surrounded by turquoise waters and untouched white sands,
        the Private Island of Grapesino exists beyond the world’s noise.
        Time slows. The horizon expands. Privacy becomes absolute.
      </p>
    </div>
    <div>
      <img src="https://images.unsplash.com/photo-1500375592092-40eb2168fd21">
    </div>
  </div>
</section>

<!-- PARALLAX -->
<section class="parallax">
  <h2 class="gold">Every Sunset Ends in Gold</h2>
</section>

<!-- EXPERIENCES -->
<section>
  <h2 class="gold center">Experiences Curated for Visionaries</h2>
  <div class="grid">
    <div class="card">Private beachfront dining at sunset</div>
    <div class="card">Personalized wellness rituals</div>
    <div class="card">Champagne beneath coral skies</div>
    <div class="card">Secluded lagoon swims</div>
    <div class="card">Bespoke yacht excursions</div>
    <div class="card">Golden-hour shoreline walks</div>
  </div>
</section>

<!-- SEA GALLERY -->
<section>
  <h2 class="gold center">The Ocean Is Our Architecture</h2>
  <div class="gallery">
    <img src="https://images.unsplash.com/photo-1507525428034-b723cf961d3e">
    <img src="https://images.unsplash.com/photo-1500375592092-40eb2168fd21">
    <img src="https://images.unsplash.com/photo-1493558103817-58b2924bce98">
    <img src="https://images.unsplash.com/photo-1501959915551-4e8b9690d5a7">
  </div>
</section>

<!-- VILLAS -->
<section>
  <div class="villas">
    <div>
      <img src="https://images.unsplash.com/photo-1505691938895-1758d7feb511">
    </div>
    <div>
      <h2 class="gold">Private Oceanfront Residences</h2>
      <p>
        Infinity pools merging with the horizon.
        Handcrafted interiors in ivory, gold, and deep ocean blue.
        Designed for discretion, engineered for serenity.
      </p>
    </div>
  </div>
</section>

<!-- MEMBERSHIP -->
<section>
  <h2 class="gold center">Membership Is By Invitation Only</h2>
  <div class="grid">
    <div class="membership-tier">
      <h3 class="gold">Founders Circle</h3>
      <p>Permanent villa privileges and lifetime concierge service.</p>
    </div>
    <div class="membership-tier">
      <h3 class="gold">Elite Escape</h3>
      <p>Seasonal stays with private yacht privileges.</p>
    </div>
    <div class="membership-tier">
      <h3 class="gold">Legacy Patron</h3>
      <p>Confidential long-term partnership and global privileges.</p>
    </div>
  </div>
</section>

<!-- ACCESS -->
<section id="access">
  <h2 class="gold center">Request Private Access</h2>
  <form>
    <input type="text" placeholder="Full Name" required>
    <input type="email" placeholder="Email Address" required>
    <input type="text" placeholder="Country of Residence">
    <input type="number" placeholder="Number of Guests">
    <textarea placeholder="Private Message"></textarea>
    <button type="submit">Submit Confidential Inquiry</button>
  </form>
</section>

<!-- FINAL -->
<section class="parallax">
  <h1 class="gold">Where Luxury Lives</h1>
</section>

<footer>
© 2026 The Private Island of Grapesino. All Rights Reserved.
</footer>

</body>
</html>
