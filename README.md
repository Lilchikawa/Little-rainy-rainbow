<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Little Rainy Rainbow 🌈</title>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  overflow: hidden;
  font-family: monospace;
  background: #c9dafa;
}

.scene {
  position: relative;
  width: 100%;
  height: 100vh;
  min-height: 480px;
  overflow: hidden;
  background: linear-gradient(
    to bottom,
    #a9c8f3 0%,
    #c5d7f6 45%,
    #ead8f5 100%
  );
  image-rendering: pixelated;
}

/* Sun glow */
.sun {
  position: absolute;
  top: 12%;
  right: 18%;
  width: 55px;
  height: 55px;
  background: #fff1b9;
  box-shadow: 0 0 30px #fff0bd;
  animation: glow 3s infinite alternate;
}

@keyframes glow {
  to { box-shadow: 0 0 55px #fff3c9; }
}

/* Rainbow */
.rainbow {
  position: absolute;
  width: 300px;
  height: 150px;
  top: 25%;
  left: 50%;
  transform: translateX(-50%);
  border-radius: 170px 170px 0 0;
  background: linear-gradient(
    to bottom,
    #ff9da9 0%,
    #ffbd91 16%,
    #ffe49b 32%,
    #c4e8a7 48%,
    #a9d9ee 64%,
    #c5b2ef 80%,
    #f2b9dd 100%
  );
  -webkit-mask: radial-gradient(
    ellipse at bottom,
    transparent 0 48%,
    black 49%
  );
  mask: radial-gradient(
    ellipse at bottom,
    transparent 0 48%,
    black 49%
  );
  animation: rainbowFloat 4s ease-in-out infinite;
}

@keyframes rainbowFloat {
  0%,100% { margin-top: 0; }
  50% { margin-top: -9px; }
}

/* Clouds */
.cloud {
  position: absolute;
  width: 100px;
  height: 30px;
  background: #fff9ff;
  box-shadow:
    0 -18px 0 -3px #fff9ff,
    22px -29px 0 -5px #fff9ff,
    45px -15px 0 0 #fff9ff,
    65px 0 0 -4px #fff9ff;
  image-rendering: pixelated;
  animation: cloudMove 8s ease-in-out infinite alternate;
}

.cloud.one {
  top: 18%;
  left: 7%;
}

.cloud.two {
  top: 34%;
  right: 8%;
  transform: scale(0.8);
  animation-delay: -3s;
}

@keyframes cloudMove {
  from { translate: -8px 0; }
  to { translate: 15px 0; }
}

/* Rain */
.rain {
  position: absolute;
  inset: 0;
  pointer-events: none;
}

.drop {
  position: absolute;
  top: -20px;
  width: 3px;
  height: 13px;
  background: #eff7ff;
  opacity: 0.8;
  animation: rainfall linear infinite;
}

@keyframes rainfall {
  to { transform: translateY(110vh); }
}

/* Ground */
.ground {
  position: absolute;
  bottom: 0;
  width: 100%;
  height: 23%;
  background: #a6c995;
  border-top: 8px solid #c4dfad;
}

.grass {
  position: absolute;
  bottom: 22%;
  width: 100%;
  height: 18px;
  background: repeating-linear-gradient(
    90deg,
    #a6c995 0 10px,
    #c4dba8 10px 17px,
    #b4d39d 17px 25px
  );
}

/* Flowers */
.flower {
  position: absolute;
  bottom: 22%;
  font-size: 24px;
  animation: flowerDance 2s ease-in-out infinite alternate;
}

.flower:nth-child(2) { animation-delay: .5s; }

@keyframes flowerDance {
  from { transform: rotate(-8deg); }
  to { transform: rotate(8deg); }
}

/* Sparkles */
.sparkle {
  position: absolute;
  color: #fff9d9;
  font-size: 19px;
  animation: twinkle 2s infinite alternate;
}

@keyframes twinkle {
  from { opacity: .2; transform: scale(.7); }
  to { opacity: 1; transform: scale(1.3); }
}

/* Text */
.message {
  position: absolute;
  top: 57%;
  width: 100%;
  text-align: center;
  color: #fffaff;
  text-shadow: 2px 2px #c2a9da;
  letter-spacing: 2px;
  line-height: 2;
  z-index: 5;
}

.message h1 {
  font-size: clamp(19px, 4vw, 30px);
}

.message p {
  font-size: 11px;
  margin-top: 8px;
}

/* Pixel stars */
.star {
  position: absolute;
  color: white;
  animation: twinkle 1.5s infinite alternate;
}

/* Footer */
.footer {
  position: absolute;
  bottom: 5%;
  width: 100%;
  text-align: center;
  color: #fff;
  font-size: 10px;
  letter-spacing: 2px;
  z-index: 5;
}

@media(max-width: 500px) {
  .rainbow {
    width: 240px;
    height: 120px;
    top: 27%;
  }

  .message {
    top: 58%;
  }

  .cloud.two {
    right: -15px;
  }
}
</style>
</head>

<body>

<div class="scene">

  <div class="sun"></div>

  <div class="rainbow"></div>

  <div class="cloud one"></div>
  <div class="cloud two"></div>

  <div class="rain" id="rain"></div>

  <div class="sparkle" style="top:20%;left:30%">✦</div>
  <div class="sparkle" style="top:32%;right:25%">✧</div>
  <div class="sparkle" style="top:48%;left:15%">✦</div>
  <div class="sparkle" style="top:15%;right:35%">✧</div>
  <div class="sparkle" style="top:46%;right:12%">✦</div>

  <div class="message">
    <h1>Little Rainy Rainbow ♡</h1>
    <p>Somewhere over the little rainbow...</p>
    <p>☁️ a little rain, a little magic ☁️</p>
  </div>

  <div class="ground"></div>
  <div class="grass"></div>

  <div class="flower" style="left:12%">🌷</div>
  <div class="flower" style="left:30%">🌼</div>
  <div class="flower" style="right:25%">🌸</div>
  <div class="flower" style="right:8%">🌷</div>

  <div class="footer">
    MADE WITH LOVE ♡
  </div>

</div>

<script>
const rain = document.getElementById("rain");

for (let i = 0; i < 65; i++) {
  const drop = document.createElement("div");
  drop.className = "drop";

  drop.style.left = Math.random() * 100 + "%";
  drop.style.animationDuration =
    (0.7 + Math.random() * 1.2) + "s";
  drop.style.animationDelay =
    (-Math.random() * 3) + "s";
  drop.style.opacity = 0.3 + Math.random() * 0.6;

  rain.appendChild(drop);
}
</script>

</body>
</html>
