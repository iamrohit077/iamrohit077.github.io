<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>My Forever Puku ❤️</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
body {
    margin: 0;
    padding: 0;
    background: radial-gradient(circle at top, #1a001a, #000000);
    font-family: 'Segoe UI', sans-serif;
    overflow-x: hidden;
    color: white;
    text-align: center;
}

/* Stars */
.stars {
    position: fixed;
    width: 100%;
    height: 100%;
    z-index: 0;
}
.star {
    position: absolute;
    width: 2px;
    height: 2px;
    background: white;
    animation: twinkle 2s infinite alternate;
}
@keyframes twinkle {
    from { opacity: 0.2; }
    to { opacity: 1; }
}

/* Card */
.card {
    position: relative;
    z-index: 10;
    margin-top: 80px;
    background: rgba(255, 255, 255, 0.08);
    padding: 40px;
    border-radius: 20px;
    backdrop-filter: blur(10px);
    width: 90%;
    max-width: 700px;
    margin-left: auto;
    margin-right: auto;
    box-shadow: 0 0 30px rgba(255, 0, 100, 0.5);
}

h1 {
    font-size: 36px;
    color: #ff4da6;
}

/* Photos */
.photo-section { margin: 25px 0; }

.main-photo img,
.second-photo img {
    width: 100%;
    border-radius: 20px;
    max-width: 500px;
    transition: transform 0.5s ease;
}

/* Unique Auto Animations */
@keyframes floatPhoto {
    0% { transform: translateY(0) scale(1); }
    50% { transform: translateY(-14px) scale(1.04); }
    100% { transform: translateY(0) scale(1); }
}
@keyframes glowPulse {
    0% { box-shadow: 0 0 25px rgba(255,0,120,0.5); }
    50% { box-shadow: 0 0 50px rgba(255,0,180,0.9); }
    100% { box-shadow: 0 0 25px rgba(255,0,120,0.5); }
}
@keyframes kenBurns {
    from { transform: scale(1); }
    to { transform: scale(1.08); }
}

.main-photo img {
    animation: floatPhoto 6s ease-in-out infinite,
               glowPulse 4s infinite,
               kenBurns 14s alternate infinite;
}

.second-photo img {
    max-width: 260px;
    margin-top: 20px;
    animation: floatPhoto 7s ease-in-out infinite reverse,
               glowPulse 5s infinite;
}

/* Text */
.typewriter {
    font-size: 20px;
    margin-top: 20px;
    min-height: 80px;
}

button {
    padding: 12px 25px;
    border: none;
    background: linear-gradient(45deg, #ff0066, #ff4da6);
    color: white;
    font-size: 16px;
    border-radius: 25px;
    cursor: pointer;
    margin-top: 20px;
    transition: 0.4s;
}
button:hover { transform: scale(1.1); }

/* Popup */
.popup {
    display: none;
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    background: #1a001a;
    padding: 30px;
    border-radius: 20px;
    box-shadow: 0 0 40px #ff0066;
    z-index: 20;
    width: 90%;
    max-width: 600px;
}

.popup h2 {
    color: #ff4da6;
    font-size: 16px;
    line-height: 1.6;
}

.yes-btn { background: #ff0066; }
.no-btn { background: grey; position: relative; }

/* Hearts */
.heart {
    position: absolute;
    font-size: 20px;
    animation: float 6s linear infinite;
}
@keyframes float {
    from { transform: translateY(100vh); opacity: 1; }
    to { transform: translateY(-10vh); opacity: 0; }
}

/* Celebration */
.celebrate {
    position: fixed;
    font-size: 40px;
    animation: explode 1s ease-out forwards;
}
@keyframes explode {
    from { transform: scale(0); opacity: 1; }
    to { transform: scale(2); opacity: 0; }
}
</style>
</head>

<body>

<!-- Music -->
<audio id="bgMusic" loop>
  <source src="https://www.bensound.com/bensound-music/bensound-romantic.mp3" type="audio/mp3">
</audio>

<div class="stars" id="stars"></div>

<div class="card">
    <h1>My Forever Puku ❤️</h1>

    <div class="photo-section">
        <div class="main-photo">
            <img src="best.jpeg" alt="Memory">
        </div>
        <div class="second-photo">
            <img src="best2.jpeg" alt="Selfie">
        </div>
    </div>

    <div class="typewriter" id="typeText"></div>
    <button onclick="openProposal()">💍 Open My Heart 💍</button>
</div>

<div class="popup" id="proposalBox">
    <h2>
    I love you soo much mero puku ❤️<br><br>
    Hami dubai lai thaxa hami ek arka lai kati dherai maya garxam 🥰<br><br>
    Kaile misunderstanding hunxa tara at the end hami dubai lai ek arka chahinxa.<br><br>
    We are made for each other. I love you more than anything 😭❤️
    </h2>
    <button class="yes-btn" onclick="yesAnswer()">Forever Yes ❤️</button>
    <button class="no-btn" onmouseover="moveButton()">No 😅</button>
</div>

<script>
/* iOS Audio Fix */
document.body.addEventListener("click", () => {
    document.getElementById("bgMusic").play();
}, { once: true });

/* Typewriter */
const message = "In every universe, I would still choose you. You are my peace, my chaos, my forever.";
let i = 0;
function typeEffect() {
    if (i < message.length) {
        document.getElementById("typeText").innerHTML += message.charAt(i++);
        setTimeout(typeEffect, 50);
    }
}
typeEffect();

/* Proposal */
function openProposal() {
    document.getElementById("proposalBox").style.display = "block";
}

/* Yes Celebration */
function yesAnswer() {
    for (let i = 0; i < 30; i++) {
        const heart = document.createElement("div");
        heart.className = "celebrate";
        heart.innerHTML = "💖";
        heart.style.left = Math.random() * 100 + "vw";
        heart.style.top = Math.random() * 100 + "vh";
        document.body.appendChild(heart);
        setTimeout(() => heart.remove(), 1000);
    }
}

/* No Button Escape */
function moveButton() {
    const btn = document.querySelector(".no-btn");
    btn.style.left = Math.random() * 300 + "px";
    btn.style.top = Math.random() * 150 + "px";
}

/* Stars */
for (let i = 0; i < 120; i++) {
    const star = document.createElement("div");
    star.className = "star";
    star.style.left = Math.random() * 100 + "vw";
    star.style.top = Math.random() * 100 + "vh";
    document.getElementById("stars").appendChild(star);
}

/* Floating Hearts */
setInterval(() => {
    const heart = document.createElement("div");
    heart.className = "heart";
    heart.innerHTML = "❤️";
    heart.style.left = Math.random() * 100 + "vw";
    document.body.appendChild(heart);
    setTimeout(() => heart.remove(), 6000);
}, 500);

/* Device Tilt Effect */
if (window.DeviceOrientationEvent) {
    window.addEventListener("deviceorientation", e => {
        const x = e.gamma / 30;
        const y = e.beta / 30;
        document.querySelectorAll("img").forEach(img => {
            img.style.transform = `rotateY(${x}deg) rotateX(${y}deg) scale(1.05)`;
        });
    });
}
</script>

</body>
</html>
