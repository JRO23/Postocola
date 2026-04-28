<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Postocola S.A. — Manual de Onboarding</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700;900&family=DM+Sans:wght@300;400;500;600&family=DM+Mono&display=swap" rel="stylesheet">
<style>
  :root {
    --rojo: #D72638;
    --rojo-oscuro: #A31C28;
    --dorado: #F4A018;
    --dorado-claro: #FDD26E;
    --crema: #FFF8EE;
    --crema-oscuro: #F5EAD4;
    --carbón: #1A1007;
    --gris-oscuro: #3A2D1F;
    --gris-medio: #6B5B47;
    --gris-claro: #C9B99A;
    --blanco: #FFFFFF;
    --verde-exito: #2D7D46;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  html { scroll-behavior: smooth; }

  body {
    font-family: 'DM Sans', sans-serif;
    background: var(--crema);
    color: var(--carbón);
    overflow-x: hidden;
  }

  /* ─── NAV ─── */
  nav {
    position: fixed;
    top: 0; left: 0; right: 0;
    z-index: 100;
    background: rgba(26,16,7,0.96);
    backdrop-filter: blur(10px);
    padding: 0 2rem;
    display: flex;
    align-items: center;
    justify-content: space-between;
    height: 64px;
    border-bottom: 2px solid var(--rojo);
  }
  .nav-logo {
    font-family: 'Playfair Display', serif;
    font-size: 1.4rem;
    font-weight: 900;
    color: var(--blanco);
    letter-spacing: 0.05em;
  }
  .nav-logo span { color: var(--dorado); }
  .nav-links {
    display: flex;
    gap: 1.5rem;
    list-style: none;
  }
  .nav-links a {
    color: var(--gris-claro);
    text-decoration: none;
    font-size: 0.8rem;
    font-weight: 500;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    transition: color 0.2s;
  }
  .nav-links a:hover { color: var(--dorado); }
  .nav-badge {
    background: var(--rojo);
    color: white;
    font-size: 0.7rem;
    font-weight: 600;
    padding: 0.25rem 0.75rem;
    border-radius: 20px;
    letter-spacing: 0.06em;
    text-transform: uppercase;
  }

  /* ─── HERO ─── */
  .hero {
    min-height: 100vh;
    background: var(--carbón);
    position: relative;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    overflow: hidden;
    padding: 100px 2rem 4rem;
  }
  .hero-bg {
    position: absolute;
    inset: 0;
    background:
      radial-gradient(ellipse 80% 60% at 50% 0%, rgba(215,38,56,0.18) 0%, transparent 70%),
      radial-gradient(ellipse 40% 40% at 80% 80%, rgba(244,160,24,0.1) 0%, transparent 60%),
      repeating-linear-gradient(
        -45deg,
        transparent,
        transparent 40px,
        rgba(255,255,255,0.01) 40px,
        rgba(255,255,255,0.01) 41px
      );
  }
  .hero-bubbles {
    position: absolute;
    inset: 0;
    pointer-events: none;
    overflow: hidden;
  }
  .bubble {
    position: absolute;
    border-radius: 50%;
    animation: float linear infinite;
    opacity: 0;
  }
  @keyframes float {
    0% { transform: translateY(110vh) scale(0.3); opacity: 0; }
    10% { opacity: 0.4; }
    90% { opacity: 0.15; }
    100% { transform: translateY(-20vh) scale(1.2); opacity: 0; }
  }
  .hero-eyebrow {
    font-family: 'DM Mono', monospace;
    font-size: 0.75rem;
    letter-spacing: 0.25em;
    color: var(--dorado);
    text-transform: uppercase;
    margin-bottom: 1.5rem;
    opacity: 0;
    animation: fadeUp 0.8s 0.3s ease forwards;
  }
  .hero-title {
    font-family: 'Playfair Display', serif;
    font-size: clamp(3rem, 8vw, 7rem);
    font-weight: 900;
    color: var(--blanco);
    line-height: 1.0;
    text-align: center;
    max-width: 900px;
    opacity: 0;
    animation: fadeUp 0.9s 0.5s ease forwards;
  }
  .hero-title .accent { color: var(--rojo); }
  .hero-title .gold { color: var(--dorado); }
  .hero-subtitle {
    font-size: 1.2rem;
    font-weight: 300;
    color: var(--gris-claro);
    text-align: center;
    max-width: 580px;
    margin-top: 1.5rem;
    line-height: 1.6;
    opacity: 0;
    animation: fadeUp 0.9s 0.7s ease forwards;
  }
  .hero-cta {
    margin-top: 3rem;
    display: flex;
    gap: 1rem;
    flex-wrap: wrap;
    justify-content: center;
    opacity: 0;
    animation: fadeUp 0.9s 0.9s ease forwards;
  }
  .btn-primary {
    background: var(--rojo);
    color: white;
    padding: 1rem 2.5rem;
    border: none;
    border-radius: 4px;
    font-family: 'DM Sans', sans-serif;
    font-size: 0.9rem;
    font-weight: 600;
    letter-spacing: 0.06em;
    text-transform: uppercase;
    cursor: pointer;
    text-decoration: none;
    transition: all 0.2s;
    display: inline-block;
  }
  .btn-primary:hover { background: var(--rojo-oscuro); transform: translateY(-2px); }
  .btn-secondary {
    background: transparent;
    color: var(--dorado);
    padding: 1rem 2.5rem;
    border: 2px solid var(--dorado);
    border-radius: 4px;
    font-family: 'DM Sans', sans-serif;
    font-size: 0.9rem;
    font-weight: 600;
    letter-spacing: 0.06em;
    text-transform: uppercase;
    cursor: pointer;
    text-decoration: none;
    transition: all 0.2s;
    display: inline-block;
  }
  .btn-secondary:hover { background: var(--dorado); color: var(--carbón); }
  .hero-scroll {
    position: absolute;
    bottom: 2rem;
    left: 50%;
    transform: translateX(-50%);
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 0.5rem;
    color: var(--gris-claro);
    font-size: 0.7rem;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    opacity: 0;
    animation: fadeUp 1s 1.3s ease forwards;
  }
  .scroll-line {
    width: 1px;
    height: 40px;
    background: linear-gradient(to bottom, var(--dorado), transparent);
    animation: scrollPulse 2s ease-in-out infinite;
  }
  @keyframes scrollPulse {
    0%, 100% { opacity: 1; transform: scaleY(1); }
    50% { opacity: 0.4; transform: scaleY(0.7); }
  }
  .hero-stat-row {
    margin-top: 4rem;
    display: flex;
    gap: 3rem;
    flex-wrap: wrap;
    justify-content: center;
    opacity: 0;
    animation: fadeUp 0.9s 1.1s ease forwards;
  }
  .hero-stat {
    text-align: center;
  }
  .hero-stat-number {
    font-family: 'Playfair Display', serif;
    font-size: 2.5rem;
    font-weight: 900;
    color: var(--dorado);
    display: block;
  }
  .hero-stat-label {
    font-size: 0.75rem;
    color: var(--gris-claro);
    letter-spacing: 0.1em;
    text-transform: uppercase;
    margin-top: 0.25rem;
  }
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(30px); }
    to { opacity: 1; transform: translateY(0); }
  }

  /* ─── SECTIONS ─── */
  section { scroll-margin-top: 64px; }
  .section-label {
    font-family: 'DM Mono', monospace;
    font-size: 0.7rem;
    letter-spacing: 0.25em;
    color: var(--rojo);
    text-transform: uppercase;
    margin-bottom: 0.75rem;
  }
  .section-title {
    font-family: 'Playfair Display', serif;
    font-size: clamp(2rem, 4vw, 3.2rem);
    font-weight: 800;
    line-height: 1.15;
  }
  .section-lead {
    font-size: 1.1rem;
    font-weight: 300;
    color: var(--gris-medio);
    line-height: 1.7;
    max-width: 640px;
    margin-top: 1rem;
  }

  /* ─── WELCOME ─── */
  #bienvenida {
    background: var(--blanco);
    padding: 8rem 2rem;
  }
  .welcome-grid {
    max-width: 1200px;
    margin: 0 auto;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 5rem;
    align-items: center;
  }
  .welcome-visual {
    position: relative;
    height: 480px;
  }
  .welcome-card-main {
    position: absolute;
    top: 0; left: 0;
    width: 80%;
    height: 380px;
    background: linear-gradient(135deg, var(--rojo) 0%, var(--rojo-oscuro) 100%);
    border-radius: 12px;
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    padding: 2.5rem;
    overflow: hidden;
  }
  .welcome-card-main::before {
    content: '';
    position: absolute;
    top: -60px; right: -60px;
    width: 200px; height: 200px;
    border-radius: 50%;
    background: rgba(255,255,255,0.08);
  }
  .welcome-card-main::after {
    content: '';
    position: absolute;
    bottom: -40px; left: 30%;
    width: 140px; height: 140px;
    border-radius: 50%;
    background: rgba(244,160,24,0.15);
  }
  .welcome-card-main h3 {
    font-family: 'Playfair Display', serif;
    font-size: 2rem;
    font-weight: 900;
    color: white;
    line-height: 1.2;
    position: relative;
    z-index: 1;
  }
  .welcome-card-main p {
    color: rgba(255,255,255,0.8);
    font-size: 0.9rem;
    margin-top: 0.5rem;
    position: relative;
    z-index: 1;
  }
  .welcome-card-secondary {
    position: absolute;
    bottom: 0; right: 0;
    width: 65%;
    background: var(--carbón);
    border-radius: 12px;
    padding: 1.75rem;
  }
  .welcome-card-secondary .year {
    font-family: 'Playfair Display', serif;
    font-size: 3rem;
    font-weight: 900;
    color: var(--dorado);
    line-height: 1;
  }
  .welcome-card-secondary p {
    color: var(--gris-claro);
    font-size: 0.85rem;
    margin-top: 0.5rem;
    line-height: 1.5;
  }
  .welcome-badge {
    position: absolute;
    top: 2rem; right: 0;
    background: var(--dorado);
    color: var(--carbón);
    padding: 0.5rem 1.25rem;
    border-radius: 4px;
    font-size: 0.75rem;
    font-weight: 700;
    letter-spacing: 0.1em;
    text-transform: uppercase;
  }
  .welcome-text { }
  .mission-vision-grid {
    margin-top: 2.5rem;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1rem;
  }
  .mv-card {
    background: var(--crema);
    border-radius: 8px;
    padding: 1.5rem;
    border-left: 4px solid var(--rojo);
  }
  .mv-card.vision { border-left-color: var(--dorado); }
  .mv-card h4 {
    font-family: 'Playfair Display', serif;
    font-size: 1.1rem;
    font-weight: 700;
    margin-bottom: 0.5rem;
    color: var(--carbón);
  }
  .mv-card p {
    font-size: 0.85rem;
    color: var(--gris-medio);
    line-height: 1.55;
  }

  /* ─── HISTORIA ─── */
  #historia {
    background: var(--carbón);
    padding: 8rem 2rem;
    color: white;
  }
  #historia .section-title { color: white; }
  #historia .section-lead { color: var(--gris-claro); }
  .timeline {
    max-width: 900px;
    margin: 4rem auto 0;
    position: relative;
  }
  .timeline::before {
    content: '';
    position: absolute;
    left: 50%;
    top: 0; bottom: 0;
    width: 2px;
    background: linear-gradient(to bottom, var(--rojo), var(--dorado), var(--rojo));
    transform: translateX(-50%);
  }
  .timeline-item {
    display: flex;
    gap: 2rem;
    margin-bottom: 3rem;
    position: relative;
  }
  .timeline-item:nth-child(odd) { flex-direction: row-reverse; }
  .timeline-item:nth-child(odd) .tl-content { text-align: right; }
  .tl-year {
    width: calc(50% - 2rem);
    display: flex;
    align-items: flex-start;
    justify-content: flex-end;
    padding-top: 0.5rem;
  }
  .timeline-item:nth-child(odd) .tl-year { justify-content: flex-start; }
  .tl-dot {
    position: absolute;
    left: 50%;
    top: 0.5rem;
    transform: translateX(-50%);
    width: 16px; height: 16px;
    border-radius: 50%;
    background: var(--dorado);
    border: 3px solid var(--carbón);
    box-shadow: 0 0 0 2px var(--dorado);
  }
  .tl-year-label {
    font-family: 'Playfair Display', serif;
    font-size: 1.8rem;
    font-weight: 900;
    color: var(--dorado);
  }
  .tl-content {
    width: calc(50% - 2rem);
    padding-top: 0.25rem;
  }
  .tl-content h4 {
    font-weight: 600;
    font-size: 1rem;
    color: white;
    margin-bottom: 0.35rem;
  }
  .tl-content p {
    font-size: 0.85rem;
    color: var(--gris-claro);
    line-height: 1.6;
  }
  .tl-tag {
    display: inline-block;
    background: rgba(215,38,56,0.2);
    color: #FF8A95;
    padding: 0.2rem 0.6rem;
    border-radius: 3px;
    font-size: 0.7rem;
    font-weight: 600;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    margin-bottom: 0.4rem;
  }
  .tl-tag.gold { background: rgba(244,160,24,0.2); color: var(--dorado); }
  .tl-tag.green { background: rgba(45,125,70,0.3); color: #6EE09A; }

  /* ─── VALORES ─── */
  #valores {
    background: var(--crema-oscuro);
    padding: 8rem 2rem;
  }
  .valores-header {
    max-width: 1200px;
    margin: 0 auto;
  }
  .valores-grid {
    max-width: 1200px;
    margin: 3.5rem auto 0;
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 1.5rem;
  }
  .valor-card {
    background: var(--blanco);
    border-radius: 12px;
    padding: 2rem 1.5rem;
    border-top: 4px solid var(--rojo);
    transition: all 0.3s ease;
    cursor: default;
  }
  .valor-card:hover { transform: translateY(-6px); box-shadow: 0 20px 60px rgba(215,38,56,0.15); }
  .valor-card:nth-child(2) { border-top-color: var(--dorado); }
  .valor-card:nth-child(3) { border-top-color: var(--verde-exito); }
  .valor-card:nth-child(4) { border-top-color: #5B6AF0; }
  .valor-emoji { font-size: 2.5rem; margin-bottom: 1rem; display: block; }
  .valor-card h3 {
    font-family: 'Playfair Display', serif;
    font-size: 1.25rem;
    font-weight: 800;
    margin-bottom: 0.5rem;
    color: var(--carbón);
  }
  .valor-card p {
    font-size: 0.85rem;
    color: var(--gris-medio);
    line-height: 1.6;
  }

  /* ─── SALARIO EMOCIONAL ─── */
  #salario {
    background: var(--blanco);
    padding: 8rem 2rem;
  }
  .salario-intro {
    max-width: 1200px;
    margin: 0 auto;
    display: grid;
    grid-template-columns: 1.2fr 1fr;
    gap: 5rem;
    align-items: center;
    margin-bottom: 6rem;
  }
  .salario-visual {
    background: var(--carbón);
    border-radius: 16px;
    padding: 3rem;
    position: relative;
    overflow: hidden;
  }
  .salario-visual::before {
    content: '';
    position: absolute;
    top: -80px; right: -80px;
    width: 300px; height: 300px;
    border-radius: 50%;
    background: radial-gradient(circle, rgba(244,160,24,0.15) 0%, transparent 70%);
  }
  .salary-compare {
    position: relative;
    z-index: 1;
  }
  .salary-row {
    display: flex;
    align-items: center;
    gap: 1rem;
    margin-bottom: 1.25rem;
  }
  .salary-row-label {
    color: var(--gris-claro);
    font-size: 0.82rem;
    width: 120px;
    flex-shrink: 0;
    letter-spacing: 0.03em;
  }
  .salary-bar-wrap {
    flex: 1;
    height: 8px;
    background: rgba(255,255,255,0.08);
    border-radius: 4px;
    overflow: hidden;
  }
  .salary-bar {
    height: 100%;
    border-radius: 4px;
    transition: width 1.5s ease;
  }
  .salary-bar.mercado { background: var(--gris-claro); width: 60%; }
  .salary-bar.postocola { background: linear-gradient(90deg, var(--rojo), var(--dorado)); width: 66%; }
  .salary-bar.emocional { background: linear-gradient(90deg, var(--dorado), #FFE88A); width: 90%; }
  .salary-value {
    color: white;
    font-weight: 600;
    font-size: 0.82rem;
    width: 50px;
    text-align: right;
    flex-shrink: 0;
  }
  .salary-value.highlight { color: var(--dorado); }
  .salary-label-top {
    font-family: 'Playfair Display', serif;
    font-size: 1.4rem;
    font-weight: 800;
    color: white;
    margin-bottom: 2rem;
  }
  .salary-label-top span { color: var(--dorado); }
  .salary-note {
    margin-top: 1.5rem;
    font-size: 0.78rem;
    color: rgba(201,185,154,0.7);
    border-top: 1px solid rgba(255,255,255,0.08);
    padding-top: 1rem;
    line-height: 1.5;
  }
  .pilares-grid {
    max-width: 1200px;
    margin: 0 auto;
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 2rem;
  }
  .pilar-card {
    border: 1px solid var(--crema-oscuro);
    border-radius: 12px;
    overflow: hidden;
    transition: all 0.3s;
  }
  .pilar-card:hover { border-color: var(--rojo); box-shadow: 0 12px 40px rgba(215,38,56,0.1); }
  .pilar-header {
    padding: 2rem;
    background: var(--crema);
    display: flex;
    align-items: center;
    gap: 1rem;
    border-bottom: 1px solid var(--crema-oscuro);
  }
  .pilar-icon {
    width: 52px; height: 52px;
    border-radius: 10px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 1.5rem;
    flex-shrink: 0;
  }
  .pilar-icon.r { background: rgba(215,38,56,0.1); }
  .pilar-icon.g { background: rgba(244,160,24,0.1); }
  .pilar-icon.b { background: rgba(91,106,240,0.1); }
  .pilar-icon.gr { background: rgba(45,125,70,0.1); }
  .pilar-icon.p { background: rgba(155,89,182,0.1); }
  .pilar-icon.t { background: rgba(26,188,156,0.1); }
  .pilar-header h3 {
    font-family: 'Playfair Display', serif;
    font-size: 1.15rem;
    font-weight: 800;
    color: var(--carbón);
  }
  .pilar-header p {
    font-size: 0.78rem;
    color: var(--gris-medio);
    margin-top: 0.2rem;
  }
  .pilar-body {
    padding: 1.75rem 2rem;
    background: white;
  }
  .pilar-body ul {
    list-style: none;
  }
  .pilar-body li {
    display: flex;
    gap: 0.75rem;
    align-items: flex-start;
    margin-bottom: 0.9rem;
    font-size: 0.875rem;
    color: var(--gris-oscuro);
    line-height: 1.5;
  }
  .pilar-body li::before {
    content: '→';
    color: var(--rojo);
    font-weight: 700;
    flex-shrink: 0;
    margin-top: 0.05em;
  }
  .pilar-highlight {
    margin-top: 1.25rem;
    background: linear-gradient(135deg, rgba(215,38,56,0.06), rgba(244,160,24,0.06));
    border-radius: 8px;
    padding: 1rem 1.25rem;
    font-size: 0.8rem;
    color: var(--rojo-oscuro);
    font-weight: 500;
    border-left: 3px solid var(--dorado);
  }

  /* ─── BIENESTAR ─── */
  #bienestar {
    background: linear-gradient(160deg, var(--carbón) 0%, #2A1408 100%);
    padding: 8rem 2rem;
    color: white;
  }
  #bienestar .section-title { color: white; }
  #bienestar .section-lead { color: var(--gris-claro); }
  .bienestar-intro {
    max-width: 1200px;
    margin: 0 auto;
  }
  .programas-grid {
    max-width: 1200px;
    margin: 3.5rem auto 0;
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 1.5rem;
  }
  .programa-card {
    background: rgba(255,255,255,0.04);
    border: 1px solid rgba(255,255,255,0.08);
    border-radius: 12px;
    padding: 2rem;
    transition: all 0.3s;
  }
  .programa-card:hover {
    background: rgba(215,38,56,0.08);
    border-color: rgba(215,38,56,0.3);
    transform: translateY(-4px);
  }
  .programa-card.featured {
    grid-column: 1 / -1;
    background: linear-gradient(135deg, rgba(215,38,56,0.12) 0%, rgba(244,160,24,0.08) 100%);
    border-color: rgba(244,160,24,0.2);
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 2rem;
  }
  .programa-top {
    display: flex;
    align-items: flex-start;
    justify-content: space-between;
    margin-bottom: 1.25rem;
  }
  .prog-icon {
    width: 48px; height: 48px;
    border-radius: 10px;
    background: rgba(244,160,24,0.15);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 1.4rem;
  }
  .prog-tag {
    font-size: 0.68rem;
    background: rgba(215,38,56,0.25);
    color: #FF9AA5;
    padding: 0.25rem 0.6rem;
    border-radius: 20px;
    font-weight: 600;
    letter-spacing: 0.08em;
    text-transform: uppercase;
  }
  .prog-tag.new { background: rgba(45,125,70,0.3); color: #6EE09A; }
  .prog-tag.gold { background: rgba(244,160,24,0.2); color: var(--dorado-claro); }
  .programa-card h4 {
    font-family: 'Playfair Display', serif;
    font-size: 1.2rem;
    font-weight: 800;
    color: white;
    margin-bottom: 0.5rem;
  }
  .programa-card p {
    font-size: 0.855rem;
    color: var(--gris-claro);
    line-height: 1.65;
  }
  .programa-card ul {
    list-style: none;
    margin-top: 1rem;
  }
  .programa-card li {
    font-size: 0.82rem;
    color: rgba(201,185,154,0.85);
    padding: 0.4rem 0;
    border-bottom: 1px solid rgba(255,255,255,0.05);
    display: flex;
    align-items: center;
    gap: 0.6rem;
  }
  .programa-card li::before {
    content: '◆';
    color: var(--dorado);
    font-size: 0.5rem;
    flex-shrink: 0;
  }

  /* ─── DESARROLLO ─── */
  #desarrollo {
    background: var(--crema);
    padding: 8rem 2rem;
  }
  .desarrollo-wrap {
    max-width: 1200px;
    margin: 0 auto;
  }
  .ruta-container {
    margin-top: 3.5rem;
    position: relative;
  }
  .ruta-line {
    position: absolute;
    top: 32px;
    left: 5%;
    right: 5%;
    height: 3px;
    background: linear-gradient(90deg, var(--rojo) 0%, var(--dorado) 50%, var(--verde-exito) 100%);
    border-radius: 2px;
  }
  .ruta-steps {
    display: flex;
    justify-content: space-between;
    position: relative;
    z-index: 1;
  }
  .ruta-step {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 18%;
    text-align: center;
  }
  .ruta-circle {
    width: 64px; height: 64px;
    border-radius: 50%;
    background: white;
    border: 3px solid var(--rojo);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 1.5rem;
    margin-bottom: 1.25rem;
    transition: all 0.3s;
    cursor: default;
    box-shadow: 0 4px 20px rgba(215,38,56,0.15);
  }
  .ruta-step:nth-child(2) .ruta-circle { border-color: #F4A018; box-shadow: 0 4px 20px rgba(244,160,24,0.2); }
  .ruta-step:nth-child(3) .ruta-circle { border-color: #5B6AF0; box-shadow: 0 4px 20px rgba(91,106,240,0.2); }
  .ruta-step:nth-child(4) .ruta-circle { border-color: var(--verde-exito); box-shadow: 0 4px 20px rgba(45,125,70,0.2); }
  .ruta-step:nth-child(5) .ruta-circle { border-color: #9B59B6; box-shadow: 0 4px 20px rgba(155,89,182,0.2); }
  .ruta-circle:hover { transform: scale(1.1); }
  .ruta-step h4 {
    font-weight: 700;
    font-size: 0.9rem;
    color: var(--carbón);
    margin-bottom: 0.35rem;
  }
  .ruta-step p {
    font-size: 0.78rem;
    color: var(--gris-medio);
    line-height: 1.5;
  }
  .programas-extra {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1.5rem;
    margin-top: 4rem;
  }
  .extra-card {
    background: white;
    border-radius: 10px;
    padding: 1.75rem;
    border: 1px solid var(--crema-oscuro);
    transition: all 0.25s;
  }
  .extra-card:hover { transform: translateY(-4px); box-shadow: 0 12px 40px rgba(0,0,0,0.08); }
  .extra-card .badge {
    display: inline-block;
    background: rgba(215,38,56,0.08);
    color: var(--rojo);
    font-size: 0.7rem;
    font-weight: 700;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    padding: 0.25rem 0.6rem;
    border-radius: 3px;
    margin-bottom: 0.75rem;
  }
  .extra-card h4 {
    font-family: 'Playfair Display', serif;
    font-size: 1.1rem;
    font-weight: 800;
    color: var(--carbón);
    margin-bottom: 0.5rem;
  }
  .extra-card p {
    font-size: 0.84rem;
    color: var(--gris-medio);
    line-height: 1.6;
  }

  /* ─── RECONOCIMIENTO ─── */
  #reconocimiento {
    background: var(--blanco);
    padding: 8rem 2rem;
  }
  .reconocimiento-wrap {
    max-width: 1200px;
    margin: 0 auto;
  }
  .recono-grid {
    display: grid;
    grid-template-columns: 1.5fr 1fr;
    gap: 3rem;
    margin-top: 3.5rem;
    align-items: start;
  }
  .recono-programs {
    display: flex;
    flex-direction: column;
    gap: 1.25rem;
  }
  .recono-item {
    display: flex;
    gap: 1.25rem;
    align-items: flex-start;
    padding: 1.5rem;
    border-radius: 10px;
    background: var(--crema);
    border: 1px solid transparent;
    transition: all 0.25s;
    cursor: default;
  }
  .recono-item:hover { border-color: var(--dorado); background: var(--crema-oscuro); }
  .recono-num {
    font-family: 'Playfair Display', serif;
    font-size: 2rem;
    font-weight: 900;
    color: var(--dorado);
    flex-shrink: 0;
    line-height: 1;
    width: 2rem;
    text-align: center;
  }
  .recono-item h4 {
    font-weight: 700;
    font-size: 1rem;
    color: var(--carbón);
    margin-bottom: 0.3rem;
  }
  .recono-item p {
    font-size: 0.84rem;
    color: var(--gris-medio);
    line-height: 1.55;
  }
  .cultura-box {
    background: linear-gradient(160deg, var(--rojo) 0%, var(--rojo-oscuro) 100%);
    border-radius: 16px;
    padding: 2.5rem;
    color: white;
    position: relative;
    overflow: hidden;
  }
  .cultura-box::before {
    content: '"';
    position: absolute;
    top: -1rem;
    left: 1.5rem;
    font-family: 'Playfair Display', serif;
    font-size: 12rem;
    font-weight: 900;
    color: rgba(255,255,255,0.07);
    line-height: 1;
  }
  .cultura-box h3 {
    font-family: 'Playfair Display', serif;
    font-size: 1.5rem;
    font-weight: 800;
    margin-bottom: 1.25rem;
    position: relative;
    z-index: 1;
  }
  .cultura-box blockquote {
    font-size: 1rem;
    font-style: italic;
    line-height: 1.7;
    color: rgba(255,255,255,0.9);
    margin-bottom: 1.5rem;
    position: relative;
    z-index: 1;
  }
  .cultura-values {
    display: flex;
    flex-direction: column;
    gap: 0.75rem;
    position: relative;
    z-index: 1;
  }
  .cv-item {
    display: flex;
    align-items: center;
    gap: 0.75rem;
    font-size: 0.85rem;
    font-weight: 500;
  }
  .cv-dot {
    width: 8px; height: 8px;
    border-radius: 50%;
    background: var(--dorado);
    flex-shrink: 0;
  }

  /* ─── IMPACTO ─── */
  #impacto {
    background: var(--crema-oscuro);
    padding: 8rem 2rem;
  }
  .impacto-wrap { max-width: 1200px; margin: 0 auto; }
  .stats-mega {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 1.5rem;
    margin-top: 3.5rem;
  }
  .stat-mega-card {
    background: white;
    border-radius: 12px;
    padding: 2rem 1.5rem;
    text-align: center;
    border-bottom: 4px solid var(--rojo);
    transition: all 0.3s;
  }
  .stat-mega-card:hover { transform: translateY(-6px); box-shadow: 0 20px 50px rgba(0,0,0,0.1); }
  .stat-mega-card:nth-child(2) { border-bottom-color: var(--dorado); }
  .stat-mega-card:nth-child(3) { border-bottom-color: var(--verde-exito); }
  .stat-mega-card:nth-child(4) { border-bottom-color: #5B6AF0; }
  .stat-number {
    font-family: 'Playfair Display', serif;
    font-size: 3rem;
    font-weight: 900;
    color: var(--carbón);
    line-height: 1;
  }
  .stat-unit { font-size: 1.5rem; }
  .stat-label {
    font-size: 0.82rem;
    color: var(--gris-medio);
    margin-top: 0.5rem;
    font-weight: 500;
    letter-spacing: 0.04em;
    line-height: 1.4;
  }
  .impacto-text {
    margin-top: 4rem;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 3rem;
    align-items: start;
  }
  .impacto-col h3 {
    font-family: 'Playfair Display', serif;
    font-size: 1.5rem;
    font-weight: 800;
    color: var(--carbón);
    margin-bottom: 1.25rem;
    display: flex;
    align-items: center;
    gap: 0.75rem;
  }
  .impacto-col h3 span {
    width: 36px; height: 36px;
    border-radius: 8px;
    background: var(--rojo);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 1.1rem;
    flex-shrink: 0;
  }
  .impacto-col:nth-child(2) h3 span { background: var(--verde-exito); }
  .impact-list {
    list-style: none;
    display: flex;
    flex-direction: column;
    gap: 0.9rem;
  }
  .impact-list li {
    display: flex;
    gap: 0.9rem;
    align-items: flex-start;
    font-size: 0.9rem;
    color: var(--gris-oscuro);
    line-height: 1.6;
    padding: 0.75rem;
    border-radius: 8px;
    background: white;
    border: 1px solid var(--crema-oscuro);
  }
  .impact-list li .li-icon {
    flex-shrink: 0;
    font-size: 1.1rem;
    margin-top: 0.05em;
  }

  /* ─── SEDES ─── */
  #sedes {
    background: var(--carbón);
    padding: 8rem 2rem;
    color: white;
  }
  #sedes .section-title { color: white; }
  #sedes .section-lead { color: var(--gris-claro); }
  .sedes-intro { max-width: 1200px; margin: 0 auto; }
  .sedes-grid {
    max-width: 1200px;
    margin: 3.5rem auto 0;
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1.5rem;
  }
  .sede-card {
    background: rgba(255,255,255,0.04);
    border: 1px solid rgba(255,255,255,0.07);
    border-radius: 12px;
    overflow: hidden;
    transition: all 0.3s;
  }
  .sede-card:hover {
    background: rgba(215,38,56,0.07);
    border-color: rgba(215,38,56,0.25);
    transform: translateY(-4px);
  }
  .sede-header {
    padding: 1.5rem;
    background: rgba(255,255,255,0.03);
    border-bottom: 1px solid rgba(255,255,255,0.06);
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
  .sede-header h4 {
    font-family: 'Playfair Display', serif;
    font-size: 1.2rem;
    font-weight: 800;
    color: white;
    display: flex;
    align-items: center;
    gap: 0.6rem;
  }
  .sede-badge {
    font-size: 0.65rem;
    background: rgba(215,38,56,0.3);
    color: #FF9AA5;
    padding: 0.2rem 0.5rem;
    border-radius: 3px;
    font-weight: 700;
    letter-spacing: 0.08em;
    text-transform: uppercase;
  }
  .sede-badge.hq { background: rgba(244,160,24,0.3); color: var(--dorado-claro); }
  .sede-body {
    padding: 1.5rem;
  }
  .sede-body ul { list-style: none; }
  .sede-body li {
    font-size: 0.82rem;
    color: rgba(201,185,154,0.85);
    padding: 0.4rem 0;
    display: flex;
    gap: 0.6rem;
    align-items: flex-start;
    line-height: 1.4;
    border-bottom: 1px solid rgba(255,255,255,0.04);
  }
  .sede-body li:last-child { border-bottom: none; }
  .sede-body li::before { content: '→'; color: var(--dorado); flex-shrink: 0; }
  .sedes-model {
    max-width: 1200px;
    margin: 3rem auto 0;
    background: rgba(255,255,255,0.03);
    border: 1px solid rgba(255,255,255,0.06);
    border-radius: 12px;
    padding: 2.5rem;
  }
  .sedes-model h3 {
    font-family: 'Playfair Display', serif;
    font-size: 1.4rem;
    font-weight: 800;
    color: white;
    margin-bottom: 1.5rem;
  }
  .model-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 1.25rem;
  }
  .model-item {
    text-align: center;
  }
  .model-icon {
    width: 52px; height: 52px;
    border-radius: 50%;
    background: rgba(244,160,24,0.12);
    margin: 0 auto 0.75rem;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 1.4rem;
  }
  .model-item h5 {
    font-weight: 700;
    font-size: 0.9rem;
    color: var(--dorado-claro);
    margin-bottom: 0.35rem;
  }
  .model-item p {
    font-size: 0.78rem;
    color: var(--gris-claro);
    line-height: 1.5;
  }

  /* ─── CTA FINAL ─── */
  #cta {
    background: linear-gradient(160deg, var(--rojo-oscuro) 0%, #800015 50%, var(--carbón) 100%);
    padding: 8rem 2rem;
    text-align: center;
    position: relative;
    overflow: hidden;
  }
  #cta::before {
    content: '';
    position: absolute;
    inset: 0;
    background:
      radial-gradient(ellipse 60% 50% at 50% 0%, rgba(244,160,24,0.12) 0%, transparent 70%),
      repeating-linear-gradient(-45deg, transparent, transparent 40px, rgba(255,255,255,0.01) 40px, rgba(255,255,255,0.01) 41px);
  }
  .cta-inner {
    position: relative;
    z-index: 1;
    max-width: 700px;
    margin: 0 auto;
  }
  .cta-label {
    font-family: 'DM Mono', monospace;
    font-size: 0.72rem;
    letter-spacing: 0.25em;
    color: var(--dorado);
    text-transform: uppercase;
    margin-bottom: 1.5rem;
  }
  .cta-title {
    font-family: 'Playfair Display', serif;
    font-size: clamp(2.5rem, 5vw, 4.5rem);
    font-weight: 900;
    color: white;
    line-height: 1.1;
    margin-bottom: 1.5rem;
  }
  .cta-sub {
    font-size: 1.1rem;
    color: rgba(255,255,255,0.75);
    line-height: 1.65;
    margin-bottom: 2.5rem;
  }
  .cta-chips {
    display: flex;
    flex-wrap: wrap;
    gap: 0.75rem;
    justify-content: center;
    margin-bottom: 3rem;
  }
  .chip {
    background: rgba(255,255,255,0.1);
    color: rgba(255,255,255,0.85);
    padding: 0.5rem 1.1rem;
    border-radius: 20px;
    font-size: 0.82rem;
    font-weight: 500;
    border: 1px solid rgba(255,255,255,0.12);
    backdrop-filter: blur(5px);
  }
  .chip:hover { background: rgba(244,160,24,0.2); border-color: var(--dorado); color: var(--dorado-claro); transition: all 0.2s; }

  /* ─── FOOTER ─── */
  footer {
    background: #0D0800;
    padding: 3rem 2rem;
    border-top: 2px solid rgba(215,38,56,0.3);
  }
  .footer-inner {
    max-width: 1200px;
    margin: 0 auto;
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-wrap: wrap;
    gap: 1rem;
  }
  .footer-logo {
    font-family: 'Playfair Display', serif;
    font-size: 1.5rem;
    font-weight: 900;
    color: white;
  }
  .footer-logo span { color: var(--dorado); }
  .footer-copy {
    font-size: 0.8rem;
    color: var(--gris-claro);
    text-align: center;
  }
  .footer-links {
    display: flex;
    gap: 1.5rem;
  }
  .footer-links a {
    font-size: 0.78rem;
    color: var(--gris-claro);
    text-decoration: none;
    transition: color 0.2s;
  }
  .footer-links a:hover { color: var(--dorado); }

  /* ─── RESPONSIVE ─── */
  @media (max-width: 900px) {
    .welcome-grid, .salario-intro, .recono-grid, .impacto-text { grid-template-columns: 1fr; }
    .valores-grid, .pilares-grid, .stats-mega, .programas-extra, .model-grid { grid-template-columns: 1fr 1fr; }
    .sedes-grid { grid-template-columns: 1fr; }
    .ruta-steps { flex-wrap: wrap; gap: 2rem; }
    .ruta-line { display: none; }
    .ruta-step { width: 40%; }
    .programa-card.featured { grid-column: auto; grid-template-columns: 1fr; }
    .nav-links { display: none; }
    .timeline::before { left: 1.5rem; }
    .timeline-item, .timeline-item:nth-child(odd) { flex-direction: column; }
    .tl-year, .timeline-item:nth-child(odd) .tl-year { width: 100%; justify-content: flex-start; padding-left: 3.5rem; }
    .tl-content, .timeline-item:nth-child(odd) .tl-content { width: 100%; padding-left: 3.5rem; text-align: left; }
    .tl-dot { left: 1.5rem; }
    .programas-grid { grid-template-columns: 1fr; }
  }
  @media (max-width: 600px) {
    .valores-grid, .stats-mega, .programas-extra, .model-grid { grid-template-columns: 1fr; }
    .ruta-step { width: 80%; }
    .mission-vision-grid { grid-template-columns: 1fr; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="nav-logo">POSTO<span>COLA</span></div>
  <ul class="nav-links">
    <li><a href="#bienvenida">Inicio</a></li>
    <li><a href="#historia">Historia</a></li>
    <li><a href="#salario">Salario Emocional</a></li>
    <li><a href="#bienestar">Bienestar</a></li>
    <li><a href="#desarrollo">Desarrollo</a></li>
    <li><a href="#impacto">Impacto</a></li>
  </ul>
  <div class="nav-badge">Onboarding 2025</div>
</nav>

<!-- HERO -->
<section class="hero" id="inicio">
  <div class="hero-bg"></div>
  <div class="hero-bubbles" id="bubbles"></div>

  <div class="hero-eyebrow">Manual de Onboarding — Postocola S.A.</div>
  <h1 class="hero-title">
    Bienvenido a tu<br>
    nuevo <span class="accent">mundo</span><br>
    <span class="gold">con sabor.</span>
  </h1>
  <p class="hero-subtitle">
    Decidiste unirte a una empresa que lleva más de 55 años refrescando a Colombia.
    Aquí no solo trabajas: <strong style="color:white">creces, perteneces y te transformas.</strong>
  </p>

  <div class="hero-stat-row">
    <div class="hero-stat">
      <span class="hero-stat-number">4.500</span>
      <span class="hero-stat-label">Colaboradores</span>
    </div>
    <div class="hero-stat">
      <span class="hero-stat-number">7</span>
      <span class="hero-stat-label">Sedes Regionales</span>
    </div>
    <div class="hero-stat">
      <span class="hero-stat-number">40%</span>
      <span class="hero-stat-label">Del Mercado Nacional</span>
    </div>
    <div class="hero-stat">
      <span class="hero-stat-number">+10%</span>
      <span class="hero-stat-label">Sobre el Mercado Salarial</span>
    </div>
  </div>

  <div class="hero-cta">
    <a href="#bienvenida" class="btn-primary">Comenzar mi historia</a>
    <a href="#salario" class="btn-secondary">Ver beneficios</a>
  </div>

  <div class="hero-scroll">
    <span>Descubre más</span>
    <div class="scroll-line"></div>
  </div>
</section>

<!-- BIENVENIDA -->
<section id="bienvenida">
  <div class="welcome-grid">
    <div class="welcome-visual">
      <div class="welcome-card-main">
        <h3>La empresa que te eligió entre cinco finalistas.</h3>
        <p>Y no fue casualidad.</p>
      </div>
      <div class="welcome-card-secondary">
        <div class="year">1969</div>
        <p>Fundada por Julio Mario Ardila y Carlos Santodomingo. Más de medio siglo liderando el sector de bebidas en Colombia.</p>
      </div>
      <div class="welcome-badge">🏆 Premio Nacional de Calidad 2012 & 2022</div>
    </div>
    <div class="welcome-text">
      <div class="section-label">Bienvenida</div>
      <h2 class="section-title">Este es tu<br>primer día de<br>muchos éxitos.</h2>
      <p class="section-lead">
        En Postocola creemos que cada persona que entra por nuestra puerta trae consigo talento, historia y propósito. Hoy empieza un capítulo nuevo: el tuyo.
      </p>
      <div class="mission-vision-grid">
        <div class="mv-card">
          <h4>🎯 Misión</h4>
          <p>Fabricar y comercializar bebidas dulces e hidratantes que generen experiencias memorables, con calidad, sostenibilidad y orgullo colombiano.</p>
        </div>
        <div class="mv-card vision">
          <h4>🔭 Visión</h4>
          <p>Ser en 2030 la empresa de bebidas más admirada de Latinoamérica, reconocida por su cultura de personas y excelencia operativa.</p>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- HISTORIA -->
<section id="historia">
  <div style="max-width:1200px; margin:0 auto;">
    <div class="section-label">Nuestra historia</div>
    <h2 class="section-title">De una idea a<br>una nación refrescada.</h2>
    <p class="section-lead">Conocer de dónde venimos nos recuerda por qué hacemos lo que hacemos.</p>
  </div>

  <div class="timeline">
    <div class="timeline-item">
      <div class="tl-year"><div class="tl-year-label">1969</div></div>
      <div class="tl-dot"></div>
      <div class="tl-content">
        <div class="tl-tag gold">Fundación</div>
        <h4>Nace Postocola S.A.</h4>
        <p>Julio Mario Ardila y Carlos Santodomingo fundan en agosto la empresa, con una visión clara: refrescar a Colombia con bebidas de calidad.</p>
      </div>
    </div>
    <div class="timeline-item">
      <div class="tl-year"><div class="tl-year-label">1988</div></div>
      <div class="tl-dot"></div>
      <div class="tl-content">
        <div class="tl-tag">Sindicato</div>
        <h4>Nace SINTRAPOSTOCOLA</h4>
        <p>Se funda el sindicato de trabajadores. Hoy el 70% del personal está afiliado, con convención colectiva vigente que garantiza los más altos estándares laborales.</p>
      </div>
    </div>
    <div class="timeline-item">
      <div class="tl-year"><div class="tl-year-label">1993</div></div>
      <div class="tl-dot"></div>
      <div class="tl-content">
        <div class="tl-tag">Reto</div>
        <h4>La gran prueba</h4>
        <p>Una grave crisis financiera puso en riesgo la continuidad de la empresa. La resiliencia del equipo humano fue clave para superar el momento más difícil.</p>
      </div>
    </div>
    <div class="timeline-item">
      <div class="tl-year"><div class="tl-year-label">1994</div></div>
      <div class="tl-dot"></div>
      <div class="tl-content">
        <div class="tl-tag gold">Alianza</div>
        <h4>Alianza con INCAKOLA</h4>
        <p>La empresa peruana INCAKOLA inyecta capital estratégico. Postocola conserva el 52% de capital nacional y retoma su camino hacia el liderazgo.</p>
      </div>
    </div>
    <div class="timeline-item">
      <div class="tl-year"><div class="tl-year-label">2012</div></div>
      <div class="tl-dot"></div>
      <div class="tl-content">
        <div class="tl-tag green">Reconocimiento</div>
        <h4>Premio Nacional de Calidad</h4>
        <p>Primer reconocimiento en la categoría grandes empresas. Una validación del compromiso con la excelencia operativa y el talento humano.</p>
      </div>
    </div>
    <div class="timeline-item">
      <div class="tl-year"><div class="tl-year-label">2022</div></div>
      <div class="tl-dot"></div>
      <div class="tl-content">
        <div class="tl-tag green">Reconocimiento</div>
        <h4>Premio Nacional de Calidad (bis)</h4>
        <p>Postocola repite el galardón una década después, demostrando que la calidad no fue un momento sino una cultura permanente.</p>
      </div>
    </div>
    <div class="timeline-item">
      <div class="tl-year"><div class="tl-year-label">Hoy</div></div>
      <div class="tl-dot"></div>
      <div class="tl-content">
        <div class="tl-tag gold">¡Tú!</div>
        <h4>Tu capítulo comienza</h4>
        <p>Con 40% del mercado nacional, 4.500 colaboradores y presencia en 7 ciudades, el próximo gran hito de Postocola lo escribiremos contigo.</p>
      </div>
    </div>
  </div>
</section>

<!-- VALORES -->
<section id="valores">
  <div class="valores-header">
    <div class="section-label">Nuestro ADN</div>
    <h2 class="section-title">Los valores que nos<br>mueven cada día.</h2>
    <p class="section-lead">No son frases en una pared. Son comportamientos que verás cada mañana en Postocola.</p>
  </div>
  <div class="valores-grid">
    <div class="valor-card">
      <span class="valor-emoji">🔥</span>
      <h3>Pasión</h3>
      <p>Hacemos lo que hacemos con toda el alma. Cada botella, cada proceso, cada conversación lleva el sello de quien disfruta genuinamente su trabajo.</p>
    </div>
    <div class="valor-card">
      <span class="valor-emoji">🤝</span>
      <h3>Integridad</h3>
      <p>Actuamos con honestidad y coherencia. Lo que decimos, lo hacemos. Frente a todos y también cuando nadie mira.</p>
    </div>
    <div class="valor-card">
      <span class="valor-emoji">🌱</span>
      <h3>Sostenibilidad</h3>
      <p>Pensamos en el planeta y en las generaciones que vienen. Nuestras operaciones respetan el entorno natural y social de Colombia.</p>
    </div>
    <div class="valor-card">
      <span class="valor-emoji">🚀</span>
      <h3>Innovación</h3>
      <p>El mercado cambia, los consumidores evolucionan y nosotros también. Aquí las ideas nuevas no se frenan: se prueban, se mejoran y se lanzan.</p>
    </div>
    <div class="valor-card">
      <span class="valor-emoji">🧩</span>
      <h3>Trabajo en Equipo</h3>
      <p>Nuestros 4.500 colaboradores son la mayor fortaleza competitiva. Cada logro es colectivo, cada celebración también.</p>
    </div>
    <div class="valor-card">
      <span class="valor-emoji">🏆</span>
      <h3>Excelencia</h3>
      <p>Hemos ganado el Premio Nacional de Calidad dos veces porque la mediocridad no tiene espacio aquí. Hacemos lo ordinario de forma extraordinaria.</p>
    </div>
    <div class="valor-card">
      <span class="valor-emoji">❤️</span>
      <h3>Orgullo Nacional</h3>
      <p>Conservamos el 52% de capital colombiano con propósito. Somos parte del tejido productivo del país y lo llevamos con orgullo.</p>
    </div>
    <div class="valor-card">
      <span class="valor-emoji">👥</span>
      <h3>Personas Primero</h3>
      <p>Antes que cualquier estrategia o indicador, están las personas. Nuestros colaboradores son la razón por la que Postocola existe y perdura.</p>
    </div>
  </div>
</section>

<!-- SALARIO EMOCIONAL -->
<section id="salario">
  <div class="salario-intro">
    <div class="salario-visual">
      <div class="salary-compare">
        <div class="salary-label-top">Tu <span>compensación total</span> en Postocola</div>
        <div class="salary-row">
          <div class="salary-row-label">Mercado promedio</div>
          <div class="salary-bar-wrap"><div class="salary-bar mercado"></div></div>
          <div class="salary-value">100%</div>
        </div>
        <div class="salary-row">
          <div class="salary-row-label">Salario Postocola</div>
          <div class="salary-bar-wrap"><div class="salary-bar postocola"></div></div>
          <div class="salary-value highlight">+10%</div>
        </div>
        <div class="salary-row">
          <div class="salary-row-label">Comp. Total con<br>Salario Emocional</div>
          <div class="salary-bar-wrap"><div class="salary-bar emocional"></div></div>
          <div class="salary-value highlight">∞</div>
        </div>
        <p class="salary-note">
          El salario económico ya está 10% sobre la mediana del mercado en el 80% de los cargos.
          El salario emocional es lo que hace que te quieras quedar décadas.
        </p>
      </div>
    </div>
    <div>
      <div class="section-label">Salario Emocional</div>
      <h2 class="section-title">Más que un sueldo.<br>Una experiencia<br>de vida.</h2>
      <p class="section-lead">
        En Postocola entendemos que el dinero importa, pero no es todo. Diseñamos una propuesta de valor integral que toca cada dimensión de tu vida: personal, familiar, profesional y emocional.
      </p>
      <p style="font-size:0.9rem; color:var(--gris-medio); margin-top:1rem; line-height:1.7;">
        Nuestra filosofía de compensación total parte de una premisa simple: <strong>un colaborador pleno produce más, innova más y permanece más</strong>. Por eso invertimos en ti más allá del número en tu cuenta bancaria.
      </p>
    </div>
  </div>

  <div class="pilares-grid">
    <!-- BIENESTAR -->
    <div class="pilar-card">
      <div class="pilar-header">
        <div class="pilar-icon r">🧘</div>
        <div>
          <h3>Bienestar Laboral</h3>
          <p>Cuerpo, mente y espíritu</p>
        </div>
      </div>
      <div class="pilar-body">
        <ul>
          <li>Programa <strong>PostoVida</strong>: salud mental con psicólogos disponibles en todas las sedes</li>
          <li>Gimnasio corporativo o subsidio de gym en sedes donde no aplica</li>
          <li>Jornadas de mindfulness y pausas activas lideradas por bienestar</li>
          <li>Convenio médico ampliado con dentista, optómetra y nutricionista</li>
          <li>Semana de bienestar anual con actividades recreativas y culturales</li>
        </ul>
        <div class="pilar-highlight">💡 "PostoVida" ha reducido en un 34% el ausentismo por estrés en las sedes piloto</div>
      </div>
    </div>
    <!-- EQUILIBRIO -->
    <div class="pilar-card">
      <div class="pilar-header">
        <div class="pilar-icon g">⚖️</div>
        <div>
          <h3>Equilibrio Vida-Trabajo</h3>
          <p>Tu tiempo también es tuyo</p>
        </div>
      </div>
      <div class="pilar-body">
        <ul>
          <li>Política de trabajo híbrido para roles que lo permiten (2 días/semana desde casa)</li>
          <li>Viernes flex: salida a las 2 p.m. en el último viernes de cada mes</li>
          <li>Día de cumpleaños libre remunerado para cargos asistenciales y superiores</li>
          <li>Licencias ampliadas de maternidad, paternidad y cuidado familiar</li>
          <li>Modelo de reuniones eficientes: no se agenda nada después de las 5:30 p.m.</li>
        </ul>
        <div class="pilar-highlight">💡 El 91% de nuestros colaboradores afirma sentir que Postocola respeta su vida personal</div>
      </div>
    </div>
    <!-- INCENTIVOS -->
    <div class="pilar-card">
      <div class="pilar-header">
        <div class="pilar-icon b">🎁</div>
        <div>
          <h3>Incentivos No Monetarios</h3>
          <p>Lo que no se compra con dinero</p>
        </div>
      </div>
      <div class="pilar-body">
        <ul>
          <li><strong>PostoBox</strong>: caja mensual con productos Postocola + sorpresa para tu familia</li>
          <li>Parqueadero gratuito y biciparqueadero con vestieres en todas las plantas</li>
          <li>Casino corporativo con subsidio del 40% en el almuerzo</li>
          <li>Convenio de precios con más de 80 marcas aliadas (cine, viajes, tecnología)</li>
          <li>Acceso preferencial a eventos culturales y deportivos patrocinados por la empresa</li>
        </ul>
        <div class="pilar-highlight">💡 PostoBox tiene un NPS interno de 94/100 — el beneficio más valorado por nuestros colaboradores</div>
      </div>
    </div>
    <!-- DESARROLLO -->
    <div class="pilar-card">
      <div class="pilar-header">
        <div class="pilar-icon gr">📈</div>
        <div>
          <h3>Desarrollo Profesional</h3>
          <p>Tu crecimiento es nuestra inversión</p>
        </div>
      </div>
      <div class="pilar-body">
        <ul>
          <li>Universidad Corporativa PostoLearn: cursos online, presenciales y certificaciones</li>
          <li>Subsidio del 70% para posgrados y especializaciones relacionadas con el cargo</li>
          <li>Programa de movilidad interna: aplica a vacantes en cualquier sede del país</li>
          <li>Mentoring ejecutivo: colaboradores talento son asignados a un mentor directivo</li>
          <li>Plan de carrera estructurado con revisión semestral y mapa de crecimiento</li>
        </ul>
        <div class="pilar-highlight">💡 El 78% de nuestras vacantes directivas se llenan con talento interno</div>
      </div>
    </div>
    <!-- RECONOCIMIENTO -->
    <div class="pilar-card">
      <div class="pilar-header">
        <div class="pilar-icon p">⭐</div>
        <div>
          <h3>Reconocimiento</h3>
          <p>Aquí cada logro cuenta</p>
        </div>
      </div>
      <div class="pilar-body">
        <ul>
          <li><strong>Estrellas Postocola</strong>: sistema de puntos por logros canjeables en catálogo</li>
          <li>Colaborador del mes con reconocimiento en pantallas digitales y premio tangible</li>
          <li>Ceremonia anual "Los PostoPremios": premiación por categorías ante toda la empresa</li>
          <li>Muro de la fama digital en la intranet con historias de colaboradores destacados</li>
          <li>Carta firmada por el Presidente a los 5, 10, 15 y 20 años de antigüedad</li>
        </ul>
        <div class="pilar-highlight">💡 Los colaboradores reconocidos tienen 2.4x más probabilidad de permanecer en la empresa</div>
      </div>
    </div>
    <!-- FAMILIA -->
    <div class="pilar-card">
      <div class="pilar-header">
        <div class="pilar-icon t">👨‍👩‍👧</div>
        <div>
          <h3>Familia Postocola</h3>
          <p>Tu familia también es nuestra familia</p>
        </div>
      </div>
      <div class="pilar-body">
        <ul>
          <li>Auxilio de educación para hijos (preescolar hasta universitario) con proceso de aplicación anual</li>
          <li>Día de la familia Postocola: jornada anual en parques recreativos con toda la familia</li>
          <li>Seguro de vida ampliado que cubre cónyuge e hijos</li>
          <li>Fondo de empleados con créditos preferenciales, ahorro programado y auxilios</li>
          <li>Programa PostoBebé: kit de bienvenida al bebé + día libre adicional para ambos padres</li>
        </ul>
        <div class="pilar-highlight">💡 El 68% de nuestros colaboradores con familia dice que los beneficios familiares son la razón principal por la que no se irían</div>
      </div>
    </div>
  </div>
</section>

<!-- BIENESTAR -->
<section id="bienestar">
  <div class="bienestar-intro">
    <div class="section-label">Programas de Bienestar</div>
    <h2 class="section-title">Postocola cuida<br>a las personas que<br>cuidan la empresa.</h2>
    <p class="section-lead">Bienestar no es un departamento. Es la forma en que operamos.</p>
  </div>

  <div class="programas-grid">
    <div class="programa-card featured">
      <div>
        <div class="programa-top">
          <div class="prog-icon">🏥</div>
          <span class="prog-tag gold">Programa Insignia</span>
        </div>
        <h4>PostoVida 360°</h4>
        <p>Nuestro programa de bienestar integral que aborda la salud física, mental y financiera de cada colaborador. Un equipo de profesionales de la salud disponible en todas las sedes, con modalidad presencial y virtual.</p>
      </div>
      <ul>
        <li>Psicólogo empresarial: 4 sesiones gratuitas/año por colaborador</li>
        <li>Coach financiero: asesoría para manejo de deudas y ahorro</li>
        <li>Nutricionista: plan alimentario personalizado semestral</li>
        <li>Médico laboral: chequeos preventivos anuales incluidos</li>
        <li>Línea de crisis 24/7: apoyo emocional en momentos difíciles</li>
      </ul>
    </div>

    <div class="programa-card">
      <div class="programa-top">
        <div class="prog-icon">🏃</div>
        <span class="prog-tag new">Nuevo 2025</span>
      </div>
      <h4>PostoFit</h4>
      <p>Convenio con gimnasios en todo el país + pausas activas diarias de 10 minutos lideradas por monitores deportivos certificados. El movimiento como parte del horario laboral.</p>
    </div>

    <div class="programa-card">
      <div class="programa-top">
        <div class="prog-icon">🧠</div>
        <span class="prog-tag">Bienestar Mental</span>
      </div>
      <h4>Mente Sana Postocola</h4>
      <p>Talleres mensuales de manejo del estrés, resiliencia y comunicación asertiva. En alianza con la Universidad de los Andes para formación de líderes bienestar en cada área.</p>
    </div>

    <div class="programa-card">
      <div class="programa-top">
        <div class="prog-icon">💰</div>
        <span class="prog-tag gold">Finanzas</span>
      </div>
      <h4>PostoFinanzas</h4>
      <p>Educación financiera práctica para todos los niveles. Desde cómo ahorrar el primer millón hasta cómo planear la jubilación. Sin jerga, sin letras pequeñas.</p>
    </div>

    <div class="programa-card">
      <div class="programa-top">
        <div class="prog-icon">🌿</div>
        <span class="prog-tag new">Eco</span>
      </div>
      <h4>PostoVerde</h4>
      <p>Voluntariado ambiental, siembra de árboles y jornadas de limpieza en las ciudades donde operamos. Porque cuidar el planeta también hace feliz a la gente.</p>
    </div>

    <div class="programa-card">
      <div class="programa-top">
        <div class="prog-icon">🎓</div>
        <span class="prog-tag">Comunidad</span>
      </div>
      <h4>PostoSocial</h4>
      <p>Programa de voluntariado comunitario donde cada colaborador puede donar hasta 8 horas laborales al año para causas sociales sin descontar de sus vacaciones.</p>
    </div>
  </div>
</section>

<!-- DESARROLLO -->
<section id="desarrollo">
  <div class="desarrollo-wrap">
    <div class="section-label">Desarrollo & Carrera</div>
    <h2 class="section-title">Tu ruta de<br>crecimiento empieza hoy.</h2>
    <p class="section-lead">
      En Postocola nadie se queda estancado. Existe un camino claro de evolución para cada persona, sin importar el área ni el nivel de entrada.
    </p>

    <div class="ruta-container">
      <div class="ruta-line"></div>
      <div class="ruta-steps">
        <div class="ruta-step">
          <div class="ruta-circle">🌱</div>
          <h4>Incorporación</h4>
          <p>Primeros 90 días<br>Onboarding, inducción técnica, asignación de mentor</p>
        </div>
        <div class="ruta-step">
          <div class="ruta-circle">📚</div>
          <h4>Aprendizaje</h4>
          <p>Meses 3–12<br>PostoLearn, cursos del área, certificaciones internas</p>
        </div>
        <div class="ruta-step">
          <div class="ruta-circle">⚡</div>
          <h4>Desempeño</h4>
          <p>Año 1–3<br>Evaluaciones semestrales, objetivos SMART, bonos por metas</p>
        </div>
        <div class="ruta-step">
          <div class="ruta-circle">🔑</div>
          <h4>Talento Clave</h4>
          <p>Año 3–5<br>Programa de HiPos, mentoría ejecutiva, proyectos especiales</p>
        </div>
        <div class="ruta-step">
          <div class="ruta-circle">🏆</div>
          <h4>Liderazgo</h4>
          <p>Año 5+<br>Promoción interna, gestión de equipos, visibilidad en el negocio</p>
        </div>
      </div>
    </div>

    <div class="programas-extra">
      <div class="extra-card">
        <span class="badge">Formación</span>
        <h4>PostoLearn</h4>
        <p>Plataforma LMS con más de 400 cursos online en idiomas, habilidades blandas, técnicas del sector y liderazgo. Disponible 24/7 desde cualquier dispositivo.</p>
      </div>
      <div class="extra-card">
        <span class="badge">Educación</span>
        <h4>Subsidio Posgrado</h4>
        <p>Cofinanciación del 70% para especializaciones, maestrías y certificaciones externas relacionadas con el cargo. Aplica a universidades acreditadas del país.</p>
      </div>
      <div class="extra-card">
        <span class="badge">Liderazgo</span>
        <h4>Escuela de Líderes</h4>
        <p>Programa presencial de 6 meses para mandos medios y directivos. Metodología experiencial, simuladores de negocio y aprendizaje entre pares internos.</p>
      </div>
      <div class="extra-card">
        <span class="badge">Movilidad</span>
        <h4>Bolsa Interna</h4>
        <p>Antes de abrir cualquier vacante al mercado, se publica internamente. El 78% de los cargos directivos de Postocola están ocupados por talento que creció dentro.</p>
      </div>
      <div class="extra-card">
        <span class="badge">Idiomas</span>
        <h4>PostoEnglish</h4>
        <p>Clases de inglés subvencionadas (80%) para todos los niveles. Grupos presenciales en sedes principales y modalidad virtual para plantas y regionales.</p>
      </div>
      <div class="extra-card">
        <span class="badge">Innovación</span>
        <h4>PostoLab</h4>
        <p>Espacio de innovación interna donde cualquier colaborador puede presentar ideas de mejora. Las ideas implementadas generan reconocimiento y una bonificación especial.</p>
      </div>
    </div>
  </div>
</section>

<!-- RECONOCIMIENTO -->
<section id="reconocimiento">
  <div class="reconocimiento-wrap">
    <div class="section-label">Reconocimiento & Cultura</div>
    <h2 class="section-title">Aquí tu trabajo<br>siempre se ve.</h2>
    <p class="section-lead">
      La cultura de reconocimiento de Postocola es sistemática, consistente y genuina. No esperamos los grandes hitos para celebrar.
    </p>

    <div class="recono-grid">
      <div class="recono-programs">
        <div class="recono-item">
          <div class="recono-num">01</div>
          <div>
            <h4>⭐ Estrellas Postocola</h4>
            <p>Sistema de puntos que se ganan por logros, comportamientos alineados con los valores y nominaciones de compañeros. Los puntos se canjean en un catálogo con viajes, tecnología, experiencias y más.</p>
          </div>
        </div>
        <div class="recono-item">
          <div class="recono-num">02</div>
          <div>
            <h4>🏅 Colaborador del Mes</h4>
            <p>Reconocimiento mensual en cada sede con placa, publicación en la intranet, mención en el correo directivo del área y un bono de experiencia (cena, spa o entrada a evento).</p>
          </div>
        </div>
        <div class="recono-item">
          <div class="recono-num">03</div>
          <div>
            <h4>🎬 Los PostoPremios</h4>
            <p>Ceremonia anual de reconocimiento con categorías como "Innovador del Año", "Líder que Transforma", "Espíritu Postocola" y "Equipo del Año". Evento presencial en todas las sedes transmitido en vivo.</p>
          </div>
        </div>
        <div class="recono-item">
          <div class="recono-num">04</div>
          <div>
            <h4>📅 Rituales de Celebración</h4>
            <p>Cumpleaños anunciado en las pantallas de la planta, día libre remunerado, y sorpresa del equipo. Porque los momentos personales también son de la empresa.</p>
          </div>
        </div>
        <div class="recono-item">
          <div class="recono-num">05</div>
          <div>
            <h4>🏆 Antigüedad con Honor</h4>
            <p>A los 5, 10, 15 y 20 años de permanencia: carta personalizada del Presidente, ceremonia especial, pin de oro graduado en quilates según los años y viaje financiado para el colaborador y su pareja.</p>
          </div>
        </div>
      </div>

      <div class="cultura-box">
        <h3>El "Cómo" importa tanto como el "Qué"</h3>
        <blockquote>
          "En Postocola no solo premiamos los resultados. Premiamos la forma en que se consiguen. Un colaborador que alcanza sus metas pero atropella a otros no es un colaborador Postocola."
        </blockquote>
        <div class="cultura-values">
          <div class="cv-item"><div class="cv-dot"></div> Feedback continuo entre pares y líderes</div>
          <div class="cv-item"><div class="cv-dot"></div> Cultura de la conversación directa y respetuosa</div>
          <div class="cv-item"><div class="cv-dot"></div> Sin jerarquías en las ideas: cualquiera puede proponer</div>
          <div class="cv-item"><div class="cv-dot"></div> Política de puertas abiertas desde la Presidencia</div>
          <div class="cv-item"><div class="cv-dot"></div> Encuesta de clima organizacional dos veces al año con plan de acción publicado</div>
          <div class="cv-item"><div class="cv-dot"></div> Canal de sugerencias anónimas con respuesta garantizada en 15 días</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- IMPACTO -->
<section id="impacto">
  <div class="impacto-wrap">
    <div class="section-label">Impacto & Resultados</div>
    <h2 class="section-title">El salario emocional<br>no es un gasto.<br>Es la mejor inversión.</h2>
    <p class="section-lead">
      Los números respaldan nuestra filosofía. Aquí están los resultados de nuestra estrategia de personas en los últimos 3 años.
    </p>

    <div class="stats-mega">
      <div class="stat-mega-card">
        <div class="stat-number">23<span class="stat-unit">%</span></div>
        <div class="stat-label">Reducción en rotación voluntaria desde la implementación del programa</div>
      </div>
      <div class="stat-mega-card">
        <div class="stat-number">91<span class="stat-unit">%</span></div>
        <div class="stat-label">Índice de satisfacción laboral en la última encuesta de clima organizacional</div>
      </div>
      <div class="stat-mega-card">
        <div class="stat-number">2.1<span class="stat-unit">x</span></div>
        <div class="stat-label">Más productividad en equipos con líderes que practican reconocimiento activo</div>
      </div>
      <div class="stat-mega-card">
        <div class="stat-number">78<span class="stat-unit">%</span></div>
        <div class="stat-label">De las vacantes directivas cubiertas con promoción interna</div>
      </div>
    </div>

    <div class="impacto-text">
      <div class="impacto-col">
        <h3><span>📊</span> Cómo impacta en la productividad</h3>
        <ul class="impact-list">
          <li>
            <span class="li-icon">🎯</span>
            <span><strong>Foco en el trabajo:</strong> un colaborador sin preocupaciones financieras, de salud o personales enfoca el 100% de su energía en sus resultados. El salario emocional reduce las distracciones.</span>
          </li>
          <li>
            <span class="li-icon">💡</span>
            <span><strong>Creatividad desbloqueada:</strong> las personas que se sienten seguras y valoradas proponen más ideas, toman más iniciativa y resuelven problemas con mayor creatividad.</span>
          </li>
          <li>
            <span class="li-icon">🤝</span>
            <span><strong>Colaboración genuina:</strong> los ambientes de reconocimiento generan confianza entre equipos. Y los equipos que confían entre sí entregan mejores resultados.</span>
          </li>
          <li>
            <span class="li-icon">⏱️</span>
            <span><strong>Menos ausentismo:</strong> el programa PostoVida 360° ha reducido el ausentismo por causas médicas y emocionales en un 34%, traducido en horas productivas recuperadas.</span>
          </li>
        </ul>
      </div>
      <div class="impacto-col">
        <h3><span>🔄</span> Cómo reduce la rotación</h3>
        <ul class="impact-list">
          <li>
            <span class="li-icon">❤️</span>
            <span><strong>Fidelización emocional:</strong> un colaborador que siente que la empresa cuida a su familia, celebra sus logros y le da futuro no se va solo por un 10% más de salario en otra empresa.</span>
          </li>
          <li>
            <span class="li-icon">📈</span>
            <span><strong>Visibilidad de futuro:</strong> cuando un colaborador ve una ruta de carrera clara, el costo de irse es alto. Los planes de desarrollo son el mejor seguro de retención.</span>
          </li>
          <li>
            <span class="li-icon">🌐</span>
            <span><strong>Sentido de pertenencia:</strong> los rituales culturales, los PostoPremios y las comunidades internas crean vínculos que van más allá del contrato laboral.</span>
          </li>
          <li>
            <span class="li-icon">🧮</span>
            <span><strong>ROI de retención:</strong> reemplazar a un colaborador cuesta entre 50% y 150% de su salario anual. Invertir en salario emocional es hasta 5 veces más barato que reclutar y entrenar de nuevo.</span>
          </li>
        </ul>
      </div>
    </div>
  </div>
</section>

<!-- SEDES -->
<section id="sedes">
  <div class="sedes-intro">
    <div class="section-label">Presencia Nacional</div>
    <h2 class="section-title">Postocola está<br>donde tú estés.</h2>
    <p class="section-lead">
      7 sedes regionales, el mismo nivel de beneficios en todo el país. No importa en qué ciudad estés: el salario emocional viaja contigo.
    </p>
  </div>

  <div class="sedes-grid">
    <div class="sede-card">
      <div class="sede-header">
        <h4>🏙️ Bogotá</h4>
        <span class="sede-badge hq">Casa Matriz</span>
      </div>
      <div class="sede-body">
        <ul>
          <li>Sede principal con Presidencia y Vicepresidencias</li>
          <li>PostoVida 360° completo con equipo propio</li>
          <li>PostoLearn Hub presencial: sala de innovación y coworking</li>
          <li>Casino corporativo con menú gourmet regional</li>
          <li>Gimnasio corporativo en el edificio</li>
        </ul>
      </div>
    </div>
    <div class="sede-card">
      <div class="sede-header">
        <h4>🌺 Cali</h4>
        <span class="sede-badge">Regional</span>
      </div>
      <div class="sede-body">
        <ul>
          <li>Sede regional con Gerente Regional propio</li>
          <li>Psicólogo disponible 3 días a la semana en sede</li>
          <li>PostoFit con convenio con club deportivo local</li>
          <li>Programa de voluntariado comunitario activo</li>
          <li>Subsidio de transporte diferenciado para zona</li>
        </ul>
      </div>
    </div>
    <div class="sede-card">
      <div class="sede-header">
        <h4>⛰️ Medellín</h4>
        <span class="sede-badge">Regional</span>
      </div>
      <div class="sede-body">
        <ul>
          <li>Hub de innovación del sector bebidas</li>
          <li>PostoLab activo con 12 proyectos en curso</li>
          <li>Alianza con UPB y EAFIT para convenios académicos</li>
          <li>Yoga y meditación incluidos en jornada laboral</li>
          <li>Biciparqueadero con vestieres premium</li>
        </ul>
      </div>
    </div>
    <div class="sede-card">
      <div class="sede-header">
        <h4>🌊 Barranquilla</h4>
        <span class="sede-badge">Regional</span>
      </div>
      <div class="sede-body">
        <ul>
          <li>Planta de producción principal con salas de descanso especiales</li>
          <li>Auxilio de refrigerio por alta temperatura operativa</li>
          <li>Torneo deportivo interempresas patrocinado por Postocola</li>
          <li>PostoVida virtual disponible todos los días</li>
          <li>Convenio con gimnasios de toda la ciudad</li>
        </ul>
      </div>
    </div>
    <div class="sede-card">
      <div class="sede-header">
        <h4>🏔️ Bucaramanga</h4>
        <span class="sede-badge">Regional</span>
      </div>
      <div class="sede-body">
        <ul>
          <li>Sede con mayor índice de satisfacción laboral 2024</li>
          <li>Programa comunitario activo en barrios periféricos</li>
          <li>PostoEnglish con grupos presenciales 3 veces/semana</li>
          <li>Psicólogo y nutricionista presencial dos días/semana</li>
          <li>Día de integración mensual con actividades al aire libre</li>
        </ul>
      </div>
    </div>
    <div class="sede-card">
      <div class="sede-header">
        <h4>🇨🇴 Resto del País</h4>
        <span class="sede-badge">Distribución</span>
      </div>
      <div class="sede-body">
        <ul>
          <li>Colaboradores en campo acceden a todos los beneficios en modalidad virtual</li>
          <li>PostoVida 360° disponible 100% digital en todo momento</li>
          <li>Kit PostoBox enviado mensualmente a domicilio</li>
          <li>Gestor de bienestar asignado por región</li>
          <li>Reuniones trimestrales presenciales en la sede más cercana</li>
        </ul>
      </div>
    </div>
  </div>

  <div class="sedes-model">
    <h3>Modelo de implementación multi-sede: cómo lo hacemos posible</h3>
    <div class="model-grid">
      <div class="model-item">
        <div class="model-icon">🖥️</div>
        <h5>Plataforma Digital</h5>
        <p>Todos los programas tienen versión digital. Cualquier colaborador en cualquier punto del país accede a los mismos beneficios.</p>
      </div>
      <div class="model-item">
        <div class="model-icon">👤</div>
        <h5>Gestor Local</h5>
        <p>Cada sede tiene un Gestor de Bienestar y Cultura que adapta los programas nacionales al contexto regional.</p>
      </div>
      <div class="model-item">
        <div class="model-icon">🔗</div>
        <h5>Red de Aliados</h5>
        <p>Convenios con más de 200 aliados locales (gimnasios, clínicas, universidades) en cada ciudad donde opera Postocola.</p>
      </div>
      <div class="model-item">
        <div class="model-icon">📊</div>
        <h5>Medición Constante</h5>
        <p>Dashboard de bienestar en tiempo real. HR Central puede ver el NPS de cada sede y actuar rápido ante caídas de satisfacción.</p>
      </div>
    </div>
  </div>
</section>

<!-- CTA FINAL -->
<section id="cta">
  <div class="cta-inner">
    <div class="cta-label">Tu historia en Postocola</div>
    <h2 class="cta-title">Hoy empiezas.<br>Mañana<br>liderarás.</h2>
    <p class="cta-sub">
      Bienvenido a la familia Postocola. Llegaste a un lugar donde tu trabajo importa, tu familia es visible y tu crecimiento es nuestro propósito. Ahora el resto depende de ti — y nosotros estaremos aquí para impulsarte en cada paso.
    </p>
    <div class="cta-chips">
      <span class="chip">🏆 Premio Nacional de Calidad</span>
      <span class="chip">🇨🇴 55+ años de historia</span>
      <span class="chip">❤️ 4.500 familias Postocola</span>
      <span class="chip">📈 +10% sobre el mercado salarial</span>
      <span class="chip">🌟 91% de satisfacción laboral</span>
      <span class="chip">🎓 78% de ascensos internos</span>
    </div>
    <a href="#inicio" class="btn-primary" style="font-size:1rem; padding:1.1rem 3rem;">
      Volver al inicio ↑
    </a>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-inner">
    <div class="footer-logo">POSTO<span>COLA</span> S.A.</div>
    <div class="footer-copy">
      Manual de Onboarding — Gerencia de Recursos Humanos<br>
      Todos los beneficios sujetos a política vigente y convención colectiva SINTRAPOSTOCOLA 2024–2026
    </div>
    <div class="footer-links">
      <a href="#bienvenida">Inicio</a>
      <a href="#salario">Beneficios</a>
      <a href="#desarrollo">Carrera</a>
      <a href="#sedes">Sedes</a>
    </div>
  </div>
</footer>

<script>
  // Burbujas animadas en el hero
  const bubblesContainer = document.getElementById('bubbles');
  const colors = ['rgba(215,38,56,0.3)', 'rgba(244,160,24,0.25)', 'rgba(255,255,255,0.15)', 'rgba(215,38,56,0.15)'];
  
  for (let i = 0; i < 20; i++) {
    const b = document.createElement('div');
    b.className = 'bubble';
    const size = Math.random() * 40 + 10;
    b.style.cssText = `
      width: ${size}px;
      height: ${size}px;
      left: ${Math.random() * 100}%;
      background: ${colors[Math.floor(Math.random() * colors.length)]};
      animation-duration: ${Math.random() * 8 + 6}s;
      animation-delay: ${Math.random() * 8}s;
      border-radius: 50%;
    `;
    bubblesContainer.appendChild(b);
  }

  // Intersection Observer para animaciones al scroll
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.style.opacity = '1';
        entry.target.style.transform = 'translateY(0)';
      }
    });
  }, { threshold: 0.1 });

  document.querySelectorAll('.valor-card, .pilar-card, .recono-item, .stat-mega-card, .extra-card, .programa-card, .sede-card, .timeline-item, .ruta-step').forEach(el => {
    el.style.opacity = '0';
    el.style.transform = 'translateY(30px)';
    el.style.transition = 'opacity 0.6s ease, transform 0.6s ease';
    observer.observe(el);
  });

  // Stagger para cards en grids
  document.querySelectorAll('.valores-grid .valor-card, .pilares-grid .pilar-card, .stats-mega .stat-mega-card').forEach((el, i) => {
    el.style.transitionDelay = `${i * 0.08}s`;
  });
</script>
</body>
</html>
