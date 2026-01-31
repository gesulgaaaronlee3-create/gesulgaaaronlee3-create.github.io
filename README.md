<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Valentine Page</title>

<style>
body {
  margin: 0;
  padding: 0;
  font-family: Arial, sans-serif;
  text-align: center;
  background: linear-gradient(120deg, #ff758c, #ff7eb3);
  color: white;
  overflow: hidden;
}

.container {
  margin-top: 60px;
}

.teddy {
  font-size: 90px;
  animation: bounce 1.5s infinite;
}

@keyframes bounce {
  0% { transform: translateY(0); }
  50% { transform: translateY(-15px); }
  100% { transform: translateY(0); }
}

button {
  background: white;
  color: #ff4d6d;
  border: none;
  padding: 12px 20px;
  border-radius: 25px;
  font-size: 16px;
  cursor: pointer;
  margin: 10px;
  position: relative;
}

button:hover {
  background: #ffe6eb;
}

#message {
  font-size: 20px;
  margin-top: 20px;
  display: none;
}
</style>
</head>

<body>

<div class="container">
  <div class="teddy">🧸</div>
  <h1>Happy Valentine's Day 💖</h1>
  <p>Can I go with you on Valentine's Day?</p>

  <button onclick="yesClicked()">Yes 😊</button>
  <button id="noBtn">No 😆</button>

  <p id="message">Yay! I'm excited for Valentine's Day! 🧸💗</p>
</div>

<!-- Background Music -->
<audio id="bgMusic" loop>
  <source src="tiktok_music_7517596256533826824 (1).mp3" type="audio/mpeg">
</audio>

<script>
let yesPressed = false;
const noBtn = document.getElementById("noBtn");
const music = document.getElementById("bgMusic");

function yesClicked() {
  yesPressed = true;
  document.getElementById("message").style.display = "block";
  music.play(); // 🎵 Music plays instantly
  noBtn.style.position = "static";
}

// No button moves away
noBtn.addEventListener("mouseover", () => {
  if (!yesPressed) {
    const x = Math.random() * (window.innerWidth - 100);
    const y = Math.random() * (window.innerHeight - 50);

    noBtn.style.position = "absolute";
    noBtn.style.left = x + "px";
    noBtn.style.top = y + "px";
  }
});
</script>

</body>
</html>
