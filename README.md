<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Maqhoba's Fridge Repair — Fast, Reliable &amp; Affordable</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Sora:wght@300;400;600;700;800&family=Lora:ital,wght@0,400;0,600;1,400&display=swap" rel="stylesheet" />
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --navy:    #0a1f3c;
      --ocean:   #0f4c81;
      --azure:   #1976d2;
      --sky:     #42a5f5;
      --mist:    #bbdefb;
      --frost:   #e3f2fd;
      --ice:     #f0f7ff;
      --white:   #ffffff;
      --g100:    #f5f8fc;
      --g300:    #cfd8e3;
      --g500:    #607d8b;
      --g700:    #334155;
      --green:   #00c853;
      --radius:  14px;
      --sh-sm:   0 2px 10px rgba(10,31,60,.08);
      --sh-md:   0 8px 36px rgba(10,31,60,.14);
      --sh-lg:   0 24px 64px rgba(10,31,60,.2);
    }

    html { scroll-behavior: smooth; }

    body {
      font-family: 'Sora', sans-serif;
      color: var(--g700);
      background: var(--white);
      line-height: 1.65;
      overflow-x: hidden;
    }

    /* TOP STRIP */
    .top-strip {
      background: var(--navy);
      color: rgba(255,255,255,.8);
      font-size: .8rem;
      padding: .45rem 5%;
      display: flex;
      justify-content: space-between;
      align-items: center;
      flex-wrap: wrap;
      gap: .4rem;
    }
    .top-strip a { color: var(--sky); text-decoration: none; font-weight: 700; font-size: .88rem; }
    .top-strip a:hover { color: var(--white); }
    .strip-badge { display: flex; align-items: center; gap: .5rem; }
    .pulse-dot {
      width: 8px; height: 8px;
      background: var(--green);
      border-radius: 50%;
      animation: pulse 2s infinite;
    }
    @keyframes pulse {
      0%,100% { opacity:1; transform:scale(1); }
      50%      { opacity:.5; transform:scale(1.5); }
    }

    /* NAVBAR */
    nav {
      position: sticky; top: 0; z-index: 100;
      display: flex; align-items: center; justify-content: space-between;
      padding: 0 5%; height: 66px;
      background: rgba(255,255,255,.95);
      backdrop-filter: blur(14px);
      border-bottom: 1px solid rgba(207,216,227,.5);
      transition: box-shadow .3s;
    }
    nav.scrolled { box-shadow: var(--sh-md); }

    .nav-logo { display: flex; align-items: center; gap: .65rem; text-decoration: none; }
    .logo-icon {
      width: 40px; height: 40px;
      background: var(--azure); border-radius: 10px;
      display: flex; align-items: center; justify-content: center; font-size: 1.3rem;
    }
    .logo-text strong { display: block; font-size: .95rem; font-weight: 800; color: var(--navy); }
    .logo-text span { font-size: .7rem; color: var(--g500); font-weight: 400; letter-spacing: .04em; }

    .nav-links { display: flex; gap: 1.8rem; list-style: none; }
    .nav-links a {
      text-decoration: none; font-size: .88rem; font-weight: 600; color: var(--g700);
      position: relative; transition: color .25s;
    }
    .nav-links a::after {
      content: ''; position: absolute; bottom: -4px; left: 0;
      width: 0; height: 2px; background: var(--azure); border-radius: 2px; transition: width .3s;
    }
    .nav-links a:hover { color: var(--azure); }
    .nav-links a:hover::after { width: 100%; }
    .nav-phone {
      background: var(--azure); color: var(--white) !important;
      padding: .5rem 1.1rem; border-radius: 8px; font-weight: 700 !important;
      transition: background .2s, transform .2s !important;
    }
    .nav-phone:hover { background: var(--ocean) !important; transform: translateY(-1px); }
    .nav-phone::after { display: none !important; }

    .hamburger { display: none; flex-direction: column; gap: 5px; cursor: pointer; padding: 4px; }
    .hamburger span { display: block; width: 24px; height: 2.5px; background: var(--navy); border-radius: 2px; transition: all .3s; }
    .hamburger.open span:nth-child(1) { transform: translateY(7.5px) rotate(45deg); }
    .hamburger.open span:nth-child(2) { opacity: 0; }
    .hamburger.open span:nth-child(3) { transform: translateY(-7.5px) rotate(-45deg); }

    .mobile-menu {
      display: none; position: fixed; top: 66px; left: 0; right: 0;
      background: var(--white); padding: 1.5rem 5% 2rem;
      border-bottom: 1px solid var(--g300); box-shadow: var(--sh-md); z-index: 99;
    }
    .mobile-menu.open { display: block; animation: slideDown .25s ease; }
    .mobile-menu ul { list-style: none; display: flex; flex-direction: column; gap: 1rem; }
    .mobile-menu a { text-decoration: none; font-size: 1.05rem; font-weight: 600; color: var(--g700); transition: color .2s; }
    .mobile-menu a:hover { color: var(--azure); }
    .mobile-call {
      margin-top: 1.3rem;
      display: flex; align-items: center; gap: .6rem;
      background: var(--azure); color: var(--white);
      padding: .85rem 1.3rem; border-radius: 10px;
      text-decoration: none; font-weight: 700; font-size: 1rem;
    }
    @keyframes slideDown {
      from { opacity:0; transform:translateY(-8px); }
      to   { opacity:1; transform:translateY(0); }
    }

    /* HERO */
    .hero {
      background: linear-gradient(135deg, var(--navy) 0%, var(--ocean) 55%, #0d60a8 100%);
      padding: 80px 5% 70px;
      position: relative; overflow: hidden;
      min-height: 88vh; display: flex; align-items: center;
    }
    .hero::before {
      content: ''; position: absolute; inset: 0;
      background-image:
        linear-gradient(rgba(255,255,255,.03) 1px, transparent 1px),
        linear-gradient(90deg, rgba(255,255,255,.03) 1px, transparent 1px);
      background-size: 44px 44px;
    }
    .hero::after {
      content: ''; position: absolute; right: -5%; bottom: -10%;
      width: clamp(280px,45vw,600px); height: clamp(280px,45vw,600px);
      background: radial-gradient(circle, rgba(66,165,245,.22) 0%, transparent 70%);
      border-radius: 50%; pointer-events: none;
    }

    .hero-inner {
      position: relative; z-index: 1;
      max-width: 1160px; margin: 0 auto; width: 100%;
      display: grid; grid-template-columns: 1fr 1fr; gap: 4rem; align-items: center;
    }

    .hero-badge {
      display: inline-flex; align-items: center; gap: .5rem;
      background: rgba(66,165,245,.18); border: 1px solid rgba(66,165,245,.35);
      color: var(--sky); font-size: .75rem; font-weight: 700;
      letter-spacing: .1em; text-transform: uppercase;
      padding: .35rem .9rem; border-radius: 100px; margin-bottom: 1.3rem;
    }

    .hero h1 {
      font-size: clamp(2.2rem,5vw,3.6rem); font-weight: 800;
      color: var(--white); line-height: 1.1; margin-bottom: 1.1rem; letter-spacing: -.5px;
    }
    .hero h1 .hl { color: var(--sky); }

    .hero-sub {
      color: rgba(255,255,255,.75); font-size: 1.05rem; font-weight: 300;
      max-width: 460px; margin-bottom: 2rem;
    }

    .hero-actions { display: flex; gap: 1rem; flex-wrap: wrap; margin-bottom: 2.5rem; }

    .btn-call {
      display: inline-flex; align-items: center; gap: .6rem;
      background: var(--white); color: var(--navy); font-weight: 800; font-size: 1rem;
      padding: .9rem 1.8rem; border-radius: 10px; text-decoration: none;
      box-shadow: 0 4px 24px rgba(0,0,0,.25); transition: transform .2s, box-shadow .2s;
    }
    .btn-call:hover { transform: translateY(-2px); box-shadow: 0 8px 32px rgba(0,0,0,.32); }

    .btn-ghost {
      display: inline-flex; align-items: center; gap: .6rem;
      background: transparent; color: var(--white); font-weight: 600; font-size: .95rem;
      padding: .9rem 1.6rem; border-radius: 10px; text-decoration: none;
      border: 1.5px solid rgba(255,255,255,.4); transition: background .2s, border-color .2s;
    }
    .btn-ghost:hover { background: rgba(255,255,255,.1); border-color: rgba(255,255,255,.7); }

    .hero-trust { display: flex; gap: 1.5rem; flex-wrap: wrap; }
    .trust-pill { display: flex; align-items: center; gap: .45rem; font-size: .82rem; color: rgba(255,255,255,.7); font-weight: 500; }

    .hero-visual { position: relative; }
    .fridge-card {
      background: rgba(255,255,255,.09); border: 1px solid rgba(255,255,255,.16);
      backdrop-filter: blur(12px); border-radius: 20px; overflow: hidden;
      box-shadow: var(--sh-lg); animation: float 5s ease-in-out infinite;
    }
    @keyframes float {
      0%,100% { transform: translateY(0); }
      50%      { transform: translateY(-12px); }
    }
    .fridge-card img { width: 100%; height: 300px; object-fit: cover; display: block; }
    .fridge-card-body { padding: 1.4rem; }
    .fridge-card-body h3 { font-size: 1rem; font-weight: 700; color: var(--white); margin-bottom: .3rem; }
    .fridge-card-body p { font-size: .82rem; color: rgba(255,255,255,.6); }

    .floating-badge {
      position: absolute; top: -16px; right: -14px;
      background: var(--green); color: var(--white);
      font-size: .78rem; font-weight: 700;
      padding: .55rem .85rem; border-radius: 10px;
      box-shadow: 0 6px 20px rgba(0,200,83,.4); white-space: nowrap;
    }

    /* CALL BANNER */
    .call-banner { background: var(--azure); padding: 1.2rem 5%; text-align: center; }
    .call-banner a {
      display: inline-flex; align-items: center; gap: .7rem;
      color: var(--white); text-decoration: none; font-weight: 700; font-size: 1.05rem;
    }
    .call-banner a:hover { opacity: .88; }

    /* SECTIONS */
    section { padding: 80px 5%; }
    .container { max-width: 1160px; margin: 0 auto; }
    .section-label {
      display: inline-block; font-size: .72rem; font-weight: 700;
      letter-spacing: .14em; text-transform: uppercase; color: var(--azure); margin-bottom: .6rem;
    }
    .section-title {
      font-size: clamp(1.7rem,3.5vw,2.5rem); font-weight: 800; color: var(--navy);
      line-height: 1.2; margin-bottom: .9rem; letter-spacing: -.3px;
    }
    .section-sub { font-size: 1rem; color: var(--g500); font-weight: 300; max-width: 520px; }
    .text-center { text-align: center; }
    .text-center .section-sub { margin: 0 auto; }

    /* SERVICES */
    .services { background: var(--g100); }
    .services-grid { display: grid; grid-template-columns: repeat(3,1fr); gap: 1.4rem; margin-top: 3rem; }

    .svc-card {
      background: var(--white); border: 1px solid var(--g300);
      border-radius: var(--radius); padding: 2rem 1.8rem;
      transition: transform .3s, box-shadow .3s, border-color .3s;
      position: relative; overflow: hidden;
    }
    .svc-card::after {
      content: ''; position: absolute; top: 0; left: 0; right: 0; height: 3px;
      background: linear-gradient(90deg, var(--azure), var(--sky));
      transform: scaleX(0); transform-origin: left; transition: transform .35s;
    }
    .svc-card:hover { transform: translateY(-6px); box-shadow: var(--sh-md); border-color: var(--mist); }
    .svc-card:hover::after { transform: scaleX(1); }
    .svc-icon {
      width: 54px; height: 54px; background: var(--frost); border-radius: 12px;
      display: flex; align-items: center; justify-content: center; font-size: 1.6rem; margin-bottom: 1.2rem;
    }
    .svc-card h3 { font-size: 1.05rem; font-weight: 700; color: var(--navy); margin-bottom: .5rem; }
    .svc-card p { font-size: .88rem; color: var(--g500); line-height: 1.7; }

    /* WHY US */
    .why { background: var(--white); }
    .why-inner { display: grid; grid-template-columns: 1fr 1fr; gap: 5rem; align-items: center; }

    .why-img { position: relative; }
    .why-img img { width: 100%; height: 420px; object-fit: cover; border-radius: 18px; box-shadow: var(--sh-md); display: block; }
    .why-stat-card {
      position: absolute; bottom: -18px; left: -18px;
      background: var(--white); border: 1px solid var(--g300);
      border-radius: 14px; padding: 1.1rem 1.4rem; box-shadow: var(--sh-md); text-align: center;
    }
    .why-stat-card strong { display: block; font-family: 'Lora',serif; font-size: 2.2rem; color: var(--azure); line-height: 1; }
    .why-stat-card span { font-size: .78rem; color: var(--g500); }

    .why-text .section-sub { margin-bottom: 1.8rem; }
    .why-points { display: flex; flex-direction: column; gap: 1.1rem; margin-bottom: 2rem; }
    .why-point { display: flex; gap: 1rem; align-items: flex-start; }
    .why-point-icon {
      width: 44px; height: 44px; background: var(--frost); border-radius: 10px;
      display: flex; align-items: center; justify-content: center; font-size: 1.2rem; flex-shrink: 0;
    }
    .why-point h4 { font-size: .95rem; font-weight: 700; color: var(--navy); margin-bottom: .2rem; }
    .why-point p { font-size: .85rem; color: var(--g500); }

    /* BRANDS */
    .brands { background: var(--ice); padding: 50px 5%; }
    .brands-inner { max-width: 1160px; margin: 0 auto; text-align: center; }
    .brands-inner > p { font-size: .78rem; font-weight: 700; letter-spacing: .12em; text-transform: uppercase; color: var(--g500); margin-bottom: 1.5rem; }
    .brands-row { display: flex; flex-wrap: wrap; gap: 1rem 1.5rem; justify-content: center; align-items: center; }
    .brand-tag {
      background: var(--white); border: 1px solid var(--g300); border-radius: 8px;
      padding: .55rem 1.2rem; font-size: .88rem; font-weight: 700; color: var(--g500);
      transition: color .2s, border-color .2s;
    }
    .brand-tag:hover { color: var(--azure); border-color: var(--azure); }

    /* PROCESS */
    .process { background: var(--navy); }
    .process .section-label { color: var(--sky); }
    .process .section-title { color: var(--white); }
    .process .section-sub { color: rgba(255,255,255,.6); }

    .steps-grid {
      display: grid; grid-template-columns: repeat(4,1fr); gap: 1.5rem; margin-top: 3rem; position: relative;
    }
    .steps-grid::before {
      content: ''; position: absolute; top: 30px;
      left: calc(12.5% + 1rem); right: calc(12.5% + 1rem);
      height: 2px; background: linear-gradient(90deg, var(--azure), var(--sky));
    }
    .step { text-align: center; position: relative; z-index: 1; }
    .step-num {
      width: 60px; height: 60px; background: var(--azure); border-radius: 50%;
      display: flex; align-items: center; justify-content: center;
      font-size: 1.3rem; font-weight: 800; color: var(--white);
      margin: 0 auto 1rem; box-shadow: 0 0 0 8px rgba(255,255,255,.06);
    }
    .step h4 { font-size: 1rem; font-weight: 700; color: var(--white); margin-bottom: .4rem; }
    .step p { font-size: .84rem; color: rgba(255,255,255,.6); }

    /* TESTIMONIALS */
    .testimonials { background: var(--g100); }
    .testi-grid { display: grid; grid-template-columns: repeat(3,1fr); gap: 1.4rem; margin-top: 3rem; }
    .testi-card {
      background: var(--white); border: 1px solid var(--g300);
      border-radius: var(--radius); padding: 1.8rem; transition: box-shadow .3s;
    }
    .testi-card:hover { box-shadow: var(--sh-md); }
    .stars { color: #f5a623; font-size: .9rem; letter-spacing: 2px; margin-bottom: .9rem; }
    .testi-card blockquote {
      font-family: 'Lora',serif; font-style: italic; font-size: .93rem;
      color: var(--g700); line-height: 1.7; margin-bottom: 1.3rem;
    }
    .testi-author { display: flex; align-items: center; gap: .85rem; }
    .author-avatar { width: 44px; height: 44px; border-radius: 50%; object-fit: cover; border: 2px solid var(--mist); }
    .author-name { font-weight: 700; font-size: .88rem; color: var(--navy); }
    .author-loc { font-size: .77rem; color: var(--g500); }

    /* CONTACT */
    .contact { background: var(--frost); }
    .contact-inner { display: grid; grid-template-columns: 1fr 1.4fr; gap: 4rem; align-items: start; }

    .contact-info h3 { font-size: 1.45rem; font-weight: 800; color: var(--navy); margin-bottom: .9rem; }
    .contact-info > p { font-size: .92rem; color: var(--g500); margin-bottom: 2rem; }

    .cinfo-item { display: flex; align-items: center; gap: .85rem; margin-bottom: 1rem; font-size: .9rem; color: var(--g700); }
    .cinfo-icon {
      width: 42px; height: 42px; background: var(--white); border: 1px solid var(--g300);
      border-radius: 10px; display: flex; align-items: center; justify-content: center; font-size: 1.1rem; flex-shrink: 0;
    }

    .big-call-btn {
      display: flex; align-items: center; gap: .8rem;
      background: var(--azure); color: var(--white);
      padding: 1rem 1.6rem; border-radius: 12px; text-decoration: none;
      font-weight: 800; font-size: 1.1rem; margin-top: 1.5rem;
      transition: background .25s, transform .2s; box-shadow: 0 6px 20px rgba(25,118,210,.35);
    }
    .big-call-btn:hover { background: var(--ocean); transform: translateY(-2px); }

    .contact-form {
      background: var(--white); border: 1px solid var(--g300);
      border-radius: 18px; padding: 2.4rem; box-shadow: var(--sh-sm);
    }
    .contact-form h3 { font-size: 1.25rem; font-weight: 800; color: var(--navy); margin-bottom: 1.5rem; }

    .form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; }
    .form-group { display: flex; flex-direction: column; gap: .38rem; margin-bottom: 1rem; }
    .form-group label { font-size: .78rem; font-weight: 700; color: var(--g700); letter-spacing: .03em; }
    .form-group input, .form-group select, .form-group textarea {
      padding: .72rem 1rem; border: 1.5px solid var(--g300); border-radius: 9px;
      font-family: 'Sora',sans-serif; font-size: .88rem; color: var(--navy); background: var(--white);
      transition: border-color .2s, box-shadow .2s; outline: none; width: 100%;
    }
    .form-group input:focus, .form-group select:focus, .form-group textarea:focus {
      border-color: var(--azure); box-shadow: 0 0 0 3px rgba(25,118,210,.14);
    }
    .form-group textarea { resize: vertical; min-height: 110px; }
    .btn-submit {
      width: 100%; background: var(--azure); color: var(--white); border: none;
      padding: .95rem; border-radius: 10px; font-family: 'Sora',sans-serif;
      font-size: .98rem; font-weight: 700; cursor: pointer;
      transition: background .25s, transform .2s; margin-top: .3rem; letter-spacing: .02em;
    }
    .btn-submit:hover { background: var(--ocean); transform: translateY(-1px); }

    /* FOOTER */
    footer { background: var(--navy); color: rgba(255,255,255,.6); padding: 56px 5% 30px; }
    .footer-inner {
      max-width: 1160px; margin: 0 auto;
      display: grid; grid-template-columns: 1.8fr 1fr 1fr; gap: 3rem;
      padding-bottom: 2.5rem; border-bottom: 1px solid rgba(255,255,255,.1);
    }
    .footer-brand-logo {
      font-size: 1.1rem; font-weight: 800; color: var(--white);
      display: flex; align-items: center; gap: .6rem; text-decoration: none; margin-bottom: .9rem;
    }
    .footer-brand-logo .licon {
      width: 36px; height: 36px; background: var(--azure); border-radius: 8px;
      display: flex; align-items: center; justify-content: center; font-size: 1.1rem;
    }
    .footer-brand p { font-size: .86rem; line-height: 1.75; margin-bottom: 1.2rem; }
    .footer-phone { display: inline-flex; align-items: center; gap: .5rem; color: var(--sky); text-decoration: none; font-weight: 700; font-size: .95rem; }

    .footer-col h4 { font-weight: 700; font-size: .88rem; color: var(--white); margin-bottom: 1rem; letter-spacing: .04em; }
    .footer-col ul { list-style: none; display: flex; flex-direction: column; gap: .6rem; }
    .footer-col ul li a { text-decoration: none; font-size: .86rem; color: rgba(255,255,255,.5); transition: color .2s; }
    .footer-col ul li a:hover { color: var(--sky); }

    .footer-bottom {
      max-width: 1160px; margin: 1.8rem auto 0;
      display: flex; justify-content: space-between; align-items: center;
      font-size: .8rem; flex-wrap: wrap; gap: .5rem;
    }

    /* REVEAL */
    .reveal { opacity: 0; transform: translateY(26px); transition: opacity .65s ease, transform .65s ease; }
    .reveal.visible { opacity: 1; transform: translateY(0); }

    /* RESPONSIVE */
    @media (max-width: 1024px) {
      .services-grid { grid-template-columns: repeat(2,1fr); }
      .testi-grid { grid-template-columns: repeat(2,1fr); }
      .steps-grid { grid-template-columns: repeat(2,1fr); }
      .steps-grid::before { display: none; }
      .footer-inner { grid-template-columns: 1fr 1fr; }
    }
    @media (max-width: 768px) {
      .nav-links { display: none; }
      .hamburger { display: flex; }
      .hero-inner { grid-template-columns: 1fr; }
      .hero-visual { display: none; }
      .hero { min-height: auto; padding-top: 60px; }
      .why-inner { grid-template-columns: 1fr; }
      .why-stat-card { right: 10px; left: auto; bottom: 10px; }
      .services-grid, .testi-grid { grid-template-columns: 1fr; }
      .steps-grid { grid-template-columns: 1fr 1fr; }
      .contact-inner { grid-template-columns: 1fr; }
      .form-row { grid-template-columns: 1fr; }
      .footer-inner { grid-template-columns: 1fr; gap: 2rem; }
      .footer-bottom { flex-direction: column; text-align: center; }
    }
    @media (max-width: 480px) {
      .steps-grid { grid-template-columns: 1fr; }
      .hero-actions { flex-direction: column; }
      .btn-call, .btn-ghost { justify-content: center; text-align: center; }
      .hero-trust { flex-direction: column; gap: .75rem; }
      .top-strip { justify-content: center; text-align: center; }
    }
  </style>
</head>
<body>

<!-- TOP STRIP -->
<div class="top-strip">
  <div class="strip-badge">
    <div class="pulse-dot"></div>
    <span>Available Mon–Sat &middot; Same-day service in most areas</span>
  </div>
  <a href="tel:0824413796">&#128222; 082 441 37396</a>
</div>

<!-- NAVBAR -->
<nav id="navbar">
  <a href="#" class="nav-logo">
    <div class="logo-icon">&#10052;&#65039;</div>
    <div class="logo-text">
      <strong>Maqhoba's</strong>
      <span>Fridge Repair</span>
    </div>
  </a>
  <ul class="nav-links">
    <li><a href="#services">Services</a></li>
    <li><a href="#why-us">Why Us</a></li>
    <li><a href="#process">How It Works</a></li>
    <li><a href="#testimonials">Reviews</a></li>
    <li><a href="tel:0824413796" class="nav-phone">&#128222; Call Now</a></li>
  </ul>
  <div class="hamburger" id="hamburger">
    <span></span><span></span><span></span>
  </div>
</nav>

<!-- MOBILE MENU -->
<div class="mobile-menu" id="mobileMenu">
  <ul>
    <li><a href="#services">Services</a></li>
    <li><a href="#why-us">Why Us</a></li>
    <li><a href="#process">How It Works</a></li>
    <li><a href="#testimonials">Reviews</a></li>
    <li><a href="#contact">Book a Repair</a></li>
  </ul>
  <a href="tel:0824413796" class="mobile-call">&#128222;&nbsp; 082 441 37396 &mdash; Call Now</a>
</div>

<!-- HERO -->
<section class="hero" id="home">
  <div class="hero-inner">
    <div class="hero-text">
      <div class="hero-badge">&#9889; Fast Response &middot; Guaranteed Work</div>
      <h1>Your Fridge Fixed <span class="hl">Fast &amp; Right</span> &mdash; First Time</h1>
      <p class="hero-sub">Maqhoba's Fridge Repair specialises in all makes and models of refrigerators, freezers &amp; fridges. Honest pricing. No hidden surprises.</p>
      <div class="hero-actions">
        <a href="tel:0824413796" class="btn-call">&#128222; 082 441 37396</a>
        <a href="#services" class="btn-ghost">See Our Services &#8595;</a>
      </div>
      <div class="hero-trust">
        <div class="trust-pill"><span>&#9989;</span> All Brands Repaired</div>
        <div class="trust-pill"><span>&#128663;</span> We Come To You</div>
        <div class="trust-pill"><span>&#128176;</span> Affordable Rates</div>
      </div>
    </div>
    <div class="hero-visual">
      <div class="floating-badge">&#9989; Available Today</div>
      <div class="fridge-card">
        <img src="https://images.unsplash.com/photo-1556909114-f6e7ad7d3136?w=700&auto=format&fit=crop&q=80" alt="Fridge repair technician" />
        <div class="fridge-card-body">
          <h3>Professional Fridge Technician</h3>
          <p>Experienced repairs &middot; Quality parts &middot; Warranty on work</p>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- CALL BANNER -->
<div class="call-banner">
  <a href="tel:0824413796">
    <span>&#128222;</span> Fridge not cooling? Call Maqhoba now: <u>082 441 37396</u> &mdash; Fast same-day response!
  </a>
</div>

<!-- SERVICES -->
<section class="services" id="services">
  <div class="container">
    <div class="reveal">
      <span class="section-label">What We Fix</span>
      <h2 class="section-title">Complete Fridge &amp; Freezer<br>Repair Services</h2>
      <p class="section-sub">From a fridge that won't cool to a freezer making strange noises, we handle it all &mdash; quickly and affordably.</p>
    </div>
    <div class="services-grid">
      <div class="svc-card reveal">
        <div class="svc-icon">&#127777;&#65039;</div>
        <h3>Not Cooling Properly</h3>
        <p>Fridge too warm? We diagnose and fix cooling issues including compressor faults, refrigerant leaks, and thermostat problems.</p>
      </div>
      <div class="svc-card reveal">
        <div class="svc-icon">&#129398;</div>
        <h3>Freezer Not Freezing</h3>
        <p>If your freezer can't hold temperature, we'll track down the fault &mdash; whether it's the evaporator, fan motor, or defrost heater.</p>
      </div>
      <div class="svc-card reveal">
        <div class="svc-icon">&#128167;</div>
        <h3>Leaking Water</h3>
        <p>Water pooling inside or under your fridge? We fix blocked drains, door seal failures, and damaged water lines efficiently.</p>
      </div>
      <div class="svc-card reveal">
        <div class="svc-icon">&#128266;</div>
        <h3>Strange Noises</h3>
        <p>Clicking, buzzing, or rattling sounds? We identify and repair noisy fans, loose compressors, and worn-out mechanical parts.</p>
      </div>
      <div class="svc-card reveal">
        <div class="svc-icon">&#129532;</div>
        <h3>Door Seals &amp; Gaskets</h3>
        <p>Broken or worn door seals waste energy and ruin food. We replace gaskets on all fridge and freezer models quickly.</p>
      </div>
      <div class="svc-card reveal">
        <div class="svc-icon">&#9889;</div>
        <h3>Electrical &amp; Control Faults</h3>
        <p>Display issues, lights not working, or fridge not starting? We repair circuit boards, thermostats, and electrical components.</p>
      </div>
    </div>
  </div>
</section>

<!-- BRANDS -->
<div class="brands">
  <div class="brands-inner">
    <p>Brands We Service</p>
    <div class="brands-row">
      <div class="brand-tag">Samsung</div>
      <div class="brand-tag">LG</div>
      <div class="brand-tag">Whirlpool</div>
      <div class="brand-tag">Defy</div>
      <div class="brand-tag">Hisense</div>
      <div class="brand-tag">Bosch</div>
      <div class="brand-tag">Siemens</div>
      <div class="brand-tag">KIC</div>
      <div class="brand-tag">Liebherr</div>
      <div class="brand-tag">Electrolux</div>
      <div class="brand-tag">AEG</div>
      <div class="brand-tag">Zanussi</div>
      <div class="brand-tag">Kelvinator</div>
    </div>
  </div>
</div>

<!-- WHY US -->
<section class="why" id="why-us">
  <div class="container">
    <div class="why-inner">
      <div class="why-img reveal">
        <img src="https://images.unsplash.com/photo-1621905252507-b35492cc74b4?w=700&auto=format&fit=crop&q=80" alt="Technician repairing a refrigerator" />
        <div class="why-stat-card">
          <strong>500+</strong>
          <span>Fridges Repaired</span>
        </div>
      </div>
      <div class="why-text reveal">
        <span class="section-label">Why Choose Us</span>
        <h2 class="section-title">Trusted by Locals.<br>Known for Getting It Right.</h2>
        <p class="section-sub">Maqhoba has been repairing fridges across the community for years. Honest. Reliable. No-nonsense.</p>
        <div class="why-points">
          <div class="why-point">
            <div class="why-point-icon">&#128663;</div>
            <div>
              <h4>We Come To You</h4>
              <p>No need to move your fridge anywhere. We arrive at your home or business and fix it on the spot.</p>
            </div>
          </div>
          <div class="why-point">
            <div class="why-point-icon">&#128176;</div>
            <div>
              <h4>Transparent, Fair Pricing</h4>
              <p>We quote upfront with no hidden fees. You approve the price before any work begins.</p>
            </div>
          </div>
          <div class="why-point">
            <div class="why-point-icon">&#128295;</div>
            <div>
              <h4>Quality Parts &amp; Guaranteed Work</h4>
              <p>We use quality replacement parts and back our repairs with a service warranty.</p>
            </div>
          </div>
          <div class="why-point">
            <div class="why-point-icon">&#9889;</div>
            <div>
              <h4>Same-Day &amp; Emergency Repairs</h4>
              <p>A broken fridge is urgent. We offer same-day response so your food stays safe.</p>
            </div>
          </div>
        </div>
        <a href="tel:0824413796" class="big-call-btn">&#128222; Call 082 441 37396</a>
      </div>
    </div>
  </div>
</section>

<!-- HOW IT WORKS -->
<section class="process" id="process">
  <div class="container">
    <div class="reveal text-center">
      <span class="section-label">Simple Process</span>
      <h2 class="section-title">How It Works</h2>
      <p class="section-sub">Getting your fridge fixed is as easy as four simple steps. We take care of everything.</p>
    </div>
    <div class="steps-grid">
      <div class="step reveal">
        <div class="step-num">1</div>
        <h4>Call or Book</h4>
        <p>Call 082 441 37396 or fill in the booking form. Tell us the problem and your location.</p>
      </div>
      <div class="step reveal">
        <div class="step-num">2</div>
        <h4>We Arrive</h4>
        <p>Our technician comes to you at an agreed time &mdash; often the same day. No long waits.</p>
      </div>
      <div class="step reveal">
        <div class="step-num">3</div>
        <h4>Diagnose &amp; Quote</h4>
        <p>We assess the fault and give you a clear, honest quote before any work starts.</p>
      </div>
      <div class="step reveal">
        <div class="step-num">4</div>
        <h4>Fixed &amp; Done</h4>
        <p>We repair your fridge on the spot wherever possible. You're back up and running &mdash; fast.</p>
      </div>
    </div>
  </div>
</section>

<!-- TESTIMONIALS -->
<section class="testimonials" id="testimonials">
  <div class="container">
    <div class="reveal text-center">
      <span class="section-label">Customer Reviews</span>
      <h2 class="section-title">What Our Customers Say</h2>
      <p class="section-sub">Real feedback from real people we've helped right here in the community.</p>
    </div>
    <div class="testi-grid">
      <div class="testi-card reveal">
        <div class="stars">&#9733;&#9733;&#9733;&#9733;&#9733;</div>
        <blockquote>"My fridge stopped cooling on a Friday evening. Maqhoba came Saturday morning and had it working by noon. Affordable and professional &mdash; I highly recommend him!"</blockquote>
        <div class="testi-author">
          <img src="https://i.pravatar.cc/88?img=5" alt="Nompumelelo" class="author-avatar" />
          <div>
            <div class="author-name">Nompumelelo D.</div>
            <div class="author-loc">Soweto</div>
          </div>
        </div>
      </div>
      <div class="testi-card reveal">
        <div class="stars">&#9733;&#9733;&#9733;&#9733;&#9733;</div>
        <blockquote>"Honest guy. Told me exactly what was wrong, gave a fair price, fixed it quickly. My Samsung fridge is running perfectly now. Will call him again for sure."</blockquote>
        <div class="testi-author">
          <img src="https://i.pravatar.cc/88?img=15" alt="Thabo" class="author-avatar" />
          <div>
            <div class="author-name">Thabo M.</div>
            <div class="author-loc">Johannesburg</div>
          </div>
        </div>
      </div>
      <div class="testi-card reveal">
        <div class="stars">&#9733;&#9733;&#9733;&#9733;&#9733;</div>
        <blockquote>"We had a fridge leaking water for weeks. Maqhoba diagnosed it in 10 minutes and fixed it on the same visit. Excellent service at a very reasonable price!"</blockquote>
        <div class="testi-author">
          <img src="https://i.pravatar.cc/88?img=25" alt="Priya" class="author-avatar" />
          <div>
            <div class="author-name">Priya N.</div>
            <div class="author-loc">Midrand</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section class="contact" id="contact">
  <div class="container">
    <div class="contact-inner">
      <div class="contact-info reveal">
        <span class="section-label">Get In Touch</span>
        <h2 class="section-title">Book Your Repair Today</h2>
        <p>Call us directly for the fastest response, or fill in the form and we'll get back to you quickly.</p>
        <div class="cinfo-item">
          <div class="cinfo-icon">&#128222;</div>
          <div><strong>082 441 37396</strong><br><small style="color:var(--g500);">Call or WhatsApp</small></div>
        </div>
        <div class="cinfo-item">
          <div class="cinfo-icon">&#128336;</div>
          <span>Monday &ndash; Saturday: 7:00 AM &ndash; 7:00 PM</span>
        </div>
        <div class="cinfo-item">
          <div class="cinfo-icon">&#128663;</div>
          <span>Mobile service &mdash; we come to your location</span>
        </div>
        <div class="cinfo-item">
          <div class="cinfo-icon">&#9889;</div>
          <span>Same-day emergency repairs available</span>
        </div>
        <a href="tel:0824413796" class="big-call-btn">&#128222; Call 082 441 37396</a>
      </div>

      <div class="contact-form reveal">
        <h3>&#128203; Request a Repair Booking</h3>
        <div class="form-row">
          <div class="form-group">
            <label for="fname">Your Name</label>
            <input type="text" id="fname" placeholder="e.g. Sipho Dlamini" />
          </div>
          <div class="form-group">
            <label for="phone">Phone Number</label>
            <input type="tel" id="phone" placeholder="e.g. 071 234 5678" />
          </div>
        </div>
        <div class="form-group">
          <label for="area">Your Area / Location</label>
          <input type="text" id="area" placeholder="e.g. Soweto, Midrand, Johannesburg" />
        </div>
        <div class="form-group">
          <label for="brand">Fridge Brand &amp; Model (if known)</label>
          <input type="text" id="brand" placeholder="e.g. Samsung 400L Double Door" />
        </div>
        <div class="form-group">
          <label for="issue">Type of Problem</label>
          <select id="issue">
            <option value="">Select the issue...</option>
            <option>Not cooling / too warm</option>
            <option>Freezer not freezing</option>
            <option>Leaking water</option>
            <option>Making strange noises</option>
            <option>Not switching on</option>
            <option>Door seal / gasket problem</option>
            <option>Ice buildup</option>
            <option>Other problem</option>
          </select>
        </div>
        <div class="form-group">
          <label for="details">More Details (optional)</label>
          <textarea id="details" placeholder="Tell us anything else that might help, e.g. how long the problem has been happening..."></textarea>
        </div>
        <button class="btn-submit" id="submitBtn">&#128232; Send Booking Request</button>
      </div>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-inner">
    <div class="footer-brand">
      <a href="#" class="footer-brand-logo">
        <div class="licon">&#10052;&#65039;</div>
        Maqhoba's Fridge Repair
      </a>
      <p>Professional, affordable, and fast refrigerator repair services. We come to your home and get your fridge working again &mdash; right the first time.</p>
      <a href="tel:0824413796" class="footer-phone">&#128222; 082 441 37396</a>
    </div>
    <div class="footer-col">
      <h4>Services</h4>
      <ul>
        <li><a href="#services">Not Cooling Repairs</a></li>
        <li><a href="#services">Freezer Repairs</a></li>
        <li><a href="#services">Water Leak Repairs</a></li>
        <li><a href="#services">Noisy Fridge Fix</a></li>
        <li><a href="#services">Door Seal Replacement</a></li>
        <li><a href="#services">Electrical Faults</a></li>
      </ul>
    </div>
    <div class="footer-col">
      <h4>Quick Links</h4>
      <ul>
        <li><a href="#why-us">Why Choose Us</a></li>
        <li><a href="#process">How It Works</a></li>
        <li><a href="#testimonials">Customer Reviews</a></li>
        <li><a href="#contact">Book a Repair</a></li>
        <li><a href="tel:0824413796">Call Us Now</a></li>
      </ul>
    </div>
  </div>
  <div class="footer-bottom">
    <span>&copy; 2026 Maqhoba's Fridge Repair. All rights reserved.</span>
    <span>&#128222; <a href="tel:0824413796" style="color:var(--sky);text-decoration:none;">082 441 37396</a></span>
  </div>
</footer>

<script>
  // Smooth scroll
  document.querySelectorAll('a[href^="#"]').forEach(function(link) {
    link.addEventListener('click', function(e) {
      var href = link.getAttribute('href');
      if (href === '#') return;
      var target = document.querySelector(href);
      if (!target) return;
      e.preventDefault();
      window.scrollTo({ top: target.offsetTop - 70, behavior: 'smooth' });
      document.getElementById('mobileMenu').classList.remove('open');
      document.getElementById('hamburger').classList.remove('open');
    });
  });

  // Navbar shadow on scroll
  var navbar = document.getElementById('navbar');
  window.addEventListener('scroll', function() {
    navbar.classList.toggle('scrolled', window.scrollY > 10);
  });

  // Hamburger toggle
  var hamburger = document.getElementById('hamburger');
  var mobileMenu = document.getElementById('mobileMenu');
  hamburger.addEventListener('click', function() {
    hamburger.classList.toggle('open');
    mobileMenu.classList.toggle('open');
  });

  // Scroll reveal
  var observer = new IntersectionObserver(function(entries) {
    entries.forEach(function(entry, i) {
      if (entry.isIntersecting) {
        setTimeout(function() { entry.target.classList.add('visible'); }, i * 90);
        observer.unobserve(entry.target);
      }
    });
  }, { threshold: 0.1 });
  document.querySelectorAll('.reveal').forEach(function(el) { observer.observe(el); });

  // Form submission
  document.getElementById('submitBtn').addEventListener('click', function() {
    var name  = document.getElementById('fname').value.trim();
    var phone = document.getElementById('phone').value.trim();
    var area  = document.getElementById('area').value.trim();
    var issue = document.getElementById('issue').value;

    if (!name || !phone || !area || !issue) {
      alert('Please fill in your name, phone number, area, and the type of problem before sending.');
      return;
    }

    alert(
      'Thank you, ' + name + '! \n\n' +
      'Your repair request has been received.\n' +
      'Maqhoba will call you back on ' + phone + ' shortly to confirm your appointment.\n\n' +
      'For urgent repairs, call directly:\n' +
      '\uD83D\uDCDE 082 441 37396'
    );

    ['fname','phone','area','brand','issue','details'].forEach(function(id) {
      document.getElementById(id).value = '';
    });
  });
</script>

</body>
</html>
