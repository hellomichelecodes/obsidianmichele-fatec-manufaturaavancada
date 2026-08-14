<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Simulador da Lei de Ohm</title>
  <style>
    :root {
      --bg-color: #121212;
      --card-bg: #1e1e1e;
      --accent: #3b82f6;
      --text: #ffffff;
      --subtext: #a0a0a0;
    }
    body {
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
      background-color: var(--bg-color);
      color: var(--text);
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
      margin: 0;
      padding: 20px;
      box-sizing: border-box;
    }
    .container {
      background-color: var(--card-bg);
      border-radius: 12px;
      padding: 24px;
      width: 100%;
      max-width: 650px;
      box-shadow: 0 10px 25px rgba(0,0,0,0.5);
    }
    h2 {
      margin-top: 0;
      font-size: 1.5rem;
      text-align: center;
    }
    .circuit-box {
      width: 100%;
      height: 220px;
      background: #0a0a0a;
      border-radius: 8px;
      margin: 20px 0;
      position: relative;
    }
    svg {
      width: 100%;
      height: 100%;
    }
    .metrics {
      display: flex;
      justify-content: space-around;
      margin-bottom: 20px;
      padding: 12px;
      background: rgba(255, 255, 255, 0.05);
      border-radius: 8px;
    }
    .metric {
      text-align: center;
    }
    .metric-label {
      font-size: 0.8rem;
      color: var(--subtext);
      margin-bottom: 4px;
    }
    .metric-val {
      font-size: 1.3rem;
      font-weight: bold;
      color: #60a5fa;
    }
    .control-group {
      display: flex;
      flex-direction: column;
      gap: 16px;
    }
    .control-row {
      display: flex;
      align-items: center;
      gap: 12px;
    }
    .control-row label {
      width: 120px;
      font-size: 0.9rem;
    }
    input[type="range"] {
      flex: 1;
      accent-color: var(--accent);
    }
    input[type="number"] {
      width: 70px;
      padding: 6px;
      border-radius: 6px;
      border: 1px solid #333;
      background: #2a2a2a;
      color: white;
      text-align: center;
    }
  </style>
</head>
<body>

<div class="container">
  <h2>Simulador da Lei de Ohm</h2>

  <div class="circuit-box">
    <svg viewBox="0 0 500 200">
      <!-- Fios do Circuito -->
      <path d="M 100 100 L 100 40 L 400 40 L 400 100 L 400 160 L 100 160 Z" fill="none" stroke="#4b5563" stroke-width="4" />
      
      <!-- Fonte de Tensão (Esquerda) -->
      <circle cx="100" cy="100" r="22" fill="#1e1e1e" stroke="#ffffff" stroke-width="3"/>
      <text x="100" y="96" fill="white" font-size="14" text-anchor="middle" font-weight="bold">+</text>
      <text x="100" y="112" fill="white" font-size="14" text-anchor="middle" font-weight="bold">-</text>
      <text x="60" y="105" fill="#a0a0a0" font-size="12" text-anchor="middle">Fonte</text>

      <!-- Resistência (Direita) -->
      <path d="M 400 70 L 400 80 L 412 85 L 388 95 L 412 105 L 388 115 L 412 125 L 388 135 L 400 140 L 400 150" fill="none" stroke="#ffffff" stroke-width="3" />
      <text x="440" y="105" fill="#a0a0a0" font-size="12" text-anchor="start" id="resistor-text">Resistência</text>

      <!-- Texto Central (Fórmula) -->
      <text x="250" y="95" fill="#ffffff" font-size="20" text-anchor="middle" font-weight="bold">V = I × R</text>
      <text x="250" y="120" fill="#a0a0a0" font-size="12" text-anchor="middle">Lei de Ohm</text>

      <!-- Indicador da Corrente -->
      <g id="current-badge">
        <rect x="200" y="25" width="100" height="24" rx="12" fill="#2563eb" />
        <text x="250" y="41" fill="white" font-size="11" text-anchor="middle" font-weight="bold" id="current-badge-text">I = 0.00 A</text>
      </g>
    </svg>
  </div>

  <div class="metrics">
    <div class="metric">
      <div class="metric-label">CORRENTE (I)</div>
      <div class="metric-val" id="val-i">0.00 A</div>
    </div>
    <div class="metric">
      <div class="metric-label">POTÊNCIA (P)</div>
      <div class="metric-val" id="val-p">0.00 W</div>
    </div>
  </div>

  <div class="control-group">
    <div class="control-row">
      <label for="slider-v">Tensão (V):</label>
      <input type="range" id="slider-v" min="0" max="240" value="12">
      <input type="number" id="num-v" min="0" max="240" value="12">
    </div>

    <div class="control-row">
      <label for="slider-r">Resistência (&Omega;):</label>
      <input type="range" id="slider-r" min="1" max="1000" value="556">
      <input type="number" id="num-r" min="1" max="1000" value="556">
    </div>
  </div>
</div>

<script>
  const sliderV = document.getElementById('slider-v');
  const numV = document.getElementById('num-v');
  const sliderR = document.getElementById('slider-r');
  const numR = document.getElementById('num-r');

  const valI = document.getElementById('val-i');
  const valP = document.getElementById('val-p');
  const currentBadgeText = document.getElementById('current-badge-text');
  const resistorText = document.getElementById('resistor-text');

  function update() {
    const v = parseFloat(sliderV.value);
    const r = parseFloat(sliderR.value);

    const i = r > 0 ? v / r : 0;
    const p = v * i;

    valI.innerText = i.toFixed(2) + ' A';
    valP.innerText = p.toFixed(2) + ' W';
    currentBadgeText.innerText = 'I = ' + i.toFixed(2) + ' A';
    resistorText.innerText = r + ' Ω';
  }

  sliderV.addEventListener('input', (e) => { numV.value = e.target.value; update(); });
  numV.addEventListener('input', (e) => { sliderV.value = e.target.value; update(); });
  sliderR.addEventListener('input', (e) => { numR.value = e.target.value; update(); });
  numR.addEventListener('input', (e) => { sliderR.value = e.target.value; update(); });

  update();
</script>

</body>
</html>