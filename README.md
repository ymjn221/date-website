<!DOCTYPE html>
<html lang="mn">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Болзоонд явах уу?</title>
<style>
  body {
    font-family: Arial, sans-serif;
    text-align: center;
    margin: 0;
    padding: 0;
    overflow: hidden;
    background: #fff0f5;
    height: 100vh;
  }

  h1 {
    margin-top: 50px;
    font-size: 2em;
  }

  .buttons {
    margin-top: 30px;
  }

  button {
    font-size: 1.5em;
    padding: 10px 30px;
    margin: 10px;
    border-radius: 10px;
    border: none;
    cursor: pointer;
    transition: transform 0.2s;
  }

  button:hover {
    transform: scale(1.1);
  }

  #yesBtn {
    background-color: #ff69b4;
    color: white;
  }

  #noBtn {
    background-color: #aaa;
    color: white;
    position: absolute;
  }

  /* GIF */
  #gifContainer {
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    display: none;
    z-index: 10;
  }

  #gifContainer img {
    width: 300px;
    height: auto;
  }

  /* Зүрхний бороо */
  .heart {
    position: fixed;
    font-size: 24px;
    color: red;
    animation: fall linear;
    pointer-events: none;
    z-index: 5;
  }

  @keyframes fall {
    0% { top: -50px; opacity: 1; }
    100% { top: 100vh; opacity: 0; }
  }
</style>
</head>
<body>

<h1>Болзоонд явах уу?🥺💗</h1>
<div class="buttons">
  <button id="yesBtn">Тэгье🥰</button>
  <button id="noBtn">Үгүээ☹️</button>
</div>

<div id="gifContainer">
  <img src="https://gifdb.com/images/high/cartoon-cute-cats-heart-tails-rqtba0l0eal90og9.gif" alt="Cute GIF">
</div>

<script>
const yesBtn = document.getElementById('yesBtn');
const noBtn = document.getElementById('noBtn');
const gifContainer = document.getElementById('gifContainer');

yesBtn.addEventListener('click', () => {
    gifContainer.style.display = 'block';
    startHeartRain();
});

function startHeartRain() {
    setInterval(() => {
        const heart = document.createElement('div');
        heart.classList.add('heart');
        heart.textContent = '💖';
        heart.style.left = Math.random() * window.innerWidth + 'px';
        heart.style.animationDuration = 3 + Math.random() * 2 + 's';
        document.body.appendChild(heart);

        setTimeout(() => {
            heart.remove();
        }, 5000);
    }, 300);
}

// Үгүээ button зугтах
noBtn.addEventListener('mouseover', () => {
    const x = Math.random() * (window.innerWidth - noBtn.offsetWidth);
    const y = Math.random() * (window.innerHeight - noBtn.offsetHeight);
    noBtn.style.left = x + 'px';
    noBtn.style.top = y + 'px';
});
</script>

</body>
</html>
