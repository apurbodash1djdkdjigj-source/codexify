<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Codexify — Global Digital Agency</title>

<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;700;800&family=Bricolage+Grotesque:wght@300;400;500;600&family=DM+Mono:wght@300;400&display=swap" rel="stylesheet">

<style>

/* ✅ FIXED RESET */
*, *::before, *::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

:root {
  --bg:#04050F;
  --bg2:#060812;
  --card:#0D1128;
  --blue:#5B8FFF;
  --violet:#A855F7;
  --pink:#EC4899;
  --white:#F1F5FF;
  --muted:#4B5680;
}

/* BODY */
body{
  background:var(--bg);
  color:var(--white);
  font-family:'Bricolage Grotesque',sans-serif;
  overflow-x:hidden;
}

/* NAV */
#nav{
  position:fixed;
  top:0;
  width:100%;
  height:60px;
  display:flex;
  justify-content:space-between;
  align-items:center;
  padding:0 40px;
  background:rgba(4,5,15,.7);
  backdrop-filter:blur(10px);
}

.nav-logo{
  font-family:'Syne',sans-serif;
  font-weight:800;
  font-size:1.2rem;
}

.nav-links{
  display:flex;
  gap:20px;
}

.nav-links a{
  color:var(--muted);
  font-size:.8rem;
}

.nav-links a:hover{
  color:white;
}

/* HERO */
#hero{
  min-height:100vh;
  display:flex;
  flex-direction:column;
  justify-content:center;
  align-items:center;
  text-align:center;
  padding:100px 20px;
}

.hero-h{
  font-family:'Syne',sans-serif;
  font-size:clamp(3rem,7vw,6rem);
  font-weight:800;
  line-height:1;
}

.hero-h .grad{
  background:linear-gradient(120deg,var(--blue),var(--violet),var(--pink));
  -webkit-background-clip:text;
  -webkit-text-fill-color:transparent;
}

.hero-sub{
  margin-top:20px;
  max-width:600px;
  color:rgba(255,255,255,.6);
  line-height:1.8;
}

/* CTA */
.cta{
  margin-top:30px;
  padding:12px 30px;
  border-radius:10px;
  border:none;
  background:linear-gradient(135deg,var(--blue),var(--violet));
  color:white;
  font-weight:600;
  cursor:pointer;
  transition:.3s;
}

.cta:hover{
  transform:translateY(-3px);
  box-shadow:0 10px 40px rgba(91,143,255,.4);
}

/* ✅ LIGHT AURORA (optimized) */
.aurora{
  position:fixed;
  width:500px;
  height:500px;
  border-radius:50%;
  filter:blur(80px); /* FIXED (140 → 80) */
  opacity:.2;
  z-index:0;
}

.a1{
  background:var(--blue);
  top:-100px;
  right:-100px;
}

.a2{
  background:var(--violet);
  bottom:-100px;
  left:-100px;
}

/* SECTION */
.section{
  padding:80px 20px;
  text-align:center;
}

.s-title{
  font-family:'Syne',sans-serif;
  font-size:2rem;
  margin-bottom:10px;
}

.s-sub{
  color:rgba(255,255,255,.5);
  max-width:500px;
  margin:auto;
}

</style>
</head>

<body>

<!-- AURORA -->
<div class="aurora a1"></div>
<div class="aurora a2"></div>

<!-- NAV -->
<div id="nav">
  <div class="nav-logo">Codexify</div>
  <div class="nav-links">
    <a href="#">Work</a>
    <a href="#">About</a>
    <a href="#">Contact</a>
  </div>
</div>

<!-- HERO -->
<section id="hero">
  <h1 class="hero-h">
    We Build <br>
    <span class="grad">Digital Future</span>
  </h1>

  <p class="hero-sub">
    A global digital agency powered by Bangladesh. We craft modern, scalable and premium web experiences.
  </p>

  <button class="cta">Start Project →</button>
</section>

<!-- SECTION -->
<section class="section">
  <h2 class="s-title">Why Bangladesh?</h2>
  <p class="s-sub">
    Fast growing tech ecosystem, skilled developers and global delivery capability.
  </p>
</section>

</body>
</html>
fonts.googleapis.com
