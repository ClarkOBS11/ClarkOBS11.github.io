<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>The Fairway — Golf News</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;0,900;1,400&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --green-deep: #1a3a2a;
    --green-mid: #2d5a3d;
    --green-light: #4a7c59;
    --cream: #f5f0e8;
    --cream-dark: #e8e0d0;
    --gold: #c9a84c;
    --gold-light: #e8c97a;
    --text-dark: #1a1a1a;
    --text-mid: #4a4a4a;
    --text-light: #888;
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    font-family: 'DM Sans', sans-serif;
    background-color: var(--cream);
    color: var(--text-dark);
    overflow-x: hidden;
  }

  /* HEADER */
  header {
    background-color: var(--green-deep);
    padding: 0 2rem;
    position: sticky;
    top: 0;
    z-index: 100;
    box-shadow: 0 2px 20px rgba(0,0,0,0.3);
  }

  nav {
    max-width: 1200px;
    margin: 0 auto;
    display: flex;
    align-items: center;
    justify-content: space-between;
    height: 64px;
  }

  .logo {
    font-family: 'Playfair Display', serif;
    font-size: 1.6rem;
    font-weight: 900;
    color: var(--cream);
    letter-spacing: -0.5px;
  }

  .logo span {
    color: var(--gold);
  }

  nav ul {
    list-style: none;
    display: flex;
    gap: 2rem;
  }

  nav ul a {
    color: var(--cream-dark);
    text-decoration: none;
    font-size: 0.85rem;
    font-weight: 500;
    letter-spacing: 0.05em;
    text-transform: uppercase;
    transition: color 0.2s;
  }

  nav ul a:hover { color: var(--gold); }

  /* HERO */
  .hero {
    background-color: var(--green-deep);
    background-image:
      radial-gradient(ellipse at 70% 50%, rgba(74,124,89,0.25) 0%, transparent 60%),
      repeating-linear-gradient(
        90deg,
        transparent,
        transparent 80px,
        rgba(255,255,255,0.015) 80px,
        rgba(255,255,255,0.015) 81px
      );
    padding: 5rem 2rem 4rem;
    text-align: center;
    position: relative;
    overflow: hidden;
  }

  .hero::after {
    content: '';
    position: absolute;
    bottom: 0; left: 0; right: 0;
    height: 60px;
    background: var(--cream);
    clip-path: ellipse(55% 100% at 50% 100%);
  }

  .hero-tag {
    display: inline-block;
    background: var(--gold);
    color: var(--green-deep);
    font-size: 0.7rem;
    font-weight: 700;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    padding: 0.3rem 0.9rem;
    border-radius: 2px;
    margin-bottom: 1.2rem;
    animation: fadeUp 0.6s ease both;
  }

  .hero h1 {
    font-family: 'Playfair Display', serif;
    font-size: clamp(2.2rem, 5vw, 3.8rem);
    font-weight: 900;
    color: var(--cream);
    line-height: 1.1;
    max-width: 720px;
    margin: 0 auto 1.2rem;
    animation: fadeUp 0.6s 0.1s ease both;
  }

  .hero p {
    color: rgba(245,240,232,0.65);
    font-size: 1.05rem;
    font-weight: 300;
    max-width: 480px;
    margin: 0 auto 2rem;
    line-height: 1.6;
    animation: fadeUp 0.6s 0.2s ease both;
  }

  .hero-meta {
    display: flex;
    justify-content: center;
    gap: 1.5rem;
    animation: fadeUp 0.6s 0.3s ease both;
  }

  .hero-meta span {
    color: rgba(245,240,232,0.5);
    font-size: 0.8rem;
    letter-spacing: 0.05em;
  }

  .hero-meta span strong {
    color: var(--gold-light);
    font-weight: 500;
  }

  /* MAIN LAYOUT */
  main {
    max-width: 1200px;
    margin: 0 auto;
    padding: 3rem 2rem 4rem;
    display: grid;
    grid-template-columns: 1fr 320px;
    gap: 3rem;
  }

  /* SECTION LABEL */
  .section-label {
    display: flex;
    align-items: center;
    gap: 0.8rem;
    margin-bottom: 1.8rem;
  }

  .section-label h2 {
    font-family: 'Playfair Display', serif;
    font-size: 1.3rem;
    font-weight: 700;
    color: var(--green-deep);
  }

  .section-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--cream-dark);
  }

  /* ARTICLE CARDS */
  .articles-grid {
    display: flex;
    flex-direction: column;
    gap: 2rem;
  }

  .card {
    background: white;
    border-radius: 8px;
    overflow: hidden;
    display: grid;
    grid-template-columns: 200px 1fr;
    box-shadow: 0 1px 4px rgba(0,0,0,0.06);
    transition: transform 0.2s, box-shadow 0.2s;
    cursor: pointer;
    animation: fadeUp 0.5s ease both;
  }

  .card:hover {
    transform: translateY(-3px);
    box-shadow: 0 8px 24px rgba(26,58,42,0.12);
  }

  .card:nth-child(1) { animation-delay: 0.1s; }
  .card:nth-child(2) { animation-delay: 0.2s; }
  .card:nth-child(3) { animation-delay: 0.3s; }
  .card:nth-child(4) { animation-delay: 0.4s; }

  .card-img {
    background: var(--green-mid);
    position: relative;
    overflow: hidden;
    min-height: 160px;
  }

  .card-img svg {
    position: absolute;
    inset: 0;
    width: 100%;
    height: 100%;
  }

  .card-img .img-label {
    position: absolute;
    top: 0.6rem;
    left: 0.6rem;
    background: var(--gold);
    color: var(--green-deep);
    font-size: 0.65rem;
    font-weight: 700;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    padding: 0.2rem 0.5rem;
    border-radius: 2px;
    z-index: 2;
  }

  .card-body {
    padding: 1.2rem 1.4rem;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
  }

  .card-category {
    font-size: 0.7rem;
    font-weight: 700;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: var(--green-light);
    margin-bottom: 0.4rem;
  }

  .card h3 {
    font-family: 'Playfair Display', serif;
    font-size: 1.1rem;
    font-weight: 700;
    line-height: 1.35;
    color: var(--text-dark);
    margin-bottom: 0.5rem;
  }

  .card h3:hover { color: var(--green-mid); }

  .card p {
    font-size: 0.85rem;
    color: var(--text-mid);
    line-height: 1.55;
    font-weight: 300;
    flex: 1;
    margin-bottom: 0.8rem;
  }

  .card-footer {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  .card-footer time {
    font-size: 0.75rem;
    color: var(--text-light);
  }

  .read-more {
    font-size: 0.75rem;
    font-weight: 600;
    color: var(--green-mid);
    text-decoration: none;
    display: flex;
    align-items: center;
    gap: 0.3rem;
    transition: gap 0.2s, color 0.2s;
  }

  .read-more:hover { gap: 0.6rem; color: var(--gold); }

  /* FEATURED FULL WIDTH */
  .card-featured {
    grid-column: 1 / -1;
    grid-template-columns: 1fr 1fr;
    min-height: 260px;
  }

  .card-featured .card-img { min-height: 240px; }

  .card-featured h3 { font-size: 1.4rem; }

  /* SIDEBAR */
  aside {
    display: flex;
    flex-direction: column;
    gap: 2rem;
  }

  .sidebar-box {
    background: white;
    border-radius: 8px;
    padding: 1.4rem;
    box-shadow: 0 1px 4px rgba(0,0,0,0.06);
  }

  .sidebar-box h3 {
    font-family: 'Playfair Display', serif;
    font-size: 1rem;
    font-weight: 700;
    color: var(--green-deep);
    margin-bottom: 1rem;
    padding-bottom: 0.6rem;
    border-bottom: 2px solid var(--gold);
    display: inline-block;
  }

  /* SCOREBOARD */
  .score-row {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0.6rem 0;
    border-bottom: 1px solid var(--cream-dark);
    font-size: 0.85rem;
  }

  .score-row:last-child { border-bottom: none; }

  .score-player { font-weight: 500; color: var(--text-dark); }
  .score-country { font-size: 0.75rem; color: var(--text-light); }

  .score-val {
    font-weight: 700;
    font-family: 'Playfair Display', serif;
    font-size: 1rem;
  }

  .score-val.under { color: var(--green-light); }
  .score-val.over { color: #c0392b; }
  .score-val.even { color: var(--text-mid); }

  /* TRENDING */
  .trending-item {
    display: flex;
    gap: 0.8rem;
    align-items: flex-start;
    padding: 0.7rem 0;
    border-bottom: 1px solid var(--cream-dark);
    cursor: pointer;
    transition: opacity 0.2s;
  }

  .trending-item:last-child { border-bottom: none; }
  .trending-item:hover { opacity: 0.7; }

  .trending-num {
    font-family: 'Playfair Display', serif;
    font-size: 1.4rem;
    font-weight: 900;
    color: var(--cream-dark);
    line-height: 1;
    flex-shrink: 0;
    width: 28px;
  }

  .trending-title {
    font-size: 0.85rem;
    font-weight: 500;
    color: var(--text-dark);
    line-height: 1.4;
  }

  .trending-date {
    font-size: 0.7rem;
    color: var(--text-light);
    margin-top: 0.2rem;
  }

  /* NEWSLETTER */
  .newsletter-box {
    background: var(--green-deep);
    border-radius: 8px;
    padding: 1.6rem;
    text-align: center;
  }

  .newsletter-box h3 {
    font-family: 'Playfair Display', serif;
    font-size: 1.1rem;
    color: var(--cream);
    margin-bottom: 0.5rem;
  }

  .newsletter-box p {
    font-size: 0.8rem;
    color: rgba(245,240,232,0.6);
    margin-bottom: 1rem;
    line-height: 1.5;
  }

  .newsletter-box input {
    width: 100%;
    padding: 0.6rem 0.9rem;
    border: none;
    border-radius: 4px;
    font-size: 0.85rem;
    margin-bottom: 0.6rem;
    background: rgba(255,255,255,0.12);
    color: var(--cream);
    outline: none;
    font-family: 'DM Sans', sans-serif;
  }

  .newsletter-box input::placeholder { color: rgba(245,240,232,0.4); }

  .newsletter-box button {
    width: 100%;
    padding: 0.65rem;
    background: var(--gold);
    color: var(--green-deep);
    border: none;
    border-radius: 4px;
    font-weight: 700;
    font-size: 0.85rem;
    letter-spacing: 0.05em;
    text-transform: uppercase;
    cursor: pointer;
    transition: background 0.2s;
    font-family: 'DM Sans', sans-serif;
  }

  .newsletter-box button:hover { background: var(--gold-light); }

  /* FOOTER */
  footer {
    background: var(--green-deep);
    color: rgba(245,240,232,0.5);
    text-align: center;
    padding: 2rem;
    font-size: 0.8rem;
  }

  footer .footer-logo {
    font-family: 'Playfair Display', serif;
    font-size: 1.3rem;
    color: var(--cream);
    margin-bottom: 0.5rem;
  }

  footer .footer-logo span { color: var(--gold); }

  /* ANIMATIONS */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(18px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  /* RESPONSIVE */
  @media (max-width: 900px) {
    main { grid-template-columns: 1fr; }
    .card { grid-template-columns: 160px 1fr; }
    .card-featured { grid-template-columns: 1fr; }
    .card-featured .card-img { min-height: 180px; }
  }

  @media (max-width: 600px) {
    nav ul { display: none; }
    .card { grid-template-columns: 1fr; }
    .card-img { min-height: 140px; }
  }
</style>
</head>
<body>

<!-- HEADER -->
<header>
  <nav>
    <div class="logo">The<span>Fairway</span></div>
    <ul>
      <li><a href="#">Tours</a></li>
      <li><a href="#">Scores</a></li>
      <li><a href="#">Gear</a></li>
      <li><a href="#">Instruction</a></li>
      <li><a href="#">Courses</a></li>
    </ul>
  </nav>
</header>

<!-- HERO -->
<div class="hero">
  <div class="hero-tag">⛳ Featured Story</div>
  <h1>Rory McIlroy Claims the Masters in Stunning Final Round</h1>
  <p>A back-nine birdie blitz at Augusta propels McIlroy to his long-awaited green jacket — and the career Grand Slam.</p>
  <div class="hero-meta">
    <span><strong>Augusta, GA</strong></span>
    <span>·</span>
    <span><strong>March 18, 2026</strong></span>
    <span>·</span>
    <span><strong>6 min read</strong></span>
  </div>
</div>

<!-- MAIN -->
<main>
  <section>
    <div class="section-label"><h2>Latest News</h2></div>
    <div class="articles-grid">

      <!-- Card 1 -->
      <article class="card">
        <div class="card-img" style="background: linear-gradient(135deg, #2d5a3d 0%, #1a3a2a 100%);">
          <svg viewBox="0 0 200 160" xmlns="http://www.w3.org/2000/svg">
            <circle cx="100" cy="130" r="80" fill="rgba(74,124,89,0.3)"/>
            <ellipse cx="100" cy="105" rx="55" ry="12" fill="rgba(74,124,89,0.5)"/>
            <circle cx="100" cy="72" r="22" fill="rgba(201,168,76,0.85)"/>
            <line x1="100" y1="94" x2="100" y2="140" stroke="rgba(255,255,255,0.3)" stroke-width="1.5"/>
          </svg>
          <div class="img-label">PGA Tour</div>
        </div>
        <div class="card-body">
          <div class="card-category">PGA Tour</div>
          <h3>Scheffler Posts Historic 59 at the Players Championship</h3>
          <p>Scottie Scheffler scorched TPC Sawgrass with a flawless 13-under 59, becoming only the fifth player to break 60 at a PGA Tour event.</p>
          <div class="card-footer">
            <time>March 17, 2026</time>
            <a class="read-more" href="#">Read →</a>
          </div>
        </div>
      </article>

      <!-- Card 2 -->
      <article class="card">
        <div class="card-img" style="background: linear-gradient(135deg, #1a3a2a 0%, #2d5a3d 100%);">
          <svg viewBox="0 0 200 160" xmlns="http://www.w3.org/2000/svg">
            <rect x="20" y="80" width="160" height="60" rx="4" fill="rgba(255,255,255,0.05)"/>
            <rect x="30" y="90" width="60" height="40" rx="2" fill="rgba(201,168,76,0.3)"/>
            <rect x="100" y="90" width="70" height="40" rx="2" fill="rgba(74,124,89,0.4)"/>
            <path d="M60 80 Q100 40 140 80" stroke="rgba(201,168,76,0.6)" stroke-width="2" fill="none"/>
            <circle cx="60" cy="80" r="5" fill="rgba(201,168,76,0.8)"/>
            <circle cx="140" cy="80" r="5" fill="rgba(74,124,89,0.8)"/>
          </svg>
          <div class="img-label">Equipment</div>
        </div>
        <div class="card-body">
          <div class="card-category">Equipment</div>
          <h3>Titleist's New Pro V1x: Is This the Best Golf Ball Ever Made?</h3>
          <p>Titleist's latest Pro V1x revision promises lower spin off the driver and more greenside control. We put it through four rounds of testing.</p>
          <div class="card-footer">
            <time>March 16, 2026</time>
            <a class="read-more" href="#">Read →</a>
          </div>
        </div>
      </article>

      <!-- Card 3 -->
      <article class="card">
        <div class="card-img" style="background: linear-gradient(135deg, #4a7c59 0%, #1a3a2a 100%);">
          <svg viewBox="0 0 200 160" xmlns="http://www.w3.org/2000/svg">
            <path d="M0 100 Q50 60 100 100 Q150 140 200 100 L200 160 L0 160Z" fill="rgba(74,124,89,0.5)"/>
            <path d="M0 120 Q50 80 100 120 Q150 160 200 120 L200 160 L0 160Z" fill="rgba(45,90,61,0.6)"/>
            <circle cx="80" cy="85" r="12" fill="rgba(255,255,255,0.15)"/>
            <line x1="80" y1="97" x2="80" y2="130" stroke="rgba(255,255,255,0.2)" stroke-width="1.5"/>
          </svg>
          <div class="img-label">Instruction</div>
        </div>
        <div class="card-body">
          <div class="card-category">Instruction</div>
          <h3>The One Swing Thought That's Fixing Amateurs' Slices</h3>
          <p>Top instructor Claude Harmon III reveals the simple mental cue that's helping high-handicappers find the fairway more consistently.</p>
          <div class="card-footer">
            <time>March 15, 2026</time>
            <a class="read-more" href="#">Read →</a>
          </div>
        </div>
      </article>

      <!-- Card 4 -->
      <article class="card">
        <div class="card-img" style="background: linear-gradient(135deg, #1a3a2a 0%, #4a7c59 100%);">
          <svg viewBox="0 0 200 160" xmlns="http://www.w3.org/2000/svg">
            <polygon points="100,20 130,80 190,80 140,115 160,175 100,135 40,175 60,115 10,80 70,80" fill="rgba(201,168,76,0.25)" stroke="rgba(201,168,76,0.5)" stroke-width="1"/>
            <circle cx="100" cy="100" r="30" fill="rgba(201,168,76,0.15)" stroke="rgba(201,168,76,0.4)" stroke-width="1.5"/>
          </svg>
          <div class="img-label">LIV Golf</div>
        </div>
        <div class="card-body">
          <div class="card-category">LIV Golf</div>
          <h3>LIV Golf Eyes Full PGA Tour Merger by End of 2026</h3>
          <p>Negotiations between LIV Golf and the PGA Tour have resumed with both sides expressing cautious optimism about reaching a framework agreement.</p>
          <div class="card-footer">
            <time>March 14, 2026</time>
            <a class="read-more" href="#">Read →</a>
          </div>
        </div>
      </article>

    </div>
  </section>

  <!-- SIDEBAR -->
  <aside>

    <!-- Leaderboard -->
    <div class="sidebar-box">
      <h3>Leaderboard</h3>
      <p style="font-size:0.72rem;color:var(--text-light);margin-bottom:0.8rem;font-weight:500;text-transform:uppercase;letter-spacing:0.08em;">The Masters · R4 Final</p>

      <div class="score-row">
        <div>
          <div class="score-player">R. McIlroy</div>
          <div class="score-country">Northern Ireland</div>
        </div>
        <div class="score-val under">-19</div>
      </div>
      <div class="score-row">
        <div>
          <div class="score-player">S. Scheffler</div>
          <div class="score-country">United States</div>
        </div>
        <div class="score-val under">-16</div>
      </div>
      <div class="score-row">
        <div>
          <div class="score-player">C. Morikawa</div>
          <div class="score-country">United States</div>
        </div>
        <div class="score-val under">-14</div>
      </div>
      <div class="score-row">
        <div>
          <div class="score-player">J. Rahm</div>
          <div class="score-country">Spain</div>
        </div>
        <div class="score-val under">-12</div>
      </div>
      <div class="score-row">
        <div>
          <div class="score-player">T. Fleetwood</div>
          <div class="score-country">England</div>
        </div>
        <div class="score-val under">-11</div>
      </div>
      <div class="score-row">
        <div>
          <div class="score-player">V. Hovland</div>
          <div class="score-country">Norway</div>
        </div>
        <div class="score-val over">+2</div>
      </div>
    </div>

    <!-- Trending -->
    <div class="sidebar-box">
      <h3>Trending</h3>

      <div class="trending-item">
        <div class="trending-num">1</div>
        <div>
          <div class="trending-title">Tiger Confirms Comeback at the US Open</div>
          <div class="trending-date">March 18, 2026</div>
        </div>
      </div>
      <div class="trending-item">
        <div class="trending-num">2</div>
        <div>
          <div class="trending-title">Best Public Golf Courses in America — 2026 Rankings</div>
          <div class="trending-date">March 17, 2026</div>
        </div>
      </div>
      <div class="trending-item">
        <div class="trending-num">3</div>
        <div>
          <div class="trending-title">How Augusta National Grows Its Famous Grass</div>
          <div class="trending-date">March 16, 2026</div>
        </div>
      </div>
      <div class="trending-item">
        <div class="trending-num">4</div>
        <div>
          <div class="trending-title">Nelly Korda Goes for 6th Consecutive LPGA Win</div>
          <div class="trending-date">March 15, 2026</div>
        </div>
      </div>
      <div class="trending-item">
        <div class="trending-num">5</div>
        <div>
          <div class="trending-title">The 10 Most Beautiful Golf Holes in the World</div>
          <div class="trending-date">March 14, 2026</div>
        </div>
      </div>
    </div>

    <!-- Newsletter -->
    <div class="newsletter-box">
      <h3>Morning Tee Time ☀️</h3>
      <p>Get the day's top golf stories before your first cup of coffee.</p>
      <input type="email" placeholder="your@email.com">
      <button>Subscribe Free</button>
    </div>

  </aside>
</main>

<!-- FOOTER -->
<footer>
  <div class="footer-logo">The<span>Fairway</span></div>
  <p>© 2026 The Fairway · All rights reserved · Golf news for those who live the game</p>
</footer>

</body>
</html>
