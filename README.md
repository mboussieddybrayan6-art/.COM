<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Compte à rebours - Anniversaire</title>

  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: Arial, sans-serif;
    }

    body {
      min-height: 200vh; /* IMPORTANT pour permettre le scroll */
      display: flex;
      justify-content: center;
      align-items: center;
      background: linear-gradient(135deg, #0f172a, #1e293b, #334155);
      color: white;
      overflow-x: hidden;
    }

    .container {
      text-align: center;
      padding: 30px;
      border-radius: 25px;
      background: rgba(255, 255, 255, 0.08);
      backdrop-filter: blur(10px);
      box-shadow: 0 8px 30px rgba(0,0,0,0.3);
      width: 90%;
      max-width: 800px;
      position: relative;
      z-index: 2;
    }

    h1 {
      font-size: 3rem;
      margin-bottom: 10px;
      color: #facc15;
    }

    p {
      margin-bottom: 30px;
      font-size: 1.2rem;
      color: #e2e8f0;
    }

    .countdown {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
      gap: 20px;
    }

    .box {
      background: rgba(255,255,255,0.12);
      padding: 25px 15px;
      border-radius: 20px;
    }

    .number {
      font-size: 3rem;
      font-weight: bold;
      color: #38bdf8;
    }

    .label {
      margin-top: 10px;
      font-size: 1rem;
      color: #cbd5e1;
      text-transform: uppercase;
    }

    /* BOUTON PRINCIPAL */
    .btn-meb {
      margin-top: 25px;
      background: black;
      color: white;
      padding: 15px 25px;
      border: none;
      font-size: 18px;
      cursor: pointer;
      border-radius: 30px;
      display: inline-flex;
      align-items: center;
      gap: 10px;
    }

    .arrow {
      transition: transform 0.3s ease;
    }

    .btn-meb:hover .arrow {
      transform: translateX(8px);
    }

    .img-anniv {
      width: 100%;
      max-width: 350px;
      margin-top: 20px;
      border-radius: 15px;
    }

    /* OVERLAY */
    #overlay {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(0,0,0,0.92);
      display: none;
      justify-content: center;
      align-items: center;
      flex-direction: column;
      z-index: 10;
      text-align: center;
    }

    #overlay h2 {
      font-size: 2.5rem;
      color: #facc15;
    }

    #overlay h3 {
      margin-top: 20px;
      font-size: 2rem;
      color: #4ade80;
    }

    .back-btn {
      margin-top: 30px;
      background: red;
      color: white;
      border: none;
      padding: 12px 25px;
      border-radius: 20px;
      cursor: pointer;
    }

    /* 🔥 FLÈCHES SCROLL */
    .scroll-btn {
      position: fixed;
      right: 20px;
      width: 50px;
      height: 50px;
      border-radius: 50%;
      border: none;
      cursor: pointer;
      font-size: 22px;
      background: white;
      color: black;
      box-shadow: 0 5px 15px rgba(0,0,0,0.3);
      z-index: 999;
      transition: 0.3s;
    }

    .scroll-btn:hover {
      transform: scale(1.1);
    }

    #upBtn {
      bottom: 90px;
    }

    #downBtn {
      bottom: 20px;
    }

  </style>
</head>

<body>

<!-- FLÈCHES -->
<button class="scroll-btn" id="upBtn" onclick="scrollToTop()">⬆</button>
<button class="scroll-btn" id="downBtn" onclick="scrollToBottom()">⬇</button>

<div class="container">

  <h1>🎉 Anniversaire de MBOUSSI EDDY BRAYAN 🎂</h1>
  <p>Compte à rebours jusqu'au 23 Juin 2026</p>

  <div class="countdown">
    <div class="box">
      <div class="number" id="days">0</div>
      <div class="label">Jours</div>
    </div>

    <div class="box">
      <div class="number" id="hours">0</div>
      <div class="label">Heures</div>
    </div>

    <div class="box">
      <div class="number" id="minutes">0</div>
      <div class="label">Minutes</div>
    </div>

    <div class="box">
      <div class="number" id="seconds">0</div>
      <div class="label">Secondes</div>
    </div>
  </div>

  <button class="btn-meb" onclick="openMagic()">
    Découvrir MEB <span class="arrow">→</span>
  </button>

  <img src="IMG_20260512_135012_862(1)(1).jpg" class="img-anniv">

</div>

<!-- OVERLAY -->
<div id="overlay">
  <h2>✨ ANNIVERSAIRE ✨</h2>
  <h3>🎆 23 JUIN 2026 🎆</h3>
  <button class="back-btn" onclick="closeMagic()">⬅ Retour</button>
</div>

<script>

function scrollToTop() {
  window.scrollTo({ top: 0, behavior: "smooth" });
}

function scrollToBottom() {
  window.scrollTo({ top: document.body.scrollHeight, behavior: "smooth" });
}

/* COMPTE À REBOURS */
const targetDate = new Date("June 23, 2026 00:00:00").getTime();

setInterval(() => {
  const now = new Date().getTime();
  const distance = targetDate - now;

  document.getElementById("days").innerText =
    Math.floor(distance / (1000 * 60 * 60 * 24));

  document.getElementById("hours").innerText =
    Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));

  document.getElementById("minutes").innerText =
    Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));

  document.getElementById("seconds").innerText =
    Math.floor((distance % (1000 * 60)) / 1000);

}, 1000);

/* OUVERTURE */
function openMagic() {
  document.getElementById("overlay").style.display = "flex";
}

/* RETOUR */
function closeMagic() {
  document.getElementById("overlay").style.display = "none";
}

</script>

</body>
</html>
