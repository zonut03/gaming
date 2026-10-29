
<!DOCTYPE html>
<html lang="ro">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="theme-color" content="#080808">
<title>Golden Arena | Gaming Zone</title>

<style>
:root {
  --gold: #f5c542;
  --gold2: #ffdf80;
  --black: #080808;
  --panel: #141414;
  --text: #f5f5f5;
  --muted: #a5a5a5;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html { scroll-behavior: smooth; }

body {
  background: var(--black);
  color: var(--text);
  font-family: Arial, Helvetica, sans-serif;
  min-height: 100vh;
}

button, input { font: inherit; }

header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 22px 7%;
  border-bottom: 1px solid #292316;
  background: rgba(8,8,8,.95);
  position: sticky;
  top: 0;
  z-index: 10;
}

.logo {
  font-size: 24px;
  font-weight: 900;
  letter-spacing: 2px;
  color: var(--gold);
}

.logo span { color: white; }

nav {
  display: flex;
  gap: 25px;
}

nav a {
  color: #ddd;
  text-decoration: none;
  font-size: 14px;
  transition: .2s;
}

nav a:hover { color: var(--gold); }

.hero {
  min-height: 440px;
  padding: 85px 20px 70px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  background:
    radial-gradient(ellipse at center, #4a3512 0%, #191307 28%, #080808 72%);
  border-bottom: 1px solid #302515;
}

.tag {
  color: var(--gold);
  border: 1px solid #8d6b22;
  border-radius: 30px;
  padding: 8px 16px;
  font-size: 12px;
  letter-spacing: 2px;
  margin-bottom: 24px;
}

.hero h1 {
  font-size: clamp(42px, 8vw, 82px);
  line-height: 1.05;
  font-weight: 900;
  letter-spacing: -2px;
}

.hero h1 span {
  color: var(--gold);
  text-shadow: 0 0 35px #e6a90045;
}

.hero p {
  color: #c4c4c4;
  max-width: 560px;
  line-height: 1.8;
  margin: 22px 0 30px;
}

.btn {
  display: inline-block;
  padding: 14px 25px;
  border: none;
  border-radius: 7px;
  background: linear-gradient(135deg, var(--gold2), #d49b17);
  color: #111;
  font-weight: bold;
  cursor: pointer;
  text-decoration: none;
  transition: .2s;
}

.btn:hover {
  transform: translateY(-3px);
  box-shadow: 0 8px 25px #f5c54235;
}

main {
  max-width: 1200px;
  padding: 65px 24px;
  margin: auto;
}

.section-heading {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 20px;
  margin-bottom: 28px;
}

.section-heading h2 {
  font-size: 29px;
}

.section-heading h2 span { color: var(--gold); }

.search {
  background: #141414;
  border: 1px solid #38312a;
  color: white;
  padding: 12px 15px;
  border-radius: 7px;
  outline: none;
  width: 230px;
  max-width: 100%;
}

.search:focus { border-color: var(--gold); }

.filters {
  display: flex;
  gap: 10px;
  flex-wrap: wrap;
  margin-bottom: 30px;
}

.filter {
  background: #161616;
  color: #bbb;
  border: 1px solid #333;
  padding: 9px 17px;
  border-radius: 30px;
  cursor: pointer;
}

.filter.active, .filter:hover {
  background: #f5c542;
  border-color: #f5c542;
  color: #111;
}

.games {
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  gap: 22px;
}

.game-card {
  background: linear-gradient(145deg, #191919, #0e0e0e);
  border: 1px solid #302a20;
  border-radius: 13px;
  overflow: hidden;
  transition: .25s;
}

.game-card:hover {
  transform: translateY(-6px);
  border-color: #c69b32;
  box-shadow: 0 12px 35px #0008;
}

.game-art {
  height: 170px;
  display: grid;
  place-items: center;
  font-size: 68px;
  position: relative;
  background: radial-gradient(circle, #443214, #17120a 65%, #101010);
}

.game-art.blue {
  background: radial-gradient(circle, #183b53, #10151b 70%);
}

.game-art.purple {
  background: radial-gradient(circle, #42224f, #17101b 70%);
}

.game-art.green {
  background: radial-gradient(circle, #204a2b, #101710 70%);
}

.game-art.red {
  background: radial-gradient(circle, #55251d, #180f0e 70%);
}

.game-art small {
  position: absolute;
  top: 13px;
  left: 13px;
  font-size: 10px;
  letter-spacing: 1px;
  background: #f5c542;
  color: #111;
  padding: 6px 9px;
  border-radius: 4px;
  font-weight: bold;
}

.game-info { padding: 20px; }

.game-info h3 {
  font-size: 19px;
  margin-bottom: 9px;
}

.game-info p {
  color: var(--muted);
  font-size: 13px;
  line-height: 1.6;
  min-height: 42px;
  margin-bottom: 18px;
}

.game-bottom {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 10px;
}

.category {
  color: var(--gold);
  font-size: 12px;
}

.play-btn {
  background: transparent;
  border: 1px solid #b58a28;
  color: var(--gold);
  padding: 9px 15px;
  border-radius: 6px;
  cursor: pointer;
}

.play-btn:hover {
  background: var(--gold);
  color: #111;
}

.empty {
  display: none;
  color: #aaa;
  padding: 40px;
  text-align: center;
}

.stats {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 15px;
  margin-top: 60px;
}

.stat {
  background: #121212;
  border: 1px solid #29251d;
  border-radius: 10px;
  padding: 25px 10px;
  text-align: center;
}

.stat strong {
  display: block;
  font-size: 27px;
  color: var(--gold);
  margin-bottom: 8px;
}

.stat span {
  color: #aaa;
  font-size: 12px;
}

footer {
  text-align: center;
  padding: 30px 15px;
  border-top: 1px solid #292316;
  color: #888;
  font-size: 13px;
  line-height: 2;
}

footer strong { color: var(--gold); }

/* Fereastra jocului */
.modal {
  position: fixed;
  inset: 0;
  background: #000d;
  z-index: 30;
  display: none;
  place-items: center;
  padding: 18px;
}

.modal.show { display: grid; }

.modal-box {
  width: 100%;
  max-width: 520px;
  max-height: 90vh;
  overflow: auto;
  background: #141414;
  border: 1px solid #9d7728;
  border-radius: 15px;
  padding: 28px;
  text-align: center;
}

.modal-top {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 25px;
}

.modal-top h2 { color: var(--gold); }

.close {
  background: transparent;
  color: white;
  border: 0;
  font-size: 28px;
  cursor: pointer;
}

#gameArea {
  padding: 20px 0;
  line-height: 1.8;
}

#gameArea input {
  display: block;
  margin: 15px auto;
  width: 150px;
  padding: 12px;
  background: #080808;
  color: white;
  border: 1px solid #8d6b22;
  border-radius: 6px;
  text-align: center;
}

#gameArea button {
  margin: 6px;
}

.reaction-box {
  width: 100%;
  min-height: 190px;
  margin-top: 15px;
  border-radius: 10px;
  border: 1px solid #555;
  background: #252525;
  color: white;
  cursor: pointer;
  font-weight: bold;
}

@media (max-width: 850px) {
  .games { grid-template-columns: repeat(2, minmax(0, 1fr)); }
  header { padding: 20px 5%; }
}

@media (max-width: 560px) {
  header { flex-wrap: wrap; gap: 18px; }
  nav { gap: 15px; }
  .logo { font-size: 20px; }
  .games { grid-template-columns: 1fr; }
  .section-heading { align-items: flex-start; flex-direction: column; }
  .search { width: 100%; }
  .hero { min-height: 390px; }
  main { padding: 45px 18px; }
}
</style>
</head>

<body>

<header>
  <a href="#" class="logo" style="text-decoration:none">
    GOLDEN <span>ARENA</span>
  </a>
  <nav>
    <a href="#">Acasă</a>
    <a href="#games">Jocuri</a>
    <a href="#about">Despre</a>
  </nav>
</header>

<section class="hero">
  <div class="tag">✦ BINE AI VENIT ÎN ARENĂ ✦</div>
  <h1>PLAY LIKE A <span>LEGEND.</span></h1>
  <p>
    Intră în Golden Arena, descoperă jocuri distractive
    și demonstrează că ai reflexe de campion.
    Aventura ta începe aici!
  </p>
  <a class="btn" href="#games">⚡ DESCOPERĂ JOCURILE</a>
</section>

<main id="games">
  <div class="section-heading">
    <h2>Jocuri <span>populare</span></h2>
    <input class="search" id="search" placeholder="⌕ Caută un joc..." aria-label="Caută un joc">
  </div>

  <div class="filters">
    <button class="filter active" data-filter="all">Toate</button>
    <button class="filter" data-filter="arcade">Arcade</button>
    <button class="filter" data-filter="logic">Logică</button>
    <button class="filter" data-filter="skill">Reflexe</button>
  </div>

  <div class="games" id="gameList">

    <article class="game-card" data-category="skill" data-name="reflex challenge">
      <div class="game-art">
        <small>HOT</small> ⚡
      </div>
      <div class="game-info">
        <h3>Reflex Challenge</h3>
        <p>Testează-ți viteza de reacție și încearcă să obții un timp record.</p>
        <div class="game-bottom">
          <span class="category">REFLEXE</span>
          <button class="play-btn" data-game="reaction">Joacă ▶</button>
        </div>
      </div>
    </article>

    <article class="game-card" data-category="arcade" data-name="golden clicker">
      <div class="game-art green">
        <small>POPULAR</small> 🪙
      </div>
      <div class="game-info">
        <h3>Golden Clicker</h3>
        <p>Apasă pe monedă, adună puncte și stabilește-ți propriul record.</p>
        <div class="game-bottom">
          <span class="category">ARCADE</span>
          <button class="play-btn" data-game="clicker">Joacă ▶</button>
        </div>
      </div>
    </article>

    <article class="game-card" data-category="logic" data-name="number master">
      <div class="game-art blue">
        <small>LOGICĂ</small> 🔢
      </div>
      <div class="game-info">
        <h3>Number Master</h3>
        <p>Găsește numărul secret folosind cât mai puține încercări.</p>
        <div class="game-bottom">
          <span class="category">LOGICĂ</span>
          <button class="play-btn" data-game="number">Joacă ▶</button>
        </div>
      </div>
    </article>

    <article class="game-card" data-category="arcade" data-name="gold rush">
      <div class="game-art purple">
        <small>NOU</small> 💎
      </div>
      <div class="game-info">
        <h3>Gold Rush</h3>
        <p>Un joc rapid de colecționat puncte. Câte poți strânge într-un minut?</p>
        <div class="game-bottom">
          <span class="category">ARCADE</span>
          <button class="play-btn" data-game="rush">Joacă ▶</button>
        </div>
      </div>
    </article>

    <article class="game-card" data-category="logic" data-name="memory master">
      <div class="game-art red">
        <small>CHALLENGE</small> 🧠
      </div>
      <div class="game-info">
        <h3>Memory Master</h3>
        <p>Memorează secvența de culori și repet-o fără greșeli.</p>
        <div class="game-bottom">
          <span class="category">MEMORIE</span>
          <button class="play-btn" data-game="memory">Joacă ▶</button>
        </div>
      </div>
    </article>

    <article class="game-card" data-category="skill" data-name="target tap">
      <div class="game-art">
        <small>SKILL</small> 🎯
      </div>
      <div class="game-info">
        <h3>Target Tap</h3>
        <p>Prinde ținta cât mai repede. Ai 15 secunde să faci un scor mare.</p>
        <div class="game-bottom">
          <span class="category">PRECIZIE</span>
          <button class="play-btn" data-game="target">Joacă ▶</button>
        </div>
      </div>
    </article>

  </div>

  <div class="empty" id="empty">Nu am găsit niciun joc. Încearcă alt cuvânt!</div>

  <div class="stats" id="about">
    <div class="stat">
      <strong>06</strong>
      <span>JOCURI DISPONIBILE</span>
    </div>
    <div class="stat">
      <strong>100%</strong>
      <span>DISTRAȚIE</span>
    </div>
    <div class="stat">
      <strong>FREE</strong>
      <span>ACCES GRATUIT</span>
    </div>
  </div>
</main>

<footer>
  <strong>GOLDEN ARENA</strong><br>
  Joacă inteligent. Devino o legendă.<br>
  © <span id="year"></span> Golden Arena. Toate drepturile rezervate.
</footer>

<div class="modal" id="modal" role="dialog" aria-modal="true" aria-labelledby="modalTitle">
  <div class="modal-box">
    <div class="modal-top">
      <h2 id="modalTitle">Golden Arena</h2>
      <button class="close" id="close" aria-label="Închide">×</button>
    </div>
    <div id="gameArea"></div>
  </div>
</div>

<script>
const $ = (s) => document.querySelector(s);
const $$ = (s) => document.querySelectorAll(s);

let activeFilter = "all";
let currentCleanup = () => {};

$("#year").textContent = new Date().getFullYear();

function filterGames() {
  const query = $("#search").value.toLowerCase().trim();
  let visible = 0;

  $$(".game-card").forEach(card => {
    const categoryMatch =
      activeFilter === "all" ||
      card.dataset.category === activeFilter;

    const searchMatch =
      card.dataset.name.includes(query) ||
      card.innerText.toLowerCase().includes(query);

    const show = categoryMatch && searchMatch;
    card.style.display = show ? "" : "none";
    if (show) visible++;
  });

  $("#empty").style.display = visible ? "none" : "block";
}

$("#search").addEventListener("input", filterGames);

$$(".filter").forEach(button => {
  button.addEventListener("click", () => {
    $$(".filter").forEach(b => b.classList.remove("active"));
    button.classList.add("active");
    activeFilter = button.dataset.filter;
    filterGames();
  });
});

const modal = $("#modal");
const area = $("#gameArea");

function showModal(title, html) {
  currentCleanup();
  currentCleanup = () => {};
  $("#modalTitle").textContent = title;
  area.innerHTML = html;
  modal.classList.add("show");
}

function closeModal() {
  currentCleanup();
  currentCleanup = () => {};
  modal.classList.remove("show");
}

$("#close").addEventListener("click", closeModal);

modal.addEventListener("click", e => {
  if (e.target === modal) closeModal();
});

document.addEventListener("keydown", e => {
  if (e.key === "Escape") closeModal();
});

function startReaction() {
  showModal("⚡ Reflex Challenge", `
    <p>Apasă butonul când devine VERDE!</p>
    <p id="reactionMessage">Pregătește-te...</p>
    <button class="reaction-box" id="reactionBox">Așteaptă...</button>
    <p id="reactionScore"></p>
  `);

  const box = $("#reactionBox");
  const message = $("#reactionMessage");
  const score = $("#reactionScore");
  let state = "waiting";
  let timer;
  let started = 0;

  const delay = 1500 + Math.random() * 3000;

  timer = setTimeout(() => {
    state = "ready";
    started = performance.now();
    box.style.background = "#167c43";
    box.textContent = "ACUM! APASĂ!";
    message.textContent = "Cât de rapid ești?";
  }, delay);

  box.onclick = () => {
    if (state === "waiting") {
      clearTimeout(timer);
      state = "early";
      box.style.background = "#8c2525";
      box.textContent = "Prea devreme!";
      message.textContent = "Încearcă din nou.";
      return;
    }

    if (state === "ready") {
      state = "done";
      const ms = Math.round(performance.now() - started);
      box.textContent = ms + " ms";
      box.style.background = "#292929";
      score.textContent = "Timpul tău: " + ms + " milisecunde.";
      message.textContent = "Bravo! Poți încerca din nou.";
    } else {
      startReaction();
    }
  };

  currentCleanup = () => clearTimeout(timer);
}

function startClicker() {
  showModal("🪙 Golden Clicker", `
    <p>Apasă moneda de cât mai multe ori în 15 secunde!</p>
    <h2 id="clickScore" style="font-size:42px;color:#f5c542">0</h2>
    <p id="clickTime">Timp: 15 secunde</p>
    <button class="btn" id="coin" style="font-size:35px">🪙</button>
    <p id="clickMessage">Pregătit? Începe!</p>
    <button class="play-btn" id="clickStart">Începe jocul</button>
  `);

  let points = 0;
  let remaining = 15;
  let running = false;
  let interval;

  $("#coin").disabled = true;
  $("#coin").style.opacity = ".5";

  $("#clickStart").onclick = () => {
    if (running) return;
    points = 0;
    remaining = 15;
    running = true;
    $("#clickScore").textContent = "0";
    $("#clickStart").disabled = true;
    $("#coin").disabled = false;
    $("#coin").style.opacity = "1";
    $("#clickMessage").textContent = "Apasă repede!";

    interval = setInterval(() => {
      remaining--;
      $("#clickTime").textContent = "Timp: " + remaining + " secunde";

      if (remaining <= 0) {
        clearInterval(interval);
        running = false;
        $("#coin").disabled = true;
        $("#clickStart").disabled = false;
        $("#clickMessage").textContent =
          "Timp expirat! Scor final: " + points;
      }
    }, 1000);
  };

  $("#coin").onclick = () => {
    if (!running) return;
    points++;
    $("#clickScore").textContent = points;
  };

  currentCleanup = () => clearInterval(interval);
}

function startNumber() {
  let secret = Math.floor(Math.random() * 100) + 1;
  let attempts = 0;

  showModal("🔢 Number Master", `
    <p>Am ales un număr între 1 și 100.</p>
    <p>Poți să-l ghicești?</p>
    <input id="guess" type="number" min="1" max="100" placeholder="Numărul tău">
    <button class="btn" id="guessBtn">Verifică</button>
    <p id="guessMessage" style="margin-top:18px">Ai încercări nelimitate!</p>
    <button class="play-btn" id="guessReset">Joc nou</button>
  `);

  function checkGuess() {
    const input = $("#guess");
    const n = Number(input.value);
    if (!input.value || n < 1 || n > 100 || !Number.isInteger(n)) {
      $("#guessMessage").textContent = "Introdu un număr întreg între 1 și 100.";
      return;
    }

    attempts++;

    if (n === secret) {
      $("#guessMessage").textContent =
        "🏆 Corect! Ai ghicit în " + attempts + " încercări!";
    } else {
      $("#guessMessage").textContent =
        (n < secret ? "Mai mare!" : "Mai mic!") +
        " Încercări: " + attempts;
    }
    input.value = "";
    input.focus();
  }

  $("#guessBtn").onclick = checkGuess;
  $("#guess").addEventListener("keydown", e => {
    if (e.key === "Enter") checkGuess();
  });

  $("#guessReset").onclick = startNumber;
}

function startRush() {
  showModal("💎 Gold Rush", `
    <p>Apasă butonul de câte ori poți în 20 de secunde!</p>
    <h2 id="rushScore" style="color:#f5c542;font-size:42px">0</h2>
    <p id="rushTime">Apasă start când ești gata.</p>
    <button class="btn" id="rushStart">START</button>
    <button class="reaction-box" id="rushTap" style="min-height:100px">💎 APASĂ!</button>
  `);

  let points = 0;
  let time = 20;
  let running = false;
  let interval;

  $("#rushTap").disabled = true;

  $("#rushStart").onclick = () => {
    if (running) return;
    points = 0;
    time = 20;
    running = true;
    $("#rushScore").textContent = "0";
    $("#rushTap").disabled = false;
    $("#rushStart").disabled = true;

    interval = setInterval(() => {
      time--;
      $("#rushTime").textContent = "Timp rămas: " + time;

      if (time <= 0) {
        clearInterval(interval);
        running = false;
        $("#rushTap").disabled = true;
        $("#rushStart").disabled = false;
        $("#rushStart").textContent = "Joacă din nou";
        $("#rushTime").textContent = "Scor final: " + points;
      }
    }, 1000);
  };

  $("#rushTap").onclick = () => {
    if (!running) return;
    points++;
    $("#rushScore").textContent = points;
  };

  currentCleanup = () => clearInterval(interval);
}

function startTarget() {
  showModal("🎯 Target Tap", `
    <p>Ai 15 secunde să prinzi cât mai multe ținte!</p>
    <p id="targetTime">Apasă start!</p>
    <p id="targetScore" style="color:#f5c542;font-size:25px">Scor: 0</p>
    <div id="targetBoard" style="position:relative;height:240px;background:#090909;border:1px solid #55431e;border-radius:10px;overflow:hidden;margin:15px 0"></div>
    <button class="btn" id="targetStart">START</button>
  `);

  let score = 0;
  let time = 15;
  let running = false;
  let interval;
  let spawn;

  $("#targetStart").onclick = () => {
    if (running) return;
    score = 0;
    time = 15;
    running = true;
    $("#targetScore").textContent = "Scor: 0";
    $("#targetStart").disabled = true;
    $("#targetBoard").innerHTML = "";

    const placeTarget = () => {
      if (!running) return;
      const board = $("#targetBoard");
      board.innerHTML = "";
      const target = document.createElement("button");
      target.textContent = "🎯";
      target.setAttribute("aria-label", "Prinde ținta");
      target.style.cssText =
        "position:absolute;font-size:30px;border:0;background:transparent;cursor:pointer;" +
        "left:" + Math.random() * 75 + "%;top:" + Math.random() * 70 + "%";
      target.onclick = () => {
        if (!running) return;
        score++;
        $("#targetScore").textContent = "Scor: " + score;
        placeTarget();
      };
      board.appendChild(target);
    };

    placeTarget();
    spawn = setInterval(placeTarget, 1300);

    interval = setInterval(() => {
      time--;
      $("#targetTime").textContent = "Timp rămas: " + time + " secunde";

      if (time <= 0) {
        running = false;
        clearInterval(interval);
        clearInterval(spawn);
        $("#targetBoard").innerHTML = "🏆 Scor final: " + score;
        $("#targetStart").disabled = false;
        $("#targetStart").textContent = "Joacă din nou";
      }
    }, 1000);
  };

  currentCleanup = () => {
    clearInterval(interval);
    clearInterval(spawn);
  };
}

function startMemory() {
  const colors = [
    { name: "ROȘU", color: "#b93434" },
    { name: "ALBASTRU", color: "#287ac4" },
    { name: "VERDE", color: "#24934c" },
    { name: "AURIU", color: "#d4a629" }
  ];

  let sequence = [];
  let position = 0;
  let round = 0;
  let locked = false;
  let token = 0;

  showModal("🧠 Memory Master", `
    <p>Memorează ordinea culorilor și repet-o!</p>
    <h3 id="memoryRound" style="color:#f5c542;margin:15px">Runda 1</h3>
    <p id="memoryMessage">Apasă start pentru a începe.</p>
    <div id="memoryColors" style="display:grid;grid-template-columns:1fr 1fr;gap:10px;margin:20px 0">
      ${colors.map((c, i) => `
        <button data-color="${i}" style="height:75px;border:0;border-radius:8px;background:${c.color};color:white;font-weight:bold">${c.name}</button>
      `).join("")}
    </div>
    <button class="btn" id="memoryStart">START</button>
  `);

  const buttons = $$("#memoryColors button");

  function nextRound() {
    round++;
    sequence.push(Math.floor(Math.random() * 4));
    position = 0;
    locked = true;
    const thisToken = ++token;
    $("#memoryRound").textContent = "Runda " + round;
    $("#memoryMessage").textContent = "Memorează secvența...";

    let i = 0;
    function flashNext() {
      if (thisToken !== token) return;
      if (i >= sequence.length) {
        buttons.forEach(b => b.style.opacity = "1");
        $("#memoryMessage").textContent = "Acum repetă secvența!";
        locked = false;
        return;
      }

      const b = buttons[sequence[i]];
      b.style.filter = "brightness(1.8)";
      setTimeout(() => {
        if (thisToken !== token) return;
        b.style.filter = "";
        i++;
        setTimeout(flashNext, 250);
      }, 450);
    }

    flashNext();
  }

  buttons.forEach(b => {
    b.onclick = () => {
      if (locked || !sequence.length) return;
      const choice = Number(b.dataset.color);

      if (choice !== sequence[position]) {
        locked = true;
        $("#memoryMessage").textContent =
          "Joc terminat! Ai ajuns la runda " + round + ". Încearcă din nou!";
        $("#memoryStart").disabled = false;
        $("#memoryStart").textContent = "Joacă din nou";
        return;
      }

      position++;
      if (position === sequence.length) {
        locked = true;
        $("#memoryMessage").textContent = "Corect! Urmează runda următoare...";
        setTimeout(nextRound, 800);
      }
    };
  });

  $("#memoryStart").onclick = () => {
    token++;
    sequence = [];
    round = 0;
    position = 0;
    locked = true;
    $("#memoryStart").disabled = true;
    nextRound();
  };

  currentCleanup = () => { token++; };
}

const games = {
  reaction: startReaction,
  clicker: startClicker,
  number: startNumber,
  rush: startRush,
  memory: startMemory,
  target: startTarget
};

$$(".play-btn[data-game]").forEach(button => {
  button.addEventListener("click", () => {
    const game = games[button.dataset.game];
    if (game) game();
  });
});
</script>

</body>
</html>
