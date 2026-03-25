<!DOCTYPE html>
<html lang="it">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>ESSENZA — Alessia Mei | Mentor per Nutrizioniste e Personal Trainer</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,500;0,600;1,400;1,500&family=Montserrat:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --cream: #F5EDED;
    --warm-white: #FAFAF7;
    --charcoal: #1C1C1A;
    --muted: #6B6558;
    --accent: #800000;
    --accent-light: #C04040;
    --line: rgba(28,28,26,0.12);
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  html { scroll-behavior: smooth; }

  body {
    background: var(--warm-white);
    color: var(--charcoal);
    font-family: 'Montserrat', sans-serif;
    font-weight: 300;
    line-height: 1.7;
    overflow-x: hidden;
  }

  /* NAV */
  nav {
    position: fixed; top: 0; left: 0; right: 0;
    z-index: 100;
    padding: 24px 60px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    background: rgba(250,250,247,0.95);
    backdrop-filter: blur(12px);
    border-bottom: 1px solid var(--line);
  }

  .nav-logo {
    font-family: 'Playfair Display', serif;
    font-size: 22px;
    font-weight: 500;
    letter-spacing: 4px;
    text-transform: uppercase;
    color: var(--charcoal);
    text-decoration: none;
  }

  .nav-links {
    display: flex;
    gap: 40px;
    list-style: none;
  }

  .nav-links a {
    font-size: 11px;
    letter-spacing: 2.5px;
    text-transform: uppercase;
    color: var(--muted);
    text-decoration: none;
    transition: color 0.3s;
    cursor: pointer;
  }

  .nav-links a:hover { color: var(--charcoal); }

  .nav-cta {
    font-size: 11px;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: var(--charcoal);
    border-bottom: 1px solid var(--accent);
    padding-bottom: 2px;
    text-decoration: none;
    transition: color 0.3s;
    cursor: pointer;
  }

  /* PAGES */
  .page { display: none; min-height: 100vh; }
  .page.active { display: block; }

  /* HERO */
  .hero {
    min-height: 100vh;
    display: grid;
    grid-template-columns: 1fr 1fr;
    padding-top: 80px;
  }

  .hero-left {
    background: var(--cream);
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: 80px 70px 80px 60px;
    position: relative;
  }

  .hero-left::after {
    content: '';
    position: absolute;
    top: 15%;
    left: 40px;
    width: 1px;
    height: 60%;
    background: var(--accent);
    opacity: 0.4;
  }

  .hero-tag {
    font-size: 11px;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 28px;
  }

  .hero-headline {
    font-family: 'Playfair Display', serif;
    font-size: clamp(42px, 5vw, 64px);
    font-weight: 300;
    line-height: 1.15;
    color: var(--charcoal);
    margin-bottom: 32px;
  }

  .hero-headline em {
    font-style: italic;
    color: var(--accent);
  }

  .hero-sub {
    font-size: 15px;
    color: var(--muted);
    max-width: 400px;
    margin-bottom: 48px;
    line-height: 1.8;
  }

  .btn-primary {
    display: inline-block;
    padding: 16px 40px;
    background: var(--charcoal);
    color: var(--warm-white);
    font-size: 11px;
    letter-spacing: 2.5px;
    text-transform: uppercase;
    text-decoration: none;
    transition: background 0.3s, transform 0.3s;
    cursor: pointer;
    border: none;
    font-family: 'Montserrat', sans-serif;
    font-weight: 400;
    align-self: flex-start;
  }

  .btn-primary:hover {
    background: var(--accent);
    transform: translateY(-2px);
  }

  .btn-ghost {
    display: inline-block;
    padding: 14px 36px;
    background: transparent;
    color: var(--charcoal);
    font-size: 11px;
    letter-spacing: 2.5px;
    text-transform: uppercase;
    border: 1px solid var(--charcoal);
    text-decoration: none;
    transition: all 0.3s;
    cursor: pointer;
    font-family: 'Montserrat', sans-serif;
    font-weight: 400;
  }

  .btn-ghost:hover {
    background: var(--charcoal);
    color: var(--warm-white);
  }

  .hero-right {
    background: var(--charcoal);
    position: relative;
    overflow: hidden;
    display: flex;
    align-items: flex-end;
    padding: 60px;
  }

  .hero-right-bg {
    position: absolute;
    inset: 0;
    background: linear-gradient(135deg, #2a2825 0%, #1C1C1A 60%);
  }

  .hero-right-pattern {
    position: absolute;
    top: 0; right: 0;
    width: 300px;
    height: 300px;
    background: radial-gradient(circle, rgba(184,150,110,0.15) 0%, transparent 70%);
  }

  .hero-right-content {
    position: relative;
    z-index: 2;
  }

  .hero-number {
    font-family: 'Playfair Display', serif;
    font-size: 120px;
    font-weight: 300;
    color: rgba(255,255,255,0.04);
    line-height: 1;
    position: absolute;
    top: 40px;
    right: 30px;
  }

  .hero-stat {
    margin-bottom: 40px;
  }

  .hero-stat-num {
    font-family: 'Playfair Display', serif;
    font-size: 52px;
    font-weight: 300;
    color: var(--accent-light);
    display: block;
    line-height: 1;
    margin-bottom: 8px;
  }

  .hero-stat-label {
    font-size: 12px;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: rgba(255,255,255,0.4);
  }

  .hero-divider {
    width: 40px;
    height: 1px;
    background: var(--accent);
    margin: 32px 0;
  }

  .hero-quote {
    font-family: 'Playfair Display', serif;
    font-size: 20px;
    font-style: italic;
    color: rgba(255,255,255,0.7);
    line-height: 1.6;
    max-width: 320px;
  }

  /* SECTION GENERIC */
  section {
    padding: 100px 60px;
  }

  .section-label {
    font-size: 11px;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 20px;
  }

  .section-title {
    font-family: 'Playfair Display', serif;
    font-size: clamp(36px, 4vw, 54px);
    font-weight: 300;
    line-height: 1.2;
    color: var(--charcoal);
    margin-bottom: 24px;
  }

  .section-title em {
    font-style: italic;
    color: var(--accent);
  }

  /* PROBLEM STRIP */
  .problem-strip {
    background: var(--charcoal);
    padding: 80px 60px;
  }

  .problem-strip-inner {
    max-width: 900px;
    margin: 0 auto;
    text-align: center;
  }

  .problem-intro {
    font-family: 'Playfair Display', serif;
    font-size: 28px;
    font-weight: 300;
    color: rgba(255,255,255,0.6);
    margin-bottom: 48px;
    line-height: 1.6;
  }

  .problem-items {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1px;
    background: rgba(255,255,255,0.08);
    margin-bottom: 56px;
  }

  .problem-item {
    background: var(--charcoal);
    padding: 40px 32px;
    text-align: left;
  }

  .problem-num {
    font-family: 'Playfair Display', serif;
    font-size: 48px;
    color: rgba(255,255,255,0.06);
    line-height: 1;
    margin-bottom: 16px;
  }

  .problem-text {
    font-size: 15px;
    color: rgba(255,255,255,0.65);
    line-height: 1.7;
  }

  .problem-text strong {
    color: rgba(255,255,255,0.9);
    font-weight: 400;
  }

  .problem-close {
    font-family: 'Playfair Display', serif;
    font-size: 26px;
    font-style: italic;
    color: var(--accent-light);
  }

  /* METHOD */
  .method-section {
    background: var(--cream);
    padding: 100px 60px;
  }

  .method-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 80px;
    align-items: start;
    max-width: 1100px;
    margin: 0 auto;
  }

  .method-pillars {
    display: flex;
    flex-direction: column;
    gap: 1px;
    margin-top: 40px;
  }

  .pillar {
    display: grid;
    grid-template-columns: 50px 1fr;
    gap: 20px;
    padding: 28px 0;
    border-bottom: 1px solid var(--line);
    align-items: start;
  }

  .pillar-letter {
    font-family: 'Playfair Display', serif;
    font-size: 40px;
    font-weight: 300;
    color: var(--accent);
    line-height: 1;
  }

  .pillar-content h4 {
    font-size: 12px;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: var(--charcoal);
    margin-bottom: 6px;
    font-weight: 500;
  }

  .pillar-content p {
    font-size: 14px;
    color: var(--muted);
    line-height: 1.6;
  }

  .method-right {
    padding-top: 40px;
  }

  .method-manifesto {
    font-family: 'Playfair Display', serif;
    font-size: 22px;
    font-weight: 300;
    line-height: 1.7;
    color: var(--charcoal);
    margin-bottom: 40px;
  }

  .method-manifesto em { font-style: italic; color: var(--accent); }

  .method-proof {
    background: var(--charcoal);
    padding: 40px;
    margin-top: 32px;
  }

  .method-proof-quote {
    font-family: 'Playfair Display', serif;
    font-size: 18px;
    font-style: italic;
    color: rgba(255,255,255,0.8);
    line-height: 1.7;
    margin-bottom: 20px;
  }

  .method-proof-author {
    font-size: 11px;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: var(--accent);
  }

  /* RESULTS */
  .results-section {
    padding: 100px 60px;
  }

  .results-header {
    max-width: 600px;
    margin-bottom: 70px;
  }

  .results-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 40px;
  }

  .result-card {
    border-top: 1px solid var(--line);
    padding-top: 32px;
  }

  .result-name {
    font-size: 11px;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 16px;
  }

  .result-quote {
    font-family: 'Playfair Display', serif;
    font-size: 18px;
    font-weight: 300;
    line-height: 1.7;
    color: var(--charcoal);
    margin-bottom: 20px;
  }

  .result-outcome {
    font-size: 12px;
    letter-spacing: 1px;
    color: var(--muted);
    border-left: 2px solid var(--accent);
    padding-left: 12px;
  }

  /* FOR WHO */
  .forwho-section {
    background: var(--charcoal);
    padding: 100px 60px;
  }

  .forwho-inner {
    max-width: 1000px;
    margin: 0 auto;
  }

  .forwho-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 80px;
    margin-top: 60px;
  }

  .forwho-col h3 {
    font-size: 11px;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 32px;
  }

  .forwho-item {
    display: flex;
    gap: 16px;
    margin-bottom: 24px;
    align-items: flex-start;
  }

  .forwho-dot {
    width: 6px;
    height: 6px;
    border-radius: 50%;
    background: var(--accent);
    margin-top: 8px;
    flex-shrink: 0;
  }

  .forwho-text {
    font-size: 15px;
    color: rgba(255,255,255,0.7);
    line-height: 1.7;
  }

  /* OFFERS PAGE */
  .offers-hero {
    background: var(--cream);
    padding: 140px 60px 80px;
    text-align: center;
  }

  .offers-hero .section-title { margin: 0 auto 20px; }

  .offers-hero-sub {
    font-size: 16px;
    color: var(--muted);
    max-width: 500px;
    margin: 0 auto;
  }

  .offers-grid {
    padding: 80px 60px;
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1px;
    background: var(--line);
  }

  .offer-card {
    background: var(--warm-white);
    padding: 50px 40px;
  }

  .offer-level {
    font-size: 10px;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 20px;
  }

  .offer-name {
    font-family: 'Playfair Display', serif;
    font-size: 28px;
    font-weight: 400;
    color: var(--charcoal);
    margin-bottom: 12px;
    line-height: 1.2;
  }

  .offer-tagline {
    font-size: 14px;
    color: var(--muted);
    line-height: 1.7;
    margin-bottom: 32px;
    padding-bottom: 32px;
    border-bottom: 1px solid var(--line);
  }

  .offer-includes {
    margin-bottom: 32px;
  }

  .offer-includes h5 {
    font-size: 10px;
    letter-spacing: 2.5px;
    text-transform: uppercase;
    color: var(--charcoal);
    margin-bottom: 16px;
    font-weight: 500;
  }

  .offer-includes ul {
    list-style: none;
    display: flex;
    flex-direction: column;
    gap: 10px;
  }

  .offer-includes li {
    font-size: 13px;
    color: var(--muted);
    display: flex;
    gap: 10px;
    align-items: flex-start;
  }

  .offer-includes li::before {
    content: '—';
    color: var(--accent);
    flex-shrink: 0;
  }

  .offer-price {
    font-family: 'Playfair Display', serif;
    font-size: 38px;
    font-weight: 300;
    color: var(--charcoal);
    margin-bottom: 24px;
  }

  .offer-price span {
    font-size: 14px;
    color: var(--muted);
    font-family: 'Montserrat', sans-serif;
  }

  .offer-card.featured {
    background: var(--charcoal);
  }

  .offer-card.featured .offer-level,
  .offer-card.featured .offer-price { color: var(--accent-light); }

  .offer-card.featured .offer-name,
  .offer-card.featured .offer-includes h5 { color: rgba(255,255,255,0.95); }

  .offer-card.featured .offer-tagline,
  .offer-card.featured .offer-includes li { color: rgba(255,255,255,0.55); }

  .offer-card.featured .offer-tagline { border-color: rgba(255,255,255,0.1); }

  .offer-card.featured .btn-primary {
    background: var(--accent);
    color: var(--charcoal);
  }

  .offer-card.featured .btn-primary:hover { background: var(--accent-light); }

  /* CALL SECTION */
  .call-section {
    background: var(--cream);
    padding: 100px 60px;
    text-align: center;
  }

  .call-inner {
    max-width: 680px;
    margin: 0 auto;
  }

  .call-section .section-title { margin-bottom: 20px; }

  .call-body {
    font-size: 16px;
    color: var(--muted);
    line-height: 1.8;
    margin-bottom: 16px;
  }

  .call-note {
    font-family: 'Playfair Display', serif;
    font-size: 18px;
    font-style: italic;
    color: var(--charcoal);
    margin-bottom: 48px;
  }

  .call-steps {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 40px;
    margin: 60px 0;
    text-align: left;
  }

  .call-step {
    border-top: 1px solid var(--line);
    padding-top: 24px;
  }

  .call-step-num {
    font-family: 'Playfair Display', serif;
    font-size: 42px;
    color: var(--accent-light);
    line-height: 1;
    margin-bottom: 12px;
  }

  .call-step-title {
    font-size: 12px;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: var(--charcoal);
    margin-bottom: 8px;
    font-weight: 500;
  }

  .call-step-text {
    font-size: 13px;
    color: var(--muted);
    line-height: 1.6;
  }

  /* ABOUT PAGE */
  .about-hero {
    display: grid;
    grid-template-columns: 1fr 1fr;
    min-height: 100vh;
    padding-top: 80px;
  }

  .about-left {
    background: var(--charcoal);
    display: flex;
    align-items: flex-end;
    padding: 80px 60px;
    position: relative;
    overflow: hidden;
  }

  .about-bg-text {
    position: absolute;
    top: 40%;
    left: 50%;
    transform: translateX(-50%);
    font-family: 'Playfair Display', serif;
    font-size: 200px;
    font-weight: 300;
    color: rgba(255,255,255,0.025);
    letter-spacing: -10px;
    white-space: nowrap;
  }

  .about-left-content {
    position: relative;
    z-index: 2;
  }

  .about-left-tag {
    font-size: 10px;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 20px;
  }

  .about-name {
    font-family: 'Playfair Display', serif;
    font-size: 56px;
    font-weight: 300;
    color: rgba(255,255,255,0.9);
    line-height: 1.1;
    margin-bottom: 16px;
  }

  .about-role {
    font-size: 13px;
    color: rgba(255,255,255,0.4);
    letter-spacing: 1.5px;
  }

  .about-right {
    background: var(--cream);
    padding: 100px 70px;
    display: flex;
    flex-direction: column;
    justify-content: center;
  }

  .about-intro {
    font-family: 'Playfair Display', serif;
    font-size: 24px;
    font-weight: 300;
    line-height: 1.7;
    color: var(--charcoal);
    margin-bottom: 40px;
  }

  .about-intro em { font-style: italic; color: var(--accent); }

  .about-body {
    font-size: 15px;
    color: var(--muted);
    line-height: 1.9;
    margin-bottom: 20px;
  }

  .about-values {
    background: var(--warm-white);
    padding: 80px 60px;
  }

  .about-values-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 40px;
    max-width: 1100px;
    margin: 50px auto 0;
  }

  .value-item {
    border-top: 1px solid var(--line);
    padding-top: 28px;
  }

  .value-item h4 {
    font-size: 11px;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: var(--charcoal);
    margin-bottom: 12px;
    font-weight: 500;
  }

  .value-item p {
    font-size: 14px;
    color: var(--muted);
    line-height: 1.7;
  }

  /* RESOURCES PAGE */
  .resources-hero {
    background: var(--cream);
    padding: 140px 60px 80px;
  }

  .resources-inner { max-width: 1100px; margin: 0 auto; }

  .resources-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 1px;
    background: var(--line);
    margin-top: 60px;
  }

  .resource-card {
    background: var(--warm-white);
    padding: 50px;
  }

  .resource-type {
    font-size: 10px;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 20px;
  }

  .resource-title {
    font-family: 'Playfair Display', serif;
    font-size: 26px;
    font-weight: 400;
    color: var(--charcoal);
    margin-bottom: 12px;
    line-height: 1.3;
  }

  .resource-desc {
    font-size: 14px;
    color: var(--muted);
    line-height: 1.7;
    margin-bottom: 28px;
  }

  .resource-price {
    font-family: 'Playfair Display', serif;
    font-size: 28px;
    color: var(--charcoal);
    margin-bottom: 20px;
  }

  /* FOOTER */
  footer {
    background: var(--charcoal);
    padding: 60px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    border-top: 1px solid rgba(255,255,255,0.06);
  }

  .footer-logo {
    font-family: 'Playfair Display', serif;
    font-size: 20px;
    letter-spacing: 4px;
    text-transform: uppercase;
    color: rgba(255,255,255,0.6);
    font-weight: 300;
  }

  .footer-tagline {
    font-size: 12px;
    letter-spacing: 1.5px;
    color: rgba(255,255,255,0.3);
    font-style: italic;
    font-family: 'Playfair Display', serif;
  }

  .footer-copy {
    font-size: 11px;
    color: rgba(255,255,255,0.2);
    letter-spacing: 1px;
  }

  /* ANIMATIONS */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(30px); }
    to { opacity: 1; transform: translateY(0); }
  }

  .page.active .hero-left > *,
  .page.active .hero-right > * {
    animation: fadeUp 0.8s ease forwards;
  }

  .page.active .hero-tag { animation-delay: 0.1s; }
  .page.active .hero-headline { animation-delay: 0.25s; }
  .page.active .hero-sub { animation-delay: 0.4s; }
  .page.active .btn-primary { animation-delay: 0.55s; }

  @media (max-width: 900px) {
    nav { padding: 18px 24px; }
    .nav-links { display: none; }
    .hero { grid-template-columns: 1fr; min-height: auto; }
    .hero-left { padding: 100px 28px 60px; }
    .hero-right { padding: 50px 28px; min-height: 300px; }
    .hero-number { font-size: 70px; }
    .problem-items { grid-template-columns: 1fr; }
    .method-grid { grid-template-columns: 1fr; gap: 40px; }
    .results-grid { grid-template-columns: 1fr; gap: 32px; }
    .forwho-grid { grid-template-columns: 1fr; gap: 40px; }
    .call-steps { grid-template-columns: 1fr; gap: 28px; }
    .about-hero { grid-template-columns: 1fr; }
    .about-left { min-height: 300px; padding: 100px 28px 50px; }
    .about-right { padding: 50px 28px; }
    .about-values-grid { grid-template-columns: 1fr 1fr; gap: 28px; }
    .offers-grid { grid-template-columns: 1fr; padding: 40px 24px; }
    .offers-hero { padding: 120px 28px 60px; }
    .resources-grid { grid-template-columns: 1fr; }
    .resources-hero { padding: 120px 28px 60px; }
    section, .method-section, .problem-strip, .forwho-section,
    .call-section, .results-section, .about-values { padding: 60px 28px; }
    footer { flex-direction: column; gap: 16px; text-align: center; padding: 40px 28px; }
    .hero-left::after { display: none; }
  }
  @media (max-width: 480px) {
    .hero-headline { font-size: 36px; }
    .section-title { font-size: 30px; }
    .about-name { font-size: 42px; }
    .about-values-grid { grid-template-columns: 1fr; }
    .offer-card { padding: 36px 24px; }
    .resource-card { padding: 36px 24px; }
    .method-proof { padding: 28px 24px; }
    nav { padding: 16px 20px; }
    .nav-logo { font-size: 18px; letter-spacing: 3px; }
    .nav-cta { font-size: 10px; letter-spacing: 1.5px; }
  }


  .faq-section { padding: 80px 60px; background: var(--cream); }
  .faq-inner { max-width: 780px; margin: 0 auto; }
  .faq-list { margin-top: 48px; }
  .faq-item { border-top: 1px solid var(--line); }
  .faq-item:last-child { border-bottom: 1px solid var(--line); }
  .faq-question {
    width: 100%; background: none; border: none; padding: 24px 0;
    display: flex; justify-content: space-between; align-items: center;
    cursor: pointer; font-family: 'Montserrat', sans-serif;
    font-size: 15px; font-weight: 500; color: var(--charcoal);
    text-align: left; gap: 20px;
  }
  .faq-question:hover { color: var(--accent); }
  .faq-icon { font-size: 22px; color: var(--accent); flex-shrink: 0; line-height: 1; }
  .faq-answer { display: none; padding: 0 0 24px; }
  .faq-answer.open { display: block; }
  .faq-answer p { font-size: 14px; color: var(--muted); line-height: 1.85; margin-bottom: 8px; }
  .faq-answer a { color: var(--accent); text-decoration: underline; }
  @media (max-width: 900px) { .faq-section { padding: 60px 28px; } }
</style>
</head>
<body>

<nav>
  <a class="nav-logo" href="#" onclick="showPage('home'); return false;">ESSENZA</a>
  <ul class="nav-links">
    <li><a href="#" onclick="showPage('home'); return false;">Home</a></li>
    <li><a href="#" onclick="showPage('about'); return false;">Chi sono</a></li>
    <li><a href="#" onclick="showPage('offers'); return false;">Percorsi</a></li>
    <li></li>
  </ul>
  <a class="nav-cta" href="https://calendly.com/alessiamei/call-conoscitiva-gratuita-con-alessia-mei?month=2026-03&date=2026-03-03" target="_blank">Prenota una call</a>
</nav>

<!-- ═══════════════════════════════════════════ HOME ═══ -->
<div id="page-home" class="page active">

  <!-- HERO -->
  <section class="hero" style="padding:0; padding-top:80px;">
    <div class="hero-left">
      <p class="hero-tag">Mentor per Nutrizioniste & Personal Trainer</p>
      <h1 class="hero-headline">
        Da professionista <em>invisibile</em><br>
        a brand che<br>
        attira clienti.
      </h1>
      <p class="hero-sub">
        Con il Metodo ESSENZA costruiamo insieme un sistema organico che porta clienti in modo costante — senza pubblicare ogni giorno, senza abbassare i prezzi, senza dipendere dalla fortuna.
      </p>
      <a class="btn-primary" href="#" onclick="showPage('offers'); return false;">Scopri i percorsi</a>
    </div>
    <div class="hero-right">
      <div class="hero-right-bg"></div>
      <div class="hero-right-pattern"></div>
      <div class="hero-number">E</div>
      <div class="hero-right-content">
        <div class="hero-stat">
          <span class="hero-stat-num">50+</span>
          <span class="hero-stat-label">Professioniste del wellness</span>
        </div>
        <div class="hero-divider"></div>
        <div class="hero-stat">
          <span class="hero-stat-num">6</span>
          <span class="hero-stat-label">Mesi per trasformare il tuo business</span>
        </div>
        <div class="hero-divider"></div>
        <p class="hero-quote">"Smetti di regalare.<br>Inizia a vendere."</p>
      </div>
    </div>
  </section>

  <!-- PROBLEM -->
  <div class="problem-strip">
    <div class="problem-strip-inner">
      <p class="problem-intro">
        Sei brava nel tuo lavoro. Eppure ogni mese ti chiedi perché i clienti non arrivano.
      </p>
      <div class="problem-items">
        <div class="problem-item">
          <div class="problem-num">01</div>
          <p class="problem-text">Pubblichi contenuti da mesi, ma i follower non diventano <strong>clienti paganti.</strong></p>
        </div>
        <div class="problem-item">
          <div class="problem-num">02</div>
          <p class="problem-text">Senti di dover dare sempre di più gratis per <strong>giustificare il tuo prezzo.</strong></p>
        </div>
        <div class="problem-item">
          <div class="problem-num">03</div>
          <p class="problem-text">Vedi altre professioniste meno competenti di te con <strong>l'agenda piena.</strong></p>
        </div>
      </div>
      <p class="problem-close">Il problema non è la tua expertise. È il sistema che manca.</p>
    </div>
  </div>

  <!-- METHOD -->
  <div class="method-section">
    <div class="method-grid">
      <div>
        <p class="section-label">Il Metodo</p>
        <h2 class="section-title">ESSENZA™<br><em>non è coaching<br>generico.</em></h2>
        <div class="method-pillars">
          <div class="pillar">
            <span class="pillar-letter">E</span>
            <div class="pillar-content">
              <h4>Energia autentica</h4>
              <p>Il tuo posizionamento unico che nessuno può copiare.</p>
            </div>
          </div>
          <div class="pillar">
            <span class="pillar-letter">S</span>
            <div class="pillar-content">
              <h4>Strategia sostenibile</h4>
              <p>Meno contenuti, più efficaci. Un funnel organico che lavora per te.</p>
            </div>
          </div>
          <div class="pillar">
            <span class="pillar-letter">S</span>
            <div class="pillar-content">
              <h4>Sistema replicabile</h4>
              <p>Processi chiari, vendita naturale, zero improvvisazione.</p>
            </div>
          </div>
          <div class="pillar">
            <span class="pillar-letter">E</span>
            <div class="pillar-content">
              <h4>Elevazione professionale</h4>
              <p>Da esperta a riferimento riconosciuto nel tuo settore.</p>
            </div>
          </div>
          <div class="pillar">
            <span class="pillar-letter">N</span>
            <div class="pillar-content">
              <h4>Nicchia dominante</h4>
              <p>Specializzazione che ti rende la scelta ovvia per il tuo cliente ideale.</p>
            </div>
          </div>
          <div class="pillar">
            <span class="pillar-letter">Z</span>
            <div class="pillar-content">
              <h4>Zero improvvisazione</h4>
              <p>Routine sostenibile, processi ottimizzati, deleghe strategiche.</p>
            </div>
          </div>
          <div class="pillar">
            <span class="pillar-letter">A</span>
            <div class="pillar-content">
              <h4>Azione concreta</h4>
              <p>Ogni step è misurabile. Niente teoria — solo risultati reali.</p>
            </div>
          </div>
        </div>
      </div>
      <div class="method-right">
        <p class="method-manifesto">
          Non lavoro con chiunque voglia crescere su Instagram.<br><br>
          Lavoro con <em>nutrizioniste e personal trainer</em> che hanno già la competenza — e vogliono costruire un sistema che la trasformi in entrate costanti.
        </p>
        <p style="font-size:15px; color: var(--muted); line-height:1.8; margin-bottom:32px;">
          La differenza tra una professionista che fatica e una con l'agenda piena non è il numero di follower. È avere un messaggio chiaro, un'offerta percepita come irresistibile e un sistema che porta clienti in modo prevedibile.
        </p>
        <a class="btn-ghost" href="#" onclick="showPage('offers'); return false;">Scopri il percorso</a>
        <div class="method-proof">
          <p class="method-proof-quote">"Da 0 a 12 clienti fissi in 90 giorni. Non ci credevo possibile partendo da 800 follower."</p>
          <span class="method-proof-author">Giulia R. — Nutrizionista</span>
        </div>
      </div>
    </div>
  </div>

  <!-- RESULTS -->
  <section class="results-section">
    <div class="results-header">
      <p class="section-label">Risultati reali</p>
      <h2 class="section-title">Il prima e dopo<br><em>parla da solo.</em></h2>
    </div>
    <div class="results-grid">
      <div class="result-card">
        <p class="result-name">Sara M. — Personal Trainer Online</p>
        <p class="result-quote">"Avevo paura di alzare i prezzi. Ora li ho triplicati e ho più clienti di prima."</p>
        <p class="result-outcome">Primo mese da €6.500 dopo anni di stagnazione</p>
      </div>
      <div class="result-card">
        <p class="result-name">Chiara V. — Nutrizionista clinica</p>
        <p class="result-quote">"Non sapevo come comunicare il mio valore. Oggi i clienti arrivano già convinti."</p>
        <p class="result-outcome">Lista d'attesa di 3 settimane in 4 mesi</p>
      </div>
      <div class="result-card">
        <p class="result-name">Martina B. — PT e Coach di benessere</p>
        <p class="result-quote">"Pubblicavo ogni giorno senza risultati. Con ESSENZA ho capito cosa stava davvero bloccando le vendite."</p>
        <p class="result-outcome">Da 0 a 8 clienti ricorrenti in 60 giorni</p>
      </div>
    </div>
  </section>

  <!-- FOR WHO -->
  <div class="forwho-section">
    <div class="forwho-inner">
      <p class="section-label" style="color: var(--accent);">Per chi è ESSENZA</p>
      <h2 class="section-title" style="color: rgba(255,255,255,0.9);">Questa è una scelta <em>consapevole.</em><br>Da entrambe le parti.</h2>
      <div class="forwho-grid">
        <div class="forwho-col">
          <h3>È per te se</h3>
          <div class="forwho-item">
            <div class="forwho-dot"></div>
            <p class="forwho-text">Sei nutrizionista o personal trainer con competenze solide ma clienti discontinui</p>
          </div>
          <div class="forwho-item">
            <div class="forwho-dot"></div>
            <p class="forwho-text">Senti che il tuo valore non viene percepito e i tuoi prezzi vengono messi in discussione</p>
          </div>
          <div class="forwho-item">
            <div class="forwho-dot"></div>
            <p class="forwho-text">Vuoi smettere di improvvisare e costruire un sistema che lavora anche quando non pubblichi</p>
          </div>
          <div class="forwho-item">
            <div class="forwho-dot"></div>
            <p class="forwho-text">Sei pronta a investire seriamente in te e nel tuo business</p>
          </div>
        </div>
        <div class="forwho-col">
          <h3>Non è per te se</h3>
          <div class="forwho-item">
            <div class="forwho-dot" style="background: rgba(255,255,255,0.2);"></div>
            <p class="forwho-text" style="color: rgba(255,255,255,0.35);">Cerchi risultati immediati senza impegno o cambiamento</p>
          </div>
          <div class="forwho-item">
            <div class="forwho-dot" style="background: rgba(255,255,255,0.2);"></div>
            <p class="forwho-text" style="color: rgba(255,255,255,0.35);">Hai già un business che gira bene e non vuoi evolvere il tuo approccio</p>
          </div>
          <div class="forwho-item">
            <div class="forwho-dot" style="background: rgba(255,255,255,0.2);"></div>
            <p class="forwho-text" style="color: rgba(255,255,255,0.35);">Non sei nel settore del wellness (nutrizioniste e PT)</p>
          </div>
        </div>
      </div>
    </div>
  </div>

  <!-- CALL CTA -->
  <div class="call-section">
    <div class="call-inner">
      <p class="section-label">Il primo passo</p>
      <h2 class="section-title">Una call per <em>capire<br>se ha senso</em> lavorare insieme.</h2>
      <p class="call-body">Prima di iniziare qualsiasi percorso, ci confrontiamo. Non per convincerti — ma per capire dove sei, dove vuoi arrivare e se il Metodo ESSENZA è la risposta giusta per te in questo momento.</p>
      <p class="call-note">Le disponibilità sono limitate. Non per urgenza — per scelta.</p>
      <div class="call-steps">
        <div class="call-step">
          <div class="call-step-num">01</div>
          <div class="call-step-title">Compila il questionario</div>
          <p class="call-step-text">Qualche domanda strategica per arrivare alla call preparate entrambe.</p>
        </div>
        <div class="call-step">
          <div class="call-step-num">02</div>
          <div class="call-step-title">Call conoscitiva (30 min)</div>
          <p class="call-step-text">Capiamo la tua situazione attuale e vediamo se e come posso aiutarti.</p>
        </div>
        <div class="call-step">
          <div class="call-step-num">03</div>
          <div class="call-step-title">Decisione consapevole</div>
          <p class="call-step-text">Se è il momento giusto, ti propongo il percorso più adatto. Senza pressioni.</p>
        </div>
      </div>
      <a class="btn-primary" href="https://calendly.com/alessiamei/call-conoscitiva-gratuita-con-alessia-mei?month=2026-03&date=2026-03-03" target="_blank">Prenota la tua call</a>
    </div>
  </div>

  <footer>
  <div class="footer-grid" style="display:grid; grid-template-columns:1fr 1fr 1fr; gap:40px; max-width:1200px; margin:0 auto; width:100%; padding:60px; background:var(--charcoal); color:#aaa;">
    
    <div>
      <div class="footer-logo" style="font-family:'Playfair Display',serif; font-size:18px; letter-spacing:4px; color:#fff; margin-bottom:16px;">ESSENZA</div>
      <p style="font-size:12px; line-height:1.8; color:#aaa;">Alessia Mei<br>Business Mentor per Nutrizioniste<br>e Personal Trainer<br>P.I. IT05127600236</p>
    </div>

    <div style="display:flex; flex-direction:column; align-items:center; justify-content:center;">
      <p style="font-family:'Playfair Display',serif; font-style:italic; font-size:15px; color:#ccc; text-align:center;"><em>Meno contenuti, più clienti.</em></p>
    </div>

    <div style="display:flex; flex-direction:column; align-items:flex-end; gap:16px;">
      <div style="display:flex; gap:16px; align-items:center;">
        <a href="https://www.instagram.com/alessiamei/" target="_blank" title="Instagram" style="color:#aaa; text-decoration:none; font-size:11px; letter-spacing:1.5px; text-transform:uppercase;">&#128247; Instagram</a>
        <a href="https://www.linkedin.com/in/alessia-mei/" target="_blank" title="LinkedIn" style="color:#aaa; text-decoration:none; font-size:11px; letter-spacing:1.5px; text-transform:uppercase;">&#128188; LinkedIn</a>
      </div>
      <div style="display:flex; gap:16px; align-items:center;">
        <a href="mailto:ciao@alessiamei.com" style="color:#aaa; text-decoration:none; font-size:11px; letter-spacing:1px;">&#9993; ciao@alessiamei.com</a>
      </div>
      <div style="display:flex; gap:16px; align-items:center;">
        <a href="https://wa.me/393511781139" target="_blank" style="color:#aaa; text-decoration:none; font-size:11px; letter-spacing:1px;">&#128242; +39 351 178 1139</a>
      </div>
      <div style="display:flex; gap:16px; margin-top:8px;">
        <a href="#" style="color:#666; text-decoration:none; font-size:10px; letter-spacing:1px;">Privacy Policy</a>
        <a href="#" style="color:#666; text-decoration:none; font-size:10px; letter-spacing:1px;">Cookie Policy</a>
      </div>
      <p style="font-size:10px; color:#555; margin-top:4px;">© 2026 Alessia Mei</p>
    </div>

  </div>
</footer>
</div>

<!-- ═══════════════════════════════════════════ CHI SONO ═══ -->
<div id="page-about" class="page">

  <div class="about-hero">
    <div class="about-left">
      <div class="about-bg-text">ESSENZA</div>
      <div class="about-left-content">
        <p class="about-left-tag">La mentor</p>
        <h1 class="about-name">Alessia<br>Mei</h1>
        <p class="about-role">Business Mentor · Fondatrice di ESSENZA</p>
      </div>
    </div>
    <div class="about-right">
      <p class="about-intro">
        Ho costruito un business da cifre significative senza ADV, senza un pubblico enorme.<br><br>
        <em>Solo con un sistema.</em>
      </p>
      <p class="about-body">
        Per anni ho lavorato nel mondo del business digitale, osservando un paradosso che si ripeteva sempre: le professioniste più competenti erano spesso le meno visibili. Non per mancanza di talento — per mancanza di metodo.
      </p>
      <p class="about-body">
        Nutrizioniste e personal trainer con anni di formazione alle spalle, bloccate in un circolo vizioso di contenuti gratuiti, prezzi svalutati e clienti discontinui. Ho capito che il problema non era mai la competenza: era il sistema.
      </p>
      <p class="about-body">
        ESSENZA nasce da questa consapevolezza. Un metodo costruito specificamente per il settore wellness — non adattato, non tradotto da altri settori. Pensato esattamente per te.
      </p>
    </div>
  </div>

  <div class="about-values">
    <div style="max-width: 1100px; margin: 0 auto;">
      <p class="section-label">I miei principi</p>
      <h2 class="section-title">Come lavoro <em>e perché</em> funziona.</h2>
      <div class="about-values-grid">
        <div class="value-item">
          <h4>Specializzazione prima di tutto</h4>
          <p>Non lavoro con tutti. Lavoro con nutrizioniste e PT. Questa scelta non limita — amplifica l'impatto.</p>
        </div>
        <div class="value-item">
          <h4>Sistema, non ispirazione</h4>
          <p>La motivazione dura giorni. Un sistema dura anni. Costruiamo strutture, non emozioni.</p>
        </div>
        <div class="value-item">
          <h4>Meno contenuti, più clienti</h4>
          <p>Il volume non è strategia. La precisione sì. Ogni contenuto ha uno scopo preciso nel funnel.</p>
        </div>
        <div class="value-item">
          <h4>Vendita come servizio</h4>
          <p>Vendere è aiutare qualcuno a prendere una decisione che cambia la sua situazione. Niente di più.</p>
        </div>
      </div>
    </div>
  </div>

  <div class="call-section" style="background: var(--charcoal);">
    <div class="call-inner">
      <p class="section-label">Lavorare insieme</p>
      <h2 class="section-title" style="color:rgba(255,255,255,0.9);">Se senti che è <em>il momento</em>,<br>parliamoci.</h2>
      <p class="call-body" style="color: rgba(255,255,255,0.5);">Non ti chiedo di fidarti ciecamente. Ti chiedo di fare una call di 30 minuti per capire se posso davvero aiutarti. Se la risposta è no, te lo dico io per prima.</p>
      <br><br>
      <a class="btn-primary" href="https://calendly.com/alessiamei/call-conoscitiva-gratuita-con-alessia-mei?month=2026-03&date=2026-03-03" target="_blank" style="background: var(--accent); color: #fff;">Prenota la call conoscitiva</a>
    </div>
  </div>

  <footer>
  <div class="footer-grid" style="display:grid; grid-template-columns:1fr 1fr 1fr; gap:40px; max-width:1200px; margin:0 auto; width:100%; padding:60px; background:var(--charcoal); color:#aaa;">
    
    <div>
      <div class="footer-logo" style="font-family:'Playfair Display',serif; font-size:18px; letter-spacing:4px; color:#fff; margin-bottom:16px;">ESSENZA</div>
      <p style="font-size:12px; line-height:1.8; color:#aaa;">Alessia Mei<br>Business Mentor per Nutrizioniste<br>e Personal Trainer<br>P.I. IT05127600236</p>
    </div>

    <div style="display:flex; flex-direction:column; align-items:center; justify-content:center;">
      <p style="font-family:'Playfair Display',serif; font-style:italic; font-size:15px; color:#ccc; text-align:center;"><em>Meno contenuti, più clienti.</em></p>
    </div>

    <div style="display:flex; flex-direction:column; align-items:flex-end; gap:16px;">
      <div style="display:flex; gap:16px; align-items:center;">
        <a href="https://www.instagram.com/alessiamei/" target="_blank" title="Instagram" style="color:#aaa; text-decoration:none; font-size:11px; letter-spacing:1.5px; text-transform:uppercase;">&#128247; Instagram</a>
        <a href="https://www.linkedin.com/in/alessia-mei/" target="_blank" title="LinkedIn" style="color:#aaa; text-decoration:none; font-size:11px; letter-spacing:1.5px; text-transform:uppercase;">&#128188; LinkedIn</a>
      </div>
      <div style="display:flex; gap:16px; align-items:center;">
        <a href="mailto:ciao@alessiamei.com" style="color:#aaa; text-decoration:none; font-size:11px; letter-spacing:1px;">&#9993; ciao@alessiamei.com</a>
      </div>
      <div style="display:flex; gap:16px; align-items:center;">
        <a href="https://wa.me/393511781139" target="_blank" style="color:#aaa; text-decoration:none; font-size:11px; letter-spacing:1px;">&#128242; +39 351 178 1139</a>
      </div>
      <div style="display:flex; gap:16px; margin-top:8px;">
        <a href="#" style="color:#666; text-decoration:none; font-size:10px; letter-spacing:1px;">Privacy Policy</a>
        <a href="#" style="color:#666; text-decoration:none; font-size:10px; letter-spacing:1px;">Cookie Policy</a>
      </div>
      <p style="font-size:10px; color:#555; margin-top:4px;">© 2026 Alessia Mei</p>
    </div>

  </div>
</footer>
</div>

<!-- ═══════════════════════════════════════════ LAVORA CON ME ═══ -->
<div id="page-offers" class="page">

  <div class="offers-hero">
    <p class="section-label" style="display:block; margin-bottom:16px;">I percorsi</p>
    <h1 class="section-title" style="max-width:600px; margin: 0 auto 16px;">Costruiamo insieme<br>il tuo business <em>da zero</em> o lo <em>scaliamo.</em></h1>
    <p class="offers-hero-sub">Ogni percorso è pensato per un momento specifico del tuo percorso. Prima di scegliere, leggi con attenzione. Se hai dubbi, la call è il posto giusto per chiarirli.</p>
  </div>

  <div class="offers-grid">
    <div class="offer-card">
      <p class="offer-level">Livello 1</p>
      <h3 class="offer-name">Scintilla ESSENZA</h3>
      <p class="offer-tagline">La sessione strategica intensiva di 2 ore per chi ha bisogno di una svolta veloce e una direzione chiara.</p>
      <div class="offer-includes">
        <h5>Cosa include</h5>
        <ul>
          <li>Audit completo del tuo profilo e della tua strategia</li>
          <li>Analisi del tuo funnel (o creazione da zero)</li>
          <li>Piano d'azione 30 giorni con priorità chiare</li>
          <li>Registrazione della sessione</li>
          <li>Documento strategico personalizzato</li>
          <li>7 giorni di supporto post-sessione via email</li>
        </ul>
      </div>
      
      <a class="btn-ghost" href="https://forms.gle/NL3Mf6HGpjgTVASV8" target="_blank">Candidati ora</a>
    </div>

    <div class="offer-card featured">
      <p class="offer-level">Livello 2</p>
      <h3 class="offer-name">Boost ESSENZA</h3>
      <p class="offer-tagline">Il programma intensivo di 3 mesi per chi ha già un business avviato e vuole costruire un sistema replicabile che scala.</p>
      <div class="offer-includes">
        <h5>Cosa include</h5>
        <ul>
          <li>6 call 1:1 da 60 minuti (2 al mese)</li>
          <li>Supporto WhatsApp illimitato lunedì–venerdì</li>
          <li>Review settimanale dei contenuti</li>
          <li>Funnel organico personalizzato</li>
          <li>Piano contenuti 90 giorni</li>
          <li>Template e risorse personalizzate</li>
          <li>Accesso a ESSENZA Vault</li>
          <li>Registrazioni di tutte le call</li>
        </ul>
      </div>
      
      <a class="btn-primary" href="https://forms.gle/NL3Mf6HGpjgTVASV8" target="_blank">Candidati ora</a>
    </div>

    <div class="offer-card">
      <p class="offer-level">Livello 3</p>
      <h3 class="offer-name">ESSENZA Esplosiva</h3>
      <p class="offer-tagline">Il percorso 1:1 di 6 mesi che ti trasforma da professionista invisibile a brand riconosciuto nel wellness — in modo permanente.</p>
      <div class="offer-includes">
        <h5>Cosa include</h5>
        <ul>
          <li>12 call 1:1 da 75 minuti (2 al mese)</li>
          <li>Supporto WhatsApp prioritario illimitato</li>
          <li>Review illimitata di contenuti e materiali</li>
          <li>Template, script e framework personalizzati</li>
          <li>Accesso completo a ESSENZA Vault</li>
          <li>1 mese extra di supporto post-percorso</li>
          <li>Masterclass registrate su vendita e funnel</li>
          <li>Accesso alla ESSENZA Community</li>
        </ul>
      </div>
      
      <a class="btn-ghost" href="https://forms.gle/NL3Mf6HGpjgTVASV8" target="_blank">Candidati ora</a>
    </div>
  </div>

  <!-- CALL PROCESS -->
  <div class="call-section">
    <div class="call-inner">
      <p class="section-label">Come si inizia</p>
      <h2 class="section-title">Non esiste un<br><em>percorso uguale</em><br>per tutte.</h2>
      <p class="call-body">Prima di procedere con qualsiasi percorso, ci sentiamo. La call non è una presentazione commerciale — è una conversazione onesta sulla tua situazione attuale e su dove vuoi arrivare.</p>

      <div class="call-steps">
        <div class="call-step">
          <div class="call-step-num">01</div>
          <div class="call-step-title">Compila il questionario</div>
          <p class="call-step-text"><strong>Questo passaggio è obbligatorio.</strong> Mi racconti dove sei, quali sono i tuoi obiettivi e cosa hai già provato. Senza questionario compilato, la call non viene confermata.</p>
        </div>
        <div class="call-step">
          <div class="call-step-num">02</div>
          <div class="call-step-title">Call conoscitiva (30 min)</div>
          <p class="call-step-text">Analizziamo insieme la tua situazione. Se c'è un percorso adatto a te, te lo propongo. Se non è il momento giusto, te lo dico — senza giri di parole.</p>
        </div>
        <div class="call-step">
          <div class="call-step-num">03</div>
          <div class="call-step-title">Inizio del percorso</div>
          <p class="call-step-text">Se decidiamo di procedere, partiamo. Con un piano chiaro, obiettivi definiti e supporto costante dall'inizio alla fine.</p>
        </div>
      </div>

      <div style="background: var(--charcoal); padding: 40px; margin: 40px 0; text-align: left;">
        <p style="font-size: 11px; letter-spacing: 2.5px; text-transform: uppercase; color: var(--accent); margin-bottom: 12px;">Importante</p>
        <p style="font-family: 'Playfair Display', serif; font-size: 20px; font-style: italic; color: rgba(255,255,255,0.85); line-height: 1.7; margin-bottom: 0;">Per prenotare la call è necessario compilare prima il questionario. È il primo gesto concreto verso il tuo cambiamento.</p>
      </div>

      <a class="btn-primary" href="https://calendly.com/alessiamei/call-conoscitiva-gratuita-con-alessia-mei?month=2026-03&date=2026-03-03" target="_blank">Compila il questionario e prenota la call →</a>
    </div>

<section class="faq-section">
  <div class="faq-inner">
    <p class="section-label">Domande frequenti</p>
    <h2 class="section-title">Tutto quello che<br><em>vuoi sapere.</em></h2>
    <div class="faq-list">

      <div class="faq-item">
        <button class="faq-question" onclick="toggleFaq(this)">Come funziona il percorso con te?<span class="faq-icon">+</span></button>
        <div class="faq-answer">
          <p>Ci sono tre tipologie di percorso con contatto diretto e call strategiche personalizzate. Ogni fase è costruita sulla tua situazione, il tuo business e i tuoi obiettivi.</p>
          <p>Per scoprire modalità e step, <a href="https://docs.google.com/forms/d/e/1FAIpQLSdG_-imQ_chZuUVnd5xyE__QLg988tQ-j2O1MKpUtTq48sMRQ/viewform" target="_blank">compila il questionario di candidatura</a> per accedere alla call conoscitiva.</p>
        </div>
      </div>

      <div class="faq-item">
        <button class="faq-question" onclick="toggleFaq(this)">A chi è adatto il percorso?<span class="faq-icon">+</span></button>
        <div class="faq-answer">
          <p>A chi vuole smettere di vendere "a caso" e iniziare a vendere con un sistema, strategia ed eleganza.</p>
          <p>Perfetto per chi ha un business già avviato, in fase di lancio, o vuole costruirlo da zero solidamente — senza perdere tempo in tentativi — e desidera risultati reali.</p>
        </div>
      </div>

      <div class="faq-item">
        <button class="faq-question" onclick="toggleFaq(this)">Posso pagare a rate?<span class="faq-icon">+</span></button>
        <div class="faq-answer">
          <p>Sì, sono disponibili piani di pagamento rateizzati. Ne parliamo durante la call conoscitiva per trovare la soluzione più adatta a te.</p>
        </div>
      </div>

      <div class="faq-item">
        <button class="faq-question" onclick="toggleFaq(this)">In quanto tempo vedrò i risultati?<span class="faq-icon">+</span></button>
        <div class="faq-answer">
          <p>Dipende da te. La maggior parte delle mie clienti vede cambiamenti concreti nella comunicazione e nei risultati già dal primo mese.</p>
        </div>
      </div>

      <div class="faq-item">
        <button class="faq-question" onclick="toggleFaq(this)">Come faccio a iniziare?<span class="faq-icon">+</span></button>
        <div class="faq-answer">
          <p><a href="https://docs.google.com/forms/d/e/1FAIpQLSdG_-imQ_chZuUVnd5xyE__QLg988tQ-j2O1MKpUtTq48sMRQ/viewform" target="_blank">Compila il questionario di candidatura e prenota una call conoscitiva.</a> Valutiamo insieme obiettivi, bisogni e possibilità di lavorare insieme.</p>
        </div>
      </div>

    </div>
  </div>
</section>

  </div>

  <footer>
  <div class="footer-grid" style="display:grid; grid-template-columns:1fr 1fr 1fr; gap:40px; max-width:1200px; margin:0 auto; width:100%; padding:60px; background:var(--charcoal); color:#aaa;">
    
    <div>
      <div class="footer-logo" style="font-family:'Playfair Display',serif; font-size:18px; letter-spacing:4px; color:#fff; margin-bottom:16px;">ESSENZA</div>
      <p style="font-size:12px; line-height:1.8; color:#aaa;">Alessia Mei<br>Business Mentor per Nutrizioniste<br>e Personal Trainer<br>P.I. IT05127600236</p>
    </div>

    <div style="display:flex; flex-direction:column; align-items:center; justify-content:center;">
      <p style="font-family:'Playfair Display',serif; font-style:italic; font-size:15px; color:#ccc; text-align:center;"><em>Meno contenuti, più clienti.</em></p>
    </div>

    <div style="display:flex; flex-direction:column; align-items:flex-end; gap:16px;">
      <div style="display:flex; gap:16px; align-items:center;">
        <a href="https://www.instagram.com/alessiamei/" target="_blank" title="Instagram" style="color:#aaa; text-decoration:none; font-size:11px; letter-spacing:1.5px; text-transform:uppercase;">&#128247; Instagram</a>
        <a href="https://www.linkedin.com/in/alessia-mei/" target="_blank" title="LinkedIn" style="color:#aaa; text-decoration:none; font-size:11px; letter-spacing:1.5px; text-transform:uppercase;">&#128188; LinkedIn</a>
      </div>
      <div style="display:flex; gap:16px; align-items:center;">
        <a href="mailto:ciao@alessiamei.com" style="color:#aaa; text-decoration:none; font-size:11px; letter-spacing:1px;">&#9993; ciao@alessiamei.com</a>
      </div>
      <div style="display:flex; gap:16px; align-items:center;">
        <a href="https://wa.me/393511781139" target="_blank" style="color:#aaa; text-decoration:none; font-size:11px; letter-spacing:1px;">&#128242; +39 351 178 1139</a>
      </div>
      <div style="display:flex; gap:16px; margin-top:8px;">
        <a href="#" style="color:#666; text-decoration:none; font-size:10px; letter-spacing:1px;">Privacy Policy</a>
        <a href="#" style="color:#666; text-decoration:none; font-size:10px; letter-spacing:1px;">Cookie Policy</a>
      </div>
      <p style="font-size:10px; color:#555; margin-top:4px;">© 2026 Alessia Mei</p>
    </div>

  </div>
</footer>
</div>

<!-- ═══════════════════════════════════════════ RISORSE ═══ -->


<script>
document.addEventListener("DOMContentLoaded",function(){showPage("home");});
function showPage(name) {
  document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
  const target = document.getElementById('page-' + name);
  if (target) {
    target.classList.add('active');
    window.scrollTo({ top: 0, behavior: 'smooth' });
  }
}

function toggleFaq(btn) {
  const ans = btn.nextElementSibling;
  const icon = btn.querySelector('.faq-icon');
  const open = ans.classList.contains('open');
  document.querySelectorAll('.faq-answer').forEach(a => a.classList.remove('open'));
  document.querySelectorAll('.faq-icon').forEach(i => i.textContent = '+');
  if (!open) { ans.classList.add('open'); icon.textContent = '×'; }
}
</script>

</body>
</html>
