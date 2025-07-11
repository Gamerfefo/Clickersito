<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Simple Clicker Game</title>
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
      transition: background-color 0.3s;
    }
    button:hover {
      background-color: #45a049;
    }
    footer {
      margin-top: 30px;
      font-size: 0.9rem;
      color: #888;
    }
  </style>
</head>
<body>
  <h1>Juegito de xp</h1>
  <div id="counter">0</div>
  <button id="clickButton">+1</button>
  <footer> XDDDDD NO SE QUE ES ESTO ESTO ES PARA UN SERVER DE DISCORD XDDDD </footer>

  <script>
    let count = parseInt(localStorage.getItem('clickCount')) || 0;
    const counter = document.getElementById('counter');
    const button = document.getElementById('clickButton');

    counter.textContent = count;

    button.addEventListener('click', () => {
      count++;
      counter.textContent = count;
      localStorage.setItem('clickCount', count);
    });
  </script>
</body>
</html>
