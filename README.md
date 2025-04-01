<!DOCTYPE html><html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Una Pregunta Especial</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #ffe4e1;
            font-family: 'Arial', sans-serif;
            text-align: center;
        }
        .carta {
            background: white;
            padding: 20px;
            border-radius: 15px;
            box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.2);
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
            padding: 10px 20px;
            font-size: 16px;
            cursor: pointer;
            border-radius: 10px;
            margin-top: 20px;
        }
    </style>
</head>
<body>
    <div class="carta">
        <h2>Hola Sofiwis 🦝❤️</h2>
        <p>¿Quieres salir conmigo este fin de semana?</p>
        <img src="https://media.giphy.com/media/JIX9t2j0ZTN9S/giphy.gif" class="gato" alt="Gatito animado">
        <br>
        <button class="boton" onclick="aceptar()">Sí</button>
    </div><script>
    function aceptar() {
        alert("¡Genial! Nos vemos pronto ♥");
    }
</script>

</body>
</html>
