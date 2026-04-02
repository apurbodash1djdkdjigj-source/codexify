# codexify
we read your online business
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Codexify — Global Digital Agency</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Outfit:wght@200;300;400;500;600;700;800;900&family=Instrument+Serif:ital@0;1&display=swap" rel="stylesheet">
<style>
:root {
  --ink:    #03040D;
  --ink2:   #070A1A;
  --panel:  #0B0F24;
  --b:      rgba(255,255,255,0.06);
  --b2:     rgba(255,255,255,0.1);
  --blue:   #4B8EFF;
  --indigo: #7C5CFF;
  --violet: #B06FFF;
  --pink:   #F06BDE;
  --cyan:   #17E8F0;
  --lime:   #7AFF8A;
  --white:  #F4F6FF;
  --dim:    #5A6490;
}

*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
html{scroll-behavior:smooth}
body{
  background:var(--ink);
  color:var(--white);
  font-family:'Outfit',sans-serif;
  overflow-x:hidden;
  cursor:none;
}

/* ── CUSTOM CURSOR ── */
#cursor{
  position:fixed;width:12px;height:12px;
  background:var(--blue);border-radius:50%;
  pointer-events:none;z-index:9999;
  transition:transform .15s,background .2s;
  transform:translate(-50%,-50%);
  mix-blend-mode:difference;
}
#cursor-ring{
  position:fixed;width:40px;height:40px;
  border:1px solid rgba(75,142,255,0.5);
  border-radius:50%;pointer-events:none;z-index:9998;
  transition:transform .35s cubic-bezier(.2,1,.2,1),opacity .3s;
  transform:translate(-50%,-50%);
}

/* ── NOISE TEXTURE ── */
body::after{
  content:'';position:fixed;inset:0;z-index:1000;
  pointer-events:none;opacity:.025;
  background-image:url("data:image/svg+xml,%3Csvg viewBox='0 0 512 512' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)'/%3E%3C/svg%3E");
}

/* ── BACKGROUND MESH ── */
.mesh{
  position:fixed;inset:0;z-index:0;
  overflow:hidden;pointer-events:none;
}
.mesh-blob{
  position:absolute;border-radius:50%;
  filter:blur(120px);
  animation:blobDrift 18s ease-in-out infinite;
}
.mb1{width:900px;height:900px;top:-300px;right:-200px;
  background:radial-gradient(circle,rgba(75,142,255,.18) 0%,transparent 70%);
  animation-delay:0s;}
.mb2{width:700px;height:700px;bottom:-200px;left:-150px;
  background:radial-gradient(circle,rgba(176,111,255,.15) 0%,transparent 70%);
  animation-delay:-6s;}
.mb3{width:500px;height:500px;top:40%;left:45%;
  background:radial-gradient(circle,rgba(23,232,240,.1) 0%,transparent 70%);
  animation-delay:-12s;}
@keyframes blobDrift{
  0%,100%{transform:translate(0,0) scale(1);}
  33%{transform:translate(60px,-40px) scale(1.05);}
  66%{transform:translate(-30px,50px) scale(.96);}
}

/* ── NAV ── */
nav{
  position:fixed;top:0;left:0;right:0;z-index:200;
  height:72px;
  display:flex;align-items:center;justify-content:space-between;
  padding:0 5vw;
  background:rgba(3,4,13,.6);
  backdrop-filter:blur(28px) saturate(1.8);
  border-bottom:1px solid var(--b);
}
.nav-brand{display:flex;align-items:center;gap:12px;text-decoration:none}
.cx-mark{width:38px;height:38px;flex-shrink:0}
.brand-name{
  font-size:1.25rem;font-weight:800;letter-spacing:-.03em;
  background:linear-gradient(120deg,#fff 0%,#a8c4ff 55%,#c49dff 100%);
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;
}
.nav-center{display:flex;gap:2.2rem}
.nav-center a{
  font-size:.82rem;font-weight:500;color:var(--dim);
  text-decoration:none;letter-spacing:.01em;
  transition:color .2s;position:relative;
}
.nav-center a::after{
  content:'';position:absolute;bottom:-4px;left:0;right:0;height:1px;
  background:var(--blue);transform:scaleX(0);transform-origin:left;
  transition:transform .3s;
}
.nav-center a:hover{color:var(--white)}
.nav-center a:hover::after{transform:scaleX(1)}
.nav-pill{
  display:flex;align-items:center;gap:6px;
  background:linear-gradient(135deg,rgba(75,142,255,.15),rgba(124,92,255,.15));
  border:1px solid rgba(75,142,255,.25);
  border-radius:100px;padding:8px 20px;
  font-size:.78rem;font-weight:600;color:var(--white);
  text-decoration:none;
  transition:border-color .2s,box-shadow .2s;
  cursor:none;
}
.nav-pill:hover{
  border-color:rgba(75,142,255,.5);
  box-shadow:0 0 24px rgba(75,142,255,.25);
}
.live-dot{
  width:7px;height:7px;border-radius:50%;background:var(--lime);
  box-shadow:0 0 8px var(--lime);
  animation:livePulse 2s infinite;
}
@keyframes livePulse{0%,100%{opacity:1;transform:scale(1)}50%{opacity:.6;transform:scale(1.4)}}

/* ── HERO ── */
#hero{
  position:relative;z-index:1;
  min-height:100vh;
  display:grid;grid-template-columns:1fr 1fr;
  align-items:center;
  padding:100px 5vw 80px;
  gap:4rem;
}
.hero-left{position:relative}

.eyebrow-row{
  display:inline-flex;align-items:center;gap:10px;
  margin-bottom:2rem;
}
.eyebrow-tag{
  font-size:.65rem;font-weight:700;letter-spacing:.18em;
  text-transform:uppercase;color:var(--dim);
  font-family:'Outfit',sans-serif;
}
.eyebrow-chip{
  display:inline-flex;align-items:center;gap:6px;
  background:rgba(122,255,138,.07);
  border:1px solid rgba(122,255,138,.2);
  border-radius:100px;padding:4px 12px;
  font-size:.65rem;font-weight:700;
  letter-spacing:.1em;text-transform:uppercase;
  color:var(--lime);
}
.eyebrow-chip::before{
  content:'';width:5px;height:5px;border-radius:50%;
  background:var(--lime);box-shadow:0 0 6px var(--lime);
  animation:livePulse 2s infinite;
}

.hero-h1{
  font-size:clamp(3rem,5.5vw,5.5rem);
  font-weight:900;letter-spacing:-.04em;line-height:1.02;
  margin-bottom:1.8rem;
}
.h1-line2{
  display:block;
  font-family:'Instrument Serif',serif;
  font-style:italic;font-weight:400;
  font-size:clamp(2.8rem,5vw,5rem);
  background:linear-gradient(120deg,var(--blue) 0%,var(--indigo) 40%,var(--violet) 70%,var(--pink) 100%);
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;
  background-size:200%;
  animation:gradShift 5s linear infinite;
}
@keyframes gradShift{
  0%{background-position:0%}
  100%{background-position:200%}
}

.hero-desc{
  font-size:1.05rem;font-weight:300;
  color:rgba(244,246,255,.5);line-height:1.85;
  max-width:480px;margin-bottom:2.5rem;
}
.hero-desc strong{color:var(--white);font-weight:500}

.hero-actions{display:flex;gap:.9rem;flex-wrap:wrap;margin-bottom:3.5rem}

.btn-primary{
  display:inline-flex;align-items:center;gap:9px;
  background:linear-gradient(135deg,var(--blue),var(--indigo));
  color:#fff;text-decoration:none;
  font-weight:700;font-size:.88rem;letter-spacing:.01em;
  padding:.9rem 2rem;border-radius:10px;border:none;cursor:none;
  box-shadow:0 8px 32px rgba(75,142,255,.35);
  transition:transform .2s,box-shadow .2s;
  position:relative;overflow:hidden;
}
.btn-primary::before{
  content:'';position:absolute;inset:0;
  background:linear-gradient(135deg,rgba(255,255,255,.1),transparent);
  opacity:0;transition:opacity .2s;
}
.btn-primary:hover{transform:translateY(-3px);box-shadow:0 16px 48px rgba(75,142,255,.5)}
.btn-primary:hover::before{opacity:1}

.btn-outline{
  display:inline-flex;align-items:center;gap:9px;
  background:rgba(255,255,255,.04);
  color:var(--white);text-decoration:none;
  font-weight:500;font-size:.88rem;
  padding:.9rem 2rem;border-radius:10px;
  border:1px solid var(--b2);cursor:none;
  transition:background .2s,border-color .2s;
}
.btn-outline:hover{background:rgba(255,255,255,.08);border-color:rgba(255,255,255,.2)}

.trust-row{display:flex;align-items:center;gap:1.5rem;flex-wrap:wrap}
.trust-label{
  font-size:.68rem;font-weight:600;letter-spacing:.12em;
  text-transform:uppercase;color:var(--dim);
}
.trust-divider{width:1px;height:20px;background:var(--b2)}
.trust-badges{display:flex;gap:.7rem}
.t-badge{
  display:flex;align-items:center;gap:7px;
  background:rgba(255,255,255,.04);
  border:1px solid var(--b);
  border-radius:8px;padding:6px 14px;
  font-size:.75rem;font-weight:600;
  color:rgba(244,246,255,.55);
  transition:border-color .2s,color .2s;cursor:none;
}
.t-badge:hover{border-color:rgba(255,255,255,.18);color:var(--white)}
.tb-dot{width:7px;height:7px;border-radius:50%}
.dot-b44{background:var(--blue);box-shadow:0 0 8px var(--blue)}
.dot-lv{background:var(--pink);box-shadow:0 0 8px var(--pink)}

/* ── HERO RIGHT: VISUAL ── */
.hero-visual{
  position:relative;
  display:flex;align-items:center;justify-content:center;
}
.hero-glow-ring{
  position:absolute;
  width:520px;height:520px;border-radius:50%;
  background:conic-gradient(
    from 0deg,
    rgba(75,142,255,0) 0deg,
    rgba(75,142,255,.3) 90deg,
    rgba(176,111,255,.3) 180deg,
    rgba(240,107,222,.3) 270deg,
    rgba(75,142,255,0) 360deg
  );
  animation:ringRotate 8s linear infinite;
  filter:blur(1px);
}
@keyframes ringRotate{from{transform:rotate(0)}to{transform:rotate(360deg)}}

.hero-glow-ring2{
  position:absolute;
  width:420px;height:420px;border-radius:50%;
  border:1px solid rgba(75,142,255,.1);
  animation:ringRotate 12s linear infinite reverse;
}
.hero-glow-ring3{
  position:absolute;
  width:320px;height:320px;border-radius:50%;
  border:1px dashed rgba(124,92,255,.15);
  animation:ringRotate 20s linear infinite;
}

.hero-cx-wrap{
  position:relative;z-index:2;
  display:flex;flex-direction:column;align-items:center;gap:1.5rem;
}
.hero-cx-logo{
  width:200px;height:200px;
  filter:
    drop-shadow(0 0 40px rgba(75,142,255,.6))
    drop-shadow(0 0 80px rgba(124,92,255,.3));
  animation:logoBreath 4s ease-in-out infinite;
}
@keyframes logoBreath{
  0%,100%{
    filter:drop-shadow(0 0 40px rgba(75,142,255,.6)) drop-shadow(0 0 80px rgba(124,92,255,.3));
    transform:scale(1);
  }
  50%{
    filter:drop-shadow(0 0 60px rgba(75,142,255,.9)) drop-shadow(0 0 100px rgba(124,92,255,.5));
    transform:scale(1.03);
  }
}

.hero-wordmark-big{
  font-size:2.8rem;font-weight:900;letter-spacing:-.05em;
  background:linear-gradient(120deg,#fff 0%,#a8c4ff 50%,#c49dff 100%);
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;
}
.hero-sub-line{
  font-size:.72rem;font-weight:600;letter-spacing:.2em;
  text-transform:uppercase;color:var(--dim);
}

.float-card{
  position:absolute;
  background:rgba(11,15,36,.85);
  border:1px solid var(--b2);
  border-radius:14px;
  padding:.9rem 1.2rem;
  backdrop-filter:blur(20px);
  display:flex;align-items:center;gap:10px;
  font-size:.78rem;font-weight:600;
  white-space:nowrap;
  box-shadow:0 20px 60px rgba(0,0,0,.4);
  animation:floatCard 6s ease-in-out infinite;
}
.fc1{top:8%;left:-8%;animation-delay:0s}
.fc2{top:20%;right:-10%;animation-delay:-2s}
.fc3{bottom:18%;left:-5%;animation-delay:-4s}
.fc4{bottom:8%;right:-8%;animation-delay:-1s}
@keyframes floatCard{
  0%,100%{transform:translateY(0)}
  50%{transform:translateY(-10px)}
}
.fc-icon{font-size:1.2rem}
.fc-info .fc-val{font-size:.85rem;font-weight:800;color:var(--white)}
.fc-info .fc-lbl{font-size:.62rem;font-weight:400;color:var(--dim);margin-top:1px}

/* ── TICKER ── */
.ticker{
  position:relative;z-index:1;
  background:linear-gradient(135deg,rgba(75,142,255,.06),rgba(124,92,255,.06));
  border-top:1px solid var(--b);border-bottom:1px solid var(--b);
  padding:.9rem 0;overflow:hidden;
}
.ticker-inner{
  display:inline-flex;gap:0;
  animation:tickerScroll 22s linear infinite;
  white-space:nowrap;
}
@keyframes tickerScroll{from{transform:translateX(0)}to{transform:translateX(-50%)}}
.ticker-item{
  display:flex;align-items:center;gap:.6rem;
  padding:0 2.5rem;
  font-size:.72rem;font-weight:600;letter-spacing:.1em;
  text-transform:uppercase;color:var(--dim);
}
.ticker-item .sep{color:var(--blue);font-size:1rem}

/* ── SECTION BASE ── */
section{position:relative;z-index:1;padding:8rem 5vw}
.sec-eyebrow{
  display:inline-flex;align-items:center;gap:10px;
  font-size:.65rem;font-weight:700;letter-spacing:.18em;
  text-transform:uppercase;color:var(--blue);
  margin-bottom:1rem;
}
.sec-eyebrow::before{
  content:'';width:24px;height:1px;
  background:linear-gradient(90deg,var(--blue),transparent);
}
.sec-title{
  font-size:clamp(2rem,3.5vw,3rem);
  font-weight:800;letter-spacing:-.03em;line-height:1.1;
  margin-bottom:1rem;
}
.sec-sub{
  font-size:.95rem;color:var(--dim);
  line-height:1.9;max-width:520px;
}

/* ── WHY SECTION ── */
#why{background:var(--ink2)}
.why-layout{
  display:grid;grid-template-columns:1.1fr 1fr;
  gap:6rem;align-items:center;margin-top:5rem;
}
.why-left{}
.why-p{
  font-size:.95rem;color:var(--dim);line-height:1.9;
  margin-bottom:1.1rem;
}
.why-p strong{color:var(--white)}

.why-checks{margin-top:2rem;display:flex;flex-direction:column;gap:.2rem}
.wc-item{
  display:flex;align-items:center;gap:14px;
  padding:.75rem 0;
  border-bottom:1px solid rgba(255,255,255,.04);
  font-size:.88rem;color:rgba(244,246,255,.7);
  transition:color .2s;cursor:default;
}
.wc-item:hover{color:var(--white)}
.wc-icon{
  width:26px;height:26px;border-radius:8px;flex-shrink:0;
  background:linear-gradient(135deg,rgba(75,142,255,.15),rgba(124,92,255,.15));
  border:1px solid rgba(75,142,255,.2);
  display:flex;align-items:center;justify-content:center;
  font-size:.7rem;
  transition:border-color .2s;
}
.wc-item:hover .wc-icon{border-color:rgba(75,142,255,.4)}

.why-right{display:flex;flex-direction:column;gap:1.2rem}
.stat-big{
  background:var(--panel);
  border:1px solid var(--b);
  border-radius:20px;padding:2rem 2rem;
  position:relative;overflow:hidden;
  transition:transform .3s,border-color .3s;
}
.stat-big:hover{transform:translateX(8px);border-color:rgba(75,142,255,.25)}
.stat-big::before{
  content:'';
  position:absolute;top:0;left:0;bottom:0;width:3px;
  background:linear-gradient(180deg,var(--blue),var(--violet));
  border-radius:3px 0 0 3px;
}
.sb-num{
  font-size:3rem;font-weight:900;letter-spacing:-.04em;
  line-height:1;margin-bottom:.3rem;
  background:linear-gradient(135deg,var(--blue),var(--cyan));
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;
}
.sb-num sup{font-size:1.4rem;vertical-align:top;margin-top:.3rem;display:inline-block}
.sb-lbl{font-size:.8rem;color:var(--dim);line-height:1.5}

/* ── PARTNERS ── */
#partners{background:var(--ink)}
.partners-head{text-align:center;margin-bottom:5rem}
.partners-head .sec-eyebrow{justify-content:center}
.partners-head .sec-sub{margin:0 auto;text-align:center}

.partners-layout{
  display:grid;grid-template-columns:1fr 1fr;
  gap:2rem;max-width:860px;margin:0 auto;
}
.pcard{
  border-radius:24px;padding:3rem 2.5rem;
  position:relative;overflow:hidden;
  transition:transform .3s;
}
.pcard:hover{transform:translateY(-8px)}

.pcard-b44{
  background:linear-gradient(145deg,rgba(75,142,255,.06) 0%,var(--panel) 50%);
  border:1px solid rgba(75,142,255,.15);
}
.pcard-lv{
  background:linear-gradient(145deg,rgba(240,107,222,.06) 0%,var(--panel) 50%);
  border:1px solid rgba(240,107,222,.15);
}
.pcard-b44:hover{box-shadow:0 24px 80px rgba(75,142,255,.12)}
.pcard-lv:hover{box-shadow:0 24px 80px rgba(240,107,222,.1)}

.pcard::before{
  content:'';position:absolute;top:0;left:0;right:0;height:1px;
}
.pcard-b44::before{background:linear-gradient(90deg,transparent,var(--blue),var(--cyan),transparent)}
.pcard-lv::before{background:linear-gradient(90deg,transparent,var(--violet),var(--pink),transparent)}

.pcard-shine{
  position:absolute;top:-60%;right:-30%;
  width:300px;height:300px;border-radius:50%;
  opacity:.04;
}
.pcard-b44 .pcard-shine{background:radial-gradient(var(--blue),transparent)}
.pcard-lv  .pcard-shine{background:radial-gradient(var(--pink),transparent)}

.pcard-logo{
  width:64px;height:64px;border-radius:16px;
  display:flex;align-items:center;justify-content:center;
  font-size:1.8rem;margin-bottom:1.5rem;
}
.pcard-b44 .pcard-logo{
  background:linear-gradient(135deg,rgba(75,142,255,.15),rgba(23,232,240,.08));
  border:1px solid rgba(75,142,255,.2);
}
.pcard-lv .pcard-logo{
  background:linear-gradient(135deg,rgba(240,107,222,.15),rgba(176,111,255,.08));
  border:1px solid rgba(240,107,222,.2);
}
.pcard-name{
  font-size:1.4rem;font-weight:800;letter-spacing:-.02em;
  margin-bottom:.25rem;
}
.pcard-b44 .pcard-name{
  background:linear-gradient(120deg,var(--blue),var(--cyan));
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;
}
.pcard-lv .pcard-name{
  background:linear-gradient(120deg,var(--violet),var(--pink));
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;
}
.pcard-role{
  font-size:.65rem;font-weight:700;letter-spacing:.14em;
  text-transform:uppercase;color:var(--dim);margin-bottom:1.2rem;
}
.pcard-desc{font-size:.85rem;color:var(--dim);line-height:1.75}
.pcard-tags{display:flex;flex-wrap:wrap;gap:.5rem;margin-top:1.3rem}
.ptag{
  font-size:.65rem;font-weight:600;padding:3px 10px;
  border-radius:100px;border:1px solid var(--b);
  color:var(--dim);
}

/* ── SERVICES ── */
#services{background:var(--ink2)}
.srv-head{
  display:flex;justify-content:space-between;
  align-items:flex-end;flex-wrap:wrap;gap:2rem;
  margin-bottom:4.5rem;
}
.srv-grid{
  display:grid;
  grid-template-columns:repeat(3,1fr);
  gap:1.5rem;
}
.srv{
  background:var(--panel);
  border:1px solid var(--b);
  border-radius:20px;
  padding:2.2rem 1.8rem;
  position:relative;overflow:hidden;
  transition:transform .3s,border-color .3s,box-shadow .3s;
}
.srv:hover{
  transform:translateY(-6px);
  border-color:rgba(75,142,255,.2);
  box-shadow:0 24px 60px rgba(0,0,0,.3);
}
.srv::before{
  content:'';position:absolute;
  top:0;left:0;right:0;height:1px;
  opacity:0;transition:opacity .3s;
  background:linear-gradient(90deg,transparent,var(--blue),transparent);
}
.srv:hover::before{opacity:1}

.srv-n{
  font-size:.6rem;font-weight:700;letter-spacing:.14em;
  text-transform:uppercase;color:var(--dim);margin-bottom:1.2rem;
  font-family:'Outfit',monospace;
}
.srv-ic{
  width:48px;height:48px;border-radius:14px;
  display:flex;align-items:center;justify-content:center;
  font-size:1.4rem;margin-bottom:1.2rem;
  transition:transform .2s;
}
.srv:hover .srv-ic{transform:scale(1.1)}
.si1{background:rgba(75,142,255,.1);border:1px solid rgba(75,142,255,.15)}
.si2{background:rgba(124,92,255,.1);border:1px solid rgba(124,92,255,.15)}
.si3{background:rgba(23,232,240,.1);border:1px solid rgba(23,232,240,.15)}
.si4{background:rgba(240,107,222,.1);border:1px solid rgba(240,107,222,.15)}
.si5{background:rgba(245,158,11,.1);border:1px solid rgba(245,158,11,.15)}
.si6{background:rgba(122,255,138,.1);border:1px solid rgba(122,255,138,.15)}

.srv h3{font-size:1.02rem;font-weight:700;margin-bottom:.5rem}
.srv p{font-size:.82rem;color:var(--dim);line-height:1.7}
.srv-price{
  margin-top:1.2rem;display:inline-flex;align-items:center;gap:5px;
  font-size:.68rem;font-weight:700;letter-spacing:.06em;
  color:var(--blue);
  background:rgba(75,142,255,.07);
  border:1px solid rgba(75,142,255,.15);
  border-radius:100px;padding:4px 12px;
}

/* ── CTA SECTION ── */
#cta{
  background:var(--ink);
  padding:8rem 5vw;
}
.cta-inner{
  max-width:760px;margin:0 auto;
  text-align:center;position:relative;
}
.cta-glow{
  position:absolute;top:50%;left:50%;
  transform:translate(-50%,-50%);
  width:600px;height:400px;
  background:radial-gradient(ellipse,rgba(75,142,255,.1) 0%,transparent 70%);
  pointer-events:none;
}
.cta-box{
  position:relative;
  background:linear-gradient(145deg,rgba(75,142,255,.06),rgba(124,92,255,.06));
  border:1px solid rgba(75,142,255,.15);
  border-radius:32px;
  padding:5.5rem 4rem;
  overflow:hidden;
}
.cta-box::before{
  content:'';
  position:absolute;top:-1px;left:15%;right:15%;height:1px;
  background:linear-gradient(90deg,transparent,var(--blue),var(--indigo),var(--violet),transparent);
}
.cta-box::after{
  content:'';
  position:absolute;bottom:-1px;left:15%;right:15%;height:1px;
  background:linear-gradient(90deg,transparent,var(--violet),var(--blue),transparent);
  opacity:.4;
}
.cta-title{
  font-size:clamp(2.2r
