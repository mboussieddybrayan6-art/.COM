 {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: Arial, sans-serif;
    }

    html {
      scroll-behavior: smooth; /* 🔥 scroll fluide */
    }

    body {
      background: linear-gradient(135deg, #0f172a, #1e293b, #334155);
      color: white;
      min-height: 100vh;
    }

    /* 🔥 ANIMATION STYLE NETFLIX */
    section {
      opacity: 0;
      transform: translateY(40px);
      transition: all 0.9s ease;
    }

    section.show {
      opacity: 1;
      transform: translateY(0);
    }

    .container {
      text-align: center;
      padding: 30px;
      margin: 60px auto;
      width: 90%;
      max-width: 850px;
      border-radius: 25px;
      background: rgba(255,255,255,0.08);
      backdrop-filter: blur(10px);
      box-shadow: 0 10px 35px rgba(0,0,0,0.4);
    }

    h1 {
      font-size: 3rem;
      color: #facc15;
      margin-bottom: 10px;
    }

    p {
      font-size: 1.2rem;
      color: #e2e8f0;
      margin-bottom: 20px;
    }

    img {
      width: 100%;
      max-width: 650px;
      border-radius: 20px;
      margin: 20px 0;
      box-shadow: 0 10px 30px rgba(0,0,0,0.3);
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
      transition: 0.3s;
    }

    .box:hover {
      transform: scale(1.05);
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
    }

    .message {
      margin-top: 30px;
      font-size: 2rem;
      color: #4ade80;
      display: none;
      animation: pop 1s infinite alternate;
    }

    @keyframes pop {
      from { transform: scale(1); }
      to { transform: scale(1.08); }
    }

    .footer {
      margin-top: 40px;
      font-size: 0.9rem;
      color: #94a3b8;
    }
  </style>
</head>

<body>

<!-- SECTION 1 -->
<section>
  <div class="container">

    <h1>🎉 Anniversaire de MBOUSSI EDDY BRAYAN 🎂</h1>
    <p>Compte à rebours jusqu'au 23 Juin 2026</p>

    <img src="IMG_20260512_135012_862.jpg" alt="photo anniversaire">

    <div class="countdown">
      <div class="box">
        <div id="days" class="number">0</div>
        <div class="label">Jours</div>
      </div>

      <div class="box">
        <div id="hours" class="number">0</div>
        <div class="label">Heures</div>
      </div>

      <div class="box">
        <div id="minutes" class="number">0</div>
        <div class="label">Minutes</div>
      </div>

      <div class="box">
        <div id="seconds" class="number">0</div>
        <div class="label">Secondes</div>
      </div>
    </div>

    <div id="message" class="message">
      🎊 Joyeux Anniversaire Brayan ! 🎊
    </div>

    <div class="footer">
      Créé avec style pour ton anniversaire ❤️
    </div>

  </div>
</section>

<script>
  // ⏳ COUNTDOWN
  const targetDate = new Date("June 23, 2026 00:00:00").getTime();

  const countdown = setInterval(() => {
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

    if (distance < 0) {
      clearInterval(countdown);
      document.querySelector(".countdown").style.display = "none";
      document.getElementById("message").style.display = "block";
    }
  }, 1000);

  // 🎬 ANIMATION SCROLL NETFLIX
  const sections = document.querySelectorAll("section");

  const observer = new IntersectionObserver(entries => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add("show");
      }
    });
  }, { threshold: 0.2 });

  sections.forEach(sec => observer.observe(sec));
</script>

</body>
</html>
