<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8" />
  <title>Papatyalar Açıyor</title>
  <style>
    body {
      margin: 0;
      background-color: #000;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      flex-direction: column;
      font-family: "Segoe UI", sans-serif;
    }

    #touchButton {
      padding: 12px 28px;
      font-size: 18px;
      border: none;
      border-radius: 20px;
      background-color: #fff;
      color: #333;
      cursor: pointer;
      transition: 0.3s;
      z-index: 2;
      box-shadow: 0 0 10px #fff4;
    }

    #touchButton:hover {
      background-color: #f4f4f4;
    }

    .scene {
      position: relative;
      width: 400px;
      height: 400px;
    }

    svg {
      width: 100%;
      height: 100%;
    }

    .flower {
      transform-origin: center;
      opacity: 0;
      transform: scale(0.5);
      transition: all 1s ease;
    }

    .flower.show {
      opacity: 1;
      transform: scale(1);
    }
  </style>
</head>
<body>
  <button id="touchButton">🌼 Dokun</button>

  <div class="scene">
    <svg viewBox="0 0 200 200">
      <!-- Gövde -->
      <line x1="100" y1="200" x2="100" y2="120" stroke="#654321" stroke-width="6" stroke-linecap="round" />

      <!-- Dallar -->
      <line x1="100" y1="140" x2="60" y2="100" stroke="#654321" stroke-width="3" stroke-linecap="round" />
      <line x1="100" y1="130" x2="140" y2="90" stroke="#654321" stroke-width="3" stroke-linecap="round" />
      <line x1="100" y1="120" x2="100" y2="70" stroke="#654321" stroke-width="2" />

      <!-- Papatyalar -->
      <g class="flower" id="f1">
        <circle cx="60" cy="100" r="8" fill="white" />
        <circle cx="60" cy="100" r="3" fill="yellow" />
      </g>
      <g class="flower" id="f2">
        <circle cx="140" cy="90" r="8" fill="white" />
        <circle cx="140" cy="90" r="3" fill="yellow" />
      </g>
      <g class="flower" id="f3">
        <circle cx="100" cy="70" r="8" fill="white" />
        <circle cx="100" cy="70" r="3" fill="yellow" />
      </g>
    </svg>
  </div>

  <script>
    const button = document.getElementById("touchButton");
    const flowers = document.querySelectorAll(".flower");

    button.addEventListener("click", () => {
      button.style.display = "none";

      flowers.forEach((flower, index) => {
        setTimeout(() => {
          flower.classList.add("show");
        }, index * 600);
      });
    });
  </script>
</body>
</html>

