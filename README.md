<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Saniya ❤️ Valentine</title>

  <style>
    body {
      margin: 0;
      height: 100vh;
      overflow: hidden;
      display: flex;
      justify-content: center;
      align-items: center;
      background: linear-gradient(135deg, #ff9a9e, #fad0c4);
      font-family: 'Segoe UI', sans-serif;
    }

    .card {
      background: white;
      padding: 30px;
      border-radius: 20px;
      text-align: center;
      width: 90%;
      max-width: 360px;
      box-shadow: 0 10px 25px rgba(0,0,0,0.2);
      z-index: 10;
    }

    .emoji {
      font-size: 60px;
    }

    h2 {
      margin: 10px 0;
    }

    .buttons {
      margin-top: 20px;
      position: relative;
      height: 90px;
    }

    button {
      padding: 12px 24px;
      border: none;
      border-radius: 30px;
      font-size: 16px;
      cursor: pointer;
    }

    #yes {
      background: #ff4d6d;
      color: white;
    }

    #no {
      background: #ddd;
      position: absolute;
    }

    .yay {
      display: none;
      font-size: 22px;
      color: #ff4d6d;
      margin-top: 15px;
      font-weight: bold;
    }

    /* Heart animation */
    .heart {
      position: fixed;
      bottom: -20px;
      font-size: 20px;
      animation: floatUp 6s linear infinite;
      opacity: 0.8;
    }

    @keyframes floatUp {
      0% {
        transform: translateY(0) scale(1);
        opacity: 1;
      }
      100% {
        transform: translateY(-110vh) scale(1.8);
        opacity: 0;
      }
    }
  </style>
</head>

<body>

  <div class="card">
    <div class="emoji">💘</div>
    <h2>Saniya, will you be my Valentine?</h2>

    <div class="buttons">
      <button id="yes">Yes 💖</button>
      <button id="no">No 🙃</button>
    </div>

    <div class="yay" id="yay">
      YAY!!! 🎉💞<br>
      I knew it 😄❤️
    </div>
  </div>

  <!-- Music -->
  <audio id="music" loop>
    <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" type="audio/mpeg">
  </audio>

  <script>
    const noBtn = document.getElementById("no");
    const yesBtn = document.getElementById("yes");
    const yayText = document.getElementById("yay");
    const music = document.getElementById("music");

    function moveNoButton() {
      const x = Math.random() * 220 - 110;
      const y = Math.random() * 80 - 40;
      noBtn.style.transform = `translate(${x}px, ${y}px)`;
    }

    noBtn.addEventListener("mouseover", moveNoButton);
    noBtn.addEventListener("touchstart", moveNoButton);

    yesBtn.addEventListener("click", () => {
      yayText.style.display = "block";
      music.play();
      startHearts();
    });

    function startHearts() {
      setInterval(() => {
        const heart = document.createElement("div");
        heart.className = "heart";
        heart.innerText = "❤️";
        heart.style.left = Math.random() * 100 + "vw";
        heart.style.animationDuration = (Math.random() * 3 + 4) + "s";
        document.body.appendChild(heart);

        setTimeout(() => {
          heart.remove();
        }, 7000);
      }, 300);
    }
  </script>

</body>
</html>
