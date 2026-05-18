# .COM
ANNIVERSAIRE
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
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      background: linear-gradient(135deg, #0f172a, #1e293b, #334155);
      color: white;
      overflow: hidden;
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
      transition: 0.3s ease;
    }

    .box:hover {
      transform: translateY(-5px);
      background: rgba(255,255,255,0.18);
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
      letter-spacing: 1px;
    }

    .message {
      margin-top: 30px;
      font-size: 2rem;
      color: #4ade80;
      display: none;
      animation: pop 1s ease infinite alternate;
    }

    @keyframes pop {
      from {
        transform: scale(1);
      }
      to {
        transform: scale(1.08);
      }
    }

    .footer {
      margin-top: 25px;
      font-size: 0.95rem;
      color: #94a3b8;
    }
  </style>
</head>
<body>

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

    <div class="message" id="message">
      🎊 Joyeux Anniversaire Brayan ! 🎊
    </div>

    <div class="footer">
      Créé spécialement pour ton anniversaire ❤️
    </div>
  </div>

  <script>
    const targetDate = new Date("June 23, 2026 00:00:00").getTime();

    const countdown = setInterval(() => {
      const now = new Date().getTime();
      const distance = targetDate - now;

      const days = Math.floor(distance / (1000 * 60 * 60 * 24));
      const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
      const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
      const seconds = Math.floor((distance % (1000 * 60)) / 1000);

      document.getElementById("days").innerText = days;
      document.getElementById("hours").innerText = hours;
      document.getElementById("minutes").innerText = minutes;
      document.getElementById("seconds").innerText = seconds;

      if (distance < 0) {
        clearInterval(countdown);
        document.querySelector(".countdown").style.display = "none";
        document.getElementById("message").style.display = "block";
      }
    }, 1000);
  </script>

</body>
</html>

![image URL](IMG_20260512_135012_862.jpg)
