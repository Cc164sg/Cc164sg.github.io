# Cc164sg.github.io
 title:ILOVEU
 <!DOCTYPE html>
 <html lang="es"> 
<head>
  <meta charset="UTF-8">
  <title>Feliz 28 ❤️</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Arial', sans-serif;
    }
    body {
      height: 100vh;
      background: linear-gradient(180deg, #ff9a9e, #fad0c4);
      overflow: hidden;
      display: flex;
      align-items: center;
      justify-content: center;
    }
 h1 {
      position: absolute;
      color: white;
      font-size: 3em;
      text-align: center;
      text-shadow: 0 0 10px rgba(0,0,0,0.3);
      z-index: 10;
      animation: latido 1.5s infinite;
    }
  @keyframes latido {
      0% { transform: scale(1); }
      50% { transform: scale(1.1); }
      100% { transform: scale(1); }
    }
    .heart {
      position: absolute;
      color: rgba(255, 0, 100, 0.8);
      font-size: 20px;
      animation: flotar linear infinite;
    }
@keyframes flotar {
      0% {
        transform: translateY(100vh) scale(1);
        opacity: 1;
      }
      100% {
        transform: translateY(-10vh) scale(1.5);
        opacity: 0;
      }
    }
  </style>
</head> 
  <body>

  <h1>Feliz 28 <br> ti amo ❤️</h1>

  <script>
    const corazones = ["❤️","💖","💕","💘","💗","💓"];

    function crearCorazon() {
      const heart = document.createElement("div");
      heart.classList.add("heart");
      heart.innerHTML = corazones[Math.floor(Math.random() * corazones.length)];

      heart.style.left = Math.random() * 100 + "vw";
      heart.style.fontSize = Math.random() * 30 + 15 + "px";
      heart.style.animationDuration = Math.random() * 3 + 3 + "s";
      
      document.body.appendChild(heart);

      setTimeout(() => {
        heart.remove();
      }, 6000);
    }

    setInterval(crearCorazon, 150);
  </script>

</body>
</html>
