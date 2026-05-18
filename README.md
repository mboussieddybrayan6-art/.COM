<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>MEB Anniversaire</title>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: Arial;
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
  background: rgba(255,255,255,0.08);
  backdrop-filter: blur(10px);
  width: 90%;
  max-width: 800px;
  position: relative;
  z-index: 2;
}

h1 {
  color: #facc15;
}

/* bouton */
.btn-meb {
  margin-top: 20px;
  background: black;
  color: white;
  padding: 15px 25px;
  border: none;
  border-radius: 30px;
  cursor: pointer;
  font-size: 18px;
  transition: 0.3s;
}

.btn-meb:hover {
  background: white;
  color: black;
  transform: scale(1.05);
}

/* IMAGE */
img {
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

/* 🔙 BOUTON RETOUR */
.back-btn {
  margin-top: 30px;
  background: #ef4444;
  color: white;
  border: none;
  padding: 12px 25px;
  border-radius: 20px;
  cursor: pointer;
  font-size: 16px;
  transition: 0.3s;
}

.back-btn:hover {
  background: white;
  color: black;
}

/* FEUX D’ARTIFICE */
.particle {
  position: absolute;
  width: 6px;
  height: 6px;
  background: yellow;
  border-radius: 50%;
  animation: explode 1s ease-out forwards;
}

@keyframes explode {
  to {
    transform: translate(var(--x), var(--y));
    opacity: 0;
  }
}
</style>
</head>

<body>

<div class="container">

<h1>🎉 Anniversaire MEB 🎂</h1>

<button class="btn-meb" onclick="openMagic()">
  Découvrir MEB →
</button>

<img src="IMG_20260512_135012_862(1)(1).jpg">

</div>

<!-- OVERLAY -->
<div id="overlay">
  <h2>✨ ANNIVERSAIRE D'EDDY BRAYAN ✨</h2>
  <h3>🎆 23 JUIN 2026 🎆</h3>

  <!-- 🔙 BOUTON RETOUR -->
  <button class="back-btn" onclick="closeMagic()">⬅ Retour</button>
</div>

<script>

function openMagic() {
  document.getElementById("overlay").style.display = "flex";
  launchFireworks();
}

function closeMagic() {
  document.getElementById("overlay").style.display = "none";
}

/* FEUX D’ARTIFICE */
function launchFireworks() {
  for (let i = 0; i < 60; i++) {
    let p = document.createElement("div");
    p.className = "particle";
    document.body.appendChild(p);

    let x = (Math.random() - 0.5) * 800 + "px";
    let y = (Math.random() - 0.5) * 800 + "px";

    p.style.left = "50%";
    p.style.top = "50%";
    p.style.setProperty("--x", x);
    p.style.setProperty("--y", y);

    setTimeout(() => {
      p.remove();
    }, 1000);
  }
}

</script>

</body>
</html>
