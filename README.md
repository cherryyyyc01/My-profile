<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Abi | Elegant Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">

<style>
*{
  margin:0;
  padding:0;
  box-sizing:border-box;
  font-family:'Poppins',sans-serif;
  scroll-behavior:smooth;
}

body{
  background:linear-gradient(135deg,#1f1c2c,#2c2a4a,#1a1a2e);
  color:#f5f5f5;
  transition:background 0.4s ease, color 0.4s ease;
}

body.light{
  background:linear-gradient(135deg,#f4f4f6,#e8e8ef,#ffffff);
  color:#222;
}

/* NAVBAR */
nav{
  position:fixed;
  width:100%;
  padding:20px 50px;
  display:flex;
  justify-content:space-between;
  align-items:center;
  background:rgba(20,20,30,0.8);
  backdrop-filter:blur(12px);
  z-index:1000;
  transition:0.4s;
}
body.light nav{
  background:rgba(255,255,255,0.85);
}

.logo{
  font-weight:700;
  letter-spacing:2px;
  font-size:20px;
}

.menu{
  font-size:26px;
  cursor:pointer;
}

/* SIDEBAR */
.sidebar{
  position:fixed;
  right:-300px;
  top:0;
  width:260px;
  height:100%;
  background:#141420;
  padding:80px 30px;
  transition:0.4s ease;
  z-index:1100;
}
body.light .sidebar{
  background:#ffffff;
}
.sidebar.active{
  right:0;
}
.sidebar a{
  display:block;
  margin:25px 0;
  text-decoration:none;
  color:inherit;
  font-weight:500;
}

/* OVERLAY */
.overlay{
  position:fixed;
  width:100%;
  height:100%;
  background:rgba(0,0,0,0.5);
  opacity:0;
  pointer-events:none;
  transition:0.3s;
}
.overlay.active{
  opacity:1;
  pointer-events:auto;
}

/* HERO */
.hero{
  height:100vh;
  display:flex;
  flex-direction:column;
  justify-content:center;
  align-items:center;
  text-align:center;
  padding:20px;
}

.hero h1{
  font-size:56px;
  font-weight:600;
  letter-spacing:2px;
}

.hero p{
  margin-top:15px;
  font-weight:300;
  opacity:0.8;
}

/* SECTIONS */
section{
  padding:100px 60px;
}

.section-title{
  text-align:center;
  margin-bottom:50px;
  font-size:28px;
  font-weight:600;
}

/* CARDS */
.cards{
  display:flex;
  flex-wrap:wrap;
  justify-content:center;
  gap:30px;
}

.card{
  width:280px;
  padding:30px;
  border-radius:18px;
  background:rgba(255,255,255,0.05);
  backdrop-filter:blur(10px);
  transition:0.4s ease;
  opacity:0;
  transform:translateY(40px);
}
body.light .card{
  background:rgba(0,0,0,0.05);
}
.card.show{
  opacity:1;
  transform:translateY(0);
}
.card:hover{
  transform:translateY(-8px);
}

.card h3{
  margin-bottom:15px;
  font-weight:600;
}

/* THEME TOGGLE */
.toggle-container{
  margin-top:40px;
}

.toggle-label{
  font-size:13px;
  letter-spacing:1px;
  margin-bottom:12px;
  opacity:0.7;
  text-transform:uppercase;
}

.switch{
  position:relative;
  display:inline-block;
  width:60px;
  height:32px;
}

.switch input{
  opacity:0;
  width:0;
  height:0;
}

.slider{
  position:absolute;
  cursor:pointer;
  top:0;left:0;right:0;bottom:0;
  background:#555;
  transition:.4s;
  border-radius:34px;
}

.slider:before{
  position:absolute;
  content:"";
  height:24px;
  width:24px;
  left:4px;
  bottom:4px;
  background:white;
  transition:.4s;
  border-radius:50%;
}

input:checked + .slider{
  background:#c5a880;
}

input:checked + .slider:before{
  transform:translateX(28px);
}

/* FOOTER */
footer{
  background:#1a1a1a;
  color:#d4af37;
  text-align:center;
  padding:50px;
  letter-spacing:2px;
}
body.light footer{
  background:#2b2b2b;
  color:#d4af37;
}
</style>
</head>
<body>

<nav>
  <div class="logo">ABI</div>
  <div class="menu" onclick="toggleMenu()">☰</div>
</nav>

<div class="overlay" id="overlay" onclick="toggleMenu()"></div>

<div class="sidebar" id="sidebar">
  <a href="#profile">Profile</a>
  <a href="#portfolio">Portfolio</a>

  <div class="toggle-container">
    <p class="toggle-label">Theme Mode</p>
    <label class="switch">
      <input type="checkbox" id="themeToggle">
      <span class="slider"></span>
    </label>
  </div>
</div>

<div class="hero">
  <h1>Abi</h1>
  <p>Calm mind. Ambitious vision. Continuous growth.</p>
</div>

<section id="profile">
  <div class="section-title">Profile</div>
  <div class="cards">
    <div class="card">
      <h3>Umur</h3>
      <p>17 Tahun</p>
    </div>
    <div class="card">
      <h3>Pendidikan</h3>
      <p>Pelajar aktif, fokus pengembangan skill & teknologi digital.</p>
    </div>
    <div class="card">
      <h3>Olahraga</h3>
      <p>Workout & menjaga kebugaran fisik secara konsisten.</p>
    </div>
  </div>
</section>

<section id="portfolio">
  <div class="section-title">Portfolio</div>
  <div class="cards">
    <div class="card">
      <h3>Web Development</h3>
      <p>Membangun website modern dengan UI elegan & animasi smooth.</p>
    </div>
    <div class="card">
      <h3>Game Concept</h3>
      <p>Eksplorasi ide game kreatif dan sistem interaktif.</p>
    </div>
    <div class="card">
      <h3>Self Development</h3>
      <p>Fokus growth mindset & pengembangan masa depan.</p>
    </div>
  </div>
</section>

<footer>
  © 2026 Abi — Elegant Personal Profile
</footer>

<script>
function toggleMenu(){
  document.getElementById("sidebar").classList.toggle("active");
  document.getElementById("overlay").classList.toggle("active");
}

/* THEME WITH SAVE */
const toggle = document.getElementById("themeToggle");

if(localStorage.getItem("theme") === "light"){
  document.body.classList.add("light");
  toggle.checked = true;
}

toggle.addEventListener("change",()=>{
  document.body.classList.toggle("light");
  if(document.body.classList.contains("light")){
    localStorage.setItem("theme","light");
  }else{
    localStorage.setItem("theme","dark");
  }
});

/* Reveal animation */
const cards=document.querySelectorAll(".card");
window.addEventListener("scroll",()=>{
  cards.forEach(card=>{
    if(card.getBoundingClientRect().top < window.innerHeight-100){
      card.classList.add("show");
    }
  });
});
</script>

</body>
</html>
