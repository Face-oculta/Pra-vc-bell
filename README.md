<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no"/>
  <title>Pra vc, Bell</title>
  <link href="https://fonts.googleapis.com/css2?family=Pacifico&family=Quicksand:wght@400;600&display=swap" rel="stylesheet"/>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    :root {
      --font-base: clamp(1rem, 2.5vw, 1.5rem);
      --font-title: clamp(2rem, 5vw, 3rem);
      --font-final: clamp(1.5rem, 4vw, 2rem);
    }

    html, body {
      height: 100%;
      width: 100%;
      overflow-x: hidden;
    }

    body {
      font-family: 'Quicksand', sans-serif;
      color: #000000;
      position: relative;
    }

    /* Fundo fixo via pseudo-elemento */
    body::before {
      content: "";
      position: fixed;
      top: 0;
      left: 0;
      width: 100vw;
      height: 100vh;
      background: url('https://i.postimg.cc/j53Ds1jq/Olhos-intensos-e-Hello-Kitty.png') no-repeat center center;
      background-size: cover;
      z-index: -2;
    }

    .overlay-bg {
      position: fixed;
      top: 0;
      left: 0;
      width: 100vw;
      height: 100vh;
      background-color: rgba(255, 255, 255, 0.4);
      z-index: -1;
    }

    .container {
      width: 100%;
      max-width: 700px;
      padding: 30px 20px;
      margin: 0 auto;
      border-radius: 16px;
      position: relative;
      z-index: 2;
      animation: fadeIn 1s ease;
    }

    h1 {
      font-family: 'Pacifico', cursive;
      font-size: var(--font-title);
      color: #d6336c;
      margin-top: 60px;
      animation: bounce 1.5s infinite alternate;
    }

    p {
      font-size: var(--font-base);
      line-height: 1.7;
      margin-bottom: 20px;
      color: #000000;
    }

    .final {
      font-weight: bold;
      font-size: var(--font-final);
      margin-top: 30px;
    }

    .buttons {
      margin-top: 30px;
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 10px;
    }

    button {
      padding: 12px 24px;
      font-size: var(--font-base);
      background-color: #ff99bb;
      border: none;
      border-radius: 10px;
      color: white;
      cursor: pointer;
      transition: 0.3s;
    }

    button:hover {
      background-color: #ff77a9;
    }

    .message-final {
      font-size: 2rem;
      color: #ff4081;
      font-weight: bold;
      margin-top: 20px;
      animation: pulse 1.5s infinite;
      display: flex;
      justify-content: center;
      align-items: center;
      text-align: center;
      flex-direction: column;
      min-height: 200px;
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(20px); }
      to { opacity: 1; transform: translateY(0); }
    }

    @keyframes pulse {
      0% { transform: scale(1); }
      50% { transform: scale(1.05); }
      100% { transform: scale(1); }
    }

    .heart {
      position: absolute;
      font-size: 48px;
      color: red;
      animation: floatHeart 4s linear forwards;
    }

    @keyframes floatHeart {
      0% { transform: translateY(0); opacity: 1; }
      100% { transform: translateY(-150px); opacity: 0; }
    }

    #main-content, #response, #closing-message {
      display: none;
    }

    #closing-message {
      opacity: 0;
      transition: opacity 3s ease-in-out;
      z-index: 12;
      text-align: center;
      font-size: 2rem;
    }

    #light-overlay {
      position: fixed;
      inset: 0;
      width: 100vw;
      height: 100vh;
      background: white;
      opacity: 0;
      pointer-events: none;
      transition: opacity 8s ease-in-out;
      z-index: 10;
    }

    @media (max-width: 600px) {
      h1 { font-size: 2rem; }
      .final, .message-final { font-size: 1.5rem; }
      .buttons { flex-direction: column; }
    }
  </style>
</head>
<body>
  <div class="overlay-bg" id="text-background"></div>

  <div class="container" id="intro">
    <h1>Abre isso com carinho...</h1>
    <div class="open-btn">
      <button onclick="openHeart()">Abrir o coração de Gidelson</button>
    </div>
  </div>

  <div class="container" id="main-content">
    <p>Bell,</p>
    <p>Desde que você chegou, meu mundo ganhou um novo significado. As cores parecem mais vivas, os dias mais leves, e cada momento se tornou precioso.</p>
    <p>Você tem um brilho que é só seu, uma luz tão intensa que ilumina até os cantos mais escuros da minha alma. Seu sorriso é como um sol radiante, capaz de transformar qualquer dia nublado em um céu azul infinito.</p>
    <p><strong>Eu amo sua voz, seu cabelo, e esse seu jeitinho tão único... bruta e fofa ao mesmo tempo kkkkk.</strong></p>
    <p>Cada batida do meu coração sussurra seu nome, como se ele soubesse desde sempre que foi feito pra te amar. Você é a melodia mais doce da minha vida, meu porto seguro, minha paz em meio ao caos.</p>
    <p>Com você, dá vontade de lutar, os desafios se tornam mais fáceis, os sonhos mais possíveis e a felicidade ainda maior. Quero dividir risadas, te apoiar nos momentos difíceis, ser seu porto seguro e multiplicar momentos inesquecíveis.</p>
    <p>Se pudesse, eu te daria o universo inteiro. Mas como não posso, entrego o que tenho de mais puro e verdadeiro: meu coração. 💖</p>
    <p class="final">Bell meu amor... você aceita namorar comigo? 🥹💗</p>
    <div class="buttons">
      <button onclick="showResponse()">Sim, eu aceito!</button>
      <button onclick="showResponse()">Claro, amor!</button>
    </div>
  </div>

  <div class="container" id="response">
    <div class="message-final">
      <span>Meu coração tá transbordando de felicidade!</span>
      <span>Esse meu amor por você só me faz querer viver momentos lindos ao seu lado.</span>
    </div>
  </div>

  <div class="container" id="closing-message">
    <p>A mágica do pedido chegou ao fim,</p>
    <p>mas nossa história mágica acaba de começar. ✨💖</p>
  </div>

  <div id="light-overlay"></div>

  <audio id="bg-music" src="https://cdn.pixabay.com/download/audio/2023/01/05/audio_735dfb77d4.mp3" autoplay loop></audio>

  <script>
    function openHeart() {
      document.getElementById("intro").style.display = "none";
      document.getElementById("main-content").style.display = "block";
      document.getElementById("text-background").style.display = "block";
    }

    function showResponse() {
      document.getElementById("main-content").style.display = "none";
      document.getElementById("text-background").style.display = "none";
      document.getElementById("response").style.display = "block";
      createHearts();

      setTimeout(() => {
        document.getElementById("response").style.display = "none";
      }, 12000);

      setTimeout(() => {
        document.getElementById("light-overlay").style.opacity = "1";
      }, 8000);

      setTimeout(() => {
        document.getElementById("closing-message").style.display = "block";
        document.getElementById("closing-message").style.opacity = "1";
      }, 16000);

      setTimeout(() => {
        window.close();
      }, 24000);
    }

    function createHearts() {
      const heartInterval = setInterval(() => {
        const heart = document.createElement("div");
        heart.classList.add("heart");
        heart.innerHTML = "❤️";
        heart.style.left = Math.random() * 100 + "vw";
        heart.style.top = Math.random() * 100 + "vh";
        document.body.appendChild(heart);

        setTimeout(() => {
          heart.remove();
        }, 4000);
      }, 300);

      setTimeout(() => {
        clearInterval(heartInterval);
      }, 12000);
    }
  </script>
</body>
</html>
