<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Una Pregunta Especial</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      background: linear-gradient(135deg, #ffe4e1, #ffc0cb);
      font-family: 'Arial', sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      overflow: hidden;
      position: relative;
      color: #d63384;
    }

    h2, p {
      color: #d63384;
    }

    .carta, .pantalla-llanto, .pantalla-final, .pantalla-sorpresa, .pantalla-rapto {
      background: white;
      padding: 25px;
      border-radius: 20px;
      box-shadow: 0px 8px 20px rgba(0, 0, 0, 0.25);
      text-align: center;
      position: relative;
      z-index: 2;
    }

    .gato {
      width: 100px;
      animation: mover 1.5s infinite alternate;
    }

    @keyframes mover {
      from { transform: translateY(0); }
      to { transform: translateY(-10px); }
    }

    .boton {
      background-color: #ff69b4;
      color: white;
      border: none;
      padding: 12px 24px;
      font-size: 16px;
      cursor: pointer;
      border-radius: 12px;
      margin: 10px;
      transition: transform 0.2s;
    }

    .boton:hover {
      transform: scale(1.05);
    }

    .pantalla-llanto,
    .pantalla-final,
    .pantalla-sorpresa,
    .pantalla-rapto {
      display: none;
      flex-direction: column;
      align-items: center;
      justify-content: center;
    }

    .botones-llanto {
      display: flex;
      gap: 20px;
      justify-content: center;
      margin-top: 20px;
    }

    .gato-triste, .gato-feliz {
      width: 250px;
      margin-top: 20px;
      border-radius: 10px;
    }

    .enunciado-triste {
      font-size: 20px;
      font-weight: bold;
      margin-top: 10px;
    }

    .url-box {
      margin-top: 15px;
    }

    .url-input {
      padding: 8px;
      width: 250px;
      border-radius: 8px;
      border: 1px solid #ccc;
      text-align: center;
    }

    /* Corazones flotando */
    .corazon {
      position: absolute;
      width: 20px;
      height: 20px;
      background-color: #ff69b4;
      clip-path: polygon(50% 0%, 100% 35%, 75% 100%, 50% 80%, 25% 100%, 0% 35%);
      animation: flotar 8s infinite ease-in;
      opacity: 0.6;
    }

    @keyframes flotar {
      0% {
        transform: translateY(100vh) scale(0.5);
        opacity: 0;
      }
      50% {
        opacity: 0.9;
      }
      100% {
        transform: translateY(-10vh) scale(1);
        opacity: 0;
      }
    }
  </style>
</head>
<body>

  <!-- Corazones flotando -->
  <script>
    for (let i = 0; i < 30; i++) {
      const heart = document.createElement('div');
      heart.className = 'corazon';
      heart.style.left = Math.random() * 100 + 'vw';
      heart.style.animationDuration = 5 + Math.random() * 5 + 's';
      heart.style.animationDelay = Math.random() * 5 + 's';
      document.body.appendChild(heart);
    }
  </script>

  <!-- Pantalla Principal -->
  <div class="carta" id="pregunta">
    <h2>Hola novitaaa🦝❤️</h2>
    <p>¿Quieres vivir conmigo?, JAJA, te haré comerrr</p>
    <img src="https://media.giphy.com/media/JIX9t2j0ZTN9S/giphy.gif" class="gato" alt="Gatito animado">
    <div>
      <button class="boton" onclick="aceptar()">Sí</button>
      <button class="boton" onclick="mostrarTriste()">No</button>
    </div>
  </div>

  <!-- Pantalla del Gatito Muy Triste -->
  <div class="pantalla-llanto" id="triste">
    <p class="enunciado-triste">¿Estás segura?</p>
    <img src="https://media1.tenor.com/m/Nqf3-gUgySsAAAAd/cat-sad-gato-triste.gif" class="gato-triste" alt="Gatito muy triste llorando">
    <div class="botones-llanto">
      <button class="boton" onclick="mostrarRapto()">Sí</button>
      <button class="boton" onclick="mostrarSorpresa()">No</button>
    </div>
  </div>

  <!-- Pantalla de Rapto -->
  <div class="pantalla-rapto" id="rapto">
    <h2>muejejejeje, igual te raptaré 😼💘</h2>
    <img src="https://media1.tenor.com/m/Humb097A6d4AAAAC/cat-kidnapped.gif" class="gato-feliz" alt="Gatito malvado tierno">
  </div>

  <!-- Pantalla Sorpresa -->
  <div class="pantalla-sorpresa" id="sorpresa">
    <h2>Genial, yo sabía que ibas a querer :3</h2>
    <img src="https://media.giphy.com/media/MDJ9IbxxvDUQM/giphy.gif" class="gato-feliz" alt="Gatito feliz saltando">
    <div class="url-box">
      <p>Copiá mi URL para guardarlo o compartirlo 💌:</p>
      <input class="url-input" type="text" readonly value="https://tupaginaespecial.com/quieres-vivir-conmigo" onclick="this.select()">
    </div>
  </div>

  <!-- Pantalla Final -->
  <div class="pantalla-final" id="final">
    <h2>¡Genial! Nos vemos en julio♥, te empacharé :3</h2>
    <img src="https://media.giphy.com/media/MDJ9IbxxvDUQM/giphy.gif" class="gato-feliz" alt="Gatito feliz saltando">
  </div>

  <script>
    function aceptar() {
      ocultarTodas();
      document.getElementById("final").style.display = "flex";
    }

    function mostrarTriste() {
      ocultarTodas();
      document.getElementById("triste").style.display = "flex";
    }

    function mostrarSorpresa() {
      ocultarTodas();
      document.getElementById("sorpresa").style.display = "flex";
    }

    function mostrarRapto() {
      ocultarTodas();
      document.getElementById("rapto").style.display = "flex";
    }

    function ocultarTodas() {
      document.getElementById("pregunta").style.display = "none";
      document.getElementById("triste").style.display = "none";
      document.getElementById("sorpresa").style.display = "none";
      document.getElementById("rapto").style.display = "none";
      document.getElementById("final").style.display = "none";
    }
  </script>

</body>
</html>

</html>
