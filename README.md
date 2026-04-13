<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<link rel="icon" type="image/x-icon" href="data:image/x-icon;base64,AAABAAEAEBAAAAAAIAD0AAAAFgAAAIlQTkcNChoKAAAADUlIRFIAAAAQAAAAEAgGAAAAH/P/YQAAALtJREFUeJxjZIACDh6h/wwkgB9f3jEyMDAwMJGjGVkPIzmakQETJZqpYgALIQViLW/h7Fc1wtR3AcUGYI0FsZa3C5G48TDGdPWdDFeuXGPYsGkzw4Y1KxnmLVhEmgF/+9UYTh49wPD//3+GkvIqBkVFBYQXxFreBsIwLue+ffuWoW/CJIbHT54wbNy0hYGBgYww+P79B8OPHz/hfLgX0GwOwOYFmkQjIwMDeZmJgQGSI5lgDHI0MzAwMAAA2kJIAqgU1oUAAAAASUVORK5CYII=">
<link rel="shortcut icon" type="image/x-icon" href="data:image/x-icon;base64,AAABAAEAEBAAAAAAIAD0AAAAFgAAAIlQTkcNChoKAAAADUlIRFIAAAAQAAAAEAgGAAAAH/P/YQAAALtJREFUeJxjZIACDh6h/wwkgB9f3jEyMDAwMJGjGVkPIzmakQETJZqpYgALIQViLW/h7Fc1wtR3AcUGYI0FsZa3C5G48TDGdPWdDFeuXGPYsGkzw4Y1KxnmLVhEmgF/+9UYTh49wPD//3+GkvIqBkVFBYQXxFreBsIwLue+ffuWoW/CJIbHT54wbNy0hYGBgYww+P79B8OPHz/hfLgX0GwOwOYFmkQjIwMDeZmJgQGSI5lgDHI0MzAwMAAA2kJIAqgU1oUAAAAASUVORK5CYII=">
<link rel="apple-touch-icon" href="data:image/x-icon;base64,AAABAAEAEBAAAAAAIAD0AAAAFgAAAIlQTkcNChoKAAAADUlIRFIAAAAQAAAAEAgGAAAAH/P/YQAAALtJREFUeJxjZIACDh6h/wwkgB9f3jEyMDAwMJGjGVkPIzmakQETJZqpYgALIQViLW/h7Fc1wtR3AcUGYI0FsZa3C5G48TDGdPWdDFeuXGPYsGkzw4Y1KxnmLVhEmgF/+9UYTh49wPD//3+GkvIqBkVFBYQXxFreBsIwLue+ffuWoW/CJIbHT54wbNy0hYGBgYww+P79B8OPHz/hfLgX0GwOwOYFmkQjIwMDeZmJgQGSI5lgDHI0MzAwMAAA2kJIAqgU1oUAAAAASUVORK5CYII=">
<title>Yuri Nossol – Marketing Digital & Sites</title>
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=DM+Sans:wght@300;400;500;700&display=swap" rel="stylesheet">
<style>
  :root {
    --blue: #1e90ff;
    --blue-dark: #0a5abf;
    --blue-glow: rgba(30,144,255,0.35);
    --black: #080c12;
    --dark: #0f1520;
    --card: #141c2b;
    --text: #e8eef8;
    --muted: #7a90b0;
    --white: #ffffff;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  html { scroll-behavior: smooth; }

  body {
    background: var(--black);
    color: var(--text);
    font-family: 'DM Sans', sans-serif;
    overflow-x: hidden;
  }

  /* ──── NOISE OVERLAY ──── */
  body::before {
    content: '';
    position: fixed; inset: 0;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.04'/%3E%3C/svg%3E");
    pointer-events: none;
    z-index: 0;
    opacity: .5;
  }

  /* ──── NAV ──── */
  nav {
    position: fixed; top: 0; width: 100%; z-index: 100;
    padding: 22px 48px;
    display: flex; justify-content: space-between; align-items: center;
    background: rgba(8,12,18,0.85);
    backdrop-filter: blur(12px);
    border-bottom: 1px solid rgba(30,144,255,0.12);
  }

  .logo { display: flex; align-items: center; }

  nav ul { list-style: none; display: flex; gap: 32px; }
  nav a { color: var(--muted); text-decoration: none; font-size: .9rem; font-weight: 500; transition: color .2s; }
  nav a:hover { color: var(--white); }

  .nav-cta {
    background: var(--blue);
    color: var(--white) !important;
    padding: 10px 22px;
    border-radius: 6px;
    font-weight: 600 !important;
    transition: background .2s, box-shadow .2s !important;
  }
  .nav-cta:hover { background: var(--blue-dark) !important; box-shadow: 0 0 20px var(--blue-glow); }

  /* ──── HERO ──── */
  .hero {
    min-height: 100vh;
    display: grid;
    grid-template-columns: 1fr 1fr;
    align-items: center;
    gap: 0;
    padding: 120px 80px 80px;
    position: relative;
    overflow: hidden;
  }

  .hero::after {
    content: '';
    position: absolute;
    right: -100px; top: 50%;
    transform: translateY(-50%);
    width: 600px; height: 600px;
    background: radial-gradient(circle, rgba(30,144,255,0.18) 0%, transparent 70%);
    pointer-events: none;
  }

  .hero-text { position: relative; z-index: 1; }

  .hero-badge {
    display: inline-block;
    background: rgba(30,144,255,0.12);
    border: 1px solid rgba(30,144,255,0.3);
    color: var(--blue);
    font-size: .75rem;
    font-weight: 600;
    letter-spacing: 2px;
    text-transform: uppercase;
    padding: 7px 16px;
    border-radius: 100px;
    margin-bottom: 28px;
    animation: fadeUp .6s ease both;
  }

  h1 {
    font-family: 'Bebas Neue', sans-serif;
    font-size: clamp(3rem, 6vw, 5.5rem);
    line-height: .95;
    letter-spacing: 2px;
    color: var(--white);
    animation: fadeUp .6s .1s ease both;
  }

  h1 span { color: var(--blue); }

  .hero-sub {
    margin-top: 24px;
    font-size: 1.1rem;
    color: var(--muted);
    line-height: 1.7;
    max-width: 440px;
    animation: fadeUp .6s .2s ease both;
  }

  .hero-btns {
    margin-top: 40px;
    display: flex; gap: 16px;
    animation: fadeUp .6s .3s ease both;
  }

  .btn-primary {
    background: var(--blue);
    color: var(--white);
    padding: 14px 32px;
    border-radius: 8px;
    font-weight: 700;
    text-decoration: none;
    font-size: .95rem;
    transition: box-shadow .2s, transform .2s;
  }
  .btn-primary:hover { box-shadow: 0 0 28px var(--blue-glow); transform: translateY(-2px); }

  .btn-ghost {
    border: 1px solid rgba(255,255,255,0.15);
    color: var(--text);
    padding: 14px 32px;
    border-radius: 8px;
    font-weight: 500;
    text-decoration: none;
    font-size: .95rem;
    transition: border-color .2s, background .2s;
  }
  .btn-ghost:hover { border-color: var(--blue); background: rgba(30,144,255,0.08); }

  /* ──── HERO PHOTO ──── */
  .hero-photo {
    position: relative;
    z-index: 1;
    display: flex;
    justify-content: center;
    animation: fadeIn .8s .2s ease both;
  }

  .photo-wrap {
    position: relative;
    width: 380px; height: 440px;
  }

  .photo-wrap::before {
    content: '';
    position: absolute;
    inset: -2px;
    border-radius: 24px;
    background: linear-gradient(135deg, var(--blue), transparent 60%);
    z-index: 0;
  }

  .photo-wrap img {
    width: 100%; height: 100%;
    object-fit: cover;
    border-radius: 22px;
    position: relative; z-index: 1;
    display: block;
  }

  .photo-badge {
    position: absolute;
    bottom: -20px; left: -20px;
    background: var(--card);
    border: 1px solid rgba(30,144,255,0.3);
    border-radius: 14px;
    padding: 14px 20px;
    z-index: 2;
    backdrop-filter: blur(8px);
  }

  .photo-badge .num { font-family: 'Bebas Neue', sans-serif; font-size: 1.8rem; color: var(--blue); line-height: 1; }
  .photo-badge .label { font-size: .72rem; color: var(--muted); letter-spacing: 1px; text-transform: uppercase; margin-top: 2px; }

  .photo-badge2 {
    position: absolute;
    top: -16px; right: -16px;
    background: var(--blue);
    border-radius: 12px;
    padding: 12px 18px;
    z-index: 2;
  }

  .photo-badge2 .num { font-family: 'Bebas Neue', sans-serif; font-size: 1.6rem; color: var(--white); line-height: 1; }
  .photo-badge2 .label { font-size: .7rem; color: rgba(255,255,255,0.75); letter-spacing: 1px; text-transform: uppercase; margin-top: 2px; }

  /* ──── STATS BAR ──── */
  .stats {
    background: var(--card);
    border-top: 1px solid rgba(255,255,255,0.05);
    border-bottom: 1px solid rgba(255,255,255,0.05);
    padding: 32px 80px;
    display: flex;
    justify-content: space-around;
    align-items: center;
    position: relative; z-index: 1;
  }

  .stat { text-align: center; }
  .stat .n { font-family: 'Bebas Neue', sans-serif; font-size: 2.4rem; color: var(--blue); letter-spacing: 2px; }
  .stat .l { font-size: .8rem; color: var(--muted); text-transform: uppercase; letter-spacing: 1.5px; margin-top: 4px; }
  .stat-div { width: 1px; height: 40px; background: rgba(255,255,255,0.07); }

  /* ──── SECTION COMMONS ──── */
  section { padding: 100px 80px; position: relative; z-index: 1; }

  .section-tag {
    display: inline-block;
    color: var(--blue);
    font-size: .75rem;
    font-weight: 700;
    letter-spacing: 3px;
    text-transform: uppercase;
    margin-bottom: 14px;
  }

  h2 {
    font-family: 'Bebas Neue', sans-serif;
    font-size: clamp(2.2rem, 4vw, 3.5rem);
    letter-spacing: 2px;
    color: var(--white);
    line-height: 1;
  }

  /* ──── SOBRE ──── */
  .sobre { background: var(--dark); }

  .sobre-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 80px;
    align-items: start;
    margin-top: 60px;
  }

  .sobre-text p {
    color: var(--muted);
    line-height: 1.8;
    font-size: 1rem;
    margin-bottom: 20px;
  }

  .sobre-text p strong { color: var(--text); }

  .xp-list { display: flex; flex-direction: column; gap: 20px; }

  .xp-item {
    background: var(--card);
    border: 1px solid rgba(255,255,255,0.06);
    border-radius: 14px;
    padding: 22px 24px;
    border-left: 3px solid var(--blue);
    transition: transform .2s;
  }
  .xp-item:hover { transform: translateX(6px); }
  .xp-item .empresa { font-weight: 700; color: var(--white); font-size: .95rem; }
  .xp-item .cargo { color: var(--blue); font-size: .82rem; font-weight: 600; margin: 4px 0; }
  .xp-item .periodo { color: var(--muted); font-size: .78rem; }

  /* ──── SERVIÇOS ──── */
  .servicos { background: var(--black); }

  .services-header { max-width: 580px; margin-bottom: 60px; }
  .services-header p { color: var(--muted); margin-top: 16px; line-height: 1.7; }

  .services-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 24px;
  }

  .service-card {
    background: var(--card);
    border: 1px solid rgba(255,255,255,0.06);
    border-radius: 20px;
    padding: 36px 30px;
    transition: transform .25s, border-color .25s, box-shadow .25s;
    cursor: default;
  }
  .service-card:hover {
    transform: translateY(-8px);
    border-color: rgba(30,144,255,0.4);
    box-shadow: 0 20px 60px rgba(30,144,255,0.12);
  }

  .service-icon {
    width: 52px; height: 52px;
    border-radius: 14px;
    background: rgba(30,144,255,0.12);
    display: flex; align-items: center; justify-content: center;
    font-size: 1.5rem;
    margin-bottom: 24px;
  }

  .service-card h3 {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 1.5rem;
    letter-spacing: 1.5px;
    color: var(--white);
    margin-bottom: 14px;
  }

  .service-card p { color: var(--muted); line-height: 1.7; font-size: .9rem; }

  .service-tags {
    margin-top: 20px;
    display: flex; flex-wrap: wrap; gap: 8px;
  }

  .tag {
    background: rgba(30,144,255,0.1);
    border: 1px solid rgba(30,144,255,0.2);
    color: var(--blue);
    font-size: .7rem;
    font-weight: 600;
    padding: 4px 12px;
    border-radius: 100px;
    text-transform: uppercase;
    letter-spacing: 1px;
  }

  /* ──── CTA ──── */
  .cta-section {
    background: linear-gradient(135deg, #0a1628 0%, #0f1e3a 50%, #0a1628 100%);
    border-top: 1px solid rgba(30,144,255,0.15);
    border-bottom: 1px solid rgba(30,144,255,0.15);
    text-align: center;
    padding: 100px 80px;
  }

  .cta-section h2 { font-size: clamp(2.5rem, 5vw, 4rem); }
  .cta-section p { color: var(--muted); margin: 20px auto 40px; max-width: 500px; line-height: 1.7; }
  .cta-wrap { display: flex; gap: 16px; justify-content: center; flex-wrap: wrap; }

  .btn-whatsapp {
    background: #25d366;
    color: var(--white);
    padding: 16px 36px;
    border-radius: 8px;
    font-weight: 700;
    text-decoration: none;
    font-size: 1rem;
    transition: transform .2s, box-shadow .2s;
    display: inline-flex; align-items: center; gap: 10px;
  }
  @keyframes bounce {
    0%, 100% { transform: translateY(0); }
    30%       { transform: translateY(-10px); }
    60%       { transform: translateY(-5px); }
  }

  .btn-whatsapp {
    animation: bounce 1.8s ease infinite;
  }
  .btn-whatsapp:hover {
    animation: none;
    transform: translateY(-2px);
    box-shadow: 0 0 28px rgba(37,211,102,0.5);
  }

  /* ──── FOOTER ──── */
  footer {
    background: var(--dark);
    padding: 40px 80px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    border-top: 1px solid rgba(255,255,255,0.05);
  }

  footer .logo { display: flex; align-items: center; }
  footer p { color: var(--muted); font-size: .85rem; }

  /* ──── ANIMATIONS ──── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(24px); }
    to { opacity: 1; transform: translateY(0); }
  }

  @keyframes slideInLeft {
    from { opacity: 0; transform: translateX(-60px) skewX(-6deg); }
    to   { opacity: 1; transform: translateX(0)     skewX(0deg); }
  }


  .word-anim {
    display: inline-block;
    opacity: 0;
    animation: slideInLeft .6s cubic-bezier(.22,.68,0,1.2) both;
  }
  @keyframes fadeIn {
    from { opacity: 0; }
    to { opacity: 1; }
  }

  /* ──── HAMBURGER ──── */
  .hamburger {
    display: none;
    flex-direction: column;
    gap: 5px;
    cursor: pointer;
    padding: 4px;
    background: none; border: none;
  }
  .hamburger span {
    display: block; width: 24px; height: 2px;
    background: var(--text);
    border-radius: 2px;
    transition: transform .3s, opacity .3s;
  }
  .hamburger.open span:nth-child(1) { transform: translateY(7px) rotate(45deg); }
  .hamburger.open span:nth-child(2) { opacity: 0; }
  .hamburger.open span:nth-child(3) { transform: translateY(-7px) rotate(-45deg); }

  .mobile-menu {
    display: none;
    position: fixed;
    top: 65px; left: 0; right: 0;
    background: rgba(8,12,18,0.97);
    backdrop-filter: blur(16px);
    border-bottom: 1px solid rgba(30,144,255,0.15);
    padding: 24px;
    flex-direction: column;
    gap: 0;
    z-index: 99;
  }
  .mobile-menu.open { display: flex; }
  .mobile-menu a {
    color: var(--text); text-decoration: none;
    font-size: 1.1rem; font-weight: 500;
    padding: 16px 0;
    border-bottom: 1px solid rgba(255,255,255,0.05);
    display: block;
  }
  .mobile-menu a:last-child {
    border-bottom: none;
    color: var(--blue);
    font-weight: 700;
    margin-top: 8px;
  }

  /* ──── PORTFOLIO ──── */
  .portfolio { background: var(--black); }
  .portfolio-grid { display: grid; grid-template-columns: repeat(2, 1fr); gap: 28px; margin-top: 50px; }
  .portfolio-card {
    background: var(--card);
    border: 1px solid rgba(255,255,255,0.06);
    border-radius: 20px;
    overflow: hidden;
    transition: transform .25s, border-color .25s, box-shadow .25s;
  }
  .portfolio-card:hover {
    transform: translateY(-6px);
    border-color: rgba(30,144,255,0.4);
    box-shadow: 0 20px 60px rgba(30,144,255,0.12);
  }
  .portfolio-preview {
    background: linear-gradient(135deg, #0a1a0a 0%, #0d2a10 50%, #0a1a0a 100%);
    height: 200px;
    display: flex; align-items: center; justify-content: center;
    position: relative; overflow: hidden;
    border-bottom: 1px solid rgba(255,255,255,0.05);
  }
  .portfolio-preview::before {
    content: '';
    position: absolute; inset: 0;
    background: url("data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' fill-rule='evenodd'%3E%3Cg fill='%2322c55e' fill-opacity='0.04'%3E%3Cpath d='M36 34v-4h-2v4h-4v2h4v4h2v-4h4v-2h-4zm0-30V0h-2v4h-4v2h4v4h2V6h4V4h-4zM6 34v-4H4v4H0v2h4v4h2v-4h4v-2H6zM6 4V0H4v4H0v2h4v4h2V6h4V4H6z'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E");
  }
  .preview-browser {
    width: 85%; background: rgba(255,255,255,0.04);
    border: 1px solid rgba(255,255,255,0.08);
    border-radius: 10px; overflow: hidden;
    box-shadow: 0 8px 32px rgba(0,0,0,0.5);
    position: relative; z-index: 1;
  }
  .preview-bar {
    background: rgba(255,255,255,0.06);
    padding: 8px 12px;
    display: flex; align-items: center; gap: 8px;
  }
  .preview-dots { display: flex; gap: 5px; }
  .preview-dots span { width: 8px; height: 8px; border-radius: 50%; }
  .preview-dots span:nth-child(1) { background: #ff5f57; }
  .preview-dots span:nth-child(2) { background: #ffbd2e; }
  .preview-dots span:nth-child(3) { background: #28ca41; }
  .preview-url {
    background: rgba(255,255,255,0.05); border-radius: 4px;
    padding: 3px 10px; font-size: .65rem;
    color: var(--muted); flex: 1;
  }
  .preview-content { padding: 14px; }
  .preview-content .pline { height: 7px; border-radius: 4px; background: rgba(255,255,255,0.08); margin-bottom: 7px; }
  .preview-content .pline.green { background: rgba(34,197,94,0.4); width: 60%; }
  .preview-content .pline.short { width: 45%; }
  .preview-content .pline.shorter { width: 30%; }

  .portfolio-info { padding: 24px 26px; }
  .portfolio-info h3 { font-family: 'Bebas Neue', sans-serif; font-size: 1.4rem; letter-spacing: 1.5px; color: var(--white); margin-bottom: 8px; }
  .portfolio-info p { color: var(--muted); font-size: .88rem; line-height: 1.65; margin-bottom: 16px; }
  .portfolio-tags { display: flex; flex-wrap: wrap; gap: 8px; margin-bottom: 18px; }
  .portfolio-link {
    display: inline-flex; align-items: center; gap: 7px;
    color: var(--blue); font-size: .85rem; font-weight: 600;
    text-decoration: none; transition: gap .2s;
  }
  .portfolio-link:hover { gap: 11px; }
  .portfolio-link svg { width: 14px; height: 14px; }

  /* ──── CERT SECTION ──── */
  .certs { background: var(--dark); }
  .cert-grid { display: grid; grid-template-columns: repeat(2, 1fr); gap: 20px; margin-top: 50px; }
  .cert-card {
    background: var(--card);
    border: 1px solid rgba(255,255,255,0.06);
    border-radius: 16px;
    padding: 28px 24px;
    display: flex; align-items: flex-start; gap: 18px;
    transition: transform .2s, border-color .2s;
  }
  .cert-card:hover { transform: translateY(-4px); border-color: rgba(30,144,255,0.35); }
  .cert-logo {
    width: 48px; height: 48px; border-radius: 12px;
    display: flex; align-items: center; justify-content: center;
    font-size: 1.4rem; flex-shrink: 0;
  }
  .cert-card h4 { font-weight: 700; color: var(--white); font-size: .95rem; margin-bottom: 6px; }
  .cert-card p { color: var(--muted); font-size: .82rem; line-height: 1.5; }
  .cert-badge {
    display: inline-block;
    background: rgba(30,144,255,0.12);
    border: 1px solid rgba(30,144,255,0.25);
    color: var(--blue);
    font-size: .68rem; font-weight: 700;
    padding: 3px 10px; border-radius: 100px;
    text-transform: uppercase; letter-spacing: 1px;
    margin-top: 10px;
  }

  /* ──── RESPONSIVE ──── */
  @media (max-width: 900px) {
    nav { padding: 16px 20px; }
    nav ul { display: none; }
    .hamburger { display: flex; }

    .hero {
      grid-template-columns: 1fr;
      padding: 90px 20px 50px;
      text-align: center;
      gap: 0;
    }
    .hero::after { display: none; }
    .hero-btns { justify-content: center; flex-wrap: wrap; }
    .hero-sub { margin-left: auto; margin-right: auto; font-size: 1rem; }

    .hero-photo { margin-top: 44px; justify-content: center; }
    .photo-wrap { width: 260px; height: 310px; }
    .photo-badge { bottom: -16px; left: -10px; padding: 10px 14px; }
    .photo-badge .num { font-size: 1.4rem; }
    .photo-badge2 { top: -12px; right: -10px; padding: 10px 14px; }
    .photo-badge2 .num { font-size: 1.3rem; }

    .stats {
      padding: 28px 16px;
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 24px;
    }
    .stat-div { display: none; }
    .stat .n { font-size: 1.8rem; }
    .stat .l { font-size: .7rem; }

    section { padding: 60px 20px; }
    .sobre-grid { grid-template-columns: 1fr; gap: 36px; }
    .services-grid { grid-template-columns: 1fr; }
    .cert-grid { grid-template-columns: 1fr; }
    .portfolio-grid { grid-template-columns: 1fr; }

    .cta-section { padding: 70px 20px; }
    .cta-wrap { flex-direction: column; align-items: center; }
    .btn-whatsapp, .btn-ghost { width: 100%; justify-content: center; text-align: center; }

    footer { flex-direction: column; gap: 12px; text-align: center; padding: 28px 20px; }
  }

  @media (max-width: 480px) {
    h1 { font-size: 2.8rem; }
    .photo-wrap { width: 220px; height: 265px; }
    .stats { grid-template-columns: 1fr 1fr; gap: 20px; padding: 24px 16px; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="logo"><svg height="36" viewBox="0 0 320 60" xmlns="http://www.w3.org/2000/svg">
  <defs>
    <linearGradient id="barG" x1="0%" y1="100%" x2="100%" y2="0%">
      <stop offset="0%" stop-color="#0a5abf"/>
      <stop offset="100%" stop-color="#1e90ff"/>
    </linearGradient>
    <linearGradient id="dG" x1="0%" y1="0%" x2="100%" y2="0%">
      <stop offset="0%" stop-color="#1e90ff"/>
      <stop offset="100%" stop-color="#38bfff"/>
    </linearGradient>
  </defs>
  <!-- Bars -->
  <rect x="0"  y="34" width="10" height="18" rx="2" fill="#1e90ff" opacity="0.25"/>
  <rect x="13" y="24" width="10" height="28" rx="2" fill="#1e90ff" opacity="0.55"/>
  <rect x="26" y="8"  width="10" height="44" rx="2" fill="url(#barG)"/>
  <!-- Arrow -->
  <polyline points="31,5 31,0 36,5" fill="none" stroke="#38bfff" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"/>
  <!-- Divider -->
  <rect x="44" y="6" width="1.5" height="42" rx="1" fill="#1e90ff" opacity="0.3"/>
  <!-- YN -->
  <text x="52" y="44" font-family="Arial Black, Arial, sans-serif" font-weight="900" font-size="38" fill="#ffffff" letter-spacing="-1">YN</text>
  <!-- DIGITAL -->
  <text x="54" y="57" font-family="Arial Black, Arial, sans-serif" font-weight="900" font-size="14" fill="url(#dG)" letter-spacing="5">DIGITAL</text>
</svg></div>
  <ul>
    <li><a href="#sobre">Sobre</a></li>
    <li><a href="#servicos">Serviços</a></li>
    <li><a href="#portfolio">Portfólio</a></li>
    <li><a href="#certificados">Certificados</a></li>
    <li><a href="#contato" class="nav-cta">Falar comigo</a></li>
  </ul>
  <button class="hamburger" id="ham" onclick="toggleMenu()" aria-label="Menu">
    <span></span><span></span><span></span>
  </button>
</nav>
<div class="mobile-menu" id="mobileMenu">
  <a href="#sobre" onclick="closeMenu()">Sobre</a>
  <a href="#servicos" onclick="closeMenu()">Serviços</a>
  <a href="#portfolio" onclick="closeMenu()">Portfólio</a>
  <a href="#certificados" onclick="closeMenu()">Certificados</a>
  <a href="#contato" onclick="closeMenu()">Falar comigo →</a>
</div>

<!-- HERO -->
<section class="hero">
  <div class="hero-text">
    <div class="hero-badge">📍 Joinville, SC · Disponível para projetos</div>
    <h1>
      <span class="word-anim" style="animation-delay:.1s">RESULTADOS</span><br>
      <span class="word-anim" style="animation-delay:.25s">REAIS COM</span><br>
      <span class="word-anim" style="animation-delay:.4s; color:var(--blue)">MARKETING</span><br>
      <span class="word-anim" style="animation-delay:.55s">DIGITAL</span>
    </h1>
    <p class="hero-sub">
      Criação de sites profissionais, tráfego pago estratégico e marketing digital que gera leads qualificados — tudo com quem vive isso na prática.
    </p>
    <div class="hero-btns">
      <a href="#contato" class="btn-primary">Solicitar orçamento</a>
      <a href="#servicos" class="btn-ghost">Ver serviços</a>
    </div>
  </div>

  <div class="hero-photo">
    <div class="photo-wrap">
      <div class="photo-badge">
        <div class="num">+2 ANOS</div>
        <div class="label">Experiência real</div>
      </div>
      <div class="photo-badge2">
        <div class="num">100%</div>
        <div class="label">Comprometido</div>
      </div>
      <img src="data:image/jpeg;base64,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" alt="Yuri Nossol">
    </div>
  </div>
</section>

<!-- STATS -->
<div class="stats">
  <div class="stat">
    <div class="n">+2 ANOS</div>
    <div class="l">em Tráfego Pago</div>
  </div>
  <div class="stat-div"></div>
  <div class="stat">
    <div class="n">B2B</div>
    <div class="l">Geração de Leads</div>
  </div>
  <div class="stat-div"></div>
  <div class="stat">
    <div class="n">CRM</div>
    <div class="l">Gestão de Clientes</div>
  </div>
  <div class="stat-div"></div>
  <div class="stat">
    <div class="n">100%</div>
    <div class="l">Focado em Resultados</div>
  </div>
</div>

<!-- SOBRE -->
<section class="sobre" id="sobre">
  <div class="section-tag">— Quem sou eu</div>
  <h2>EXPERIÊNCIA QUE<br>FAZ DIFERENÇA</h2>

  <div class="sobre-grid">
    <div class="sobre-text">
      <p>
        Sou <strong>Yuri Nossol</strong>, profissional de marketing digital e tecnologia de Joinville – SC. Atualmente atuo como <strong>Aprendiz Administrativo na Conta Azul</strong>, uma das maiores empresas de software de gestão financeira do Brasil.
      </p>
      <p>
        No meu dia a dia, trabalho diretamente com <strong>mídias pagas, geração e qualificação de leads, suporte em CRM</strong> e apoio à equipe comercial — experiência real em ambiente corporativo de alto nível.
      </p>
      <p>
        Sou estudante de <strong>Engenharia de Software</strong> e possuo formação Técnica em Administração e certificação profissionalizante em CRM, o que me dá uma visão única que une marketing, negócios e tecnologia.
      </p>
      <p>
        Meu objetivo é simples: <strong>ajudar negócios a crescerem online</strong> com estratégias que funcionam de verdade.
      </p>
    </div>

    <div class="xp-list">
      <div class="xp-item">
        <div class="empresa">Conta Azul Software LTDA</div>
        <div class="cargo">Aprendiz Administrativo · Marketing</div>
        <div class="periodo">06/2024 – Atual</div>
      </div>
      <div class="xp-item">
        <div class="empresa">Mabra Máquinas e Equipamentos</div>
        <div class="cargo">Menor Aprendiz · Qualidade & Processos</div>
        <div class="periodo">01/2023 – 04/2024</div>
      </div>
      <div class="xp-item" style="border-left-color: #7a90b0;">
        <div class="empresa">Engenharia de Software – Cursando</div>
        <div class="cargo">1º Semestre · Foco em Desenvolvimento</div>
        <div class="periodo">2025 – Em andamento</div>
      </div>
    </div>
  </div>
</section>

<!-- SERVIÇOS -->
<section class="servicos" id="servicos">
  <div class="services-header">
    <div class="section-tag">— O que eu ofereço</div>
    <h2>SERVIÇOS QUE<br>GERAM RESULTADO</h2>
    <p>Soluções digitais completas para negócios que querem crescer com consistência e estratégia.</p>
  </div>

  <div class="services-grid">
    <div class="service-card">
      <div class="service-icon">🌐</div>
      <h3>Criação de Sites</h3>
      <p>Sites profissionais, modernos e otimizados para converter visitantes em clientes. Do design à publicação, tudo pensado para o seu negócio.</p>
      <div class="service-tags">
        <span class="tag">Landing Page</span>
        <span class="tag">Site Institucional</span>
        <span class="tag">Responsivo</span>
        <span class="tag">SEO</span>
      </div>
    </div>

    <div class="service-card">
      <div class="service-icon">🎯</div>
      <h3>Tráfego Pago</h3>
      <p>Gestão de campanhas no Google Ads e Meta Ads com foco em geração de leads qualificados e retorno real sobre o investimento.</p>
      <div class="service-tags">
        <span class="tag">Google Ads</span>
        <span class="tag">Meta Ads</span>
        <span class="tag">Geração de Leads</span>
        <span class="tag">ROI</span>
      </div>
    </div>

    <div class="service-card">
      <div class="service-icon">📈</div>
      <h3>Marketing Digital</h3>
      <p>Estratégia completa de presença digital: produção de conteúdo, otimização de perfis, automações e gestão de CRM para crescer de forma consistente.</p>
      <div class="service-tags">
        <span class="tag">Conteúdo</span>
        <span class="tag">CRM</span>
        <span class="tag">Automação</span>
        <span class="tag">Estratégia</span>
      </div>
    </div>
  </div>
</section>

<!-- PORTFOLIO -->
<section class="portfolio" id="portfolio">
  <div class="section-tag">— Portfólio</div>
  <h2>SITES QUE EU<br><span style="color:var(--blue)">CRIEI DO ZERO</span></h2>

  <div class="portfolio-grid">
    <div class="portfolio-card">
      <div class="portfolio-preview">
        <div class="preview-browser">
          <div class="preview-bar">
            <div class="preview-dots">
              <span></span><span></span><span></span>
            </div>
            <div class="preview-url">madeireirarossi.netlify.app</div>
          </div>
          <div class="preview-content">
            <div class="pline green"></div>
            <div class="pline"></div>
            <div class="pline short"></div>
            <div class="pline"></div>
            <div class="pline shorter"></div>
          </div>
        </div>
      </div>
      <div class="portfolio-info">
        <h3>Madeireira Rossi</h3>
        <p>Site institucional criado do zero para madeireira de Joinville – SC, especializada em Cambará e Eucalipto. Landing page completa com catálogo de produtos, seção de serviços, localização integrada e botão direto para WhatsApp.</p>
        <div class="portfolio-tags">
          <span class="tag">HTML & CSS</span>
          <span class="tag">Landing Page</span>
          <span class="tag">WhatsApp CTA</span>
          <span class="tag">Mobile First</span>
          <span class="tag">Joinville – SC</span>
        </div>
        <a href="https://madeireirarossi.netlify.app" target="_blank" class="portfolio-link">
          Ver site ao vivo
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"/><polyline points="15 3 21 3 21 9"/><line x1="10" y1="14" x2="21" y2="3"/></svg>
        </a>
      </div>
    </div>

    <div class="portfolio-card" style="border-style: dashed; border-color: rgba(30,144,255,0.2); display:flex; flex-direction:column; align-items:center; justify-content:center; padding: 48px 32px; text-align:center; min-height: 340px;">
      <div style="font-size:2.5rem; margin-bottom:16px; opacity:.4">+</div>
      <h3 style="font-family:'Bebas Neue',sans-serif; font-size:1.3rem; letter-spacing:1.5px; color:var(--muted); margin-bottom:10px;">SEU PROJETO AQUI</h3>
      <p style="color:var(--muted); font-size:.88rem; line-height:1.6; max-width:240px;">Quer um site profissional para o seu negócio? Entre em contato e vamos criar juntos.</p>
      <a href="#contato" style="margin-top:20px; color:var(--blue); font-size:.85rem; font-weight:600; text-decoration:none;">Solicitar orçamento →</a>
    </div>
  </div>
</section>

<!-- CERTIFICADOS -->
<section class="certs" id="certificados">
  <div class="section-tag">— Certificações</div>
  <h2>CERTIFICADO PELAS<br><span style="color:var(--blue)">MAIORES PLATAFORMAS</span></h2>
  <div class="cert-grid">
    <div class="cert-card">
      <div class="cert-logo" style="background:rgba(66,133,244,0.08)"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 48 48" width="32" height="32">
  <path fill="#EA4335" d="M24 9.5c3.54 0 6.71 1.22 9.21 3.6l6.85-6.85C35.9 2.38 30.47 0 24 0 14.62 0 6.51 5.38 2.56 13.22l7.98 6.19C12.43 13.72 17.74 9.5 24 9.5z"/>
  <path fill="#4285F4" d="M46.98 24.55c0-1.57-.15-3.09-.38-4.55H24v9.02h12.94c-.58 2.96-2.26 5.48-4.78 7.18l7.73 6c4.51-4.18 7.09-10.36 7.09-17.65z"/>
  <path fill="#FBBC05" d="M10.53 28.59c-.48-1.45-.76-2.99-.76-4.59s.27-3.14.76-4.59l-7.98-6.19C.92 16.46 0 20.12 0 24c0 3.88.92 7.54 2.56 10.78l7.97-6.19z"/>
  <path fill="#34A853" d="M24 48c6.48 0 11.93-2.13 15.89-5.81l-7.73-6c-2.15 1.45-4.92 2.3-8.16 2.3-6.26 0-11.57-4.22-13.47-9.91l-7.98 6.19C6.51 42.62 14.62 48 24 48z"/>
  <path fill="none" d="M0 0h48v48H0z"/>
</svg></div>
      <div>
        <h4>Google Ads</h4>
        <p>Certificação oficial em campanhas de pesquisa, display e geração de leads no Google Ads.</p>
        <span class="cert-badge">✓ Certificado</span>
      </div>
    </div>
    <div class="cert-card">
      <div class="cert-logo" style="background:rgba(0,129,251,0.08)"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 48 48" width="32" height="32">
  <path d="M24 12c-4.5 0-7.5 2.4-10.2 6.8-1.8 2.9-4.3 8.2-4.3 8.2S7 31 7 33.2C7 37 9.2 40 13 40c3 0 5-1.5 8-5.5l3-4.5 3 4.5c3 4 5 5.5 8 5.5 3.8 0 6-3 6-6.8 0-2.2-2.5-6.2-2.5-6.2s-2.5-5.3-4.3-8.2C31.5 14.4 28.5 12 24 12z" fill="url(#metaGrad)"/>
  <defs>
    <linearGradient id="metaGrad" x1="7" y1="12" x2="41" y2="40" gradientUnits="userSpaceOnUse">
      <stop offset="0%" stop-color="#0081FB"/>
      <stop offset="100%" stop-color="#0064E0"/>
    </linearGradient>
  </defs>
</svg></div>
      <div>
        <h4>Meta Ads</h4>
        <p>Certificação em campanhas no Facebook e Instagram Ads com foco em conversão e alcance.</p>
        <span class="cert-badge">✓ Certificado</span>
      </div>
    </div>
  </div>
</section>

<!-- CTA -->
<section class="cta-section" id="contato">
  <div class="section-tag">— Vamos conversar</div>
  <h2>PRONTO PARA<br><span style="color:var(--blue)">CRESCER ONLINE?</span></h2>
  <p>Entre em contato agora e descubra como posso ajudar seu negócio a se destacar no digital.</p>
  <div class="cta-wrap">
    <a href="https://wa.me/5547991699755?text=Olá%20Yuri!%20Vi%20seu%20site%20e%20gostaria%20de%20conversar%20sobre%20marketing%20digital." class="btn-whatsapp" target="_blank">
      <svg width="22" height="22" viewBox="0 0 24 24" fill="currentColor"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413Z"/></svg>
      Falar no WhatsApp
    </a>
    <a href="/cdn-cgi/l/email-protection#58212d2a3136372b2b3734183f35393134763b3735" class="btn-ghost">
      ✉️ <span class="__cf_email__" data-cfemail="631a16110a0d0c10100c0f23040e020a0f4d000c0e">[email&#160;protected]</span>
    </a>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="logo"><svg height="36" viewBox="0 0 320 60" xmlns="http://www.w3.org/2000/svg">
  <defs>
    <linearGradient id="barG" x1="0%" y1="100%" x2="100%" y2="0%">
      <stop offset="0%" stop-color="#0a5abf"/>
      <stop offset="100%" stop-color="#1e90ff"/>
    </linearGradient>
    <linearGradient id="dG" x1="0%" y1="0%" x2="100%" y2="0%">
      <stop offset="0%" stop-color="#1e90ff"/>
      <stop offset="100%" stop-color="#38bfff"/>
    </linearGradient>
  </defs>
  <!-- Bars -->
  <rect x="0"  y="34" width="10" height="18" rx="2" fill="#1e90ff" opacity="0.25"/>
  <rect x="13" y="24" width="10" height="28" rx="2" fill="#1e90ff" opacity="0.55"/>
  <rect x="26" y="8"  width="10" height="44" rx="2" fill="url(#barG)"/>
  <!-- Arrow -->
  <polyline points="31,5 31,0 36,5" fill="none" stroke="#38bfff" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"/>
  <!-- Divider -->
  <rect x="44" y="6" width="1.5" height="42" rx="1" fill="#1e90ff" opacity="0.3"/>
  <!-- YN -->
  <text x="52" y="44" font-family="Arial Black, Arial, sans-serif" font-weight="900" font-size="38" fill="#ffffff" letter-spacing="-1">YN</text>
  <!-- DIGITAL -->
  <text x="54" y="57" font-family="Arial Black, Arial, sans-serif" font-weight="900" font-size="14" fill="url(#dG)" letter-spacing="5">DIGITAL</text>
</svg></div>
  <p>© 2026 · Joinville, SC · Marketing Digital & Sites</p>
  <p style="color: #3a4f6e; font-size: .8rem;">(47) 99169-9755</p>
</footer>

<script data-cfasync="false" src="/cdn-cgi/scripts/5c5dd728/cloudflare-static/email-decode.min.js"></script><script>
function toggleMenu() {
  var ham = document.getElementById('ham');
  var menu = document.getElementById('mobileMenu')
