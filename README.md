<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Jonathan Cajulao | Personal Portfolio</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=DM+Mono&family=Manrope:wght@400;600;800&display=swap" rel="stylesheet">
<style>
:root{--bg:#0b1020;--panel:#141d32;--text:#f4f5fb;--muted:#9aa5bd;--lime:#c5f467;--cyan:#75e5d4;--tomato:#ff6b57;--line:rgba(255,255,255,.12)}
*{box-sizing:border-box}
html{scroll-behavior:smooth;scroll-padding-top:80px}
body{margin:0;background:var(--bg);color:var(--text);font-family:Manrope,system-ui,sans-serif;overflow-x:hidden;line-height:1.6}
body::before{content:"";position:fixed;inset:0;z-index:-1;pointer-events:none;opacity:.5;background-image:linear-gradient(#ffffff06 1px,transparent 1px),linear-gradient(90deg,#ffffff06 1px,transparent 1px);background-size:40px 40px}
a{color:inherit;text-decoration:none}
button{font:inherit;cursor:pointer;color:inherit}
:focus-visible{outline:3px solid var(--lime);outline-offset:3px}
.wrap{max-width:1120px;margin:auto;padding:0 25px}
.mono{font-family:"DM Mono",monospace}

/* nav */
header{position:sticky;top:0;z-index:10;background:#0b1020ee;backdrop-filter:blur(14px);border-bottom:1px solid var(--line)}
.nav{height:72px;display:flex;align-items:center;justify-content:space-between}
.brand{display:flex;align-items:center;gap:10px;font-size:11px;letter-spacing:2px;font-weight:800}
.logo{display:grid;place-items:center;width:36px;height:36px;border:1px solid #c5f46780;border-radius:10px;color:var(--lime);font-size:20px}
nav{display:flex;gap:22px;align-items:center;font-size:13px;color:#c4ccdc}
nav a:hover{color:var(--lime)}
.nav-play{border:1px solid var(--lime);color:var(--lime);padding:8px 14px;border-radius:8px;font-weight:800}
.menu{display:none;background:none;border:0;font-size:24px}

/* sections (distinct class so padding is never overridden) */
.sec{padding:90px 0;border-bottom:1px solid var(--line)}
.hero-sec{padding:70px 0 80px}
.kicker{font:10px "DM Mono",monospace;letter-spacing:1.6px;color:#aeb9cd;margin-bottom:26px}
.kicker b{color:var(--lime)}
h1{font-size:clamp(38px,5.6vw,66px);line-height:1.08;letter-spacing:-3px;margin:0 0 20px}
h2{font-size:clamp(30px,4.4vw,46px);line-height:1.15;letter-spacing:-2px;margin:0 0 14px}
.grad{background:linear-gradient(100deg,var(--lime),var(--cyan));-webkit-background-clip:text;background-clip:text;-webkit-text-fill-color:transparent}
.muted{color:#8995ac}
.lead{color:var(--muted);font-size:14px;max-width:520px}

.btn{border:1px solid transparent;border-radius:10px;padding:13px 20px;font-size:13px;font-weight:800;transition:.2s;display:inline-flex;gap:10px;align-items:center}
.btn:hover{transform:translateY(-3px)}
.btn:disabled{opacity:.4;cursor:not-allowed;transform:none}
.primary{background:var(--lime);color:#151c10;box-shadow:0 8px 30px #c5f46722}
.ghost{background:#ffffff0a;border-color:var(--line)}
.actions{display:flex;gap:12px;flex-wrap:wrap;margin-top:22px}

/* hero */
.hero{display:grid;grid-template-columns:1.1fr .9fr;gap:40px;align-items:center}
.term{background:#080c18;border:1px solid var(--line);border-radius:12px;padding:14px 16px;font:13px "DM Mono",monospace;min-height:122px;max-width:520px;cursor:pointer}
.term p{margin:3px 0}.err{color:var(--tomato)}.ok{color:var(--lime)}
.term .dots i{display:inline-block;width:9px;height:9px;border-radius:50%;background:var(--tomato);margin-right:5px}
.term .dots i:nth-child(2){background:#ffd23f}.term .dots i:nth-child(3){background:var(--lime)}
.skiphint{font-size:11px;color:#6d7890;margin-top:8px}
.profile-area{display:grid;place-items:center;position:relative;min-height:400px}
.orbit{position:absolute;width:340px;height:280px;border:1px solid #75e5d41b;border-radius:50%;transform:rotate(-25deg)}
.orbit.two{width:390px;height:320px;transform:rotate(35deg);border-color:#c5f46719}
.profile{width:min(100%,330px);position:relative;padding:22px;border:1px solid #c5f46740;border-radius:17px;background:linear-gradient(145deg,#19243b,#101727);box-shadow:0 30px 80px #0005;animation:float 5s ease-in-out infinite}
.avatar{margin:10px auto 18px;width:140px;height:140px;border:1px solid #c5f46790;border-radius:50%;display:grid;place-items:center;overflow:hidden;background:radial-gradient(circle at 30% 20%,#34445a,#101728 70%);color:var(--lime);font-size:44px;font-weight:800}
.avatar img{width:100%;height:100%;object-fit:cover}
.pname{text-align:center;font-size:19px;font-weight:800}
.prole{text-align:center;color:var(--muted);font-size:12px}
.pstat{display:flex;justify-content:center;gap:8px;margin-top:14px;color:var(--lime);font:11px "DM Mono",monospace}
@keyframes float{50%{transform:translateY(-9px)}}
.crew{display:grid;grid-template-columns:repeat(5,1fr);gap:10px;margin:22px 0 14px}
.cm{--c:#c5f467;background:#ffffff08;border:1px solid var(--line);border-radius:12px;padding:12px 4px 10px;text-align:center;transition:.2s}
.cm:hover{transform:translateY(-4px);border-color:var(--c)}
.cm .ic{display:block;font-size:32px;line-height:1.2}
.cm .n{display:block;font-size:12px;font-weight:700;margin-top:2px}
.cm.on{border-color:var(--c);background:color-mix(in srgb,var(--c) 18%,transparent);box-shadow:0 0 0 2px color-mix(in srgb,var(--c) 40%,transparent)}
.crewstory{--c:#c5f467;border:1px solid var(--line);border-radius:14px;padding:22px;background:#ffffff05;min-height:150px}
.crewstory.filled{border-color:var(--c);background:color-mix(in srgb,var(--c) 8%,#0b1020);animation:rise .4s}
.crewhint{margin:0;color:var(--muted);font-size:14px;text-align:center;padding:36px 0}
.csh{display:flex;align-items:center;gap:14px;margin-bottom:12px}
.csh .big{font-size:46px;line-height:1}
.csh h3{margin:0;font-size:22px;letter-spacing:-.5px;color:var(--c)}
.csh small{display:block;color:var(--muted);font-size:12px}
.crewstory p{margin:0 0 10px;font-size:14px;color:#d4dae8}
.crewstory .dream b,.crewstory .lesson b{color:var(--c)}
.crewstory .lesson{border-top:1px dashed #ffffff30;padding-top:12px;margin:12px 0 0;font-weight:600}
@keyframes rise{from{opacity:0;transform:translateY(10px)}to{opacity:1;transform:none}}
.crewbadge{display:none;margin:12px auto 0;width:max-content;padding:5px 14px;border:2px solid #f6d98a;border-radius:8px;color:#f6d98a;font:800 12px "DM Mono",monospace;letter-spacing:2px;animation:pop .4s}
.marine{position:absolute;width:64px;height:64px;border-radius:50%;border:2px solid #ffffff55;background:#1d3b6e;font-size:32px;line-height:1;padding:0;display:grid;place-items:center;animation:pop .2s;box-shadow:0 4px 0 #0c1f40}
.marine:hover{border-color:var(--lime)}
.marine{overflow:hidden}
.marine svg,.marine img{width:100%;height:100%;object-fit:cover;pointer-events:none;display:block}
.rankline{font:11px "DM Mono",monospace;color:var(--lime);margin:-4px 0 10px;min-height:16px}
.marine.final{animation:pop .2s,glow .8s .2s infinite alternate}
@keyframes glow{from{box-shadow:0 0 8px #b44cff,0 4px 0 #1a0a30}to{box-shadow:0 0 26px #e08cff,0 4px 0 #1a0a30}}
.marine.dead{animation:splat .35s forwards;pointer-events:none;background:var(--lime)}
.ovbadge{display:inline-block;margin:4px auto;padding:6px 16px;border:2px solid var(--lime);border-radius:10px;color:var(--lime);font-weight:800}
@keyframes pop{from{transform:scale(0)}to{transform:scale(1)}}
.wanted{text-align:center;font-weight:800;font-size:26px;letter-spacing:8px;color:#f6d98a;border-bottom:1px dashed #f6d98a66;padding-bottom:8px}
.pstat{font-size:13px!important}

/* story chapters */
.chapters{display:grid;gap:12px;margin-top:30px}
.chap{border:1px solid var(--line);border-radius:12px;background:#ffffff05;overflow:hidden}
.chap button{width:100%;background:none;border:0;padding:18px 20px;display:flex;justify-content:space-between;align-items:center;text-align:left;font-weight:800;font-size:17px}
.chap button small{display:block;font:10px "DM Mono",monospace;color:var(--lime);letter-spacing:1px;margin-bottom:3px;font-weight:400}
.chap .plus{color:var(--lime);font-size:24px;transition:.3s}
.chap.open{border-color:#c5f46766}.chap.open .plus{transform:rotate(45deg)}
.chap .body{max-height:0;overflow:hidden;transition:max-height .45s ease;color:var(--muted);font-size:14px}
.chap .body p{margin:0;padding:0 20px 20px}
.facts{display:grid;grid-template-columns:repeat(3,1fr);gap:12px;margin-top:28px}
.fact{padding:16px;border:1px solid var(--line);border-radius:10px;background:#ffffff04}
.fact small{display:block;font:9px "DM Mono",monospace;color:#8b97ae;margin-bottom:4px}
.fact strong{font-size:13px}

/* flip cards */
.cards{display:grid;grid-template-columns:repeat(3,1fr);gap:16px;margin-top:30px}
.flip{perspective:900px;height:300px;background:none;border:0;padding:0;text-align:left}
.flip-in{position:relative;width:100%;height:100%;transition:transform .6s;transform-style:preserve-3d}
.flip.flipped .flip-in{transform:rotateY(180deg)}
.face{position:absolute;inset:0;backface-visibility:hidden;border:1px solid var(--line);border-radius:14px;padding:22px;display:flex;flex-direction:column;justify-content:space-between;background:linear-gradient(145deg,#1a2540,#111a2e)}
.flip:hover .face{border-color:#c5f46770}
.back{transform:rotateY(180deg);background:linear-gradient(145deg,#1f2d1c,#141d12);border-color:#c5f46766}
.big{font-size:64px;text-align:center}
.face h3{margin:0 0 6px;font-size:20px}
.face p{margin:0;font-size:13px;color:var(--muted)}
.tap{font:9px "DM Mono",monospace;color:var(--lime);letter-spacing:1px}

/* game */
.gamebox{border:1px solid #75e5d42e;border-radius:16px;padding:20px;background:radial-gradient(circle at top right,#75e5d40d,transparent 45%),var(--panel)}
.gbar{display:flex;justify-content:space-between;align-items:center;font-weight:800;margin-bottom:10px;gap:10px;flex-wrap:wrap}
.timer{height:7px;background:#ffffff1f;border-radius:8px;overflow:hidden;margin-bottom:12px}
.timer i{display:block;height:100%;width:100%;background:var(--tomato);transform-origin:left}
.arena{position:relative;height:320px;background:#080c18;border:2px dashed #ffffff30;border-radius:12px;overflow:hidden;user-select:none}
.overlay{position:absolute;inset:0;display:grid;place-content:center;text-align:center;gap:14px;padding:20px;color:var(--muted);font-size:14px}
.overlay h3{margin:0;font-size:24px;color:var(--text)}
.bug{position:absolute;background:#ffd23f;color:#241a38;border:0;border-radius:30px;padding:6px 13px 6px 9px;font-weight:800;font-size:13px;box-shadow:0 3px 0 #a98a00;animation:wob .5s infinite alternate}
.bug.dead{animation:splat .4s forwards;pointer-events:none;background:var(--lime)}
@keyframes wob{to{transform:rotate(7deg) translateY(-4px)}}
@keyframes splat{to{transform:scale(1.7);opacity:0}}
.chips{display:flex;flex-wrap:wrap;gap:8px;margin-top:14px}
.chip{border:1px solid #ffffff33;border-radius:30px;padding:3px 12px;font-size:12px;color:var(--muted);transition:.3s}
.chip.lit{background:var(--lime);border-color:var(--lime);color:#151c10;font-weight:800}

/* skills */
.skills-grid{display:grid;grid-template-columns:.9fr 1.1fr;gap:70px}
.skill{margin-bottom:22px;padding:10px 12px;border:1px solid transparent;border-radius:10px;transition:.4s}
.skill.unlocked{border-color:#c5f46755;background:#c5f46710}
.sinfo{display:flex;justify-content:space-between;font-size:13px;font-weight:700;margin-bottom:8px}
.sinfo small{font:9px "DM Mono",monospace;color:#8a97ae}
.skill.unlocked .sinfo small{color:var(--lime)}
.track{height:6px;background:#263149;border-radius:20px;overflow:hidden}
.track span{display:block;height:100%;width:var(--level);background:linear-gradient(90deg,var(--lime),var(--cyan));transform-origin:left;animation:grow 1.4s ease both}
@keyframes grow{from{transform:scaleX(0)}}
.tip{color:var(--cyan);font-size:13px;min-height:44px;margin-top:14px}
.link{background:none;border:0;padding:0;color:var(--lime);font-weight:800;font-size:13px}

/* quiz */
.quiz{max-width:760px;padding:26px;border:1px solid #75e5d42e;border-radius:15px;background:var(--panel);margin-top:26px}
.qmeta{display:flex;justify-content:space-between;font:10px "DM Mono",monospace;color:var(--lime);margin-bottom:12px}
.prog{height:4px;background:#29334a;border-radius:10px;overflow:hidden;margin-bottom:20px}
.prog span{display:block;height:100%;background:linear-gradient(90deg,var(--lime),var(--cyan));transition:width .35s}
.quiz h3{font-size:21px;margin:0 0 18px}
.opts{display:grid;grid-template-columns:repeat(3,1fr);gap:10px}
.opt{padding:13px;text-align:left;background:#ffffff06;border:1px solid var(--line);border-radius:9px;font-size:13px;transition:.2s}
.opt:hover:not(:disabled){transform:translateY(-3px);border-color:var(--cyan)}
.opt.ok{border-color:#4ee79a;background:#4ee79a18}.opt.no{border-color:#ff7078;background:#ff707818}
.fb{min-height:26px;margin:16px 0;font-size:13px;color:var(--muted)}
.qfoot{display:flex;justify-content:space-between;align-items:center;border-top:1px solid var(--line);padding-top:14px}
.result{text-align:center;padding:12px 0}.result .big{font-size:44px;color:var(--lime)}

/* contact */
.center{text-align:center;border-bottom:0}
.center .lead{margin:0 auto 24px}
.hello{min-height:26px;color:var(--cyan);font-size:13px;margin-top:16px}
footer{margin-top:60px;padding-top:20px;border-top:1px solid var(--line);display:flex;justify-content:space-between;flex-wrap:wrap;gap:12px;color:#8793aa;font:10px "DM Mono",monospace}

.toast{position:fixed;bottom:22px;left:50%;transform:translate(-50%,20px);opacity:0;pointer-events:none;padding:12px 18px;border-radius:9px;background:var(--lime);color:#14200d;font-size:13px;font-weight:800;transition:.25s;z-index:20;max-width:90%}
.toast.show{opacity:1;transform:translate(-50%,0)}

@media(max-width:820px){
  .hero,.skills-grid{grid-template-columns:1fr;gap:30px}
  .cards,.facts,.opts{grid-template-columns:1fr}
  .flip{height:250px}
  .profile-area{min-height:360px}
}
@media(max-width:700px){
  .crew{gap:6px}.cm{padding:9px 2px 7px}.cm .ic{font-size:26px}.cm .n{font-size:10px}
  .menu{display:block}
  nav{display:none;position:absolute;top:71px;left:0;right:0;padding:20px;background:#10172a;border-bottom:1px solid var(--line);flex-direction:column;align-items:stretch;gap:18px}
  nav.open{display:flex}
  .sec{padding:65px 0}
  .arena{height:290px}
}
@media(prefers-reduced-motion:reduce){*{animation-duration:.01ms!important;transition-duration:.01ms!important;scroll-behavior:auto!important}}
</style>
</head>
<body>

<header>
  <div class="wrap nav">
    <a class="brand" href="#home"><span class="logo">J</span>PERSONAL SPACE</a>
    <nav id="nav">
      <a href="#about">My Voyage</a>
      <a href="#interests">Interests</a>
      <a href="#skills">Skills</a>
      <a href="#quiz">Quiz</a>
      <a href="#game" class="nav-play">Join the crew</a>
    </nav>
    <button class="menu" id="menu" aria-label="Toggle navigation" aria-expanded="false">☰</button>
  </div>
</header>

<main>
<!-- HOME -->
<section class="sec hero-sec" id="home">
  <div class="wrap hero">
    <div>
      <div class="kicker"><b>●</b> FUTURE IT PIRATE · CEBU, PHILIPPINES</div>
      <h1>Ahoy, I'm <span class="grad">Jonathan.</span><br>Marines are chasing my ship.</h1>
      <div class="term" id="term" aria-live="polite">
        <div class="dots"><i></i><i></i><i></i></div>
        <div id="lines"></div>
      </div>
      <div class="skiphint">Click the terminal to skip the typing</div>
      <div class="actions">
        <a class="btn primary" href="#game">Join my crew (20 sec chase) ↓</a>
        <a class="btn ghost" href="#about">Read my voyage</a>
      </div>
    </div>
    <div class="profile-area">
      <div class="orbit"></div><div class="orbit two"></div>
      <div class="profile">
        <div class="wanted">WANTED</div>
        <div class="avatar" id="avatar"></div>
        <div class="pname">Jonathan Cajulao</div>
        <div class="prole">For turning ideas into websites</div>
        <div class="pstat">BOUNTY ฿ <span id="homeBugs">100,000,000</span></div>
        <div class="crewbadge" id="posterBadge">🏴‍☠️ NEW CREWMATE</div>
      </div>
    </div>
  </div>
</section>

<!-- STORY -->
<section class="sec" id="about">
  <div class="wrap">
    <div class="kicker"><b>01</b> / MY VOYAGE, IN 3 CHAPTERS</div>
    <h2>Meet the crew.<br><span class="muted">Every pirate has a story.</span></h2>
    <p class="lead" style="margin-top:6px">Tap a crew icon to read that pirate's story.</p>
    <div class="crew" id="crew" role="group" aria-label="Straw Hat crew"></div>
    <div class="crewstory" id="crewStory" aria-live="polite">
      <p class="crewhint">👆 Pick a crew member above to open their story.</p>
    </div>
    <p class="kicker" style="margin:38px 0 0">MY OWN VOYAGE LOG: TAP AN ENTRY</p>
    <div class="chapters">
      <div class="chap open">
        <button aria-expanded="true"><span><small>LOG 1</small>The Dream</span><span class="plus">+</span></button>
        <div class="body"><p>EDIT: Tell how you got into IT, pirate style. Example: "Every pirate has a dream. Mine began when I typed my first line of HTML and watched a page appear. It looked terrible, and I set sail anyway."</p></div>
      </div>
      <div class="chap">
        <button aria-expanded="false"><span><small>LOG 2</small>The Storm</span><span class="plus">+</span></button>
        <div class="body"><p>EDIT: Describe a time something went wrong. Example: "I once spent three hours lost in a storm that turned out to be one missing semicolon. Now I read the map calmly and fix one thing at a time."</p></div>
      </div>
      <div class="chap">
        <button aria-expanded="false"><span><small>LOG 3</small>The Voyage</span><span class="plus">+</span></button>
        <div class="body"><p>EDIT: Say where you're sailing. Example: "I'm heading for my own treasure: building useful things for people. This page is my ship, and you just helped defend it."</p></div>
      </div>
    </div>
    <div class="facts">
      <div class="fact"><small>CURRENT CHAPTER</small><strong>Learning &amp; building</strong></div>
      <div class="fact"><small>BASED IN</small><strong>Cebu, Philippines</strong></div>
      <div class="fact"><small>PERSONAL GOAL</small><strong>Make useful things</strong></div>
    </div>
  </div>
</section>

<!-- INTERESTS -->
<section class="sec" id="interests">
  <div class="wrap">
    <div class="kicker"><b>02</b> / THE CREW'S TREASURES</div>
    <h2>My treasures<br><span class="grad">on this voyage.</span></h2>
    <p class="lead">Flip each treasure chest to see why it matters to me.</p>
    <div class="cards">
      <button class="flip" aria-label="Flip Tech and Coding card">
        <div class="flip-in">
          <div class="face"><div class="big">💻</div><div><h3>Tech &amp; Coding</h3><p>How technology solves everyday problems.</p></div><span class="tap">TAP TO FLIP ↻</span></div>
          <div class="face back"><h3>Why it matters</h3><p>EDIT: Share a real moment. "Nothing beats the feeling when code that failed ten times finally runs."</p><span class="tap">TAP TO FLIP BACK ↻</span></div>
        </div>
      </button>
      <button class="flip" aria-label="Flip Basketball card">
        <div class="flip-in">
          <div class="face"><div class="big">🏀</div><div><h3>Basketball</h3><p>Consistency, teamwork, and practice.</p></div><span class="tap">TAP TO FLIP ↻</span></div>
          <div class="face back"><h3>Why it matters</h3><p>EDIT: Tell your team, position, or favorite memory. "It taught me that shortcuts don't win games, practice does."</p><span class="tap">TAP TO FLIP BACK ↻</span></div>
        </div>
      </button>
      <button class="flip" aria-label="Flip Gaming card">
        <div class="flip-in">
          <div class="face"><div class="big">🎮</div><div><h3>Gaming</h3><p>Challenge, strategy, and fun.</p></div><span class="tap">TAP TO FLIP ↻</span></div>
          <div class="face back"><h3>Why it matters</h3><p>EDIT: Name your favorite game. "Every lost match is a free lesson. It's the same mindset I use to debug."</p><span class="tap">TAP TO FLIP BACK ↻</span></div>
        </div>
      </button>
    </div>
  </div>
</section>

<!-- GAME -->
<section class="sec" id="game">
  <div class="wrap">
    <div class="kicker"><b>03</b> / PLAY: ESCAPE THE MARINES</div>
    <h2>Tap the marines.<br><span class="grad">Earn your place on the crew.</span></h2>
    <p class="lead">Marines are chasing my ship! Tap as many as you can in 20 seconds. <b>Every tap makes the enemy stronger</b>, from a small marine all the way up to <b>Imu</b> at 30 taps. Beat him to earn the New Crewmate badge. There's no maximum score, so try to beat your best.</p>
    <div class="gamebox" style="margin-top:26px">
      <div class="gbar">
        <span>Score: <span id="score">0</span> <span class="mono" style="color:var(--muted);font-size:11px">/ goal 30</span></span>
        <span>Best: <span id="best">0</span></span>
        <span class="mono" style="font-size:12px;color:var(--muted)" id="timeLeft">20s</span>
      </div>
      <div class="timer"><i id="timeBar"></i></div>
      <div class="rankline" id="rankLine" aria-live="polite">Enemy: Marine Recruit 💂 · rank up in 5 taps</div>
      <div class="arena" id="arena">
        <div class="overlay" id="overlay">
          <h3>Ready, recruit?</h3>
          <p>The enemy ranks up every 5 taps: Marine, Captain, Vice Admiral, Admiral, Fleet Admiral, Elder, then Imu. Tap fast!</p>
          <div><button class="btn primary" id="startGame">Start the 20-second chase</button></div>
        </div>
      </div>
      <div class="chips" id="chips"></div>
    </div>
  </div>
</section>

<!-- SKILLS -->
<section class="sec" id="skills">
  <div class="wrap skills-grid">
    <div>
      <div class="kicker"><b>04</b> / CREW SKILLS</div>
      <h2>Skills in progress.<br><span class="muted">Potential in motion.</span></h2>
      <p class="lead">Skills unlock as your score climbs in the game: one skill for every 6 marines. Haven't played yet? <a href="#game" class="link">Start the chase ↑</a></p>
      <button class="link" id="tipBtn" style="margin-top:14px">Get a learning tip ↗</button>
      <p class="tip" id="tip" aria-live="polite"></p>
    </div>
    <div id="skillList">
      <div class="skill" data-skill="HTML"><div class="sinfo"><span>HTML</span><small>BUILDING</small></div><div class="track"><span style="--level:78%"></span></div></div>
      <div class="skill" data-skill="CSS"><div class="sinfo"><span>CSS</span><small>BUILDING</small></div><div class="track"><span style="--level:72%"></span></div></div>
      <div class="skill" data-skill="JavaScript"><div class="sinfo"><span>JavaScript</span><small>PRACTICING</small></div><div class="track"><span style="--level:56%"></span></div></div>
      <div class="skill" data-skill="Java"><div class="sinfo"><span>Java</span><small>PRACTICING</small></div><div class="track"><span style="--level:62%"></span></div></div>
      <div class="skill" data-skill="UI/UX"><div class="sinfo"><span>UI / UX Thinking</span><small>EXPLORING</small></div><div class="track"><span style="--level:67%"></span></div></div>
    </div>
  </div>
</section>

<!-- QUIZ -->
<section class="sec" id="quiz">
  <div class="wrap">
    <div class="kicker"><b>05</b> / DO YOU KNOW YOUR CAPTAIN?</div>
    <h2>Captain's Quiz.<br><span class="grad">Three questions.</span></h2>
    <div class="quiz" id="quizCard"></div>
  </div>
</section>

<!-- CONTACT -->
<section class="sec center" id="contact">
  <div class="wrap">
    <div class="kicker" style="text-align:left"><b>06</b> / SET SAIL</div>
    <h2>You're officially on the crew.<br><span class="grad">Let's find the treasure.</span></h2>
    <p class="lead">Thanks for helping defend my ship. Raise the flag before you go.</p>
    <button class="btn primary" id="hello">Raise the flag 🏴‍☠️</button>
    <div class="hello" id="helloMsg" aria-live="polite"></div>
    <footer><span>J. KEEP SAILING. KEEP BUILDING.</span><span>© <span id="year"></span> · MADE WITH A PIRATE'S DREAM</span><a href="#home">BACK TO TOP ↑</a></footer>
  </div>
</section>
</main>

<div class="toast" id="toast" role="status" aria-live="polite"></div>

<script>
/* ===== EDIT ME: your photo (put the file next to index.html) ===== */
const PHOTO = "images/me.jpg";
const INITIALS = "JC";
/* ================================================================= */
const $ = id => document.getElementById(id);

// avatar
if (PHOTO) { const im = document.createElement("img"); im.src = PHOTO; im.alt = "Jonathan"; $("avatar").appendChild(im); }
else $("avatar").textContent = INITIALS;

// nav
$("menu").addEventListener("click", () => {
  const o = $("nav").classList.toggle("open");
  $("menu").textContent = o ? "✕" : "☰"; $("menu").setAttribute("aria-expanded", String(o));
});
document.querySelectorAll("#nav a").forEach(a => a.addEventListener("click", () => {
  $("nav").classList.remove("open"); $("menu").textContent = "☰";
}));

// toast
let tt;
function toast(m){ $("toast").textContent = m; $("toast").classList.add("show"); clearTimeout(tt); tt = setTimeout(() => $("toast").classList.remove("show"), 2600); }

/* ---- typed story in hero ---- */
const lines = [
  ["$ set_sail portfolio.html", ""],
  ["ALERT: Marines are chasing the ship!", "err"],
  ["WARNING: crew is one member short", "err"],
  ["Searching the Grand Line for a nakama...", ""],
  ["Found you. Welcome aboard, new crewmate!", "ok"]
];
let skipType = false;
(async () => {
  for (const [t, c] of lines) {
    const p = document.createElement("p"); p.className = c; $("lines").appendChild(p);
    for (let i = 1; i <= t.length; i++) { p.textContent = t.slice(0, i); if (!skipType) await new Promise(r => setTimeout(r, 15)); }
    if (!skipType) await new Promise(r => setTimeout(r, 110));
  }
})();
$("term").addEventListener("click", () => skipType = true);

/* ---- crew stories (icons are emoji; stories are short original summaries) ---- */
const CREW = [
  { n: "Luffy", ic: "👒", c: "#ff5d47", full: "Monkey D. Luffy", role: "Captain · Rubber-bodied adventurer",
    dream: "Become the Pirate King",
    story: "He ate a strange fruit that made his body stretch like rubber, then set sail with a straw hat and a huge dream. He gathers friends one by one, and his courage makes people want to follow him.",
    lesson: "Dream big and start with one step. I started this portfolio the same way: one line of code." },
  { n: "Zoro", ic: "⚔️", c: "#4ee79a", full: "Roronoa Zoro", role: "Swordsman · Three-sword style",
    dream: "Become the world's greatest swordsman",
    story: "Zoro trains harder than anyone and fights with three swords, even holding one in his mouth. He promised himself never to lose, and he keeps that promise by never skipping practice.",
    lesson: "Practice beats talent. It's why I keep coding and keep playing every week." },
  { n: "Sanji", ic: "🍳", c: "#ffd23f", full: "Vinsmoke Sanji", role: "Cook · Fights with his kicks",
    dream: "Find the legendary sea called the All Blue",
    story: "Sanji cooks for the whole crew and never lets anyone go hungry. He protects his hands because they are made for cooking, so he fights using powerful kicks instead.",
    lesson: "Take pride in your craft. Clean, careful code is like a well-cooked meal." },
  { n: "Nami", ic: "🧭", c: "#ff9a3c", full: "Nami", role: "Navigator · Mapmaker",
    dream: "Draw a map of the entire world",
    story: "Nami reads the weather and the sea better than anyone, so the crew survives storms that would sink other ships. She is clever, and she always knows where the ship needs to go.",
    lesson: "Plan before you sail. A good plan saves hours of debugging." },
  { n: "Usopp", ic: "🎯", c: "#d9a066", full: "Usopp", role: "Sniper · Inventor and storyteller",
    dream: "Become a brave warrior of the sea",
    story: "Usopp is scared a lot of the time, yet he builds clever gadgets, fires with amazing aim, and stands up when his friends need him. His tall tales sometimes turn out to be real courage.",
    lesson: "Courage means acting while afraid. I was nervous about my first project, but I finished it." },
  { n: "Robin", ic: "📚", c: "#b48cff", full: "Nico Robin", role: "Archaeologist · Reader of ancient texts",
    dream: "Uncover the true history of the world",
    story: "Robin spent years alone studying a history others tried to erase. On the ship she finally found a family, and her knowledge solves puzzles nobody else can read.",
    lesson: "Read the docs. Curiosity and research solve problems faster than guessing." },
  { n: "Franky", ic: "🔧", c: "#4fd1ff", full: "Franky", role: "Shipwright · Cyborg builder",
    dream: "Build a ship that can sail the whole world",
    story: "Franky builds and repairs the crew's ship and loves adding clever new features to it. He shows that making something with your own hands is a kind of art.",
    lesson: "Love building things. Every project is a chance to add a new feature." },
  { n: "Chopper", ic: "🦌", c: "#ff8ab3", full: "Tony Tony Chopper", role: "Doctor · A reindeer who can transform",
    dream: "Become a doctor who can cure any illness",
    story: "Chopper ate a fruit that gave him human-like abilities, then set out to become a doctor. He is small and shy, but he never stops studying so he can heal the people he cares about.",
    lesson: "Keep learning so you can help others. I study IT to build useful things for people." },
  { n: "Brook", ic: "🎻", c: "#e6e8f0", full: "Brook", role: "Musician · A living skeleton with a violin",
    dream: "Keep a promise to an old whale friend",
    story: "Brook came back to life as a skeleton and plays music to lift the crew's spirits. He jokes about his own bones while carrying a very old promise.",
    lesson: "Joy matters. Music helps me keep going on tough days." },
  { n: "Jinbe", ic: "🦈", c: "#4a8cff", full: "Jinbe", role: "Helmsman · Fish-man karate master",
    dream: "Help fish-men and humans live in peace",
    story: "Jinbe is a fish-man and karate master who joined the crew as helmsman. He steers the ship steadily through rough waters and values loyalty and honor above all.",
    lesson: "Stay steady and loyal. Good teamwork needs someone who keeps the ship on course." }
];
CREW.forEach((m, i) => {
  const b = document.createElement("button");
  b.className = "cm"; b.type = "button"; b.style.setProperty("--c", m.c);
  b.setAttribute("aria-pressed", "false");
  const ic = document.createElement("span"); ic.className = "ic"; ic.textContent = m.ic;
  const nm = document.createElement("span"); nm.className = "n"; nm.textContent = m.n;
  b.append(ic, nm);
  b.addEventListener("click", () => showCrew(i));
  $("crew").appendChild(b);
});
function showCrew(i) {
  const m = CREW[i];
  document.querySelectorAll(".cm").forEach((x, j) => { x.classList.toggle("on", j === i); x.setAttribute("aria-pressed", String(j === i)); });
  const box = $("crewStory"); box.replaceChildren(); box.style.setProperty("--c", m.c);
  box.classList.remove("filled"); void box.offsetWidth; box.classList.add("filled");
  const head = document.createElement("div"); head.className = "csh";
  const big = document.createElement("span"); big.className = "big"; big.textContent = m.ic;
  const t = document.createElement("div"); const h = document.createElement("h3"); h.textContent = m.full;
  const sm = document.createElement("small"); sm.textContent = m.role; t.append(h, sm); head.append(big, t);
  const dream = document.createElement("p"); dream.className = "dream"; const db = document.createElement("b"); db.textContent = "Dream: "; dream.append(db, m.dream);
  const story = document.createElement("p"); story.textContent = m.story;
  const lesson = document.createElement("p"); lesson.className = "lesson"; const lb = document.createElement("b"); lb.textContent = "What I learn from " + m.n + ": "; lesson.append(lb, m.lesson);
  box.append(head, dream, story, lesson);
}

/* ---- chapters ---- */
document.querySelectorAll(".chap").forEach(ch => {
  const btn = ch.querySelector("button"), body = ch.querySelector(".body");
  const sync = () => { body.style.maxHeight = ch.classList.contains("open") ? body.scrollHeight + "px" : "0"; btn.setAttribute("aria-expanded", ch.classList.contains("open")); };
  btn.addEventListener("click", () => { ch.classList.toggle("open"); sync(); });
  sync(); window.addEventListener("resize", sync);
});

/* ---- flip cards ---- */
document.querySelectorAll(".flip").forEach(c => c.addEventListener("click", () => c.classList.toggle("flipped")));

/* ---- marine game ---- */
const SKILLS = ["HTML", "CSS", "JavaScript", "Java", "UI/UX"];
const GAME_MS = 20000, PASS = 30, PER_SKILL = PASS / SKILLS.length;
let score = 0, best = 0, earned = false, running = false, spawnT, endT, tickT;
try { best = Number(localStorage.getItem("jc_best")) || 0; earned = localStorage.getItem("jc_badge") === "1"; } catch (e) {}
$("best").textContent = best;
if (earned) $("posterBadge").style.display = "block";

SKILLS.forEach(s => { const c = document.createElement("span"); c.className = "chip"; c.id = "chip-" + s; c.textContent = s; $("chips").appendChild(c); });
document.querySelectorAll(".skill").forEach(s => { s.dataset.was = s.querySelector("small").textContent; });

function unlockSkill(i) {
  const name = SKILLS[i];
  $("chip-" + name).classList.add("lit");
  const sk = document.querySelector('.skill[data-skill="' + name + '"]');
  if (sk) { sk.classList.add("unlocked"); sk.querySelector("small").textContent = "UNLOCKED ✓"; }
}
function resetSkills() {
  document.querySelectorAll(".chip").forEach(c => c.classList.remove("lit"));
  document.querySelectorAll(".skill").forEach(s => { s.classList.remove("unlocked"); s.querySelector("small").textContent = s.dataset.was; });
}
function earnBadge() {
  if (!earned) { earned = true; try { localStorage.setItem("jc_badge", "1"); } catch (e) {} }
  $("posterBadge").style.display = "block";
  toast("🏴‍☠️ 30 marines! You're a New Crewmate!");
}

/* enemy ranks up every 5 taps (all emoji, no official art) */
const TIERS = [
  { at: 0,  name: "Marine Recruit", ic: "💂", size: 54, bg: "#1d3b6e" },
  { at: 5,  name: "Marine Captain", ic: "🪖", size: 58, bg: "#2a4f8f" },
  { at: 10, name: "Vice Admiral",   ic: "🎖️", size: 62, bg: "#3b5fa8" },
  { at: 15, name: "Admiral",        ic: "🔥", size: 66, bg: "#8a3418" },
  { at: 20, name: "Fleet Admiral",  ic: "⚓", size: 70, bg: "#6b1f3a" },
  { at: 25, name: "Elder",          ic: "🔮", size: 74, bg: "#4a2670" },
  { at: 30, name: "Imu",            ic: "👑", size: 82, bg: "#2b0f4a", final: true }
];
/* Original cartoon faces, drawn as SVG (not official artwork).
   Want your own pictures? Put image files next to index.html and fill FACE_IMAGES,
   e.g. FACE_IMAGES[6] = "imu.png"  (index 0 = Marine Recruit ... 6 = Imu). */
const FACE_IMAGES = ["", "", "", "", "", "", ""];
const SK = "#f2c9a0", INK = "#241a38";
const ears = c => `<circle cx="19" cy="58" r="6" fill="${c}"/><circle cx="81" cy="58" r="6" fill="${c}"/>`;
const FACES = [
  /* 0 Marine Recruit: small navy cap, big friendly eyes */
  ears(SK) + `<circle cx="50" cy="56" r="30" fill="${SK}"/><path d="M18 46 Q50 6 82 46Z" fill="#6c93e6"/><rect x="16" y="43" width="68" height="9" rx="4" fill="#fff"/><circle cx="38" cy="63" r="4" fill="${INK}"/><circle cx="62" cy="63" r="4" fill="${INK}"/><path d="M41 76 Q50 84 59 76" stroke="${INK}" stroke-width="3" fill="none" stroke-linecap="round"/>`,
  /* 1 Marine Captain: gold badge, moustache */
  ears("#e8b98c") + `<circle cx="50" cy="56" r="30" fill="#e8b98c"/><path d="M16 47 Q50 0 84 47Z" fill="#6f9cf0"/><rect x="14" y="44" width="72" height="8" rx="4" fill="#d8b64a"/><circle cx="50" cy="28" r="6" fill="#d8b64a"/><path d="M30 57 L45 60 M70 57 L55 60" stroke="${INK}" stroke-width="3.5" stroke-linecap="round"/><circle cx="38" cy="66" r="3" fill="${INK}"/><circle cx="62" cy="66" r="3" fill="${INK}"/><path d="M34 77 Q50 69 66 77 Q50 85 34 77Z" fill="#4a3320"/>`,
  /* 2 Vice Admiral: peaked cap, stern brows */
  ears("#e0ad80") + `<circle cx="50" cy="57" r="30" fill="#e0ad80"/><path d="M12 48 Q50 -4 88 48Z" fill="#1c3570"/><rect x="8" y="45" width="84" height="9" rx="4" fill="#fff"/><path d="M41 40 L59 40 L50 26Z" fill="#d8b64a"/><path d="M28 58 L45 63 M72 58 L55 63" stroke="${INK}" stroke-width="4.5" stroke-linecap="round"/><circle cx="38" cy="68" r="3" fill="${INK}"/><circle cx="62" cy="68" r="3" fill="${INK}"/><path d="M40 82 L60 82" stroke="${INK}" stroke-width="3.5" stroke-linecap="round"/><path d="M22 60 L22 72 M78 60 L78 72" stroke="#4a3320" stroke-width="4"/>`,
  /* 3 Admiral: fiery aura, sunglasses, white coat */
  `<circle cx="50" cy="52" r="47" fill="#ff7a2f" opacity=".4"/>` + ears("#dcaa82") + `<circle cx="50" cy="56" r="29" fill="#dcaa82"/><path d="M19 52 Q50 8 81 52 Q50 36 19 52Z" fill="${INK}"/><rect x="24" y="55" width="22" height="13" rx="4" fill="#0b0b12"/><rect x="54" y="55" width="22" height="13" rx="4" fill="#0b0b12"/><path d="M46 59 L54 59" stroke="#0b0b12" stroke-width="3"/><path d="M39 79 L61 79" stroke="${INK}" stroke-width="3.5" stroke-linecap="round"/><path d="M14 100 L50 84 L86 100Z" fill="#fff"/>`,
  /* 4 Fleet Admiral: white hair and beard, scar, thick brows */
  ears("#e2b48c") + `<circle cx="50" cy="55" r="30" fill="#e2b48c"/><path d="M15 56 Q50 0 85 56 Q72 30 50 28 Q28 30 15 56Z" fill="#d9dde6"/><path d="M26 64 Q50 108 74 64 Q62 76 50 74 Q38 76 26 64Z" fill="#eef0f5"/><path d="M28 54 L45 60 M72 54 L55 60" stroke="#8a8fa0" stroke-width="5.5" stroke-linecap="round"/><circle cx="38" cy="64" r="3.2" fill="${INK}"/><circle cx="62" cy="64" r="3.2" fill="${INK}"/><path d="M63 46 L73 68" stroke="#b34a4a" stroke-width="2.6"/><path d="M14 100 L50 86 L86 100Z" fill="#6b1f3a"/>`,
  /* 5 Elder: long white hair, narrow eyes, purple robe */
  `<path d="M16 42 Q50 -6 84 42 L90 96 L70 72 L30 72 L10 96Z" fill="#e8e6f2"/>` + `<circle cx="50" cy="57" r="27" fill="#efe3da"/><path d="M36 44 Q50 39 64 44" stroke="#c9b8aa" stroke-width="2" fill="none"/><path d="M31 59 Q38 54 45 59 M55 59 Q62 54 69 59" stroke="${INK}" stroke-width="3" fill="none" stroke-linecap="round"/><path d="M41 76 Q50 72 59 76" stroke="${INK}" stroke-width="3" fill="none" stroke-linecap="round"/><path d="M18 100 L50 84 L82 100Z" fill="#4a2670"/>`,
  /* 6 Imu: shadowy ruler, glowing violet eyes, golden crown */
  `<circle cx="50" cy="52" r="47" fill="#b44cff" opacity=".3"/><path d="M14 98 L20 46 Q50 6 80 46 L86 98 Q50 76 14 98Z" fill="#0d0618"/><ellipse cx="50" cy="58" rx="22" ry="26" fill="#d9cfe6"/><ellipse cx="40" cy="58" rx="7" ry="4" fill="#e8a8ff"/><ellipse cx="60" cy="58" rx="7" ry="4" fill="#e8a8ff"/><circle cx="40" cy="58" r="2" fill="#2b0f4a"/><circle cx="60" cy="58" r="2" fill="#2b0f4a"/><path d="M43 77 Q50 81 57 77" stroke="#3b1d5e" stroke-width="3" fill="none" stroke-linecap="round"/><path d="M27 34 L32 12 L41 26 L50 6 L59 26 L68 12 L73 34Z" fill="#f2c94c" stroke="#b8952a" stroke-width="1.5"/><circle cx="50" cy="22" r="3" fill="#b44cff"/>`
].map(inner => '<svg viewBox="0 0 100 100" aria-hidden="true">' + inner + '</svg>');

let lastTier = 0;
function tierOf(n) { let k = 0; TIERS.forEach((t, i) => { if (n >= t.at) k = i; }); return k; }
function updateRank() {
  const k = tierOf(score), t = TIERS[k], nx = TIERS[k + 1];
  $("rankLine").textContent = "Enemy: " + t.name + " " + t.ic + (nx ? " · rank up in " + (nx.at - score) + " tap" + (nx.at - score === 1 ? "" : "s") : " · final boss! Keep tapping!");
  if (k > lastTier) toast("⬆ Rank up! Now facing: " + t.name + " " + t.ic);
  lastTier = k;
}

function spawnMarine(life) {
  const arena = $("arena");
  const t = TIERS[tierOf(score)];
  const m = document.createElement("button");
  m.className = "marine" + (t.final ? " final" : ""); m.type = "button";
  const k = tierOf(score);
  if (FACE_IMAGES[k]) { const im = document.createElement("img"); im.src = FACE_IMAGES[k]; im.alt = ""; m.appendChild(im); }
  else m.innerHTML = FACES[k];
  m.setAttribute("aria-label", t.name + ", tap to defeat");
  m.style.width = m.style.height = t.size + "px"; m.style.fontSize = Math.round(t.size * 0.5) + "px"; m.style.background = t.bg;
  m.style.left = Math.random() * Math.max(10, arena.clientWidth - t.size - 6) + "px";
  m.style.top = Math.random() * Math.max(10, arena.clientHeight - t.size - 6) + "px";
  m.addEventListener("click", () => {
    if (m.classList.contains("dead") || !running) return;
    m.classList.add("dead"); setTimeout(() => m.remove(), 360);
    score++; $("score").textContent = score; updateRank();
    if (score % PER_SKILL === 0 && score / PER_SKILL <= SKILLS.length) unlockSkill(score / PER_SKILL - 1);
    if (score === PASS) earnBadge();
  });
  arena.appendChild(m);
  setTimeout(() => m.remove(), life);
}

function startGame() {
  running = true; score = 0; $("score").textContent = 0; resetSkills(); lastTier = 0; updateRank();
  $("overlay").style.display = "none";
  $("arena").querySelectorAll(".marine").forEach(m => m.remove());
  const bar = $("timeBar"); bar.style.transition = "none"; bar.style.transform = "scaleX(1)";
  requestAnimationFrame(() => requestAnimationFrame(() => { bar.style.transition = `transform ${GAME_MS}ms linear`; bar.style.transform = "scaleX(0)"; }));
  const t0 = Date.now();
  tickT = setInterval(() => { $("timeLeft").textContent = Math.max(0, Math.ceil((GAME_MS - (Date.now() - t0)) / 1000)) + "s"; }, 200);
  const loop = () => {
    if (!running) return;
    const p = Math.min(1, (Date.now() - t0) / GAME_MS);   // 0 to 1: the chase speeds up
    spawnMarine(1500 - 650 * p);
    spawnT = setTimeout(loop, 720 - 360 * p);
  };
  loop(); endT = setTimeout(finish, GAME_MS);
}

function finish() {
  if (!running) return; running = false;
  clearTimeout(spawnT); clearTimeout(endT); clearInterval(tickT);
  $("timeLeft").textContent = "0s";
  $("arena").querySelectorAll(".marine").forEach(m => m.remove());
  const isNew = score > best;
  if (isNew) { best = score; $("best").textContent = best; try { localStorage.setItem("jc_best", String(best)); } catch (e) {} }
  const passed = score >= PASS;
  const o = $("overlay"); o.style.display = "grid"; o.replaceChildren();
  const h = document.createElement("h3");
  h.textContent = passed ? "You beat Imu! Welcome aboard, New Crewmate!" : "Not yet, recruit. Reach " + PASS + " to join the crew.";
  const p = document.createElement("p");
  p.textContent = `Score: ${score}  ·  Best: ${best}  ·  Strongest foe: ${TIERS[tierOf(score)].name} ${TIERS[tierOf(score)].ic}` + (isNew && score > 0 ? "  ·  New high score!" : "");
  o.append(h, p);
  if (passed) { const b = document.createElement("div"); b.className = "ovbadge"; b.textContent = "🏴‍☠️ NEW CREWMATE BADGE EARNED"; o.append(b); }
  const d = document.createElement("div");
  const again = document.createElement("button"); again.className = "btn ghost"; again.textContent = "Play again ↻"; again.addEventListener("click", startGame);
  const next = document.createElement("a"); next.className = "btn primary"; next.href = "#skills"; next.textContent = "See crew skills ↓"; next.style.marginLeft = "10px";
  d.append(again, next); o.append(d);
}
$("startGame").addEventListener("click", startGame);

/* ---- tips ---- */
const tips = ["Build a tiny project after every new concept. Using it makes it stick.", "When code breaks, change one thing at a time. Debugging is a skill too.", "Explain a concept in your own words. If you can teach it simply, you understand it.", "Practice for 20 focused minutes, then take a short break."];
let ti = 0; $("tipBtn").addEventListener("click", () => { $("tip").textContent = tips[ti++ % tips.length]; });

/* ---- quiz (EDIT the questions to match your real life) ---- */
const Q = [
  { cat: "GETTING TO KNOW ME", q: "What keeps me going on tough days?", o: ["Music", "Sleep", "Snacks"], a: 0, e: "Music is a great pick-me-up! ✦" },
  { cat: "MY INTERESTS", q: "Which activity is one of my interests?", o: ["Basketball", "Gardening", "Cooking contests"], a: 0, e: "Basketball: teamwork, practice, and fun. 🏀" },
  { cat: "MY FUTURE", q: "What am I studying?", o: ["Information Technology", "Architecture", "Nursing"], a: 0, e: "Yes! I'm learning to build with technology. 💻" }
];
let qi = 0, qs = 0, answered = false;
function el(tag, cls, text) { const e = document.createElement(tag); if (cls) e.className = cls; if (text !== undefined) e.textContent = text; return e; }
function renderQ() {
  const card = $("quizCard"); card.replaceChildren(); answered = false;
  const q = Q[qi];
  const meta = el("div", "qmeta"); meta.append(el("span", "", `QUESTION ${qi + 1} / ${Q.length}`), el("span", "", `SCORE ${qs}`));
  const prog = el("div", "prog"); const bar = el("span"); bar.style.width = ((qi + 1) / Q.length * 100) + "%"; prog.append(bar);
  const opts = el("div", "opts"); const fb = el("p", "fb", "Pick an answer ✦"); fb.setAttribute("aria-live", "polite");
  const next = el("button", "btn primary", qi === Q.length - 1 ? "See my result →" : "Next question →"); next.disabled = true;
  q.o.forEach((t, i) => {
    const b = el("button", "opt", String.fromCharCode(65 + i) + ".  " + t); b.type = "button";
    b.addEventListener("click", () => {
      if (answered) return; answered = true;
      const right = i === q.a; if (right) qs++;
      fb.textContent = right ? "Correct! " + q.e : `Close! My answer was "${q.o[q.a]}".`;
      opts.querySelectorAll("button").forEach((x, j) => { x.disabled = true; if (j === q.a) x.classList.add("ok"); else if (j === i) x.classList.add("no"); });
      next.disabled = false;
    });
    opts.append(b);
  });
  next.addEventListener("click", () => { if (qi < Q.length - 1) { qi++; renderQ(); } else resultQ(); });
  const foot = el("div", "qfoot"); foot.append(el("small", "mono", q.cat), next);
  card.append(meta, prog, el("h3", "", q.q), opts, fb, foot);
}
function resultQ() {
  const card = $("quizCard"); card.replaceChildren();
  const r = el("div", "result");
  const title = qs === 3 ? "You know me pretty well!" : qs === 2 ? "Almost a personal expert!" : "The mystery remains!";
  const again = el("button", "btn primary", "Play again ↻"); again.addEventListener("click", () => { qi = 0; qs = 0; renderQ(); });
  r.append(el("div", "big", "✦"), el("h3", "", title), el("p", "lead", `You scored ${qs} out of ${Q.length}.`), again);
  r.querySelector(".lead").style.margin = "0 auto 16px";
  card.append(r);
}
renderQ();

/* ---- closing ---- */
$("hello").addEventListener("click", () => {
  const m = ["🏴‍☠️ The flag is up! Keep chasing your dream, crewmate.", "🏴‍☠️ Every great crew starts with one brave volunteer. Thanks for sailing with me!", "🏴‍☠️ Bounty claimed. Adventure never ends, keep building!"];
  $("helloMsg").textContent = m[Math.floor(Math.random() * m.length)];
});
$("year").textContent = new Date().getFullYear();
</script>
</body>
</html>
