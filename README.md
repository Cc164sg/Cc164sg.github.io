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
    background: radial-gradient(circle, #ff758c, #ff7eb3);
    overflow: hidden;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
  }
  h1 {
    position: absolute;
    color: white;
    font-size: 3.2em;
    text-align: center;
    text-shadow: 0 0 15px rgba(0,0,0,0.4);
    animation: latido 1.4s infinite;
    z-index: 10;
  }

  @keyframes latido {
    0% { transform: scale(1); }
    50% { transform: scale(1.12); }
    100% { transform: scale(1); }
  }

  .heart {
    position: absolute;
    font-size: 20px;
    animation: flotar linear infinite;
    pointer-events: none;
  }

  @keyframes flotar {
    0% {
      transform: translateY(100vh) scale(1);
      opacity: 1;
    }
    100% {
      transform: translateY(-10vh) scale(1.6);
      opacity: 0;
    }
  }

  .mensaje {
    position: absolute;
    color: white;
    font-size: 1.4em;
    background: rgba(0,0,0,0.25);
    padding: 12px 18px;
    border-radius: 20px;
    animation: aparecer 2.5s forwards;
    pointer-events: none;
  }

  @keyframes aparecer {
    0% { opacity: 0; transform: scale(0.6); }
    20% { opacity: 1; transform: scale(1); }
    100% { opacity: 0; transform: translateY(-40px); }
  }

  .contador {
    position: fixed;
    bottom: 20px;
    right: 25px;
    color: white;
    font-size: 1em;
    opacity: 0.8;
  }
</style>
</head>

<body>

<h1>Feliz 28,<br>te amo ❤️</h1>
<div class="contador">Clicks de amor: <span id="count">0</span></div>

<script>
  const corazones = ["❤️","💖","💕","💘","💗","💓","💞"];
  const frases = [
    "Te amo más de lo que sé decir",
    "Siempre vos",
    "Mi lugar seguro",
    "Elegirte es fácil",
    "Sos mi casualidad favorita",
    "Con vos, todo",
    "Mi hogar sos vos",
    "Te amo hoy y siempre",
    "Mis ojitos favoritos"
  ];

  let contador = 0;

  function crearCorazon() {
    const heart = document.createElement("div");
    heart.className = "heart";
    heart.innerHTML = corazones[Math.floor(Math.random() * corazones.length)];

    heart.style.left = Math.random() * 100 + "vw";
    heart.style.fontSize = Math.random() * 30 + 15 + "px";
    heart.style.animationDuration = Math.random() * 3 + 3 + "s";

    document.body.appendChild(heart);

    setTimeout(() => heart.remove(), 6000);
  }

  setInterval(crearCorazon, 120);

  document.body.addEventListener("click", (e) => {
    contador++;
    document.getElementById("count").textContent = contador;

    const msg = document.createElement("div");
    msg.className = "mensaje";
    msg.textContent = frases[Math.floor(Math.random() * frases.length)];

    msg.style.left = e.clientX + "px";
    msg.style.top = e.clientY + "px";

    document.body.appendChild(msg);

    setTimeout(() => msg.remove(), 2500);
  });
</script>

</body>
</html>
