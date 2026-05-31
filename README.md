
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>AI for Everyday People — The Course</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Lora:ital,wght@0,400;0,600;0,700;1,400;1,600&family=Source+Sans+3:wght@300;400;500;600;700&display=swap" rel="stylesheet">
<style>
  :root {
    --teal-dark: #0B4F5A;
    --teal: #0E8A8F;
    --teal-mid: #12A4A0;
    --seafoam: #9FE3DC;
    --ice: #CFEFEB;
    --tint: #EAF4F4;
    --coral: #FF6B5B;
    --coral-dk: #E8533F;
    --ink: #1B2B2E;
    --muted: #5E7479;
    --white: #FFFFFF;
    --off-white: #F8FAFA;
    --max-w: 820px;
    --wide: 1100px;
  }
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
  html { scroll-behavior: smooth; }
  body { font-family: 'Source Sans 3', sans-serif; color: var(--ink); background: var(--white); line-height: 1.65; }
  h1, h2, h3, h4 { font-family: 'Lora', serif; line-height: 1.2; }
  img { max-width: 100%; }
  a { color: inherit; }

  /* ── NAV ── */
  nav {
    background: var(--teal-dark);
    padding: 0 2rem;
    display: flex; align-items: center; justify-content: space-between;
    height: 64px; position: sticky; top: 0; z-index: 100;
  }
  .nav-brand { font-family: 'Source Sans 3', sans-serif; font-weight: 700; color: var(--ice); font-size: 1rem; letter-spacing: .03em; }
  .nav-cta {
    background: var(--coral); color: #fff; border: none; border-radius: 30px;
    padding: .55rem 1.5rem; font-family: 'Source Sans 3'; font-weight: 700; font-size: .95rem;
    cursor: pointer; text-decoration: none; transition: background .2s;
  }
  .nav-cta:hover { background: var(--coral-dk); }

  /* ── HERO ── */
  .hero {
    background: var(--teal-dark);
    clip-path: polygon(0 0, 100% 0, 100% 90%, 0 100%);
    padding: 5rem 2rem 8rem;
    text-align: center;
    position: relative;
    overflow: hidden;
  }
  .hero::before {
    content: '';
    position: absolute; inset: 0;
    background: radial-gradient(ellipse 80% 60% at 50% 0%, rgba(14,138,143,.35) 0%, transparent 70%);
  }
  .hero-inner { position: relative; max-width: var(--max-w); margin: 0 auto; }
  .hero-kicker {
    display: inline-block; background: var(--coral); color: #fff;
    font-family: 'Source Sans 3'; font-weight: 700; font-size: .82rem;
    letter-spacing: .1em; text-transform: uppercase;
    padding: .35rem 1.1rem; border-radius: 30px; margin-bottom: 1.8rem;
  }
  .hero h1 {
    font-size: clamp(2.2rem, 5vw, 3.5rem);
    color: #fff; font-weight: 700; margin-bottom: 1.4rem;
    letter-spacing: -.01em;
  }
  .hero h1 em { color: var(--seafoam); font-style: italic; }
  .hero-sub {
    font-size: 1.22rem; color: var(--ice); max-width: 580px;
    margin: 0 auto 2.5rem; font-weight: 400; line-height: 1.7;
  }
  .hero-ctas { display: flex; gap: 1rem; justify-content: center; flex-wrap: wrap; }
  .btn-primary {
    background: var(--coral); color: #fff; border: none; border-radius: 50px;
    padding: .95rem 2.5rem; font-family: 'Source Sans 3'; font-weight: 700; font-size: 1.08rem;
    cursor: pointer; text-decoration: none; transition: all .2s; display: inline-block;
    box-shadow: 0 6px 24px rgba(255,107,91,.35);
  }
  .btn-primary:hover { background: var(--coral-dk); transform: translateY(-2px); box-shadow: 0 10px 30px rgba(255,107,91,.4); }
  .btn-ghost {
    background: transparent; color: var(--ice); border: 1.5px solid rgba(159,227,220,.5);
    border-radius: 50px; padding: .95rem 2.2rem; font-family: 'Source Sans 3'; font-weight: 600;
    font-size: 1.05rem; cursor: pointer; text-decoration: none; transition: all .2s; display: inline-block;
  }
  .btn-ghost:hover { border-color: var(--seafoam); color: #fff; }
  .hero-proof {
    margin-top: 3rem; display: flex; align-items: center; justify-content: center; gap: 2rem;
    flex-wrap: wrap;
  }
  .proof-item { color: var(--ice); font-size: .9rem; display: flex; align-items: center; gap: .4rem; }
  .proof-item .stars { color: #FCD34D; letter-spacing: .1em; }

  /* ── TRUST BAR ── */
  .trust-bar {
    background: var(--tint); border-top: 1px solid var(--ice); border-bottom: 1px solid var(--ice);
    padding: 1.4rem 2rem;
  }
  .trust-bar-inner {
    max-width: var(--wide); margin: 0 auto;
    display: flex; align-items: center; justify-content: center; gap: 3rem; flex-wrap: wrap;
  }
  .trust-item { font-size: .92rem; color: var(--muted); font-weight: 500; display: flex; align-items: center; gap: .5rem; }
  .trust-icon { width: 18px; height: 18px; background: var(--teal); border-radius: 50%; display: grid; place-items: center; flex-shrink: 0; }
  .trust-icon::after { content: '✓'; color: #fff; font-size: .65rem; font-weight: 700; }

  /* ── SECTION HELPERS ── */
  section { padding: 5rem 2rem; }
  .container { max-width: var(--max-w); margin: 0 auto; }
  .container-wide { max-width: var(--wide); margin: 0 auto; }
  .section-kicker {
    font-family: 'Source Sans 3'; font-weight: 700; font-size: .82rem;
    letter-spacing: .12em; text-transform: uppercase; color: var(--teal);
    display: block; margin-bottom: .8rem;
  }
  .section-title { font-size: clamp(1.7rem, 3.5vw, 2.5rem); margin-bottom: 1.2rem; }
  .section-sub { font-size: 1.12rem; color: var(--muted); line-height: 1.7; }
  .divider { width: 48px; height: 3px; background: var(--coral); border-radius: 2px; margin: 1.2rem 0 2rem; }

  /* ── PROBLEM / PROMISE ── */
  .problem { background: var(--off-white); }
  .problem-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 3rem; align-items: center; }
  .problem-list { list-style: none; }
  .problem-list li {
    padding: .9rem 1.1rem .9rem 1.5rem; margin-bottom: .7rem;
    border-left: 3px solid var(--coral); background: #fff;
    border-radius: 0 8px 8px 0; font-size: 1.02rem; color: var(--ink);
    box-shadow: 0 2px 8px rgba(11,79,90,.07);
  }
  .promise-card {
    background: var(--teal-dark); border-radius: 16px; padding: 2.2rem;
    color: #fff;
  }
  .promise-card h3 { color: var(--seafoam); margin-bottom: 1.2rem; font-size: 1.2rem; }
  .promise-item { display: flex; gap: .8rem; margin-bottom: 1rem; align-items: flex-start; }
  .promise-dot { width: 22px; height: 22px; background: var(--coral); border-radius: 50%; flex-shrink: 0; display: grid; place-items: center; margin-top: .12rem; }
  .promise-dot::after { content: '✓'; color: #fff; font-size: .7rem; font-weight: 700; }
  .promise-item p { font-size: 1rem; color: var(--ice); line-height: 1.5; }
  @media(max-width: 680px) { .problem-grid { grid-template-columns: 1fr; } }

  /* ── WHO IT'S FOR ── */
  .who { background: var(--white); }
  .who-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(230px, 1fr)); gap: 1.2rem; margin-top: 2.5rem; }
  .who-card {
    background: var(--tint); border-radius: 12px; padding: 1.4rem 1.5rem;
    border-left: 4px solid var(--teal-mid);
    font-size: 1rem; color: var(--ink); line-height: 1.5;
  }
  .who-card strong { display: block; color: var(--teal-dark); font-family: 'Lora'; font-size: 1.05rem; margin-bottom: .3rem; }
  .not-for { margin-top: 2.5rem; padding: 1.2rem 1.5rem; background: #fff2f1; border-radius: 10px; border-left: 4px solid var(--coral); font-size: .98rem; color: var(--ink); }
  .not-for strong { color: var(--coral-dk); }

  /* ── MODULES ── */
  .modules { background: var(--teal-dark); }
  .modules .section-kicker { color: var(--seafoam); }
  .modules .section-title { color: #fff; }
  .modules .section-sub { color: var(--ice); }
  .modules .divider { background: var(--coral); }
  .module-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(300px, 1fr)); gap: 1rem; margin-top: 2.5rem; }
  .module-card {
    background: rgba(255,255,255,.07); border: 1px solid rgba(159,227,220,.2);
    border-radius: 12px; padding: 1.4rem 1.5rem;
    transition: background .2s;
  }
  .module-card:hover { background: rgba(255,255,255,.12); }
  .module-num { font-family: 'Source Sans 3'; font-size: .8rem; font-weight: 700; letter-spacing: .1em; color: var(--coral); text-transform: uppercase; margin-bottom: .4rem; }
  .module-card h4 { font-size: 1.05rem; color: #fff; margin-bottom: .5rem; }
  .module-card p { font-size: .92rem; color: rgba(207,239,235,.8); line-height: 1.5; }
  .module-bonus {
    margin-top: 1.5rem; background: var(--coral); border-radius: 12px;
    padding: 1.2rem 1.5rem; display: flex; gap: 1rem; align-items: center;
  }
  .bonus-icon { font-size: 1.6rem; flex-shrink: 0; }
  .module-bonus p { color: #fff; font-size: .98rem; line-height: 1.5; }
  .module-bonus strong { display: block; font-size: 1.1rem; margin-bottom: .2rem; }

  /* ── WHAT YOU'LL BUILD ── */
  .build { background: var(--off-white); }
  .build-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(200px, 1fr)); gap: 1rem; margin-top: 2rem; }
  .build-item {
    background: #fff; border-radius: 10px; padding: 1.1rem 1.2rem;
    box-shadow: 0 2px 12px rgba(11,79,90,.08);
    display: flex; gap: .8rem; align-items: flex-start;
  }
  .build-tick { width: 20px; height: 20px; background: var(--teal); border-radius: 50%; flex-shrink: 0; display: grid; place-items: center; margin-top: .1rem; }
  .build-tick::after { content: '✓'; color: #fff; font-size: .62rem; font-weight: 700; }
  .build-item p { font-size: .95rem; color: var(--ink); line-height: 1.4; }

  /* ── INSTRUCTOR ── */
  .instructor { background: var(--white); }
  .instructor-card {
    background: var(--tint); border-radius: 16px; padding: 2.5rem;
    display: grid; grid-template-columns: 160px 1fr; gap: 2.5rem; align-items: start;
  }
  .instructor-photo {
    width: 160px; height: 160px; border-radius: 50%; background: var(--teal);
    display: grid; place-items: center; font-size: 3.5rem; color: var(--ice);
    box-shadow: 0 8px 24px rgba(11,79,90,.2);
  }
  .instructor-name { font-size: 1.5rem; margin-bottom: .3rem; }
  .instructor-title { font-size: 1rem; color: var(--teal); font-weight: 600; margin-bottom: 1rem; }
  .instructor-bio { font-size: 1rem; color: var(--muted); line-height: 1.7; }
  @media(max-width: 580px) { .instructor-card { grid-template-columns: 1fr; text-align: center; } .instructor-photo { margin: 0 auto; } }

  /* ── PRICING ── */
  .pricing { background: var(--off-white); }
  .pricing-card {
    background: var(--teal-dark); border-radius: 20px; max-width: 540px; margin: 2.5rem auto 0;
    overflow: hidden; box-shadow: 0 20px 60px rgba(11,79,90,.3);
  }
  .pricing-top { background: var(--teal); padding: 2.2rem 2.5rem; text-align: center; }
  .pricing-tag { font-family: 'Source Sans 3'; font-size: .8rem; font-weight: 700; letter-spacing: .12em; text-transform: uppercase; color: var(--ice); margin-bottom: .5rem; }
  .pricing-name { font-size: 1.8rem; color: #fff; font-family: 'Lora'; margin-bottom: .5rem; }
  .pricing-price { font-size: 3.8rem; color: #fff; font-family: 'Lora'; font-weight: 700; line-height: 1; }
  .pricing-price span { font-size: 1.3rem; vertical-align: top; margin-top: .7rem; display: inline-block; }
  .pricing-note { font-size: .9rem; color: var(--ice); margin-top: .5rem; }
  .pricing-body { padding: 2rem 2.5rem 2.5rem; }
  .pricing-includes { list-style: none; margin-bottom: 2rem; }
  .pricing-includes li { display: flex; gap: .8rem; padding: .65rem 0; border-bottom: 1px solid rgba(159,227,220,.15); align-items: center; color: var(--ice); font-size: .98rem; }
  .pricing-includes li:last-child { border-bottom: none; }
  .pricing-includes li::before { content: '✓'; background: var(--coral); width: 20px; height: 20px; border-radius: 50%; display: grid; place-items: center; flex-shrink: 0; color: #fff; font-size: .65rem; font-weight: 700; }
  .pricing-cta { display: block; background: var(--coral); color: #fff; text-align: center; border-radius: 50px; padding: 1.1rem; font-family: 'Source Sans 3'; font-weight: 700; font-size: 1.12rem; text-decoration: none; transition: all .2s; box-shadow: 0 6px 20px rgba(255,107,91,.4); }
  .pricing-cta:hover { background: var(--coral-dk); transform: translateY(-2px); }
  .pricing-guarantee { text-align: center; margin-top: 1.2rem; font-size: .88rem; color: rgba(207,239,235,.7); }

  /* ── FAQ ── */
  .faq { background: var(--white); }
  .faq-list { margin-top: 2.5rem; }
  .faq-item { border-bottom: 1px solid var(--tint); }
  .faq-q {
    width: 100%; background: none; border: none; text-align: left; cursor: pointer;
    padding: 1.3rem 0; display: flex; justify-content: space-between; align-items: center; gap: 1rem;
    font-family: 'Lora'; font-size: 1.08rem; color: var(--ink); font-weight: 600;
  }
  .faq-q:hover { color: var(--teal); }
  .faq-icon { flex-shrink: 0; width: 24px; height: 24px; background: var(--tint); border-radius: 50%; display: grid; place-items: center; transition: transform .25s, background .2s; }
  .faq-item.open .faq-icon { transform: rotate(45deg); background: var(--coral); }
  .faq-icon::after { content: '+'; color: var(--teal-dark); font-size: 1rem; font-weight: 700; }
  .faq-item.open .faq-icon::after { color: #fff; }
  .faq-a { max-height: 0; overflow: hidden; transition: max-height .35s ease, padding .25s; }
  .faq-a-inner { padding-bottom: 1.4rem; font-size: 1rem; color: var(--muted); line-height: 1.7; }
  .faq-item.open .faq-a { max-height: 400px; }

  /* ── FINAL CTA ── */
  .final-cta {
    background: var(--teal-dark);
    clip-path: polygon(0 10%, 100% 0, 100% 100%, 0 100%);
    padding: 7rem 2rem 5rem; text-align: center;
  }
  .final-cta-inner { max-width: 640px; margin: 0 auto; }
  .final-cta h2 { font-size: clamp(1.8rem, 4vw, 2.8rem); color: #fff; margin-bottom: 1.2rem; }
  .final-cta h2 em { color: var(--seafoam); font-style: italic; }
  .final-cta p { font-size: 1.12rem; color: var(--ice); margin-bottom: 2.2rem; line-height: 1.7; }

  /* ── FOOTER ── */
  footer { background: #081f24; padding: 2rem; text-align: center; font-size: .88rem; color: rgba(207,239,235,.5); }

  /* ── SCROLL ANIMATIONS ── */
  .reveal { opacity: 0; transform: translateY(24px); transition: opacity .6s ease, transform .6s ease; }
  .reveal.visible { opacity: 1; transform: none; }

  /* ── RESPONSIVE ── */
  @media(max-width: 680px) {
    section { padding: 3.5rem 1.4rem; }
    .hero { padding: 3.5rem 1.4rem 6rem; clip-path: polygon(0 0, 100% 0, 100% 94%, 0 100%); }
    .module-grid { grid-template-columns: 1fr; }
    .trust-bar-inner { gap: 1.4rem; }
    .pricing-card { margin: 2rem 0 0; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <span class="nav-brand">AI for Everyday People</span>
  <a href="#pricing" class="nav-cta">Enrol now</a>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-inner">
    <span class="hero-kicker">🎓 Self-paced online course</span>
    <h1>AI for <em>everyday</em> people,<br>not just tech people.</h1>
    <p class="hero-sub">The practical, jargon-free course that takes you from "I should probably learn about this" to actually using AI every single day — in about 3 hours.</p>
    <div class="hero-ctas">
      <a href="#pricing" class="btn-primary">Yes, I want in →</a>
      <a href="#modules" class="btn-ghost">See what's inside</a>
    </div>
    <div class="hero-proof">
      <span class="proof-item"><span class="stars">★★★★★</span> 5-star rated</span>
      <span class="proof-item">⚡ 8 modules, ~3 hours</span>
      <span class="proof-item">🎁 Free prompt cheat sheet included</span>
    </div>
  </div>
</section>

<!-- TRUST BAR -->
<div class="trust-bar">
  <div class="trust-bar-inner">
    <span class="trust-item"><span class="trust-icon"></span>No tech background needed</span>
    <span class="trust-item"><span class="trust-icon"></span>Free tools — no paid subscriptions required</span>
    <span class="trust-item"><span class="trust-icon"></span>30-day money-back guarantee</span>
    <span class="trust-item"><span class="trust-icon"></span>Lifetime access + all future updates</span>
  </div>
</div>

<!-- PROBLEM / PROMISE -->
<section class="problem">
  <div class="container">
    <div class="problem-grid">
      <div class="reveal">
        <span class="section-kicker">Sound familiar?</span>
        <h2 class="section-title">You keep hearing about AI.<br>You're just not sure where to start.</h2>
        <div class="divider"></div>
        <ul class="problem-list">
          <li>Everyone else seems to be using it and getting ahead</li>
          <li>You've tried it once or twice but didn't know what to ask</li>
          <li>There's so much hype it's hard to know what's actually useful</li>
          <li>You're not techy — and most AI content feels like it's not for you</li>
          <li>You don't want to waste time learning something that won't stick</li>
        </ul>
      </div>
      <div class="reveal" style="transition-delay:.15s">
        <div class="promise-card">
          <h3>After this course, you'll…</h3>
          <div class="promise-item"><div class="promise-dot"></div><p>Write and edit emails in seconds — even the awkward ones</p></div>
          <div class="promise-item"><div class="promise-dot"></div><p>Handle life admin: meal plans, summaries, trip planning, documents</p></div>
          <div class="promise-item"><div class="promise-dot"></div><p>Use a simple 4-part formula that improves every answer you get</p></div>
          <div class="promise-item"><div class="promise-dot"></div><p>Spot scams, deepfakes and stay protected in an AI world</p></div>
          <div class="promise-item"><div class="promise-dot"></div><p>Have a daily habit that compounds over months into a real advantage</p></div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- WHO IT'S FOR -->
<section class="who">
  <div class="container">
    <div class="reveal">
      <span class="section-kicker">Is this for me?</span>
      <h2 class="section-title">This course is for you if…</h2>
      <div class="divider"></div>
    </div>
    <div class="who-grid">
      <div class="who-card reveal"><strong>You're curious but confused</strong>You've heard AI is a big deal but don't know where to start or what's actually useful for everyday life.</div>
      <div class="who-card reveal" style="transition-delay:.1s"><strong>You're not a techie</strong>You don't code, don't work in tech, and every AI tutorial you've found feels like it's for someone else.</div>
      <div class="who-card reveal" style="transition-delay:.2s"><strong>You're busy</strong>You want the practical stuff, not theory. Short lessons, real examples, things that save you time from day one.</div>
      <div class="who-card reveal" style="transition-delay:.3s"><strong>You care about staying safe</strong>You've heard about scams and deepfakes and want to understand the risks — not just the benefits.</div>
    </div>
    <p class="not-for reveal" style="margin-top:1.5rem"><strong>Not for you if:</strong> you're already using AI daily and want advanced techniques. This course is genuinely built for beginners — every lesson assumes you're starting from zero.</p>
  </div>
</section>

<!-- MODULES -->
<section class="modules" id="modules">
  <div class="container-wide">
    <div class="reveal" style="text-align:center">
      <span class="section-kicker">What's inside</span>
      <h2 class="section-title">8 modules. ~3 hours. A complete foundation.</h2>
      <div class="divider" style="margin:1.2rem auto 2rem"></div>
    </div>
    <div class="module-grid">
      <div class="module-card reveal">
        <div class="module-num">Module 0</div>
        <h4>Welcome + Your First Win</h4>
        <p>Get oriented and use AI for the first time in under 15 minutes — before the module ends.</p>
      </div>
      <div class="module-card reveal" style="transition-delay:.07s">
        <div class="module-num">Module 1</div>
        <h4>AI, Demystified</h4>
        <p>What AI actually is, what it's brilliant at, where it gets things wrong, and how to stay safe. Zero jargon.</p>
      </div>
      <div class="module-card reveal" style="transition-delay:.14s">
        <div class="module-num">Module 2</div>
        <h4>Setting Up Your Toolkit</h4>
        <p>The 3 free tools worth your time, how to set them up in 10 minutes, and which to use for what.</p>
      </div>
      <div class="module-card reveal" style="transition-delay:.21s">
        <div class="module-num">Module 3</div>
        <h4>The Core Skill: Prompting</h4>
        <p>The 4-part formula — Role, Context, Task, Format — that makes every AI response dramatically better.</p>
      </div>
      <div class="module-card reveal" style="transition-delay:.28s">
        <div class="module-num">Module 4</div>
        <h4>AI for Everyday Writing</h4>
        <p>Emails, messages, letters, social posts, editing. The 5 emails everyone dreads — handled.</p>
      </div>
      <div class="module-card reveal" style="transition-delay:.35s">
        <div class="module-num">Module 5</div>
        <h4>AI for Life Admin</h4>
        <p>Meal planning, document summaries, trip itineraries, event planning, image generation intro.</p>
      </div>
      <div class="module-card reveal" style="transition-delay:.42s">
        <div class="module-num">Module 6</div>
        <h4>Staying Safe &amp; Smart</h4>
        <p>AI-powered scams, deepfakes, fact-checking, and the 4 ethical rules that keep you on the right side.</p>
      </div>
      <div class="module-card reveal" style="transition-delay:.49s">
        <div class="module-num">Module 7</div>
        <h4>Your AI Habit &amp; What's Next</h4>
        <p>Building a daily practice, keeping up as tools change, and where to go from here.</p>
      </div>
    </div>
    <div class="module-bonus reveal">
      <div class="bonus-icon">🎁</div>
      <p><strong>Free bonus: The Everyday AI Prompt Cheat Sheet</strong>16 copy-paste prompts for the most common everyday situations — emails, planning, research, and more. Yours to keep.</p>
    </div>
  </div>
</section>

<!-- WHAT YOU'LL BUILD -->
<section class="build">
  <div class="container">
    <div class="reveal">
      <span class="section-kicker">What you'll own by the end</span>
      <h2 class="section-title">These aren't things you'll read about.<br>They're things you'll build.</h2>
      <div class="divider"></div>
    </div>
    <div class="build-grid">
      <div class="build-item reveal"><div class="build-tick"></div><p>The 4-part prompting formula</p></div>
      <div class="build-item reveal" style="transition-delay:.06s"><div class="build-tick"></div><p>A paste-and-improve writing system</p></div>
      <div class="build-item reveal" style="transition-delay:.12s"><div class="build-tick"></div><p>A personal prompt library</p></div>
      <div class="build-item reveal" style="transition-delay:.18s"><div class="build-tick"></div><p>A universal planning template</p></div>
      <div class="build-item reveal" style="transition-delay:.24s"><div class="build-tick"></div><p>A 10-point safety checklist</p></div>
      <div class="build-item reveal" style="transition-delay:.30s"><div class="build-tick"></div><p>A daily AI habit with a trigger</p></div>
      <div class="build-item reveal" style="transition-delay:.36s"><div class="build-tick"></div><p>At least one free tool, set up and ready</p></div>
      <div class="build-item reveal" style="transition-delay:.42s"><div class="build-tick"></div><p>A new skill: AI literacy</p></div>
    </div>
  </div>
</section>

<!-- INSTRUCTOR -->
<section class="instructor">
  <div class="container">
    <div class="reveal">
      <span class="section-kicker">Your instructor</span>
      <h2 class="section-title">Hi, I'm [Your Name].</h2>
      <div class="divider"></div>
    </div>
    <div class="instructor-card reveal">
      <div class="instructor-photo">👋</div>
      <div>
        <h3 class="instructor-name">[Your Name]</h3>
        <p class="instructor-title">[Your title / tagline — e.g. "AI educator & content creator"]</p>
        <p class="instructor-bio">[Write 3–4 sentences here about your background and why you're the right person to teach this. Be warm and human — what made you want to make AI accessible to everyday people? What's your own story with it? This is where students decide whether they trust you.]</p>
        <br>
        <p class="instructor-bio" style="font-style:italic;color:var(--teal-dark)">"I built this course because I kept seeing brilliant, capable people feel left behind by technology that was supposed to help them. I wanted to change that."</p>
      </div>
    </div>
  </div>
</section>

<!-- PRICING -->
<section class="pricing" id="pricing">
  <div class="container">
    <div class="reveal" style="text-align:center">
      <span class="section-kicker">Enrol today</span>
      <h2 class="section-title">One price. Everything included.</h2>
      <div class="divider" style="margin:1.2rem auto 0"></div>
    </div>
    <div class="pricing-card reveal">
      <div class="pricing-top">
        <p class="pricing-tag">AI for Everyday People — Full Course</p>
        <p class="pricing-name">Complete Access</p>
        <div class="pricing-price"><span>$</span>97</div>
        <p class="pricing-note">One-time payment · No subscription</p>
      </div>
      <div class="pricing-body">
        <ul class="pricing-includes">
          <li>8 complete video modules (~3 hours total)</li>
          <li>Speaker notes / full transcript for every lesson</li>
          <li>The Everyday AI Prompt Cheat Sheet (PDF)</li>
          <li>Safety checklist to save &amp; share</li>
          <li>All future course updates included free</li>
          <li>Lifetime access — learn at your own pace</li>
        </ul>
        <a href="[YOUR-COURSE-LINK-HERE]" class="pricing-cta">Enrol now for $97 →</a>
        <p class="pricing-guarantee">🛡 30-day money-back guarantee. If you try the course and don't feel it was worth every penny, just email and you'll get a full refund. No questions asked.</p>
      </div>
    </div>
  </div>
</section>

<!-- FAQ -->
<section class="faq">
  <div class="container">
    <div class="reveal">
      <span class="section-kicker">Questions</span>
      <h2 class="section-title">Common questions answered.</h2>
      <div class="divider"></div>
    </div>
    <div class="faq-list">
      <div class="faq-item reveal">
        <button class="faq-q">Do I need any tech experience? <span class="faq-icon"></span></button>
        <div class="faq-a"><div class="faq-a-inner">None whatsoever. This course is built from the ground up for people who have never used AI before and don't consider themselves technical. If you can send a text message, you have every skill you need.</div></div>
      </div>
      <div class="faq-item reveal">
        <button class="faq-q">Do I need to pay for any AI tools? <span class="faq-icon"></span></button>
        <div class="faq-a"><div class="faq-a-inner">No. The course teaches you to use the free tiers of ChatGPT, Claude, and Gemini — all of which are genuinely capable at no cost. You can absolutely complete the whole course without spending a penny on tools.</div></div>
      </div>
      <div class="faq-item reveal">
        <button class="faq-q">How long do I have access? <span class="faq-icon"></span></button>
        <div class="faq-a"><div class="faq-a-inner">Lifetime access. Go at your own pace, take breaks, come back whenever you want. You'll also get any future updates or new modules at no extra cost.</div></div>
      </div>
      <div class="faq-item reveal">
        <button class="faq-q">What if the AI tools change? <span class="faq-icon"></span></button>
        <div class="faq-a"><div class="faq-a-inner">Good question — AI tools do change fast. This course is specifically designed to teach durable skills and frameworks (like the 4-part formula) that apply to any tool, not just the current version of any specific one. When things change significantly, the course gets updated.</div></div>
      </div>
      <div class="faq-item reveal">
        <button class="faq-q">Is there a refund policy? <span class="faq-icon"></span></button>
        <div class="faq-a"><div class="faq-a-inner">Yes — a full 30-day money-back guarantee, no questions asked. Try the course. If it's not right for you, just send an email within 30 days and you'll get every penny back.</div></div>
      </div>
      <div class="faq-item reveal">
        <button class="faq-q">How is this different from free YouTube tutorials? <span class="faq-icon"></span></button>
        <div class="faq-a"><div class="faq-a-inner">Free content is scattered, inconsistent in quality, and rarely designed as a structured journey from zero to confident. This course is a complete, sequenced learning experience — built specifically for everyday people — that takes you step by step with exercises, examples, and a framework you can use forever. The prompt cheat sheet alone saves you hours of trial and error.</div></div>
      </div>
    </div>
  </div>
</section>

<!-- FINAL CTA -->
<section class="final-cta">
  <div class="final-cta-inner">
    <h2>You're the <em>editor-in-chief.</em></h2>
    <p>AI writes the first draft. You decide everything. This course gives you the skills, the tools, and the habit to make that real — starting today.</p>
    <a href="#pricing" class="btn-primary">Enrol for $97 →</a>
    <p style="margin-top:1.2rem;font-size:.9rem;color:var(--ice);opacity:.7">30-day guarantee · Lifetime access · No tech skills needed</p>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <p>© 2026 [Your Name] · AI for Everyday People · <a href="mailto:[your@email.com]" style="color:var(--seafoam)">Contact</a></p>
  <p style="margin-top:.5rem">Results shown are illustrative. Individual results will vary.</p>
</footer>

<script>
  // FAQ accordion
  document.querySelectorAll('.faq-q').forEach(btn => {
    btn.addEventListener('click', () => {
      const item = btn.parentElement;
      const isOpen = item.classList.contains('open');
      document.querySelectorAll('.faq-item').forEach(i => i.classList.remove('open'));
      if (!isOpen) item.classList.add('open');
    });
  });

  // Scroll reveal
  const revealEls = document.querySelectorAll('.reveal');
  const observer = new IntersectionObserver(entries => {
    entries.forEach(e => { if (e.isIntersecting) { e.target.classList.add('visible'); observer.unobserve(e.target); } });
  }, { threshold: 0.12 });
  revealEls.forEach(el => observer.observe(el));
</script>
</body>
</html>
