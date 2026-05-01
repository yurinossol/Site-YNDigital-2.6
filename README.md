<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Yuri Nossol Alves — Dev & Marketing Digital</title>

<!-- Segurança -->
<meta http-equiv="X-Content-Type-Options" content="nosniff">
<meta http-equiv="X-Frame-Options" content="DENY">
<meta http-equiv="Referrer-Policy" content="strict-origin-when-cross-origin">
<meta http-equiv="Permissions-Policy" content="camera=(), microphone=(), geolocation=()">
<meta http-equiv="Content-Security-Policy" content="
  default-src 'self';
  style-src 'self' 'unsafe-inline' https://fonts.googleapis.com;
  font-src 'self' https://fonts.gstatic.com;
  img-src 'self' data:;
  script-src 'self' 'unsafe-inline';
  connect-src 'none';
  frame-ancestors 'none';
  base-uri 'self';
  form-action 'none';
">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=DM+Mono:ital,wght@0,300;0,400;0,500;1,300&family=Sora:wght@300;400;500;600;700&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #080810;
    --bg2: #0d0d1a;
    --bg3: #111122;
    --accent: #f0c040;
    --accent2: #e07b20;
    --text: #e8e8f0;
    --muted: #7070a0;
    --border: rgba(240,192,64,0.15);
    --grad: linear-gradient(135deg, #f0c040, #e07b20);
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  html { scroll-behavior: smooth; }

  body {
    font-family: 'Sora', sans-serif;
    background: var(--bg);
    color: var(--text);
    overflow-x: hidden;
    cursor: none;
  }

  /* CUSTOM CURSOR */
  .cursor {
    width: 10px; height: 10px;
    background: var(--accent);
    border-radius: 50%;
    position: fixed;
    top: 0; left: 0;
    pointer-events: none;
    z-index: 9999;
    transition: transform 0.15s ease;
    mix-blend-mode: difference;
  }
  .cursor-ring {
    width: 38px; height: 38px;
    border: 1.5px solid rgba(240,192,64,0.5);
    border-radius: 50%;
    position: fixed;
    top: 0; left: 0;
    pointer-events: none;
    z-index: 9998;
    transition: all 0.08s ease;
  }

  /* NOISE OVERLAY */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.04'/%3E%3C/svg%3E");
    pointer-events: none;
    z-index: 1000;
    opacity: 0.5;
  }

  /* NAV */
  nav {
    position: fixed;
    top: 0; left: 0; right: 0;
    z-index: 500;
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 20px 60px;
    border-bottom: 1px solid transparent;
    transition: all 0.4s;
  }
  nav.scrolled {
    background: rgba(8,8,16,0.92);
    backdrop-filter: blur(20px);
    border-bottom-color: var(--border);
  }
  .nav-logo {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 1.6rem;
    letter-spacing: 0.05em;
    color: var(--text);
    text-decoration: none;
  }
  .nav-logo span { color: var(--accent); }
  .nav-links { display: flex; gap: 36px; list-style: none; }
  .nav-links a {
    font-family: 'DM Mono', monospace;
    font-size: 0.75rem;
    letter-spacing: 0.1em;
    color: var(--muted);
    text-decoration: none;
    text-transform: uppercase;
    transition: color 0.3s;
  }
  .nav-links a:hover { color: var(--accent); }
  .nav-cta {
    font-family: 'DM Mono', monospace;
    font-size: 0.75rem;
    letter-spacing: 0.1em;
    color: var(--bg);
    background: var(--accent);
    padding: 10px 22px;
    text-decoration: none;
    text-transform: uppercase;
    transition: opacity 0.3s;
  }
  .nav-cta:hover { opacity: 0.85; }

  /* HERO */
  .hero {
    min-height: 100vh;
    display: grid;
    place-items: center;
    padding: 120px 60px 60px;
    position: relative;
    overflow: hidden;
  }
  .hero-grid-bg {
    position: absolute;
    inset: 0;
    background-image:
      linear-gradient(rgba(240,192,64,0.04) 1px, transparent 1px),
      linear-gradient(90deg, rgba(240,192,64,0.04) 1px, transparent 1px);
    background-size: 60px 60px;
    mask-image: radial-gradient(ellipse 80% 80% at 50% 50%, black 40%, transparent 100%);
  }
  .hero-glow {
    position: absolute;
    width: 700px; height: 700px;
    background: radial-gradient(circle, rgba(240,192,64,0.07) 0%, transparent 70%);
    border-radius: 50%;
    top: 50%; left: 50%;
    transform: translate(-50%, -50%);
    pointer-events: none;
  }
  .hero-inner {
    position: relative;
    text-align: center;
    max-width: 900px;
  }
  .hero-badge {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    font-family: 'DM Mono', monospace;
    font-size: 0.7rem;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--accent);
    border: 1px solid rgba(240,192,64,0.3);
    padding: 6px 16px;
    margin-bottom: 32px;
    animation: fadeUp 0.8s ease both;
  }
  .hero-badge::before {
    content: '';
    width: 6px; height: 6px;
    background: var(--accent);
    border-radius: 50%;
    animation: pulse 2s ease infinite;
  }
  @keyframes pulse { 0%,100%{opacity:1} 50%{opacity:0.3} }

  .hero-name {
    font-family: 'Bebas Neue', sans-serif;
    font-size: clamp(4rem, 12vw, 10rem);
    line-height: 0.9;
    letter-spacing: 0.02em;
    margin-bottom: 8px;
    animation: fadeUp 0.8s 0.1s ease both;
  }
  .hero-name .line1 { display: block; color: var(--text); }
  .hero-name .line2 { display: block; color: var(--accent); }

  .hero-roles {
    font-family: 'DM Mono', monospace;
    font-size: 0.85rem;
    color: var(--muted);
    letter-spacing: 0.12em;
    text-transform: uppercase;
    margin: 24px 0 48px;
    animation: fadeUp 0.8s 0.2s ease both;
  }
  .hero-roles span {
    color: var(--accent2);
    padding: 0 12px;
  }

  .hero-desc {
    font-size: 1.05rem;
    line-height: 1.8;
    color: rgba(232,232,240,0.65);
    max-width: 560px;
    margin: 0 auto 48px;
    animation: fadeUp 0.8s 0.3s ease both;
  }

  .hero-btns {
    display: flex;
    gap: 16px;
    justify-content: center;
    flex-wrap: wrap;
    animation: fadeUp 0.8s 0.4s ease both;
  }
  .btn-primary {
    display: inline-block;
    font-family: 'DM Mono', monospace;
    font-size: 0.75rem;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: var(--bg);
    background: var(--grad);
    padding: 16px 36px;
    text-decoration: none;
    position: relative;
    overflow: hidden;
    transition: transform 0.3s;
  }
  .btn-primary:hover { transform: translateY(-2px); }
  .btn-outline {
    display: inline-block;
    font-family: 'DM Mono', monospace;
    font-size: 0.75rem;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: var(--text);
    border: 1px solid var(--border);
    padding: 16px 36px;
    text-decoration: none;
    transition: border-color 0.3s, color 0.3s;
  }
  .btn-outline:hover { border-color: var(--accent); color: var(--accent); }

  .hero-stats {
    display: flex;
    justify-content: center;
    gap: 64px;
    margin-top: 80px;
    padding-top: 48px;
    border-top: 1px solid var(--border);
    animation: fadeUp 0.8s 0.5s ease both;
  }
  .stat-num {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 2.8rem;
    color: var(--accent);
    display: block;
    line-height: 1;
  }
  .stat-label {
    font-family: 'DM Mono', monospace;
    font-size: 0.65rem;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--muted);
    display: block;
    margin-top: 6px;
  }

  @keyframes fadeUp {
    from { opacity:0; transform:translateY(30px); }
    to { opacity:1; transform:translateY(0); }
  }

  /* SECTION COMMON */
  section { padding: 120px 60px; }
  .section-tag {
    font-family: 'DM Mono', monospace;
    font-size: 0.7rem;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 16px;
    display: flex;
    align-items: center;
    gap: 12px;
  }
  .section-tag::before {
    content: '';
    height: 1px;
    width: 40px;
    background: var(--accent);
    flex-shrink: 0;
  }
  .section-title {
    font-family: 'Bebas Neue', sans-serif;
    font-size: clamp(2.5rem, 5vw, 4.5rem);
    line-height: 1;
    letter-spacing: 0.02em;
    margin-bottom: 20px;
  }

  /* SOBRE */
  .sobre { background: var(--bg2); }
  .sobre-grid {
    display: grid;
    grid-template-columns: 1fr 1.2fr;
    gap: 80px;
    align-items: center;
    max-width: 1200px;
    margin: 0 auto;
  }
  .sobre-photo-wrap {
    position: relative;
  }
  .sobre-photo-frame {
    position: relative;
    display: inline-block;
  }
  .sobre-photo-frame::before {
    content: '';
    position: absolute;
    inset: -12px -12px 12px 12px;
    border: 1px solid rgba(240,192,64,0.3);
    pointer-events: none;
  }
  .sobre-photo-frame::after {
    content: 'YNA';
    font-family: 'Bebas Neue', sans-serif;
    font-size: 0.8rem;
    letter-spacing: 0.2em;
    color: var(--accent);
    position: absolute;
    bottom: -32px;
    right: 0;
  }
  .sobre-photo-frame img {
    width: 100%;
    max-width: 380px;
    display: block;
    filter: grayscale(20%);
    aspect-ratio: 3/4;
    object-fit: cover;
  }
  .sobre-photo-placeholder {
    width: 100%;
    max-width: 380px;
    aspect-ratio: 3/4;
    background: var(--bg3);
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: 'Bebas Neue', sans-serif;
    font-size: 5rem;
    color: var(--accent);
    letter-spacing: 0.05em;
    border: 1px solid var(--border);
  }
  .sobre-content p {
    font-size: 1rem;
    line-height: 1.9;
    color: rgba(232,232,240,0.7);
    margin-bottom: 20px;
  }
  .sobre-content p strong { color: var(--text); font-weight: 600; }
  .sobre-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    margin-top: 32px;
  }
  .tag {
    font-family: 'DM Mono', monospace;
    font-size: 0.72rem;
    letter-spacing: 0.08em;
    color: var(--accent);
    border: 1px solid rgba(240,192,64,0.25);
    padding: 6px 14px;
    background: rgba(240,192,64,0.05);
  }
  .loc-badge {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    font-family: 'DM Mono', monospace;
    font-size: 0.72rem;
    color: var(--muted);
    margin-bottom: 20px;
  }

  /* SERVIÇOS */
  .servicos { background: var(--bg); }
  .servicos-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 2px;
    margin-top: 64px;
    max-width: 1200px;
    margin-left: auto;
    margin-right: auto;
  }
  .servico-card {
    background: var(--bg2);
    padding: 48px 40px;
    position: relative;
    overflow: hidden;
    transition: background 0.3s;
    cursor: none;
  }
  .servico-card::after {
    content: '';
    position: absolute;
    bottom: 0; left: 0; right: 0;
    height: 2px;
    background: var(--grad);
    transform: scaleX(0);
    transform-origin: left;
    transition: transform 0.4s ease;
  }
  .servico-card:hover::after { transform: scaleX(1); }
  .servico-card:hover { background: var(--bg3); }
  .servico-icon {
    font-size: 2rem;
    margin-bottom: 24px;
    display: block;
  }
  .servico-num {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 0.8rem;
    letter-spacing: 0.15em;
    color: rgba(240,192,64,0.3);
    display: block;
    margin-bottom: 12px;
  }
  .servico-title {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 1.8rem;
    letter-spacing: 0.03em;
    margin-bottom: 16px;
  }
  .servico-desc {
    font-size: 0.9rem;
    line-height: 1.7;
    color: rgba(232,232,240,0.55);
  }
  .servico-list {
    list-style: none;
    margin-top: 20px;
  }
  .servico-list li {
    font-family: 'DM Mono', monospace;
    font-size: 0.72rem;
    color: var(--muted);
    padding: 6px 0;
    border-bottom: 1px solid rgba(240,192,64,0.06);
    display: flex;
    align-items: center;
    gap: 8px;
  }
  .servico-list li::before {
    content: '→';
    color: var(--accent);
    font-size: 0.7rem;
  }

  /* SKILLS */
  .skills { background: var(--bg2); }
  .skills-inner {
    max-width: 1200px;
    margin: 0 auto;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 80px;
    align-items: start;
  }
  .skills-list { margin-top: 64px; }
  .skill-item { margin-bottom: 28px; }
  .skill-top {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 8px;
  }
  .skill-name {
    font-family: 'DM Mono', monospace;
    font-size: 0.78rem;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    color: var(--text);
  }
  .skill-pct {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 1.1rem;
    color: var(--accent);
  }
  .skill-bar {
    height: 3px;
    background: rgba(240,192,64,0.1);
    position: relative;
    overflow: hidden;
  }
  .skill-fill {
    height: 100%;
    background: var(--grad);
    transform: scaleX(0);
    transform-origin: left;
    transition: transform 1.2s cubic-bezier(0.16,1,0.3,1);
  }
  .skill-fill.animated { transform: scaleX(1); }

  .tech-cloud {
    margin-top: 64px;
    display: flex;
    flex-direction: column;
    gap: 20px;
  }
  .tech-row {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
  }
  .tech-chip {
    font-family: 'DM Mono', monospace;
    font-size: 0.7rem;
    letter-spacing: 0.06em;
    text-transform: uppercase;
    padding: 8px 16px;
    border: 1px solid rgba(240,192,64,0.15);
    color: var(--muted);
    background: rgba(240,192,64,0.03);
    transition: all 0.3s;
  }
  .tech-chip:hover {
    border-color: var(--accent);
    color: var(--accent);
    background: rgba(240,192,64,0.08);
  }
  .tech-cat {
    font-family: 'DM Mono', monospace;
    font-size: 0.65rem;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: rgba(240,192,64,0.4);
    margin-bottom: -4px;
  }

  /* PROJETOS */
  .projetos { background: var(--bg); }
  .projetos-inner { max-width: 1200px; margin: 0 auto; }
  .projetos-header {
    display: flex;
    justify-content: space-between;
    align-items: flex-end;
    margin-bottom: 64px;
  }
  .projetos-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 2px;
  }
  .projeto-card {
    background: var(--bg2);
    padding: 40px;
    position: relative;
    overflow: hidden;
    transition: background 0.3s;
    display: flex;
    flex-direction: column;
  }
  .projeto-card:hover { background: var(--bg3); }
  .projeto-card.featured {
    grid-column: span 2;
  }
  .projeto-num {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 0.75rem;
    letter-spacing: 0.2em;
    color: rgba(240,192,64,0.25);
    margin-bottom: 20px;
  }
  .projeto-emoji {
    font-size: 2.5rem;
    margin-bottom: 20px;
    display: block;
  }
  .projeto-title {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 2rem;
    letter-spacing: 0.02em;
    margin-bottom: 12px;
  }
  .projeto-desc {
    font-size: 0.88rem;
    line-height: 1.7;
    color: rgba(232,232,240,0.55);
    flex: 1;
    margin-bottom: 24px;
  }
  .projeto-techs {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
    margin-bottom: 24px;
  }
  .tech-tag {
    font-family: 'DM Mono', monospace;
    font-size: 0.65rem;
    letter-spacing: 0.06em;
    color: var(--accent);
    background: rgba(240,192,64,0.08);
    padding: 4px 10px;
    border: 1px solid rgba(240,192,64,0.15);
  }
  .projeto-link {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    font-family: 'DM Mono', monospace;
    font-size: 0.72rem;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--accent);
    text-decoration: none;
    border-bottom: 1px solid rgba(240,192,64,0.3);
    padding-bottom: 4px;
    width: fit-content;
    transition: gap 0.3s;
  }
  .projeto-link:hover { gap: 14px; }

  /* CERTIFICADOS */
  .certificados { background: var(--bg2); }
  .certs-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 2px;
    margin-top: 64px;
    max-width: 1200px;
    margin-left: auto;
    margin-right: auto;
  }
  .cert-card {
    background: var(--bg3);
    padding: 32px 28px;
    border-top: 2px solid transparent;
    transition: border-color 0.3s;
  }
  .cert-card:hover { border-top-color: var(--accent); }
  .cert-platform {
    font-family: 'DM Mono', monospace;
    font-size: 0.65rem;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--accent2);
    margin-bottom: 12px;
    display: block;
  }
  .cert-name {
    font-size: 0.9rem;
    font-weight: 600;
    line-height: 1.4;
    margin-bottom: 8px;
  }
  .cert-year {
    font-family: 'DM Mono', monospace;
    font-size: 0.65rem;
    color: var(--muted);
  }

  /* CONTATO */
  .contato { background: var(--bg); overflow: hidden; position: relative; }
  .contato-marquee {
    font-family: 'Bebas Neue', sans-serif;
    font-size: clamp(4rem, 8vw, 8rem);
    letter-spacing: 0.02em;
    color: rgba(240,192,64,0.06);
    white-space: nowrap;
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    animation: marquee 20s linear infinite;
    pointer-events: none;
  }
  @keyframes marquee {
    from { transform: translateY(-50%) translateX(0); }
    to { transform: translateY(-50%) translateX(-50%); }
  }
  .contato-inner {
    max-width: 1200px;
    margin: 0 auto;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 80px;
    align-items: center;
    position: relative;
  }
  .contato-left .section-title { font-size: clamp(3rem, 6vw, 6rem); }
  .contato-sub {
    font-size: 1rem;
    line-height: 1.8;
    color: rgba(232,232,240,0.55);
    margin-top: 20px;
  }
  .contato-links { margin-top: 48px; display: flex; flex-direction: column; gap: 0; }
  .contato-link {
    display: flex;
    align-items: center;
    gap: 16px;
    text-decoration: none;
    color: var(--text);
    padding: 20px 0;
    border-bottom: 1px solid var(--border);
    transition: color 0.3s;
    font-size: 0.95rem;
  }
  .contato-link:first-child { border-top: 1px solid var(--border); }
  .contato-link:hover { color: var(--accent); }
  .contato-link-icon {
    font-family: 'DM Mono', monospace;
    font-size: 0.65rem;
    letter-spacing: 0.12em;
    color: var(--accent);
    text-transform: uppercase;
    width: 60px;
    flex-shrink: 0;
  }

  .contato-form {
    background: var(--bg2);
    padding: 48px;
    border: 1px solid var(--border);
  }
  .form-group { margin-bottom: 20px; }
  .form-group label {
    font-family: 'DM Mono', monospace;
    font-size: 0.65rem;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--muted);
    display: block;
    margin-bottom: 8px;
  }
  .form-group input,
  .form-group textarea,
  .form-group select {
    width: 100%;
    background: var(--bg3);
    border: 1px solid rgba(240,192,64,0.12);
    color: var(--text);
    font-family: 'Sora', sans-serif;
    font-size: 0.9rem;
    padding: 14px 18px;
    outline: none;
    transition: border-color 0.3s;
    appearance: none;
  }
  .form-group input:focus,
  .form-group textarea:focus,
  .form-group select:focus { border-color: var(--accent); }
  .form-group textarea { resize: vertical; min-height: 100px; }
  .form-group select option { background: var(--bg3); }
  .btn-submit {
    width: 100%;
    background: var(--grad);
    color: var(--bg);
    border: none;
    font-family: 'Bebas Neue', sans-serif;
    font-size: 1.2rem;
    letter-spacing: 0.15em;
    padding: 18px;
    cursor: none;
    transition: opacity 0.3s;
  }
  .btn-submit:hover { opacity: 0.85; }

  /* FOOTER */
  footer {
    background: var(--bg2);
    border-top: 1px solid var(--border);
    padding: 40px 60px;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
  .footer-logo {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 1.4rem;
    letter-spacing: 0.05em;
  }
  .footer-logo span { color: var(--accent); }
  .footer-copy {
    font-family: 'DM Mono', monospace;
    font-size: 0.65rem;
    letter-spacing: 0.1em;
    color: var(--muted);
  }
  .footer-social { display: flex; gap: 20px; }
  .footer-social a {
    font-family: 'DM Mono', monospace;
    font-size: 0.65rem;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--muted);
    text-decoration: none;
    transition: color 0.3s;
  }
  .footer-social a:hover { color: var(--accent); }

  /* DIVIDER */
  .divider {
    height: 1px;
    background: var(--border);
    max-width: 1200px;
    margin: 0 auto;
  }

  /* SCROLL REVEAL */
  .reveal {
    opacity: 0;
    transform: translateY(40px);
    transition: opacity 0.8s ease, transform 0.8s ease;
  }
  .reveal.visible {
    opacity: 1;
    transform: translateY(0);
  }
  .reveal-delay-1 { transition-delay: 0.1s; }
  .reveal-delay-2 { transition-delay: 0.2s; }
  .reveal-delay-3 { transition-delay: 0.3s; }

  /* HAMBURGER */
  .nav-hamburger {
    display: none;
    flex-direction: column;
    gap: 5px;
    cursor: pointer;
    padding: 4px;
    z-index: 600;
  }
  .nav-hamburger span {
    display: block;
    width: 24px;
    height: 2px;
    background: var(--text);
    transition: all 0.3s ease;
    transform-origin: center;
  }
  .nav-hamburger.open span:nth-child(1) { transform: translateY(7px) rotate(45deg); }
  .nav-hamburger.open span:nth-child(2) { opacity: 0; }
  .nav-hamburger.open span:nth-child(3) { transform: translateY(-7px) rotate(-45deg); }

  .nav-mobile-menu {
    display: none;
    position: fixed;
    inset: 0;
    background: rgba(8,8,16,0.98);
    backdrop-filter: blur(20px);
    z-index: 450;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 36px;
  }
  .nav-mobile-menu.open { display: flex; }
  .nav-mobile-menu a {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 2.6rem;
    letter-spacing: 0.05em;
    color: var(--text);
    text-decoration: none;
    transition: color 0.3s;
  }
  .nav-mobile-menu a:hover { color: var(--accent); }
  .nav-mobile-cta {
    font-family: 'DM Mono', monospace !important;
    font-size: 0.8rem !important;
    letter-spacing: 0.12em !important;
    color: var(--bg) !important;
    background: var(--grad);
    padding: 14px 32px;
    margin-top: 8px;
  }

  /* TABLET */
  @media (max-width: 1024px) {
    .servicos-grid { grid-template-columns: 1fr 1fr; }
    .projetos-grid { grid-template-columns: 1fr 1fr; }
    .projeto-card.featured { grid-column: span 2; }
    .projeto-card[style*="span 3"] { grid-column: span 2 !important; }
    .certs-grid { grid-template-columns: repeat(3, 1fr); }
    .skills-inner { gap: 48px; }
  }

  /* MOBILE */
  @media (max-width: 768px) {
    body { cursor: auto; }
    .cursor, .cursor-ring { display: none; }

    /* Nav */
    nav { padding: 16px 20px; }
    .nav-links { display: none; }
    .nav-cta { display: none; }
    .nav-hamburger { display: flex; }

    /* Hero */
    .hero { padding: 100px 20px 56px; min-height: 100svh; }
    .hero-badge { font-size: 0.62rem; letter-spacing: 0.1em; padding: 5px 12px; margin-bottom: 24px; }
    .hero-name { font-size: clamp(3.4rem, 18vw, 5.5rem); }
    .hero-roles {
      font-size: 0.72rem;
      letter-spacing: 0.06em;
      margin: 16px 0 28px;
      line-height: 1.8;
    }
    .hero-roles span { padding: 0 6px; display: inline-block; }
    .hero-desc { font-size: 0.9rem; margin-bottom: 32px; }
    .hero-btns { gap: 12px; }
    .btn-primary, .btn-outline { padding: 14px 28px; font-size: 0.7rem; width: 100%; text-align: center; }
    .hero-stats {
      gap: 0;
      display: grid;
      grid-template-columns: 1fr 1fr;
      margin-top: 48px;
      padding-top: 32px;
    }
    .hero-stats > div {
      padding: 20px 0;
      border-bottom: 1px solid var(--border);
    }
    .hero-stats > div:nth-child(odd) { border-right: 1px solid var(--border); padding-right: 16px; }
    .hero-stats > div:nth-child(even) { padding-left: 20px; }
    .stat-num { font-size: 2.2rem; }
    .stat-label { font-size: 0.6rem; }

    /* Sections */
    section { padding: 72px 20px; }
    .section-title { font-size: clamp(2rem, 10vw, 3rem); }

    /* Sobre */
    .sobre-grid { grid-template-columns: 1fr; gap: 40px; }
    .sobre-photo-placeholder { max-width: 100%; aspect-ratio: 4/3; font-size: 3.5rem; }
    .sobre-photo-frame::before { display: none; }
    .sobre-photo-frame::after { bottom: -24px; }
    .sobre-content p { font-size: 0.92rem; }

    /* Serviços */
    .servicos-grid { grid-template-columns: 1fr; gap: 2px; margin-top: 40px; }
    .servico-card { padding: 36px 24px; }
    .servico-title { font-size: 1.6rem; }

    /* Skills */
    .skills-inner { grid-template-columns: 1fr; gap: 48px; }
    .skills-list { margin-top: 32px; }
    .tech-cloud { margin-top: 32px; }

    /* Projetos */
    .projetos-grid { grid-template-columns: 1fr; gap: 2px; }
    .projeto-card.featured { grid-column: span 1; }
    .projeto-card[style*="span 3"] { grid-column: span 1 !important; }
    .projeto-card { padding: 28px 24px; }
    .projetos-header { margin-bottom: 40px; }

    /* Certificados */
    .certs-grid { grid-template-columns: 1fr; gap: 2px; margin-top: 40px; }
    .cert-card { padding: 28px 24px; }

    /* Contato */
    .contato-marquee { font-size: 3rem; }
    .contato-inner { grid-template-columns: 1fr; gap: 48px; }
    .contato-left .section-title { font-size: clamp(2.2rem, 9vw, 3.5rem); }
    .contato-sub { font-size: 0.9rem; }
    .contato-form { padding: 28px 20px; }
    .contato-link { font-size: 0.85rem; }

    /* Footer */
    footer { flex-direction: column; gap: 20px; text-align: center; padding: 32px 20px; }
    .footer-social { justify-content: center; }
  }

  @media (max-width: 400px) {
    .hero-name { font-size: clamp(3rem, 20vw, 4rem); }
    .hero-roles { font-size: 0.65rem; }
  }
</style>
</head>
<body>

<div class="cursor" id="cursor"></div>
<div class="cursor-ring" id="cursorRing"></div>

<!-- NAV -->
<nav id="navbar">
  <a class="nav-logo" href="#"><span>YN</span>A</a>
  <ul class="nav-links">
    <li><a href="#sobre" class="menu-link">Sobre</a></li>
    <li><a href="#servicos" class="menu-link">Serviços</a></li>
    <li><a href="#skills" class="menu-link">Skills</a></li>
    <li><a href="#projetos" class="menu-link">Projetos</a></li>
    <li><a href="#contato" class="menu-link">Contato</a></li>
  </ul>
  <a class="nav-cta" href="https://wa.me/5547991699755?text=Olá%20Yuri!%20Gostaria%20de%20um%20orçamento" target="_blank" rel="noopener noreferrer">Solicitar orçamento</a>
  <div class="nav-hamburger" id="hamburger">
    <span></span><span></span><span></span>
  </div>
</nav>

<!-- MOBILE MENU -->
<div class="nav-mobile-menu" id="mobileMenu">
  <a href="#sobre" class="menu-link">Sobre</a>
  <a href="#servicos" class="menu-link">Serviços</a>
  <a href="#skills" class="menu-link">Skills</a>
  <a href="#projetos" class="menu-link">Projetos</a>
  <a href="#contato" class="menu-link">Contato</a>
  <a href="https://wa.me/5547991699755?text=Olá%20Yuri!%20Gostaria%20de%20um%20orçamento" target="_blank" rel="noopener noreferrer" class="nav-mobile-cta">Solicitar orçamento</a>
</div>

<!-- HERO -->
<section class="hero" id="inicio">
  <div class="hero-grid-bg"></div>
  <div class="hero-glow"></div>
  <div class="hero-inner">
    <div class="hero-badge">📍 Joinville, SC · Disponível para projetos</div>
    <h1 class="hero-name">
      <span class="line1">Yuri Nossol</span>
      <span class="line2">Alves.</span>
    </h1>
    <p class="hero-roles">Frontend Developer <span>×</span> Marketing Digital <span>×</span> IA</p>
    <p class="hero-desc">
      Criando interfaces que unem estética, performance e inteligência —
      e resultados reais com tráfego pago, geração de leads e presença digital estratégica.
    </p>
    <div class="hero-btns">
      <a href="#projetos" class="btn-primary">Ver projetos →</a>
      <a href="#contato" class="btn-outline">Fale comigo</a>
    </div>
    <div class="hero-stats">
      <div>
        <span class="stat-num">+2</span>
        <span class="stat-label">Anos de experiência</span>
      </div>
      <div>
        <span class="stat-num">3</span>
        <span class="stat-label">Projetos entregues</span>
      </div>
      <div>
        <span class="stat-num">5+</span>
        <span class="stat-label">Tecnologias</span>
      </div>
      <div>
        <span class="stat-num">∞</span>
        <span class="stat-label">Curiosidade</span>
      </div>
    </div>
  </div>
</section>

<!-- SOBRE -->
<section class="sobre" id="sobre">
  <div class="sobre-grid">
    <div class="reveal">
      <div class="sobre-photo-frame">
        <div class="sobre-photo-placeholder">YNA</div>
      </div>
    </div>
    <div class="reveal reveal-delay-1">
      <div class="section-tag">Sobre mim</div>
      <h2 class="section-title">Quem sou eu</h2>
      <div class="loc-badge">📍 Joinville, SC</div>
      <p>
        Sou um desenvolvedor <strong>frontend</strong> apaixonado por criar experiências digitais
        que combinam código limpo com design intencional. Minha jornada começou com HTML e CSS,
        evoluindo para JavaScript, Python e, mais recentemente, <strong>Inteligência Artificial</strong>.
      </p>
      <p>
        Além do desenvolvimento, atuo com <strong>marketing digital</strong> estratégico — tráfego pago,
        geração de leads qualificados e criação de sites profissionais que convertem.
        Uma combinação rara de técnica e estratégia de negócios.
      </p>
      <p>
        Acredito que tecnologia deve ser ao mesmo tempo <strong>funcional e bela</strong>.
        Cada projeto é uma oportunidade de resolver problemas reais enquanto cria algo que
        as pessoas realmente querem usar — e que gera resultados mensuráveis.
      </p>
      <div class="sobre-tags">
        <span class="tag">HTML5</span>
        <span class="tag">CSS3</span>
        <span class="tag">JavaScript</span>
        <span class="tag">Python</span>
        <span class="tag">IA / LLMs</span>
        <span class="tag">Tráfego Pago</span>
        <span class="tag">Meta Ads</span>
        <span class="tag">Google Ads</span>
        <span class="tag">Figma</span>
        <span class="tag">REST APIs</span>
      </div>
    </div>
  </div>
</section>

<!-- SERVIÇOS -->
<section class="servicos" id="servicos">
  <div style="max-width:1200px;margin:0 auto">
    <div class="reveal">
      <div class="section-tag">O que eu faço</div>
      <h2 class="section-title">Serviços</h2>
    </div>
  </div>
  <div class="servicos-grid">
    <div class="servico-card reveal">
      <span class="servico-num">01 —</span>
      <span class="servico-icon">🌐</span>
      <div class="servico-title">Criação de Sites</div>
      <p class="servico-desc">Sites profissionais, rápidos e responsivos que convertem visitantes em clientes. Do design ao deploy.</p>
      <ul class="servico-list">
        <li>Sites institucionais</li>
        <li>Landing pages</li>
        <li>E-commerce</li>
        <li>Integração WhatsApp / CRM</li>
      </ul>
    </div>
    <div class="servico-card reveal reveal-delay-1">
      <span class="servico-num">02 —</span>
      <span class="servico-icon">📣</span>
      <div class="servico-title">Tráfego Pago</div>
      <p class="servico-desc">Campanhas estratégicas no Meta Ads e Google Ads com foco em ROI e leads qualificados para o seu negócio.</p>
      <ul class="servico-list">
        <li>Meta Ads (Facebook/Instagram)</li>
        <li>Google Ads</li>
        <li>Remarketing</li>
        <li>Análise de métricas</li>
      </ul>
    </div>
    <div class="servico-card reveal reveal-delay-2">
      <span class="servico-num">03 —</span>
      <span class="servico-icon">🤖</span>
      <div class="servico-title">IA & Automação</div>
      <p class="servico-desc">Interfaces e soluções inteligentes com IA integrada — desde automação de processos até dashboards em tempo real.</p>
      <ul class="servico-list">
        <li>Integração com LLMs</li>
        <li>Dashboards com APIs</li>
        <li>Automações Python</li>
        <li>Prompt Engineering</li>
      </ul>
    </div>
  </div>
</section>

<!-- SKILLS -->
<section class="skills" id="skills">
  <div class="skills-inner">
    <div>
      <div class="reveal">
        <div class="section-tag">Habilidades</div>
        <h2 class="section-title">Stack &amp; Expertise</h2>
      </div>
      <div class="skills-list">
        <div class="skill-item reveal">
          <div class="skill-top">
            <span class="skill-name">HTML5 / CSS3</span>
            <span class="skill-pct">95%</span>
          </div>
          <div class="skill-bar"><div class="skill-fill" style="--w:0.95"></div></div>
        </div>
        <div class="skill-item reveal reveal-delay-1">
          <div class="skill-top">
            <span class="skill-name">JavaScript</span>
            <span class="skill-pct">82%</span>
          </div>
          <div class="skill-bar"><div class="skill-fill" style="--w:0.82"></div></div>
        </div>
        <div class="skill-item reveal reveal-delay-1">
          <div class="skill-top">
            <span class="skill-name">Python</span>
            <span class="skill-pct">78%</span>
          </div>
          <div class="skill-bar"><div class="skill-fill" style="--w:0.78"></div></div>
        </div>
        <div class="skill-item reveal reveal-delay-2">
          <div class="skill-top">
            <span class="skill-name">Inteligência Artificial</span>
            <span class="skill-pct">75%</span>
          </div>
          <div class="skill-bar"><div class="skill-fill" style="--w:0.75"></div></div>
        </div>
        <div class="skill-item reveal reveal-delay-2">
          <div class="skill-top">
            <span class="skill-name">Meta Ads / Google Ads</span>
            <span class="skill-pct">80%</span>
          </div>
          <div class="skill-bar"><div class="skill-fill" style="--w:0.80"></div></div>
        </div>
        <div class="skill-item reveal reveal-delay-3">
          <div class="skill-top">
            <span class="skill-name">UI / UX Design</span>
            <span class="skill-pct">68%</span>
          </div>
          <div class="skill-bar"><div class="skill-fill" style="--w:0.68"></div></div>
        </div>
      </div>
    </div>
    <div>
      <div class="reveal">
        <div class="section-tag">Ferramentas</div>
        <h2 class="section-title">Tecnologias</h2>
      </div>
      <div class="tech-cloud">
        <div class="reveal reveal-delay-1">
          <div class="tech-cat">Frontend</div>
          <div class="tech-row">
            <span class="tech-chip">HTML5</span>
            <span class="tech-chip">CSS3</span>
            <span class="tech-chip">JavaScript</span>
            <span class="tech-chip">Responsive Design</span>
          </div>
        </div>
        <div class="reveal reveal-delay-2">
          <div class="tech-cat">Backend & Tools</div>
          <div class="tech-row">
            <span class="tech-chip">Python</span>
            <span class="tech-chip">REST APIs</span>
            <span class="tech-chip">Git</span>
            <span class="tech-chip">Figma</span>
          </div>
        </div>
        <div class="reveal reveal-delay-2">
          <div class="tech-cat">Marketing</div>
          <div class="tech-row">
            <span class="tech-chip">Meta Ads</span>
            <span class="tech-chip">Google Ads</span>
            <span class="tech-chip">Meta Ads API</span>
            <span class="tech-chip">Analytics</span>
          </div>
        </div>
        <div class="reveal reveal-delay-3">
          <div class="tech-cat">IA & Automação</div>
          <div class="tech-row">
            <span class="tech-chip">LLMs</span>
            <span class="tech-chip">Prompt Engineering</span>
            <span class="tech-chip">AI Integrations</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- PROJETOS -->
<section class="projetos" id="projetos">
  <div class="projetos-inner">
    <div class="projetos-header reveal">
      <div>
        <div class="section-tag">Portfólio</div>
        <h2 class="section-title">Projetos em Destaque</h2>
      </div>
    </div>
    <div class="projetos-grid">
      <div class="projeto-card featured reveal">
        <div class="projeto-num">01 — PROJETO</div>
        <span class="projeto-emoji">📣</span>
        <div class="projeto-title">YN Digital</div>
        <p class="projeto-desc">Site profissional de marketing digital com foco em geração de leads, tráfego pago e criação de sites. Apresenta serviços, portfólio, certificados e formulário de contato integrado.</p>
        <div class="projeto-techs">
          <span class="tech-tag">HTML</span>
          <span class="tech-tag">CSS</span>
          <span class="tech-tag">JavaScript</span>
        </div>
        <a href="https://yndigital.netlify.app" target="_blank" rel="noopener noreferrer" class="projeto-link">Ver site →</a>
      </div>
      <div class="projeto-card reveal reveal-delay-1">
        <div class="projeto-num">02 — PROJETO</div>
        <span class="projeto-emoji">🪵</span>
        <div class="projeto-title">Madeireira Rossi</div>
        <p class="projeto-desc">Site institucional para madeireira em Joinville/SC. Apresenta produtos (Cambará e Eucalipto), serviços, localização e integração direta com WhatsApp para orçamentos rápidos.</p>
        <div class="projeto-techs">
          <span class="tech-tag">HTML</span>
          <span class="tech-tag">CSS</span>
          <span class="tech-tag">JavaScript</span>
        </div>
        <a href="https://madeireirarossi.netlify.app" target="_blank" rel="noopener noreferrer" class="projeto-link">Ver site →</a>
      </div>
      <div class="projeto-card reveal reveal-delay-2" style="grid-column:span 3">
        <div class="projeto-num">03 — PROJETO</div>
        <span class="projeto-emoji">📊</span>
        <div class="projeto-title">Metron — Dashboard Meta Ads</div>
        <p class="projeto-desc">Dashboard completo para gestão de Meta Ads (Facebook/Instagram). Exibe métricas em tempo real, gráficos de desempenho, tabela de campanhas e integração com a API do Meta.</p>
        <div class="projeto-techs">
          <span class="tech-tag">HTML</span>
          <span class="tech-tag">CSS</span>
          <span class="tech-tag">JavaScript</span>
          <span class="tech-tag">Meta Ads API</span>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- CERTIFICADOS -->
<section class="certificados" id="certificados">
  <div style="max-width:1200px;margin:0 auto">
    <div class="reveal">
      <div class="section-tag">Formação</div>
      <h2 class="section-title">Certificados</h2>
    </div>
  </div>
  <div class="certs-grid">
    <div class="cert-card reveal">
      <span class="cert-platform">Meta Blueprint</span>
      <div class="cert-name">Meta Certified Digital Marketing Associate</div>
      <span class="cert-year">2023</span>
    </div>
    <div class="cert-card reveal reveal-delay-1">
      <span class="cert-platform">Google</span>
      <div class="cert-name">Google Ads — Fundamentos de Marketing Digital</div>
      <span class="cert-year">2023</span>
    </div>
    <div class="cert-card reveal reveal-delay-2">
      <span class="cert-platform">Anhanguera · Em andamento</span>
      <div class="cert-name">Bacharelado em Engenharia de Software</div>
      <span class="cert-year">2026 — cursando</span>
    </div>

  </div>
</section>

<!-- CONTATO -->
<section class="contato" id="contato">
  <div class="contato-marquee">VAMOS TRABALHAR JUNTOS · VAMOS TRABALHAR JUNTOS · VAMOS TRABALHAR JUNTOS · VAMOS TRABALHAR JUNTOS · </div>
  <div class="contato-inner">
    <div>
      <div class="reveal">
        <div class="section-tag">Contato</div>
        <h2 class="section-title">Vamos trabalhar juntos?</h2>
        <p class="contato-sub">Estou sempre aberto para novos projetos, colaborações ou simplesmente um bom papo sobre tecnologia, IA e marketing. Respondo em até 24h.</p>
      </div>
      <div class="contato-links reveal reveal-delay-1">
        <a href="mailto:yurinossol@gmail.com" class="contato-link">
          <span class="contato-link-icon">Email</span>
          yurinossol@gmail.com
        </a>
        <a href="tel:+5547991699755" class="contato-link">
          <span class="contato-link-icon">Tel</span>
          (47) 99169-9755
        </a>
        <a href="https://wa.me/5547991699755?text=Olá%20Yuri!%20Gostaria%20de%20um%20orçamento" target="_blank" rel="noopener noreferrer" class="contato-link">
          <span class="contato-link-icon">WhatsApp</span>
          Solicitar orçamento →
        </a>
        <a href="https://www.linkedin.com/in/yuri-nossol-alves-a51888316" target="_blank" rel="noopener noreferrer" class="contato-link">
          <span class="contato-link-icon">LinkedIn</span>
          yuri-nossol-alves →
        </a>
      </div>
    </div>
    <div class="contato-form reveal reveal-delay-2">
      <div class="form-group">
        <label>Seu nome</label>
        <input type="text" placeholder="Como posso te chamar?">
      </div>
      <div class="form-group">
        <label>E-mail</label>
        <input type="email" placeholder="seu@email.com">
      </div>
      <div class="form-group">
        <label>Serviço de interesse</label>
        <select>
          <option value="">Selecione um serviço</option>
          <option>Criação de site</option>
          <option>Tráfego pago / Meta Ads</option>
          <option>Google Ads</option>
          <option>IA & Automação</option>
          <option>Outro</option>
        </select>
      </div>
      <div class="form-group">
        <label>Mensagem</label>
        <textarea placeholder="Conte sobre seu projeto..."></textarea>
      </div>
      <button class="btn-submit" id="btnSubmit">Enviar mensagem</button>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-logo"><span>YN</span>A · Yuri Nossol Alves</div>
  <div class="footer-copy">Feito com HTML, CSS, JS & muito ☕ — © 2025</div>
  <div class="footer-social">
    <a href="https://www.linkedin.com/in/yuri-nossol-alves-a51888316" target="_blank" rel="noopener noreferrer">LinkedIn</a>
    <a href="https://wa.me/5547991699755" target="_blank" rel="noopener noreferrer">WhatsApp</a>
    <a href="mailto:yurinossol@gmail.com">Email</a>
  </div>
</footer>

<script>
  // Mobile menu — sem inline handlers
  function toggleMenu() {
    const h = document.getElementById('hamburger');
    const m = document.getElementById('mobileMenu');
    h.classList.toggle('open');
    m.classList.toggle('open');
    document.body.style.overflow = m.classList.contains('open') ? 'hidden' : '';
  }
  function closeMenu() {
    document.getElementById('hamburger').classList.remove('open');
    document.getElementById('mobileMenu').classList.remove('open');
    document.body.style.overflow = '';
  }

  document.getElementById('hamburger').addEventListener('click', toggleMenu);
  document.querySelectorAll('.menu-link').forEach(link => {
    link.addEventListener('click', closeMenu);
  });

  // Form submit
  const btnSubmit = document.getElementById('btnSubmit');
  if (btnSubmit) {
    btnSubmit.addEventListener('click', function() {
      alert('Mensagem recebida! Entrarei em contato em breve. 🚀');
    });
  }

  // Custom cursor (desktop only)
  const cursor = document.getElementById('cursor');
  const ring = document.getElementById('cursorRing');
  let mx = 0, my = 0, rx = 0, ry = 0;

  document.addEventListener('mousemove', e => {
    mx = e.clientX; my = e.clientY;
    cursor.style.left = mx - 5 + 'px';
    cursor.style.top = my - 5 + 'px';
  });

  function animateRing() {
    rx += (mx - rx - 19) * 0.12;
    ry += (my - ry - 19) * 0.12;
    ring.style.left = rx + 'px';
    ring.style.top = ry + 'px';
    requestAnimationFrame(animateRing);
  }
  animateRing();

  // Navbar scroll
  const navbar = document.getElementById('navbar');
  window.addEventListener('scroll', () => {
    navbar.classList.toggle('scrolled', window.scrollY > 50);
  });

  // Scroll reveal
  const reveals = document.querySelectorAll('.reveal');
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        e.target.classList.add('visible');
        // Animate skill bars
        e.target.querySelectorAll('.skill-fill').forEach(bar => {
          bar.classList.add('animated');
        });
        observer.unobserve(e.target);
      }
    });
  }, { threshold: 0.15 });

  reveals.forEach(el => observer.observe(el));

  // Also observe skill fills separately
  document.querySelectorAll('.skill-item').forEach(item => {
    const fill = item.querySelector('.skill-fill');
    if (!fill) return;
    const w = fill.style.getPropertyValue('--w') || '0.8';
    fill.style.setProperty('--target', w);

    const obs = new IntersectionObserver(entries => {
      if (entries[0].isIntersecting) {
        setTimeout(() => {
          fill.style.width = (parseFloat(w) * 100) + '%';
          fill.style.transform = 'scaleX(1)';
        }, 200);
        obs.unobserve(item);
      }
    }, { threshold: 0.5 });
    obs.observe(item);
  });
</script>
</body>
</html>
