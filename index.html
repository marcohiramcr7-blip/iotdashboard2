<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <title>Dashboard IoT ESP32</title>
    <style>
        .led { width: 50px; height: 50px; border-radius: 50%; display: inline-block; background: gray; }
        .active-azul { background: blue; }
        .active-verde { background: green; }
        .active-amarillo { background: yellow; }
    </style>
</head>
<body>
    <h1>Monitor Ambiental</h1>
    <p>Temperatura: <span id="temp">--</span> °C</p>
    
    <div>
        <div id="ledAzul" class="led"></div>
        <div id="ledVerde" class="led"></div>
        <div id="ledAmarillo" class="led"></div>
    </div>

    <br>
    <button onclick="toggleBuzzer()">Activar/Desactivar Buzzer Manual</button>

    <script type="module">
        import { initializeApp } from "https://www.gstatic.com/firebasejs/9.22.0/firebase-app.js";
        import { getDatabase, ref, onValue, set } from "https://www.gstatic.com/firebasejs/9.22.0/firebase-database.js";

        const firebaseConfig = { databaseURL: "https://proyecto-redes-8d766-default-rtdb.firebaseio.com/" };
        const db = getDatabase(initializeApp(firebaseConfig));

        // Escuchar datos
        onValue(ref(db, 'sensores/temperatura'), (s) => document.getElementById('temp').innerText = s.val());
        
        onValue(ref(db, 'estado/ledAzul'), (s) => document.getElementById('ledAzul').className = s.val() ? 'led active-azul' : 'led');
        // ... repite para los otros leds
        
        window.toggleBuzzer = () => {
            const dbRef = ref(db, 'control/buzzerWeb');
            onValue(dbRef, (s) => {
                set(dbRef, !s.val());
            }, {onlyOnce: true});
        };
    </script>
</body>
</html>
