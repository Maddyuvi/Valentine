# Valentine
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Be My Valentine 💖</title>

  <style>
    body {
      font-family: 'Arial', sans-serif;
      background: linear-gradient(to right, #ff758c, #ff7eb3);
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      text-align: center;
      color: white;
      overflow: hidden;
    }

    .container {
      background: rgba(255, 255, 255, 0.15);
      padding: 40px;
      border-radius: 20px;
      box-shadow: 0 10px 25px rgba(0,0,0,0.2);
      max-width: 400px;
      z-index: 2;
    }

    h1 {
      font-size: 2.3rem;
      margin-bottom: 15px;
    }

    p {
      font-size: 1.2rem;
      margin-bottom: 25px;
    }

    button {
      font-size: 1.1rem;
      padding: 12px 25px;
      border: none;
      border-radius: 30px;
      cursor: pointer;
      margin: 10px;
    }

    #yesBtn {
      background-color: #ff4d6d;
      color: white;
    }

    #noBtn {
      background-color: white;
      color: #ff4d6d;
      position: absolute;
    }

    .message {
      display: none;
      font-size: 1.4rem;
    }

    /* 💕 Floating Hearts */
    .heart {
      position: fixed;
      bottom: -20px;
      font-size: 24px;
      animation: floatUp 4s linear forwards;
      pointer-events: none;
    }

    @keyframes floatUp {
      0% {
        transform: translateY(0) scale(1);
        opacity: 1;
      }
      100% {
        transform: translateY(-100vh) scale(1.5);
        opacity: 0;
      }
    }
  </style>
</head>
<body>

  <!-- 🎵 Background Music -->
  <audio autoplay loop>
    <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" type="audio/mpeg">
  </audio>

  <!-- 💖 Proposal -->
  <div class="container" id="proposal">
    <h1>💖 My Love 💖</h1>
    <p>
      You make my days brighter and my heart happier 🌸<br><br>
      Will you be my Valentine? 💘
    </p>
    <button id="yesBtn">Yes 💕</button>
    <button id="noBtn">No 🙈</button>
  </div>

  <!-- 🎉 Success -->
  <div class="container message" id="success">
    <h1>🎉 Congratulations 🎉</h1>
    <p>
      You said YES 😍❤️<br><br>
      Happy Valentine’s Day, My Love 💐<br>
      Let’s make this love story unforgettable 🌹
    </p>
  </div>

  <script>
    const noBtn = document.getElementById("noBtn");
    const yesBtn = document.getElementById("yesBtn");
    const proposal = document.getElementById("proposal");
    const success = document.getElementById("success");

    // Move NO button
    noBtn.addEventListener("mouseover", () => {
      const x = Math.random() * (window.innerWidth - noBtn.offsetWidth);
      const y = Math.random() * (window.innerHeight - noBtn.offsetHeight);
      noBtn.style.left = `${x}px`;
      noBtn.style.top = `${y}px`;
    });

    // YES click
    yesBtn.addEventListener("click", () => {
      proposal.style.display = "none";
      success.style.display = "block";
      startHearts();
    });

    // 💕 Create floating hearts
    function startHearts() {
      setInterval(() => {
        const heart = document.createElement("div");
        heart.classList.add("heart");
        heart.innerHTML = "❤️";

        heart.style.left = Math.random() * 100 + "vw";
        heart.style.fontSize = Math.random() * 20 + 20 + "px";

        document.body.appendChild(heart);

        setTimeout(() => {
          heart.remove();
        }, 4000);
      }, 300);
    }
  </script>

</body>
</html>
