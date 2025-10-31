
<html lang="es">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Clínica Veterinaria · Mis Mascotas — Anapoima</title>
  <meta name="description" content="Clínica Veterinaria Mis Mascotas en Anapoima — baños, peluquería, guardería, urgencias 24h, cirugías, exámenes y venta de medicamentos y accesorios.">

  <!-- Google Fonts -->
  <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@600;700&family=Open+Sans:wght@300;400;600&display=swap" rel="stylesheet">

  <style>
    :root{
      --blue: #0078d7;
      --blue-dark: #0056a3;
      --bg: #ffffff;
      --muted: #6b7280;
      --dark: #0f1724;
      --glass: rgba(255,255,255,0.7);
      --card-shadow: 0 8px 30px rgba(3,12,40,0.08);
      --radius: 14px;
      --header-h: 72px;

      /* Extras para efectos */
      --glow-color: rgba(0, 120, 215, 0.35);
      --btn-pulse: rgba(0, 120, 215, 0.18);
    }

    /* Reset & base */
    *{box-sizing:border-box}
    html,body{height:100%}
    body{
      margin:0;
      font-family: "Open Sans", system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
      color:var(--dark);
      background: linear-gradient(180deg,#fbfdff 0%, #ffffff 100%);
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
      line-height:1.5;
      scroll-behavior:smooth;
    }
    img{display:block; max-width:100%; height:auto}

    /* Header */
    header{
      position:fixed;
      top:0;
      left:0;
      width:100%;
      height:var(--header-h);
      display:flex;
      align-items:center;
      justify-content:space-between;
      padding:12px 20px;
      gap:12px;
      z-index:1200;
      background: linear-gradient(90deg, rgba(255,255,255,0.85), rgba(255,255,255,0.7));
      backdrop-filter: blur(6px);
      border-bottom:1px solid rgba(15,23,36,0.06);
      transition: box-shadow .25s ease, transform .25s ease;
    }

    /* small header lift on scroll (JS toggles 'scrolled' class) */
    header.scrolled{
      box-shadow: 0 10px 30px rgba(3,12,40,0.08);
      transform: translateY(-2px);
    }

    .container{ width:92%; max-width:1150px; margin:0 auto; display:flex; align-items:center; justify-content:space-between; gap:12px }

    .brand{
      display:flex; flex-direction:column; line-height:1;
      transition: transform .35s ease;
    }
    .brand.halo:hover{ transform: translateY(-4px) scale(1.02); filter: drop-shadow(0 10px 20px var(--glow-color)); }
    .brand h1{
      margin:0;
      font-family: "Montserrat", sans-serif;
      font-size:1.1rem;
      color:var(--dark);
    }
    .brand small{ color:var(--muted); font-size:0.78rem }

    /* Nav */
    nav.desktop{ display:flex; gap:14px; align-items:center }
    nav.desktop a{
      text-decoration:none; color:var(--dark); font-weight:600; padding:8px 12px; border-radius:10px;
      transition: all .28s cubic-bezier(.2,.9,.2,1);
      will-change: transform, box-shadow;
    }
    nav.desktop a:hover{
      background:rgba(0,120,215,0.08);
      color:var(--blue);
      transform: translateY(-4px) scale(1.08);
      box-shadow: 0 8px 20px rgba(0,120,215,0.12);
      text-shadow: 0 0 10px rgba(0,120,215,0.12);
    }

    .btn-cta{
      background:linear-gradient(90deg,var(--blue),var(--blue-dark));
      color:white; padding:8px 14px; border-radius:12px; text-decoration:none; font-weight:700;
      transition: all .28s cubic-bezier(.2,.9,.2,1);
      position:relative;
      overflow:visible;
    }
    /* pulse behind button on hover */
    .btn-cta::after{
      content: "";
      position: absolute;
      left: -6px;
      right: -6px;
      top: -6px;
      bottom: -6px;
      border-radius: 16px;
      background: radial-gradient(circle at 50% 20%, var(--btn-pulse), transparent 40%);
      opacity: 0;
      transform: scale(.9);
      transition: all .35s ease;
      pointer-events: none;
      filter: blur(10px);
    }
    .btn-cta:hover::after{ opacity:1; transform: scale(1); }

    .btn-cta:hover{
      transform: translateY(-4px) scale(1.06);
      box-shadow: 0 12px 30px rgba(0,120,215,0.28);
      filter:brightness(1.08);
    }

    .btn-ghost{
      border:1px solid rgba(15,23,36,0.06); padding:7px 12px; border-radius:10px; text-decoration:none; color:var(--dark);
      transition: all .28s cubic-bezier(.2,.9,.2,1);
      position:relative;
    }
    .btn-ghost::after{
      content:"";
      position:absolute; inset: -6px; border-radius:12px; opacity:0; transition: all .25s ease;
    }
    .btn-ghost:hover{
      transform: translateY(-3px) scale(1.04);
      box-shadow: 0 8px 20px rgba(0,120,215,0.12);
      color:var(--blue);
    }

    /* Mobile nav (checkbox hack) */
    .mobile-toggle{ display:none }
    .mobile-btn{
      display:none;
      width:44px; height:44px; border-radius:10px; display:flex; align-items:center; justify-content:center; cursor:pointer;
      background:transparent; border:1px solid rgba(15,23,36,0.04)
    }
    .mobile-btn span{ display:block; width:18px; height:2px; background:var(--dark); position:relative }
    .mobile-btn span::before, .mobile-btn span::after{ content:""; position:absolute; left:0; right:0; height:2px; background:var(--dark) }
    .mobile-btn span::before{ top:-6px } .mobile-btn span::after{ top:6px }

    /* Page sections — add top padding so content not hidden under fixed header */
    section{ padding:calc(var(--header-h) + 36px) 0; }
    .section-inner{ width:92%; max-width:1150px; margin:0 auto; }

    /* HERO */
    #inicio{
      background: linear-gradient(180deg, rgba(0,120,215,0.07), rgba(255,255,255,0));
      display:flex; align-items:center; justify-content:center; min-height: calc(100vh - var(--header-h));
      padding-top:40px; padding-bottom:40px;
    }
    .hero-grid{ display:grid; grid-template-columns: 1fr 1fr; gap:28px; align-items:center; width:100%; max-width:1150px; }
    .hero-text h2{ font-family:"Montserrat",sans-serif; font-size:2.1rem; margin-bottom:10px; color:var(--dark) }
    .hero-text p{ color:var(--muted); margin-bottom:18px; max-width:640px }

    .hero-cta{ display:flex; gap:12px; flex-wrap:wrap }

    .hero-image{ border-radius:18px; overflow:hidden; box-shadow: var(--card-shadow); transition: transform .45s cubic-bezier(.2,.9,.2,1), filter .35s ease, box-shadow .35s ease; }
    .hero-image img{ width:100%; height:360px; object-fit:cover; display:block; transition: transform .45s ease, filter .45s ease; }
    .hero-image:hover{ transform: translateY(-6px) scale(1.02); box-shadow: 0 30px 70px rgba(0,120,215,0.18); filter: brightness(1.03); }
    .hero-image:hover img{ transform: scale(1.03); filter: brightness(1.05); }

    /* Servicios grid & cards */
    .section-title{ font-family:"Montserrat",sans-serif; font-size:1.25rem; margin-bottom:6px }
    .lead{ color:var(--muted); margin-bottom:18px }

    .cards-grid{
      display:grid;
      grid-template-columns: repeat(3,1fr);
      gap:20px;
      margin-top:14px;
    }
    .card{
      background:var(--bg);
      border-radius:var(--radius);
      overflow:hidden;
      box-shadow:var(--card-shadow);
      transition: transform .28s ease, box-shadow .28s ease, filter .28s ease;
      display:flex; flex-direction:column;
      min-height:320px;

      /* reveal base (hidden until in-view by JS) */
      opacity:0;
      transform: translateY(18px) scale(.995);
      will-change: transform, opacity;
    }
    /* in-view class applied by JS */
    .card.in-view{
      opacity:1;
      transform: translateY(0) scale(1);
      transition: transform .5s cubic-bezier(.2,.9,.2,1), opacity .45s ease;
    }

    /* hover effects: zoom, strong elevation, glow behind card */
    .card:hover{
      transform: translateY(-14px) scale(1.03);
      box-shadow: 0 30px 80px rgba(3,12,40,0.25), 0 0 30px var(--glow-color);
      filter:brightness(1.06);
    }
    .card-img{ height:170px; width:100%; object-fit:cover; display:block; transition: transform .45s ease, filter .35s ease; }
    .card:hover .card-img{ transform:scale(1.08); filter:brightness(1.12); }
    .card-body{ padding:16px; display:flex; flex-direction:column; gap:10px; flex:1 }
    .card-body h3{ margin:0; font-size:1.05rem; color:var(--blue) }
    .card-body p{ color:var(--muted); margin-top:4px; flex:1 }
    .card-actions{ display:flex; gap:10px; align-items:center }

    .pill{
      display:inline-block; padding:8px 12px; border-radius:999px; background:rgba(0,120,215,0.08); color:var(--blue); font-weight:700; font-size:0.9rem;
    }

    /* subtle glowing outline that appears on hover */
    .card::after{
      content: "";
      position: absolute;
      inset: 0;
      border-radius: var(--radius);
      pointer-events: none;
      box-shadow: 0 0 0 0 rgba(0,120,215,0);
      transition: box-shadow .35s ease;
    }
    .card:hover::after{
      box-shadow: 0 0 30px 6px rgba(0,120,215,0.06);
    }

    /* About / guardería */
    .grid-2{ display:grid; grid-template-columns: 1fr 1fr; gap:20px; align-items:center; margin-top:18px }
    .about-card{
      background:linear-gradient(180deg, #fff, #fbfdff); padding:18px; border-radius:12px; box-shadow:var(--card-shadow);
      transition: transform .35s ease, box-shadow .35s ease, filter .35s ease;
      opacity:0; transform: translateY(18px) scale(.995);
    }
    .about-card.in-view{ opacity:1; transform: translateY(0) scale(1); transition: all .5s cubic-bezier(.2,.9,.2,1); }
    .about-card:hover{
      transform: translateY(-10px) scale(1.02);
      box-shadow:0 22px 50px rgba(0,120,215,0.18);
      filter:brightness(1.03);
    }

    /* Button pulse animation (subtle heartbeat for CTAs) */
    @keyframes btnPulse {
      0% { transform: scale(1); box-shadow: 0 0 0 0 rgba(0,120,215,0.18); }
      50% { transform: scale(1.03); box-shadow: 0 8px 30px rgba(0,120,215,0.18); }
      100% { transform: scale(1); box-shadow: 0 0 0 0 rgba(0,120,215,0.0); }
    }
    .btn-cta.pulse {
      animation: btnPulse 2.4s infinite ease-in-out;
    }

    /* Footer */
    footer{
      background:#0b1020; color:#fff; padding:28px 0; margin-top:30px;
    }
    .footer-inner{ width:92%; max-width:1150px; margin:0 auto; display:flex; gap:20px; justify-content:space-between; flex-wrap:wrap }
    .footer-col{ flex:1 1 220px }
    .footer-col h4{ margin:0 0 8px 0; font-size:1rem }
    .footer-col p{ margin:6px 0; color:#cbd5e1 }

    /* small helpers */
    .center{ text-align:center }
    .muted{ color:var(--muted) }

    /* RESPONSIVE */
    @media (max-width: 1000px){
      .cards-grid{ grid-template-columns: repeat(2,1fr) }
      .hero-grid{ grid-template-columns: 1fr; }
      .hero-image img{ height:320px }
    }

    @media (max-width: 700px){
      header{ height:72px; padding:10px }
      .container{ width:95% }
      nav.desktop{ display:none }
      .mobile-btn{ display:flex }
      .mobile-toggle{ display:block }
      .section-inner{ padding:0 12px }

      .cards-grid{ grid-template-columns: 1fr }
      .grid-2{ grid-template-columns: 1fr }
      .hero-image img{ height:220px }
    }

    /* Mobile nav panel (appears when checkbox checked) */
    #nav-toggle{ display:none }
    #nav-toggle:checked + .mobile-menu{ display:block }
    .mobile-menu{
      display:none;
      position:absolute;
      right:12px; top:calc(var(--header-h) + 10px);
      background:var(--bg);
      border-radius:12px;
      box-shadow: var(--card-shadow);
      padding:12px;
      min-width:200px;
      z-index:1300;
    }
    .mobile-menu a{ display:block; padding:10px; text-decoration:none; color:var(--dark); border-radius:8px; transition:all .3s ease; }
    .mobile-menu a:hover{ background:rgba(0,120,215,0.05); color:var(--blue); transform:translateY(-2px); box-shadow: 0 6px 18px rgba(0,120,215,0.08); }

    /* small animation on load fallback for cards (if JS disabled) */
    .no-js .card { opacity:1; transform:none; }
  </style>
</head>
<body>
  <!-- HEADER -->
  <header>
    <div class="container">
      <div class="brand halo" aria-hidden="false">
        <h1>Mis Mascotas</h1>
        <small>Clínica Veterinaria · Anapoima</small>
      </div>

      <!-- Desktop nav -->
      <nav class="desktop" aria-label="Menú principal">
        <a href="#inicio">Inicio</a>
        <a href="#servicios">Servicios</a>
        <a href="#guarderia">Guardería</a>
        <a href="#nosotros">Nosotros</a>
        <a class="btn-cta pulse" href="https://wa.me/573054395826" target="_blank" rel="noopener">WhatsApp</a>
      </nav>

      <!-- Mobile toggle -->
      <label for="nav-toggle" class="mobile-btn" title="Abrir menú" aria-hidden="false">
        <span></span>
      </label>
      <input id="nav-toggle" class="mobile-toggle" type="checkbox" />
      <div class="mobile-menu" role="menu" aria-hidden="true">
        <a href="#inicio">Inicio</a>
        <a href="#servicios">Servicios</a>
        <a href="#guarderia">Guardería</a>
        <a href="#nosotros">Nosotros</a>
        <a href="#contacto" class="btn-ghost">Contacto</a>
      </div>
    </div>
  </header>

  <!-- INICIO / HERO -->
  <main id="main">
    <section id="inicio" aria-label="Inicio">
      <div class="hero-grid section-inner">
        <div class="hero-text">
          <h2>Tu mascota merece lo mejor</h2>
          <p>En <strong>Clínica Veterinaria Mis Mascotas</strong> cuidamos la salud, la higiene y la felicidad de tu compañero. Atención profesional, servicios integrales y urgencias 24 horas.</p>
          <div class="hero-cta">
            <a class="btn-cta" href="https://wa.me/573054395826" target="_blank" rel="noopener">Pedir cita (WhatsApp)</a>
            <a class="btn-ghost" href="#servicios">Ver servicios</a>
          </div>
        </div>

        <div class="hero-image" aria-hidden="false">
          <img src="imagenes/hero.png" alt="Mascotas felices en la clínica">
        </div>
      </div>
    </section>

    <!-- SERVICIOS -->
    <section id="servicios" aria-label="Servicios">
      <div class="section-inner">
        <h3 class="section-title">Nuestros Servicios</h3>
        <p class="lead">Servicios para caninos, felinos, aves, conejos y peces — todo en un solo lugar.</p>

        <div class="cards-grid" role="list">
          <!-- 1 Baño -->
          <article class="card" role="listitem" aria-labelledby="s1-title">
            <img src="imagenes/banio.png" class="card-img" alt="Baño y aseo">
            <div class="card-body">
              <h3 id="s1-title">Baño y Aseo</h3>
              <p>Baño con shampoo y acondicionador, secado, perfume, limpieza de uñas y aseo general. Precio aproximado: <strong>$50.000 COP</strong>.</p>
              <div class="card-actions">
                <span class="pill">Desde $50.000</span>
                <a class="btn-cta" href="https://wa.me/573054395826" target="_blank" rel="noopener">Solicitar cita</a>
              </div>
            </div>
          </article>

          <!-- 2 Peluquería -->
          <article class="card" role="listitem" aria-labelledby="s2-title">
            <img src="imagenes/peluqueria.png" class="card-img" alt="Peluquería canina">
            <div class="card-body">
              <h3 id="s2-title">Peluquería Canina</h3>
              <p>Peluquería para todas las razas: cortes, peinados, colocación de pañoletas y estilizado. Precios: <strong>$30.000 - $60.000 COP</strong>.</p>
              <div class="card-actions">
                <span class="pill">Cortes y estilizado</span>
                <a class="btn-cta" href="https://wa.me/573054395826" target="_blank" rel="noopener">Solicitar</a>
              </div>
            </div>
          </article>

          <!-- 3 Medicamentos -->
          <article class="card" role="listitem" aria-labelledby="s3-title">
            <img src="imagenes/medicamentos.png" class="card-img" alt="Venta de medicamentos">
            <div class="card-body">
              <h3 id="s3-title">Venta de Medicamentos</h3>
              <p>Surtimos medicamentos y recetas para distintas especies. Recomendamos consulta previa con el médico veterinario.</p>
              <div class="card-actions">
                <span class="pill">Recetas y surtido</span>
                <a class="btn-cta" href="https://wa.me/573054395826" target="_blank" rel="noopener">Consultar</a>
              </div>
            </div>
          </article>

          <!-- 4 Exámenes -->
          <article class="card" role="listitem" aria-labelledby="s4-title">
            <img src="imagenes/examenes.png" class="card-img" alt="Toma de exámenes">
            <div class="card-body">
              <h3 id="s4-title">Toma de Exámenes</h3>
              <p>Analíticas y pruebas diagnósticas con entrega de resultados y recomendaciones médicas.</p>
              <div class="card-actions">
                <span class="pill">Diagnóstico</span>
                <a class="btn-cta" href="https://wa.me/573054395826" target="_blank" rel="noopener">Solicitar</a>
              </div>
            </div>
          </article>

          <!-- 5 Cirugías -->
          <article class="card" role="listitem" aria-labelledby="s5-title">
            <img src="imagenes/cirugia.png" class="card-img" alt="Cirugías veterinarias">
            <div class="card-body">
              <h3 id="s5-title">Cirugías</h3>
              <p>Procedimientos programados y de emergencia con anestesia y control postoperatorio por personal calificado.</p>
              <div class="card-actions">
                <span class="pill">Procedimientos</span>
                <a class="btn-cta" href="https://wa.me/573054395826" target="_blank" rel="noopener">Consultar</a>
              </div>
            </div>
          </article>

          <!-- 6 Urgencias -->
          <article class="card" role="listitem" aria-labelledby="s6-title">
            <img src="imagenes/urgencias.png" class="card-img" alt="Urgencias 24 horas">
            <div class="card-body">
              <h3 id="s6-title">Urgencias 24h</h3>
              <p>Atención inmediata las 24 horas. Contáctanos por WhatsApp si tu mascota necesita atención urgente.</p>
              <div class="card-actions">
                <span class="pill">24 / 7</span>
                <a class="btn-cta" href="https://wa.me/573054395826" target="_blank" rel="noopener">Contactar Urgencias</a>
              </div>
            </div>
          </article>

          <!-- 7 Accesorios -->
          <article class="card" role="listitem" aria-labelledby="s7-title">
            <img src="imagenes/accesorios.jpg" class="card-img" alt="Accesorios para mascotas">
            <div class="card-body">
              <h3 id="s7-title">Venta de Accesorios</h3>
              <p>Collares, platos, juguetes, placas y más para consentir a tu amigo peludo.</p>
              <div class="card-actions">
                <span class="pill">Catálogo</span>
                <a class="btn-cta" href="https://wa.me/573054395826" target="_blank" rel="noopener">Ver catálogo</a>
              </div>
            </div>
          </article>

          <!-- 8 Guardería -->
          <article class="card" role="listitem" aria-labelledby="s8-title">
            <img src="imagenes/guarderia.webp" class="card-img" alt="Guardería canina">
            <div class="card-body">
              <h3 id="s8-title">Guardería Canina</h3>
              <p>Espacios amplios y supervisados para que tu mascota juegue y socialice. Ideal para días cortos o estancias largas.</p>
              <div class="card-actions">
                <span class="pill">Reserva</span>
                <a class="btn-cta" href="https://wa.me/573054395826" target="_blank" rel="noopener">Reservar</a>
              </div>
            </div>
          </article>
        </div>
      </div>
    </section>
    <!-- CONTACTO -->
    <section id="contacto" aria-label="Contacto">
      <div class="section-inner">
        <h3 class="section-title">Contacto</h3>
        <p class="muted">Dirección: Carrera 5 #10-32, Centro, Anapoima — Horario: Lunes a domingo 8:00 - 20:00. Urgencias 24h.</p>

        <div class="grid-2" style="margin-top:16px">
          <div class="about-card">
            <p><strong>Teléfono</strong><br><a href="wa.me/573054395826" target="_blank" rel="noopener"> 305 4395826 </a></p>
            <p style="margin-top:8px"><strong>Email</strong><br>info@clinicamismascotas.com </p>
            <p style="margin-top:8px"><strong>Nota</strong><br>Para reservar, envía nombre, servicio deseado y fecha aproximada.</p>
          
          
          </div>
        </div>
      </div>
    </section>
  </main>

  <!-- FOOTER -->
  <footer>
    <div class="footer-inner">
      <div class="footer-col">
        <h4>Clínica Mis Mascotas</h4>
        <p>Carrera 5 #10-32, Centro — Anapoima, Cundinamarca</p>
      </div>
      <div class="footer-col">
        <h4>Contacto</h4>
        <p><a href="https://wa.me/573054395826" target="_blank" rel="noopener">WhatsApp / Teléfono</a></p>
        <p class="muted">Urgencias 24h</p>
      </div>
      <div class="footer-col">
        <h4>Horario</h4>
        <p>Lun - Dom: 08:00 - 20:00</p>
      </div>
    </div>
    <div style="text-align:center; margin-top:16px; color:#cbd5e1; font-size:0.9rem">© <span id="yr"></span> Clínica Veterinaria Mis Mascotas — Diseñado por Alex</div>
  </footer>

  <script>
    // Feature-detection: add .no-js when JS disabled (CSS fallback)
    document.documentElement.classList.remove('no-js');

    // Set current year
    document.getElementById('yr').textContent = new Date().getFullYear();

    // Mobile menu aria toggle (improve accessibility)
    const navToggle = document.getElementById('nav-toggle');
    const mobileMenu = document.querySelector('.mobile-menu');
    if (navToggle && mobileMenu) {
      navToggle.addEventListener('change', () => {
        const open = navToggle.checked;
        mobileMenu.style.display = open ? 'block' : 'none';
        mobileMenu.setAttribute('aria-hidden', !open);
      });

      // Close mobile menu when clicking an internal anchor
      document.querySelectorAll('.mobile-menu a').forEach(a => {
        a.addEventListener('click', () => {
          navToggle.checked = false;
          mobileMenu.style.display = 'none';
          mobileMenu.setAttribute('aria-hidden', 'true');
        });
      });
    }

    // Header shadow on scroll
    const header = document.querySelector('header');
    const onScrollHeader = () => {
      if (window.scrollY > 20) header.classList.add('scrolled');
      else header.classList.remove('scrolled');
    };
    window.addEventListener('scroll', onScrollHeader, { passive: true });
    onScrollHeader();

    // SCROLL REVEAL for elements with class .card and .about-card and hero-image
    // Uses IntersectionObserver (JS puro, ligero)
    const revealSelector = '.card, .about-card, .hero-image';
    const revealElems = document.querySelectorAll(revealSelector);

    const revealOptions = {
      root: null,
      rootMargin: '0px 0px -8% 0px', // trigger a bit before element fully visible
      threshold: 0.12
    };

    const revealObserver = new IntersectionObserver((entries, observer) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          entry.target.classList.add('in-view');
          // if you want one-time reveal, unobserve after in-view:
          observer.unobserve(entry.target);
        }
      });
    }, revealOptions);

    revealElems.forEach(el => revealObserver.observe(el));

    // Add small pointer / keyboard accessibility for cards (keyboard focus)
    document.querySelectorAll('.card').forEach(card => {
      card.setAttribute('tabindex', '0');
      card.addEventListener('keydown', (e) => {
        if (e.key === 'Enter' || e.key === ' ') {
          // find first .btn-cta in card and focus/click
          const btn = card.querySelector('.btn-cta, .btn-ghost, a');
          if (btn) btn.click();
        }
      });
    });

    // Gentle hover for brand (for desktop only)
    const brand = document.querySelector('.brand');
    if (brand) {
      brand.addEventListener('mouseenter', () => brand.classList.add('halo'));
      brand.addEventListener('mouseleave', () => brand.classList.remove('halo'));
    }

    // Make CTAs pulse only initially for attention, then stop after a while
    const pulseBtns = document.querySelectorAll('.btn-cta.pulse');
    setTimeout(() => {
      pulseBtns.forEach(b => b.classList.remove('pulse'));
    }, 6000); // 6 seconds of initial pulse

    // Accessibility: ensure focus visible outlines
    document.addEventListener('keydown', (e) => {
      if (e.key === 'Tab') document.documentElement.classList.add('show-focus');
    });

    // If JS disabled fallback handled by .no-js class (CSS would show elements)
    // End of script
  </script>
</body>
</html>
