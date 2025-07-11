<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Clicker Game</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      background-color: #f7f7f7;
    }
    h1 {
      color: #333;
    }
    #counter {
      font-size: 3rem;
      margin: 20px;
    }
    button {
      padding: 1rem 2rem;
      font-size: 1.2rem;
      border: none;
      border-radius: 10px;
      background-color: #4CAF50;
      color: white;
      cursor: pointer;
      margin: 10px;
      transition: background-color 0.3s;
    }
    button:hover {
      background-color: #45a049;
    }
    #shop {
      margin-top: 30px;
    }
    #shop button {
      background-color: #2196F3;
    }
    #shop button:hover {
      background-color: #1976D2;
    }
    footer {
      margin-top: 30px;
      font-size: 0.9rem;
      color: #888;
    }
  </style>
</head>
<body>
  <h1>Clicker Game</h1>
  <div id="counter">0</div>
  <button id="clickButton">+1</button>

  <div id="shop">
    <h2>Tienda</h2>
    <button id="buyX2">Comprar x2 Clicks (2000 clics)</button>
  </div>

  <footer>Cosa para un server de DC</footer>

  <script>
    let count = parseInt(localStorage.getItem('clickCount')) || 0;
    let multiplier = parseInt(localStorage.getItem('clickMultiplier')) || 1;
    let x2Bought = localStorage.getItem('x2Bought') === 'true';

    const counter = document.getElementById('counter');
    const clickButton = document.getElementById('clickButton');
    const buyX2 = document.getElementById('buyX2');

    function updateDisplay() {
      counter.textContent = count;
      if (x2Bought) {
        buyX2.disabled = true;
        buyX2.textContent = 'x2 Comprado ✅';
      }
    }

    clickButton.addEventListener('click', () => {
      count += multiplier;
      localStorage.setItem('clickCount', count);
      updateDisplay();
    });

    buyX2.addEventListener('click', () => {
      if (count >= 2000 && !x2Bought) {
        count -= 2000;
        multiplier = 2;
        x2Bought = true;
        localStorage.setItem('clickCount', count);
        localStorage.setItem('clickMultiplier', multiplier);
        localStorage.setItem('x2Bought', true);
        updateDisplay();
      }
    });

    updateDisplay();
  </script>
</body>
</html>


