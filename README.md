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
