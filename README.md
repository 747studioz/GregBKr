<!DOCTYPE html>

<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>GREGBKr | Chicago Artist & Author</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=DM+Serif+Display:ital@0;1&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --gold: #C9A84C;
    --gold-light: #E8C97A;
    --gold-dim: rgba(201,168,76,0.15);
    --black: #0A0A0A;
    --surface: #111111;
    --surface2: #181818;
    --text: #F0EBE0;
    --muted: #888880;
    --border: rgba(201,168,76,0.2);
  }

*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

html { scroll-behavior: smooth; }

body {
font-family: ‘DM Sans’, sans-serif;
background: var(–black);
color: var(–text);
min-height: 100vh;
overflow-x: hidden;
}

/* ── NOISE TEXTURE OVERLAY ── */
body::before {
content: ‘’;
position: fixed;
inset: 0;
background-image: url(“data:image/svg+xml,%3Csvg viewBox=‘0 0 256 256’ xmlns=‘http://www.w3.org/2000/svg’%3E%3Cfilter id=‘noise’%3E%3CfeTurbulence type=‘fractalNoise’ baseFrequency=‘0.9’ numOctaves=‘4’ stitchTiles=‘stitch’/%3E%3C/filter%3E%3Crect width=‘100%25’ height=‘100%25’ filter=‘url(%23noise)’ opacity=‘0.04’/%3E%3C/svg%3E”);
pointer-events: none;
z-index: 1000;
opacity: 0.5;
}

/* ── BACKGROUND GLOW ── */
.bg-glow {
position: fixed;
top: -200px;
left: 50%;
transform: translateX(-50%);
width: 600px;
height: 600px;
background: radial-gradient(ellipse, rgba(201,168,76,0.12) 0%, transparent 70%);
pointer-events: none;
z-index: 0;
}

.container {
position: relative;
z-index: 1;
max-width: 520px;
margin: 0 auto;
padding: 40px 20px 80px;
}

/* ── HEADER ── */
.header {
text-align: center;
margin-bottom: 40px;
animation: fadeUp 0.8s ease both;
}

.avatar-ring {
width: 96px;
height: 96px;
border-radius: 50%;
background: linear-gradient(135deg, var(–gold), #7A5A1A, var(–gold-light));
padding: 2px;
margin: 0 auto 18px;
position: relative;
}

.avatar-inner {
width: 100%;
height: 100%;
border-radius: 50%;
background: var(–surface);
display: flex;
align-items: center;
justify-content: center;
font-family: ‘Bebas Neue’, sans-serif;
font-size: 36px;
color: var(–gold);
letter-spacing: 1px;
}

.name {
font-family: ‘Bebas Neue’, sans-serif;
font-size: clamp(42px, 12vw, 64px);
letter-spacing: 4px;
color: var(–text);
line-height: 1;
margin-bottom: 6px;
}

.name span {
color: var(–gold);
}

.tagline {
font-family: ‘DM Serif Display’, serif;
font-style: italic;
font-size: 15px;
color: var(–muted);
letter-spacing: 0.5px;
margin-bottom: 8px;
}

.location {
font-size: 11px;
text-transform: uppercase;
letter-spacing: 3px;
color: var(–gold);
font-weight: 500;
opacity: 0.8;
}

/* ── GOLD DIVIDER ── */
.divider {
display: flex;
align-items: center;
gap: 12px;
margin: 28px 0;
}

.divider::before,
.divider::after {
content: ‘’;
flex: 1;
height: 1px;
background: linear-gradient(to right, transparent, var(–border), transparent);
}

.divider-diamond {
width: 6px;
height: 6px;
background: var(–gold);
transform: rotate(45deg);
flex-shrink: 0;
}

/* ── FEATURED CTA ── */
.featured {
background: linear-gradient(135deg, rgba(201,168,76,0.08), rgba(201,168,76,0.02));
border: 1px solid var(–border);
border-radius: 16px;
padding: 24px 20px;
margin-bottom: 32px;
text-align: center;
position: relative;
overflow: hidden;
animation: fadeUp 0.8s 0.2s ease both;
}

.featured::before {
content: ‘’;
position: absolute;
top: 0; left: 0; right: 0;
height: 1px;
background: linear-gradient(90deg, transparent, var(–gold), transparent);
}

.badge {
display: inline-block;
background: var(–gold);
color: var(–black);
font-size: 9px;
font-weight: 700;
text-transform: uppercase;
letter-spacing: 2px;
padding: 4px 10px;
border-radius: 20px;
margin-bottom: 12px;
}

.featured-title {
font-family: ‘Bebas Neue’, sans-serif;
font-size: 26px;
letter-spacing: 2px;
color: var(–text);
margin-bottom: 6px;
line-height: 1.1;
}

.featured-sub {
font-size: 12px;
color: var(–muted);
margin-bottom: 6px;
line-height: 1.5;
}

.featured-items {
font-size: 11px;
color: var(–gold-light);
margin-bottom: 18px;
font-weight: 500;
opacity: 0.85;
}

.price-row {
display: flex;
align-items: center;
justify-content: center;
gap: 10px;
margin-bottom: 18px;
}

.price-was {
font-size: 13px;
color: var(–muted);
text-decoration: line-through;
}

.price-now {
font-family: ‘Bebas Neue’, sans-serif;
font-size: 32px;
color: var(–gold);
letter-spacing: 2px;
}

.cta-btn {
display: block;
width: 100%;
background: linear-gradient(135deg, var(–gold), #A07828, var(–gold));
background-size: 200% 100%;
color: var(–black);
font-family: ‘DM Sans’, sans-serif;
font-weight: 700;
font-size: 13px;
text-transform: uppercase;
letter-spacing: 2px;
padding: 14px 20px;
border-radius: 8px;
text-decoration: none;
border: none;
cursor: pointer;
transition: background-position 0.4s ease, transform 0.15s ease, box-shadow 0.3s ease;
box-shadow: 0 4px 24px rgba(201,168,76,0.25);
}

.cta-btn:hover {
background-position: 100% 0;
transform: translateY(-2px);
box-shadow: 0 8px 32px rgba(201,168,76,0.4);
}

.cta-btn:active { transform: translateY(0); }

/* ── SECTION LABEL ── */
.section-label {
font-size: 10px;
text-transform: uppercase;
letter-spacing: 4px;
color: var(–muted);
margin-bottom: 14px;
font-weight: 500;
animation: fadeUp 0.8s 0.4s ease both;
}

/* ── SOCIAL LINKS ── */
.links-grid {
display: flex;
flex-direction: column;
gap: 10px;
margin-bottom: 32px;
}

.link-card {
display: flex;
align-items: center;
gap: 16px;
background: var(–surface);
border: 1px solid rgba(255,255,255,0.05);
border-radius: 12px;
padding: 16px 18px;
text-decoration: none;
color: var(–text);
transition: border-color 0.25s, background 0.25s, transform 0.2s;
animation: fadeUp 0.8s ease both;
position: relative;
overflow: hidden;
}

.link-card::after {
content: ‘’;
position: absolute;
inset: 0;
opacity: 0;
transition: opacity 0.3s;
}

.link-card:hover {
transform: translateX(4px);
border-color: var(–border);
background: var(–surface2);
}

.link-card:nth-child(1) { animation-delay: 0.45s; }
.link-card:nth-child(2) { animation-delay: 0.55s; }
.link-card:nth-child(3) { animation-delay: 0.65s; }
.link-card:nth-child(4) { animation-delay: 0.75s; }
.link-card:nth-child(5) { animation-delay: 0.85s; }

.link-icon {
width: 40px;
height: 40px;
border-radius: 10px;
display: flex;
align-items: center;
justify-content: center;
flex-shrink: 0;
font-size: 18px;
}

.link-icon.instagram { background: linear-gradient(135deg, #833AB4, #FD1D1D, #FCB045); }
.link-icon.tiktok    { background: #010101; border: 1px solid rgba(255,255,255,0.1); }
.link-icon.youtube   { background: #FF0000; }
.link-icon.facebook  { background: #1877F2; }
.link-icon.shop      { background: linear-gradient(135deg, var(–gold), #7A5A1A); }

.link-text { flex: 1; }
.link-name {
font-weight: 600;
font-size: 14px;
margin-bottom: 2px;
}
.link-handle {
font-size: 11px;
color: var(–muted);
}

.link-arrow {
color: var(–muted);
font-size: 16px;
transition: transform 0.2s, color 0.2s;
}

.link-card:hover .link-arrow {
transform: translateX(3px);
color: var(–gold);
}

/* ── SECONDARY STORE LINKS ── */
.quick-links {
display: flex;
flex-wrap: wrap;
gap: 8px;
margin-bottom: 32px;
animation: fadeUp 0.8s 0.9s ease both;
}

.quick-link {
flex: 1;
min-width: 130px;
display: flex;
align-items: center;
justify-content: center;
gap: 6px;
background: var(–surface);
border: 1px solid var(–border);
border-radius: 8px;
padding: 12px 14px;
text-decoration: none;
color: var(–gold-light);
font-size: 11px;
font-weight: 600;
text-transform: uppercase;
letter-spacing: 1.5px;
transition: background 0.2s, transform 0.15s;
}

.quick-link:hover {
background: var(–gold-dim);
transform: translateY(-2px);
}

/* ── QUOTE ── */
.quote-block {
border-left: 2px solid var(–gold);
padding: 4px 0 4px 16px;
margin-bottom: 32px;
animation: fadeUp 0.8s 1s ease both;
}

.quote-text {
font-family: ‘DM Serif Display’, serif;
font-style: italic;
font-size: 15px;
color: var(–text);
line-height: 1.6;
opacity: 0.85;
}

.quote-attr {
font-size: 10px;
text-transform: uppercase;
letter-spacing: 2px;
color: var(–gold);
margin-top: 6px;
opacity: 0.7;
}

/* ── FOOTER ── */
.footer {
text-align: center;
font-size: 11px;
color: var(–muted);
letter-spacing: 1px;
padding-top: 24px;
border-top: 1px solid rgba(255,255,255,0.05);
animation: fadeUp 0.8s 1.1s ease both;
}

.footer span { color: var(–gold); }

/* ── ANIMATIONS ── */
@keyframes fadeUp {
from { opacity: 0; transform: translateY(20px); }
to   { opacity: 1; transform: translateY(0); }
}

/* ── MOBILE TWEAKS ── */
@media (max-width: 400px) {
.container { padding: 28px 16px 60px; }
.featured-title { font-size: 22px; }
}
</style>

</head>
<body>

<div class="bg-glow"></div>

<div class="container">

  <!-- HEADER -->

  <header class="header">
    <div class="avatar-ring">
      <div class="avatar-inner">G</div>
    </div>
    <h1 class="name">GREG<span>BKr</span></h1>
    <p class="tagline">Producer · Author · Independent Artist</p>
    <p class="location">✦ Chicago, IL — South Side ✦</p>
  </header>

  <!-- FEATURED PRODUCT -->

  <div class="featured">
    <span class="badge">🔥 Featured Drop</span>
    <div class="featured-title">The Great Thinker<br>Series Bundle</div>
    <p class="featured-sub">Everything you need to build your mind, your music, and your peace — in one complete package.</p>
    <p class="featured-items">5 Ebooks · Logic Pro X Vocal Masterclass · Instant Download</p>
    <div class="price-row">
      <span class="price-was">$49.95</span>
      <span class="price-now">$37</span>
    </div>
    <a class="cta-btn" href="https://gregbkr.myshopify.com/" target="_blank" rel="noopener">
      Get the Bundle →
    </a>
  </div>

  <div class="divider"><div class="divider-diamond"></div></div>

  <!-- SOCIAL LINKS -->

  <p class="section-label">Follow the Journey</p>
  <div class="links-grid">

```
<a class="link-card" href="https://www.instagram.com/gregbaker_pbmg?igsh=MWNmNGJocm41NG1oOQ%3D%3D&utm_source=qr" target="_blank" rel="noopener">
  <div class="link-icon instagram">
    <svg width="18" height="18" viewBox="0 0 24 24" fill="white"><path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"/></svg>
  </div>
  <div class="link-text">
    <div class="link-name">Instagram</div>
    <div class="link-handle">@gregbaker_pbmg</div>
  </div>
  <span class="link-arrow">›</span>
</a>

<a class="link-card" href="https://www.tiktok.com/@gregbaker_pbmg" target="_blank" rel="noopener">
  <div class="link-icon tiktok">
    <svg width="18" height="18" viewBox="0 0 24 24" fill="white"><path d="M19.59 6.69a4.83 4.83 0 01-3.77-4.25V2h-3.45v13.67a2.89 2.89 0 01-2.88 2.5 2.89 2.89 0 01-2.89-2.89 2.89 2.89 0 012.89-2.89c.28 0 .54.04.79.1V9.01a6.33 6.33 0 00-.79-.05 6.34 6.34 0 00-6.34 6.34 6.34 6.34 0 006.34 6.34 6.34 6.34 0 006.33-6.34V8.69a8.19 8.19 0 004.79 1.53V6.77a4.85 4.85 0 01-1.02-.08z"/></svg>
  </div>
  <div class="link-text">
    <div class="link-name">TikTok</div>
    <div class="link-handle">@gregbaker_pbmg</div>
  </div>
  <span class="link-arrow">›</span>
</a>

<a class="link-card" href="https://youtube.com/@gregbaker_pbmg" target="_blank" rel="noopener">
  <div class="link-icon youtube">
    <svg width="18" height="18" viewBox="0 0 24 24" fill="white"><path d="M23.498 6.186a3.016 3.016 0 00-2.122-2.136C19.505 3.545 12 3.545 12 3.545s-7.505 0-9.377.505A3.017 3.017 0 00.502 6.186C0 8.07 0 12 0 12s0 3.93.502 5.814a3.016 3.016 0 002.122 2.136c1.871.505 9.376.505 9.376.505s7.505 0 9.377-.505a3.015 3.015 0 002.122-2.136C24 15.93 24 12 24 12s0-3.93-.502-5.814zM9.545 15.568V8.432L15.818 12l-6.273 3.568z"/></svg>
  </div>
  <div class="link-text">
    <div class="link-name">YouTube</div>
    <div class="link-handle">@gregbaker_pbmg</div>
  </div>
  <span class="link-arrow">›</span>
</a>

<a class="link-card" href="https://www.facebook.com/share/1GhmcT8j66/" target="_blank" rel="noopener">
  <div class="link-icon facebook">
    <svg width="18" height="18" viewBox="0 0 24 24" fill="white"><path d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z"/></svg>
  </div>
  <div class="link-text">
    <div class="link-name">Facebook</div>
    <div class="link-handle">GREGBKr</div>
  </div>
  <span class="link-arrow">›</span>
</a>

<a class="link-card" href="https://gregbkr.myshopify.com/" target="_blank" rel="noopener" style="border-color: var(--border);">
  <div class="link-icon shop">
    <svg width="18" height="18" viewBox="0 0 24 24" fill="#0A0A0A"><path d="M6 2L3 6v14a2 2 0 002 2h14a2 2 0 002-2V6l-3-4z"/><line x1="3" y1="6" x2="21" y2="6" stroke="#0A0A0A" stroke-width="2"/><path d="M16 10a4 4 0 01-8 0" fill="none" stroke="#0A0A0A" stroke-width="2"/></svg>
  </div>
  <div class="link-text">
    <div class="link-name" style="color: var(--gold);">Official Store</div>
    <div class="link-handle">Merch · Music · Ebooks</div>
  </div>
  <span class="link-arrow" style="color: var(--gold);">›</span>
</a>
```

  </div>

  <!-- QUICK SHOP CATEGORIES -->

  <p class="section-label">Shop By Category</p>
  <div class="quick-links">
    <a class="quick-link" href="https://gregbkr.myshopify.com/" target="_blank" rel="noopener">📖 Books</a>
    <a class="quick-link" href="https://gregbkr.myshopify.com/" target="_blank" rel="noopener">🎧 Music</a>
    <a class="quick-link" href="https://gregbkr.myshopify.com/" target="_blank" rel="noopener">👕 Merch</a>
  </div>

  <div class="divider"><div class="divider-diamond"></div></div>

  <!-- BRAND QUOTE -->

  <div class="quote-block">
    <p class="quote-text">"Every great thought begins with the decision to think differently."</p>
    <p class="quote-attr">— GREGBKr · The Great Thinker Series</p>
  </div>

  <!-- FOOTER -->

  <footer class="footer">
    <p>© 2025 <span>GREGBKr</span> · Chicago, IL · All Rights Reserved</p>
    <p style="margin-top:6px; opacity:0.5;">gregbkr.com</p>
  </footer>

</div>

</body>
</html>
