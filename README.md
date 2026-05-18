<meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Compte à rebours - Anniversaire</title>

  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: Arial, sans-serif;
    }

    html, body {
      height: auto;
      min-height: 100vh;
      overflow-y: auto;
      background: linear-gradient(135deg, #0f172a, #1e293b, #334155);
      color: white;
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
      margin: 50px auto;
    }

    h1 {
      font-size: 3rem;
      margin-bottom: 10px;
      color: #facc15;
    }

    p {
      margin-bottom: 20px;
      font-size: 1.2rem;
      color: #e2e8f0;
    }

    img {
      width: 100%;
      max-width: 600px;
      border-radius: 20px;
      margin: 20px 0;
    }

    .countdown {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
      gap: 20px;
      margin-top: 20px;
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

    .message {
      margin-top: 30px;
      font-size: 2rem;
      color: #4ade80;
      display: none;
    }
  </style>
</head>

<body>

  <div class="container">

    <h1>🎉 Anniversaire de MBOUSSI EDDY BRAYAN 🎂</h1>

    <p>Compte à rebours jusqu'au 23 Juin 2026</p>

    <!-- ✅ TON IMAGE BIEN PLACÉE ICI -->
    <img src="IMG_20260512_135012_862.jpg" alt="image anniversaire">

    <div class="countdown">
      <div class="box"><div id="days" class="number">0</div><div class="label">Jours</div></div>
      <div class="box"><div id="hours" class="number">0</div><div class="label">Heures</div></div>
      <div class="box"><div id="minutes" class="number">0</div><div class="label">Minutes</div></div>
      <div class="box"><div id="seconds" class="number">0</div><div class="label">Secondes</div></div>
    </div>

    <div id="message" class="message">
      🎊 Joyeux Anniversaire Brayan ! 🎊
    </div>

  </div>

  <script>
    const targetDate = new Date("June 23, 2026 00:00:00").getTime();

    const countdown = setInterval(() => {
      const now = new Date().getTime();
      const distance = targetDate - now;

      document.getElementById("days").innerText = Math.floor(distance / (1000 * 60 * 60 * 24));
      document.getElementById("hours").innerText = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
      document.getElementById("minutes").innerText = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
      document.getElementById("seconds").innerText = Math.floor((distance % (1000 * 60)) / 1000);

      if (distance < 0) {
        clearInterval(countdown);
        document.querySelector(".countdown").style.display = "none";
        document.getElementById("message").style.display = "block";
      }
    }, 1000);
  </script>

</body>
</html>
🔥 Résultat

✔ image visible
✔ scroll activé
✔ site propre GitHub Pages
✔ aucun code supprimé important
✔ structure corrigée

Si tu veux, prochaine étape je peux te faire :
✨ 
animation sur l’image (zoom lent)
✨ 
pluie de confettis au chargement
✨ 
site anniversaire encore plus pro (style Apple / Nike)
