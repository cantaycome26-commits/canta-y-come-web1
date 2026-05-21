<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Canta & Come — LEH</title>
<link href="https://fonts.googleapis.com/css2?family=Barlow+Condensed:ital,wght@0,400;0,700;0,900;1,900&family=Barlow:wght@400;500;600&display=swap" rel="stylesheet">
<style>
*{margin:0;padding:0;box-sizing:border-box}
:root{
  --rojo:#A50000;
  --gold:#E8B800;
  --ink:#0A0000;
  --paper:#F2EAD8;
  --muted:rgba(242,234,216,0.55);
  --g:clamp(1.2rem,4vw,4rem);
}
html{scroll-behavior:smooth}
body{font-family:'Barlow',sans-serif;background:var(--ink);color:var(--paper);overflow-x:hidden}

nav{display:flex;align-items:center;justify-content:space-between;padding:.9rem var(--g);border-bottom:1px solid rgba(232,184,0,0.15);position:sticky;top:0;z-index:99;background:rgba(10,0,0,0.96);backdrop-filter:blur(8px)}
.logo{font-family:'Barlow Condensed',sans-serif;font-weight:900;font-size:1.5rem;letter-spacing:2px;color:var(--gold);text-transform:uppercase;text-decoration:none}
.nav-links{display:flex;gap:2.5rem;list-style:none}
.nav-links a{font-size:.8rem;font-weight:600;letter-spacing:2px;text-transform:uppercase;color:var(--muted);text-decoration:none;transition:color .2s}
.nav-links a:hover{color:var(--gold)}
.nav-btn{font-family:'Barlow Condensed',sans-serif;font-weight:700;font-size:.9rem;letter-spacing:2px;text-transform:uppercase;padding:.55rem 1.5rem;background:var(--gold);color:var(--ink);border:none;cursor:pointer;text-decoration:none;transition:background .2s}
.nav-btn:hover{background:#FFD000}

.hero{display:grid;grid-template-columns:1fr 1px 1fr;min-height:92vh;border-bottom:1px solid rgba(232,184,0,0.2)}
.hero-left{padding:4rem var(--g) 3rem;display:flex;flex-direction:column;justify-content:space-between;border-right:1px solid rgba(232,184,0,0.15)}
.hero-eyebrow{font-size:.7rem;font-weight:600;letter-spacing:4px;text-transform:uppercase;color:var(--gold);margin-bottom:1.5rem;display:flex;align-items:center;gap:.75rem}
.hero-eyebrow::before{content:'';display:block;width:32px;height:1px;background:var(--gold)}
.hero-h1{font-family:'Barlow Condensed',sans-serif;font-weight:900;font-style:italic;font-size:clamp(5rem,10vw,9rem);line-height:.9;text-transform:uppercase;color:var(--paper);letter-spacing:-1px}
.hero-h1 em{color:var(--gold);font-style:italic}
.hero-bottom{display:grid;grid-template-columns:1fr 1fr;gap:1px;border-top:1px solid rgba(232,184,0,0.15);margin-top:3rem}
.hero-stat{padding:1.2rem 0;border-right:1px solid rgba(232,184,0,0.15)}
.hero-stat:last-child{border-right:none;padding-left:1.5rem}
.stat-n{font-family:'Barlow Condensed',sans-serif;font-weight:900;font-size:2.8rem;line-height:1;color:var(--gold)}
.stat-l{font-size:.7rem;letter-spacing:2px;text-transform:uppercase;color:var(--muted);margin-top:.2rem}
.hero-right{padding:4rem var(--g) 3rem;display:flex;flex-direction:column;gap:2rem}
.hero-sub{font-size:1.05rem;line-height:1.7;color:var(--muted);max-width:400px;border-left:3px solid var(--rojo);padding-left:1.2rem}
.hero-cta-row{display:flex;flex-direction:column;gap:.75rem}
.cta-main{font-family:'Barlow Condensed',sans-serif;font-weight:700;font-size:1.1rem;letter-spacing:3px;text-transform:uppercase;padding:1rem 2rem;background:var(--gold);color:var(--ink);text-decoration:none;display:inline-block;transition:background .15s;text-align:center}
.cta-main:hover{background:#FFD000}
.cta-ghost{font-size:.75rem;letter-spacing:3px;text-transform:uppercase;color:var(--muted);text-decoration:none;padding:.7rem 2rem;border:1px solid rgba(232,184,0,0.25);text-align:center;transition:border-color .2s,color .2s}
.cta-ghost:hover{border-color:var(--gold);color:var(--gold)}
.hero-ticker{overflow:hidden;border-top:1px solid rgba(232,184,0,0.15);padding:.75rem 0;white-space:nowrap}
.ticker-inner{display:inline-block;animation:tick 18s linear infinite;font-family:'Barlow Condensed',sans-serif;font-weight:700;font-size:.85rem;letter-spacing:3px;text-transform:uppercase;color:var(--gold)}
@keyframes tick{0%{transform:translateX(0)}100%{transform:translateX(-50%)}}
.shows-row{display:flex;gap:1rem}
.show-pill{font-family:'Barlow Condensed',sans-serif;font-weight:700;font-size:.9rem;letter-spacing:2px;text-transform:uppercase;padding:.4rem .9rem;border:1px solid rgba(232,184,0,0.25);color:var(--paper)}

.sep{padding:.6rem var(--g);background:var(--rojo);display:flex;align-items:center;gap:2rem;overflow:hidden}
.sep-text{font-family:'Barlow Condensed',sans-serif;font-weight:900;font-size:.8rem;letter-spacing:4px;text-transform:uppercase;color:rgba(0,0,0,0.5);white-space:nowrap}
.sep-line{flex:1;height:1px;background:rgba(0,0,0,0.2)}

.exp-section{border-bottom:1px solid rgba(232,184,0,0.12)}
.exp-header{padding:3rem var(--g) 1.5rem;display:flex;align-items:baseline;justify-content:space-between;border-bottom:1px solid rgba(232,184,0,0.12)}
.section-label{font-size:.7rem;font-weight:600;letter-spacing:4px;text-transform:uppercase;color:var(--gold)}
.section-num{font-family:'Barlow Condensed',sans-serif;font-weight:900;font-size:5rem;line-height:1;color:rgba(232,184,0,0.08);pointer-events:none}
.exp-grid{display:grid;grid-template-columns:repeat(3,1fr)}
.exp-item{padding:2rem;border-right:1px solid rgba(232,184,0,0.1);border-bottom:1px solid rgba(232,184,0,0.1);transition:background .2s}
.exp-item:hover{background:rgba(165,0,0,0.12)}
.exp-item:nth-child(3n){border-right:none}
.exp-num{font-family:'Barlow Condensed',sans-serif;font-weight:900;font-size:.75rem;letter-spacing:3px;color:var(--rojo);margin-bottom:1rem}
.exp-item h3{font-family:'Barlow Condensed',sans-serif;font-weight:900;font-size:1.5rem;text-transform:uppercase;color:var(--paper);margin-bottom:.6rem;line-height:1.1}
.exp-item p{font-size:.88rem;color:var(--muted);line-height:1.6}

.menu-section{padding:0}
.menu-header{padding:3rem var(--g) 2rem;display:grid;grid-template-columns:1fr 1fr;align-items:end;gap:2rem;border-bottom:1px solid rgba(232,184,0,0.12)}
.menu-header h2{font-family:'Barlow Condensed',sans-serif;font-weight:900;font-style:italic;font-size:clamp(3rem,6vw,5.5rem);text-transform:uppercase;line-height:.9;color:var(--paper)}
.menu-header h2 span{color:var(--gold)}
.menu-header p{font-size:.9rem;color:var(--muted);line-height:1.65;border-left:2px solid var(--rojo);padding-left:1rem}
.menu-grid{display:grid;grid-template-columns:repeat(2,1fr)}
.menu-item{padding:2rem;border-right:1px solid rgba(232,184,0,0.1);border-bottom:1px solid rgba(232,184,0,0.1);display:grid;grid-template-columns:1fr auto;gap:1rem;align-items:start;transition:background .2s}
.menu-item:hover{background:rgba(232,184,0,0.04)}
.menu-item:nth-child(2n){border-right:none}
.menu-tag{display:inline-block;font-size:.65rem;font-weight:700;letter-spacing:2px;text-transform:uppercase;color:var(--rojo);border:1px solid var(--rojo);padding:.15rem .6rem;margin-bottom:.6rem}
.menu-item h3{font-family:'Barlow Condensed',sans-serif;font-weight:900;font-size:1.4rem;text-transform:uppercase;color:var(--paper);line-height:1.1;margin-bottom:.4rem}
.menu-item p{font-size:.82rem;color:var(--muted);line-height:1.55}
.price-col{text-align:right}
.price{font-family:'Barlow Condensed',sans-serif;font-weight:900;font-size:1.8rem;color:var(--gold);line-height:1}
.price-unit{font-size:.65rem;letter-spacing:1px;color:var(--muted);text-transform:uppercase}

.manifesto{padding:5rem var(--g);background:var(--rojo);display:grid;grid-template-columns:1fr 1.4fr;gap:4rem;align-items:center;border-bottom:4px solid var(--gold)}
.manifesto-label{font-size:.7rem;font-weight:600;letter-spacing:4px;text-transform:uppercase;color:rgba(0,0,0,0.5);margin-bottom:1.5rem}
.manifesto h2{font-family:'Barlow Condensed',sans-serif;font-weight:900;font-style:italic;font-size:clamp(3.5rem,6vw,5rem);text-transform:uppercase;line-height:.9;color:#0A0000}
.manifesto-right p{font-size:1.05rem;line-height:1.75;color:rgba(0,0,0,0.75);border-left:3px solid rgba(0,0,0,0.25);padding-left:1.5rem;margin-bottom:2rem}
.manifesto-values{display:grid;grid-template-columns:1fr 1fr;gap:1px;background:rgba(0,0,0,0.15)}
.mv{background:var(--rojo);padding:.9rem 1.2rem}
.mv-n{font-family:'Barlow Condensed',sans-serif;font-weight:900;font-size:1.1rem;text-transform:uppercase;color:#0A0000;margin-bottom:.2rem}
.mv-d{font-size:.78rem;color:rgba(0,0,0,0.55);line-height:1.4}

.testi-section{padding:0}
.testi-header{padding:3rem var(--g) 2rem;border-bottom:1px solid rgba(232,184,0,0.12);display:flex;align-items:baseline;justify-content:space-between}
.testi-header h2{font-family:'Barlow Condensed',sans-serif;font-weight:900;font-size:clamp(2.5rem,5vw,4rem);text-transform:uppercase;line-height:1;color:var(--paper)}
.testi-grid{display:grid;grid-template-columns:repeat(3,1fr)}
.testi-item{padding:2rem;border-right:1px solid rgba(232,184,0,0.1)}
.testi-item:last-child{border-right:none}
.testi-stars{display:flex;gap:3px;margin-bottom:1rem}
.star{width:12px;height:12px;background:var(--gold);clip-path:polygon(50% 0%,61% 35%,98% 35%,68% 57%,79% 91%,50% 70%,21% 91%,32% 57%,2% 35%,39% 35%);display:inline-block}
blockquote{font-size:.9rem;line-height:1.65;color:var(--muted);font-style:italic;margin-bottom:1.5rem;padding-bottom:1.5rem;border-bottom:1px solid rgba(232,184,0,0.08)}
.testi-name{font-family:'Barlow Condensed',sans-serif;font-weight:700;font-size:1rem;text-transform:uppercase;color:var(--paper);letter-spacing:1px}
.testi-role{font-size:.75rem;color:var(--muted);margin-top:.2rem}

.reserva{display:grid;grid-template-columns:1fr 1fr}
.reserva-left{padding:3.5rem var(--g);background:var(--paper);color:var(--ink);border-right:4px solid var(--rojo)}
.reserva-left .section-label{color:var(--rojo);margin-bottom:1.5rem}
.reserva-left h2{font-family:'Barlow Condensed',sans-serif;font-weight:900;font-style:italic;font-size:clamp(3rem,5vw,4.5rem);text-transform:uppercase;line-height:.9;color:var(--ink);margin-bottom:2rem}
.reserva-left h2 span{color:var(--rojo)}
.info-list{display:flex;flex-direction:column;gap:1rem;margin-bottom:2rem}
.info-li{display:flex;gap:1rem;align-items:flex-start;font-size:.9rem;color:#3a2a2a;line-height:1.5}
.info-li::before{content:'—';color:var(--rojo);font-weight:700;flex-shrink:0}
.social-redes-label{font-size:.65rem;font-weight:600;letter-spacing:3px;text-transform:uppercase;color:var(--rojo);margin-bottom:.9rem}
.social-btns{display:flex;flex-direction:column;gap:.75rem}
.social-btn{display:flex;align-items:center;gap:.9rem;padding:.85rem 1.2rem;text-decoration:none;transition:opacity .2s,transform .2s;cursor:pointer}
.social-btn:hover{opacity:.85;transform:translateX(3px)}
.social-btn-tiktok{background:#0A0000;color:#F2EAD8}
.social-btn-wp{background:#1a7c3e;color:#fff}
.social-icon{width:28px;height:28px;flex-shrink:0;display:flex;align-items:center;justify-content:center}
.social-btn-label{display:flex;flex-direction:column}
.social-btn-action{font-family:'Barlow Condensed',sans-serif;font-weight:700;font-size:.95rem;letter-spacing:2px;text-transform:uppercase;line-height:1}
.social-btn-handle{font-size:.72rem;letter-spacing:1px;opacity:.65;margin-top:.15rem}

.reserva-right{padding:3.5rem var(--g);background:#100000}
.reserva-right .section-label{margin-bottom:1.5rem}
.form-field{margin-bottom:1.2rem}
.form-field label{display:block;font-size:.65rem;font-weight:600;letter-spacing:3px;text-transform:uppercase;color:var(--muted);margin-bottom:.5rem}
.form-field input,.form-field select{width:100%;padding:.8rem 1rem;background:rgba(232,184,0,0.05);border:1px solid rgba(232,184,0,0.15);color:var(--paper);font-family:'Barlow',sans-serif;font-size:.95rem;transition:border-color .2s;-webkit-appearance:none;border-radius:0}
.form-field input:focus,.form-field select:focus{outline:none;border-color:var(--gold)}
.form-field input::placeholder{color:rgba(242,234,216,0.25)}
.form-field select option{background:#1a0000}
.form-row{display:grid;grid-template-columns:1fr 1fr;gap:1rem}
.btn-form{width:100%;padding:1rem;background:var(--rojo);color:var(--paper);font-family:'Barlow Condensed',sans-serif;font-weight:700;font-size:1rem;letter-spacing:3px;text-transform:uppercase;border:none;cursor:pointer;margin-top:.5rem;transition:background .2s;border-radius:0}
.btn-form:hover{background:#C80000}
.wp-note{text-align:center;margin-top:.9rem;font-size:.75rem;letter-spacing:1px;color:var(--muted)}

footer{background:#060000;padding:2.5rem var(--g) 1.5rem;border-top:1px solid rgba(232,184,0,0.12)}
.footer-inner{display:grid;grid-template-columns:2fr 1fr 1fr;gap:3rem;margin-bottom:2rem;padding-bottom:2rem;border-bottom:1px solid rgba(232,184,0,0.08)}
.ft-brand p{font-size:.82rem;color:var(--muted);line-height:1.6;max-width:240px;margin:.75rem 0 1.5rem}
.ft-social-row{display:flex;flex-direction:column;gap:.6rem}
.ft-social-btn{display:flex;align-items:center;gap:.75rem;padding:.65rem 1rem;text-decoration:none;transition:opacity .2s;font-family:'Barlow Condensed',sans-serif;font-weight:700;font-size:.85rem;letter-spacing:2px;text-transform:uppercase}
.ft-social-btn:hover{opacity:.8}
.ft-tiktok{background:rgba(242,234,216,0.06);color:var(--paper);border:1px solid rgba(242,234,216,0.1)}
.ft-whatsapp{background:#1a7c3e;color:#fff}
.ft-col h4{font-size:.65rem;font-weight:700;letter-spacing:3px;text-transform:uppercase;color:var(--gold);margin-bottom:1rem}
.ft-col ul{list-style:none;display:flex;flex-direction:column;gap:.5rem}
.ft-col a{font-size:.85rem;color:var(--muted);text-decoration:none;transition:color .2s}
.ft-col a:hover{color:var(--gold)}
.footer-bottom{display:flex;justify-content:space-between;font-size:.72rem;color:rgba(242,234,216,0.3);letter-spacing:1px}

/* REVEAL */
.reveal{opacity:0;transform:translateY(24px);transition:opacity .65s ease,transform .65s ease}
.reveal.visible{opacity:1;transform:none}
.reveal-d1{transition-delay:.1s}
.reveal-d2{transition-delay:.2s}
.reveal-d3{transition-delay:.3s}

@media(max-width:860px){
  .hero{grid-template-columns:1fr;min-height:auto}
  .hero-left{border-right:none;border-bottom:1px solid rgba(232,184,0,0.15)}
  .exp-grid{grid-template-columns:1fr 1fr}
  .exp-item:nth-child(3n){border-right:1px solid rgba(232,184,0,0.1)}
  .exp-item:nth-child(2n){border-right:none}
  .menu-header,.manifesto{grid-template-columns:1fr}
  .menu-grid{grid-template-columns:1fr}
  .menu-item{border-right:none}
  .testi-grid{grid-template-columns:1fr}
  .testi-item{border-right:none;border-bottom:1px solid rgba(232,184,0,0.1)}
  .reserva{grid-template-columns:1fr}
  .footer-inner{grid-template-columns:1fr 1fr}
  .nav-links{display:none}
}
@media(max-width:560px){
  .exp-grid{grid-template-columns:1fr}
  .form-row{grid-template-columns:1fr}
  .footer-inner{grid-template-columns:1fr}
  .hero-bottom{grid-template-columns:1fr 1fr}
}
</style>
</head>
<body>

<nav>
  <a href="#" class="logo">CANTA&COME</a>
  <ul class="nav-links">
    <li><a href="#exp">Experiencia</a></li>
    <li><a href="#menu">Menú</a></li>
    <li><a href="#reserva">Reservar</a></li>
  </ul>
  <a href="#reserva" class="nav-btn">Reservar mesa</a>
</nav>

<section class="hero">
  <div class="hero-left">
    <div>
      <div class="hero-eyebrow">East High · Bogotá · Est. 2025</div>
      <h1 class="hero-h1">El show<br>empieza<br><em>aquí.</em></h1>
    </div>
    <div>
      <div class="hero-ticker">
        <span class="ticker-inner">WILDCATS &nbsp;·&nbsp; SHOW EN VIVO &nbsp;·&nbsp; KARAOKE &nbsp;·&nbsp; MENÚ TEMÁTICO &nbsp;·&nbsp; CHAPINERO &nbsp;·&nbsp; NOSTALGIA &nbsp;·&nbsp; WILDCATS &nbsp;·&nbsp; SHOW EN VIVO &nbsp;·&nbsp; KARAOKE &nbsp;·&nbsp; MENÚ TEMÁTICO &nbsp;·&nbsp; CHAPINERO &nbsp;·&nbsp; NOSTALGIA &nbsp;·&nbsp;</span>
      </div>
      <div class="hero-bottom">
        <div class="hero-stat"><div class="stat-n">4.9</div><div class="stat-l">Calificación</div></div>
        <div class="hero-stat"><div class="stat-n">500+</div><div class="stat-l">Wildcats</div></div>
      </div>
    </div>
  </div>
  <div class="hero-right">
    <p class="hero-sub">Restaurante temático inspirado en High School Musical. Comida americana, shows en vivo, karaoke y toda la nostalgia de los 2000s — en el corazón de Bogotá.</p>
    <div class="hero-cta-row">
      <a href="#reserva" class="cta-main">Reservar mi mesa</a>
      <a href="#menu" class="cta-ghost">Ver el menú completo</a>
    </div>
    <div style="border-top:1px solid rgba(232,184,0,0.12);padding-top:2rem;margin-top:auto">
      <div style="font-size:.65rem;font-weight:600;letter-spacing:3px;text-transform:uppercase;color:var(--muted);margin-bottom:1rem">Shows en vivo</div>
      <div class="shows-row">
        <span class="show-pill">Viernes</span>
        <span class="show-pill">Sábado</span>
        <span class="show-pill">Domingo</span>
      </div>
    </div>
  </div>
</section>

<div class="sep">
  <span class="sep-text">Diversión</span><div class="sep-line"></div>
  <span class="sep-text">Nostalgia</span><div class="sep-line"></div>
  <span class="sep-text">Autenticidad</span><div class="sep-line"></div>
  <span class="sep-text">Comunidad</span><div class="sep-line"></div>
  <span class="sep-text">Sabor</span>
</div>

<section id="exp" class="exp-section">
  <div class="exp-header">
    <div class="section-label reveal">La experiencia</div>
    <div class="section-num">01</div>
  </div>
  <div class="exp-grid">
    <div class="exp-item reveal"><div class="exp-num">01 — Ambiente</div><h3>Ambientación Total</h3><p>Casilleros, gimnasio, escenario. Cada rincón diseñado para que sientas que estás en East High. Cada visita, una foto diferente.</p></div>
    <div class="exp-item reveal reveal-d1"><div class="exp-num">02 — Live</div><h3>Shows en Vivo</h3><p>Coreografías, canto y karaoke cada viernes, sábado y domingo. El staff canta con vos — podés subirte al escenario.</p></div>
    <div class="exp-item reveal reveal-d2"><div class="exp-num">03 — Comunidad</div><h3>Todos son Wildcats</h3><p>Un espacio sin juicios donde todos comparten el mismo gusto. Sé quien sos, sin miedo al qué dirán.</p></div>
    <div class="exp-item reveal"><div class="exp-num">04 — Interacción</div><h3>Retos y Karaoke</h3><p>Concursos de baile, dinámicas grupales y premios sorpresa. El público no mira — el público es el show.</p></div>
    <div class="exp-item reveal reveal-d1"><div class="exp-num">05 — Contenido</div><h3>Instagrameable</h3><p>Cada ángulo pensado para que tu contenido destaque. El lugar que todos en tus historias van a querer conocer.</p></div>
    <div class="exp-item reveal reveal-d2"><div class="exp-num">06 — Celebra</div><h3>Eventos Especiales</h3><p>Cumpleaños, despedidas y salidas grupales con experiencias personalizadas y sorpresas temáticas.</p></div>
  </div>
</section>

<section id="menu" class="menu-section">
  <div class="menu-header">
    <h2 class="reveal">El menú<br>que <span>esperabas.</span></h2>
    <p class="reveal reveal-d1">Cada plato lleva el nombre de un personaje. Cada bocado, una escena. Comida americana con sabor a HSM — hecha para compartir y fotografiar.</p>
  </div>
  <div class="menu-grid">
    <div class="menu-item reveal"><div><span class="menu-tag">★ Más pedido</span><h3>Troy Bolton Burger</h3><p>Doble carne angus, queso cheddar, bacon crocante y salsa Wildcats sobre pan brioche tostado.</p></div><div class="price-col"><div class="price">28K</div><div class="price-unit">COP</div></div></div>
    <div class="menu-item reveal reveal-d1"><div><span class="menu-tag">Clásico</span><h3>Gabriella's Dog</h3><p>Hot dog estilo americano con mostaza, cebolla caramelizada y papas fritas. Simple y perfecto.</p></div><div class="price-col"><div class="price">22K</div><div class="price-unit">COP</div></div></div>
    <div class="menu-item reveal"><div><span class="menu-tag">Bebida icónica</span><h3>Sharpay Pink Shake</h3><p>Malteada de fresa con leche condensada, chantilly y decoración de estrellas doradas.</p></div><div class="price-col"><div class="price">18K</div><div class="price-unit">COP</div></div></div>
    <div class="menu-item reveal reveal-d1"><div><span class="menu-tag">Para compartir</span><h3>East High Pizza</h3><p>Pizza americana con 4 quesos y pepperoni. La favorita de los Wildcats después de cada partido.</p></div><div class="price-col"><div class="price">45K</div><div class="price-unit">COP</div></div></div>
  </div>
</section>

<section class="manifesto">
  <div class="reveal">
    <div class="manifesto-label">Nuestra filosofía</div>
    <h2>Aquí<br>todos<br>somos<br>wildcats.</h2>
  </div>
  <div class="manifesto-right reveal reveal-d1">
    <p>Queremos transformar la idea errónea que muchos tienen sobre los fanáticos de HSM. Este espacio existe para que puedas ser quien sos — sin miedo al qué dirán — rodeado de personas que comparten exactamente el mismo gusto.</p>
    <div class="manifesto-values">
      <div class="mv"><div class="mv-n">Pertenencia</div><div class="mv-d">Un lugar para todos los fans, sin excepción</div></div>
      <div class="mv"><div class="mv-n">Nostalgia</div><div class="mv-d">Los 2000s revividos en cada detalle</div></div>
      <div class="mv"><div class="mv-n">Autenticidad</div><div class="mv-d">Cantá, bailá, sé vos mismo</div></div>
      <div class="mv"><div class="mv-n">Experiencia</div><div class="mv-d">Más que comida — momentos memorables</div></div>
    </div>
  </div>
</section>

<section class="testi-section">
  <div class="testi-header">
    <h2 class="reveal">Dicen los<br>Wildcats</h2>
    <div class="section-label reveal">Reseñas verificadas</div>
  </div>
  <div class="testi-grid">
    <div class="testi-item reveal">
      <div class="testi-stars"><span class="star"></span><span class="star"></span><span class="star"></span><span class="star"></span><span class="star"></span></div>
      <blockquote>"Fui con mis amigas y lloramos de nostalgia. La ambientación es increíble, el staff canta con vos y la comida está deliciosa. Ya reservé para volver."</blockquote>
      <div class="testi-name">Salomé García</div><div class="testi-role">Estudiante · 21 años · Chapinero</div>
    </div>
    <div class="testi-item reveal reveal-d1">
      <div class="testi-stars"><span class="star"></span><span class="star"></span><span class="star"></span><span class="star"></span><span class="star"></span></div>
      <blockquote>"El mejor plan de Bogotá ahora mismo. El karaoke del viernes fue una experiencia única — todos cantando como si tuviéramos 15 años otra vez."</blockquote>
      <div class="testi-name">Miguel Rodríguez</div><div class="testi-role">Diseñador · 28 años · Usaquén</div>
    </div>
    <div class="testi-item reveal reveal-d2">
      <div class="testi-stars"><span class="star"></span><span class="star"></span><span class="star"></span><span class="star"></span><span class="star"></span></div>
      <blockquote>"Nadie te juzga ahí. Todos somos iguales. Cel lleno de fotos y el corazón lleno de recuerdos. Es nuestro nuevo spot favorito."</blockquote>
      <div class="testi-name">Laura Arias</div><div class="testi-role">Profesora · 32 años · Suba</div>
    </div>
  </div>
</section>

<section id="reserva" class="reserva">
  <div class="reserva-left">
    <div class="section-label">Contacto &amp; Reservas</div>
    <h2>Asegurá<br>tu <span>lugar</span><br>en el show.</h2>
    <div class="info-list">
      <div class="info-li">Chapinero, Bogotá — dirección exacta al confirmar</div>
      <div class="info-li">Martes a domingo · 12pm – 10pm</div>
      <div class="info-li">Shows en vivo: Viernes · Sábado · Domingo</div>
      <div class="info-li">Los fines de semana se llenan — reservá con anticipación</div>
    </div>
    <div class="social-redes-label">Nuestras redes</div>
    <div class="social-btns">
      <a href="https://www.tiktok.com/@cantacome_" target="_blank" rel="noopener" class="social-btn social-btn-tiktok">
        <div class="social-icon">
          <svg viewBox="0 0 24 24" fill="currentColor" width="24" height="24" xmlns="http://www.w3.org/2000/svg">
            <path d="M19.59 6.69a4.83 4.83 0 0 1-3.77-4.25V2h-3.45v13.67a2.89 2.89 0 0 1-2.88 2.5 2.89 2.89 0 0 1-2.89-2.89 2.89 2.89 0 0 1 2.89-2.89c.28 0 .54.04.79.1V9.01a6.34 6.34 0 0 0-.79-.05 6.34 6.34 0 0 0-6.34 6.34 6.34 6.34 0 0 0 6.34 6.34 6.34 6.34 0 0 0 6.33-6.34V8.69a8.18 8.18 0 0 0 4.78 1.52V6.76a4.85 4.85 0 0 1-1.01-.07z"/>
          </svg>
        </div>
        <div class="social-btn-label">
          <span class="social-btn-action">Seguinos en TikTok</span>
          <span class="social-btn-handle">@cantacome_</span>
        </div>
      </a>
      <a href="https://wa.me/573026497926" target="_blank" rel="noopener" class="social-btn social-btn-wp">
        <div class="social-icon">
          <svg viewBox="0 0 24 24" fill="currentColor" width="24" height="24" xmlns="http://www.w3.org/2000/svg">
            <path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 0 1-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 0 1-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 0 1 2.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0 0 12.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 0 0 5.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 0 0-3.48-8.413z"/>
          </svg>
        </div>
        <div class="social-btn-label">
          <span class="social-btn-action">Escribinos por WhatsApp</span>
          <span class="social-btn-handle">+57 302 649 7926</span>
        </div>
      </a>
    </div>
  </div>
  <div class="reserva-right">
    <div class="section-label">Completá tus datos</div>
    <form id="res-form">
      <div class="form-row">
        <div class="form-field"><label>Nombre completo</label><input type="text" placeholder="Tu nombre" required></div>
        <div class="form-field"><label>WhatsApp</label><input type="tel" placeholder="+57 300..."></div>
      </div>
      <div class="form-row">
        <div class="form-field"><label>Fecha</label><input type="date" required></div>
        <div class="form-field"><label>Personas</label>
          <select>
            <option>2 personas</option>
            <option>3 personas</option>
            <option>4 personas</option>
            <option>5+ personas</option>
          </select>
        </div>
      </div>
      <div class="form-field"><label>Ocasión</label>
        <select>
          <option>Salida con amigos</option>
          <option>Cumpleaños</option>
          <option>Cita / pareja</option>
          <option>Celebración especial</option>
        </select>
      </div>
      <button type="submit" class="btn-form" id="res-btn">Confirmar reserva</button>
    </form>
    <div class="wp-note">O escríbenos directo por WhatsApp al +57 302 649 7926</div>
  </div>
</section>

<footer>
  <div class="footer-inner">
    <div class="ft-brand">
      <a href="#" class="logo">CANTA&COME</a>
      <p>El restaurante temático de High School Musical en el corazón de Bogotá. Comida, música y nostalgia en un solo lugar.</p>
      <div class="ft-social-row">
        <a href="https://www.tiktok.com/@cantacome_" target="_blank" rel="noopener" class="ft-social-btn ft-tiktok">
          <svg viewBox="0 0 24 24" fill="currentColor" width="18" height="18"><path d="M19.59 6.69a4.83 4.83 0 0 1-3.77-4.25V2h-3.45v13.67a2.89 2.89 0 0 1-2.88 2.5 2.89 2.89 0 0 1-2.89-2.89 2.89 2.89 0 0 1 2.89-2.89c.28 0 .54.04.79.1V9.01a6.34 6.34 0 0 0-.79-.05 6.34 6.34 0 0 0-6.34 6.34 6.34 6.34 0 0 0 6.34 6.34 6.34 6.34 0 0 0 6.33-6.34V8.69a8.18 8.18 0 0 0 4.78 1.52V6.76a4.85 4.85 0 0 1-1.01-.07z"/></svg>
          TikTok · @cantacome_
        </a>
        <a href="https://wa.me/573026497926" target="_blank" rel="noopener" class="ft-social-btn ft-whatsapp">
          <svg viewBox="0 0 24 24" fill="currentColor" width="18" height="18"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 0 1-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 0 1-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 0 1 2.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0 0 12.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 0 0 5.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 0 0-3.48-8.413z"/></svg>
          WhatsApp · +57 302 649 7926
        </a>
      </div>
    </div>
    <div class="ft-col">
      <h4>Visítanos</h4>
      <ul>
        <li><a href="#">Chapinero, Bogotá</a></li>
        <li><a href="#">Mar–Dom: 12pm–10pm</a></li>
        <li><a href="https://wa.me/573026497926" target="_blank">+57 302 649 7926</a></li>
        <li><a href="#">hola@cantaycome.co</a></li>
      </ul>
    </div>
    <div class="ft-col">
      <h4>Navegar</h4>
      <ul>
        <li><a href="#exp">Experiencia</a></li>
        <li><a href="#menu">Menú</a></li>
        <li><a href="#reserva">Reservar</a></li>
        <li><a href="#">Eventos privados</a></li>
        <li><a href="https://www.tiktok.com/@cantacome_" target="_blank">TikTok</a></li>
        <li><a href="https://wa.me/573026497926" target="_blank">WhatsApp</a></li>
      </ul>
    </div>
  </div>
  <div class="footer-bottom">
    <span>© 2025 Canta &amp; Come — LEH. Bogotá, Colombia.</span>
    <span>WILDCATS FOREVER</span>
  </div>
</footer>

<script>
document.getElementById('res-form').addEventListener('submit',function(e){
  e.preventDefault();
  const b=document.getElementById('res-btn');
  b.textContent='Reserva confirmada — te contactamos pronto';
  b.style.background='#1a5c1a';
  b.disabled=true;
});

const obs=new IntersectionObserver((entries)=>{
  entries.forEach(el=>{
    if(el.isIntersecting){el.target.classList.add('visible');obs.unobserve(el.target)}
  });
},{threshold:0.12});
document.querySelectorAll('.reveal').forEach(el=>obs.observe(el));
</script>
</body>
</html>
