# marriage-proposal
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Marriage Proposal to Kaniz</title>
  <style>
    body {
      font-family: 'Arial', sans-serif;
      background: linear-gradient(135deg, #ff9a9e 0%, #fad0c4 100%);
      color: #fff;
      text-align: center;
      margin: 0;
      padding: 0;
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      overflow: hidden;
    }

    .container {
      background: rgba(255, 255, 255, 0.2);
      padding: 30px;
      border-radius: 15px;
      box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
    }

    h1 {
      font-size: 2.5rem;
      margin-bottom: 20px;
    }

    .buttons {
      display: flex;
      justify-content: center;
      gap: 20px;
    }

    button {
      padding: 10px 20px;
      font-size: 1.2rem;
      border: none;
      border-radius: 10px;
      cursor: pointer;
      transition: transform 0.2s, background 0.3s;
    }

    #yesBtn {
      background: #4caf50;
      color: white;
    }

    #noBtn {
      background: #f44336;
      color: white;
    }

    button:hover {
      transform: scale(1.1);
    }

    .emoji {
      font-size: 2rem;
      position: absolute;
      top: -50px;
      animation: fall 5s linear infinite;
    }

    @keyframes fall {
      0% {
        transform: translateY(-100px);
      }
      100% {
        transform: translateY(100vh);
      }
    }

    .hidden {
      display: none;
    }

    .message {
      margin-top: 20px;
      font-size: 1.5rem;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>Kaniz, you are the love of my life. Will you make me the happiest man in the world?</h1>
    <div class="buttons">
      <button id="yesBtn">Yes</button>
      <button id="noBtn">No</button>
    </div>
    <div id="message" class="message hidden"></div>
  </div>

  <script>
    const yesBtn = document.getElementById('yesBtn');
    const noBtn = document.getElementById('noBtn');
    const message = document.getElementById('message');
    const container = document.querySelector('.container');

    yesBtn.addEventListener('click', () => {
      message.textContent = "💍💖 Yay! You've made me the happiest man in the world! 💖💍";
      message.classList.remove('hidden');
      container.style.background = 'rgba(76, 175, 80, 0.3)';
      createEmojis('💐', '❤️', '🌸');
    });

    noBtn.addEventListener('click', () => {
      message.textContent = "😢💔 My heart is broken... 💔😢";
      message.classList.remove('hidden');
      container.style.background = 'rgba(244, 67, 54, 0.3)';
      createEmojis('😢', '💔', '😭');
    });

    function createEmojis(...emojis) {
      for (let i = 0; i < 20; i++) {
        const emoji = document.createElement('div');
        emoji.classList.add('emoji');
        emoji.textContent = emojis[Math.floor(Math.random() * emojis.length)];
        emoji.style.left = `${Math.random() * 100}vw`;
        emoji.style.animationDuration = `${Math.random() * 3 + 2}s`;
        document.body.appendChild(emoji);
        setTimeout(() => {
          emoji.remove();
        }, 5000);
      }
    }
  </script>
</body>
</html>
