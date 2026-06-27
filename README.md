<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dashboard ESP32 - Monitoreo</title>
    <style>
        body { font-family: sans-serif; text-align: center; padding: 20px; }
        .card { border: 1px solid #ccc; padding: 20px; border-radius: 10px; display: inline-block; }
        .valor { font-size: 3em; color: #007bff; }
    </style>
</head>
<body>

    <h1>Monitoreo en Tiempo Real</h1>
    
    <div class="card">
        <h3>Temperatura Actual</h3>
        <div id="temp" class="valor">-- °C</div>
    </div>

    <script type="module">
        import { initializeApp } from "https://www.gstatic.com/firebasejs/10.7.1/firebase-app.js";
        import { getDatabase, ref, onValue } from "https://www.gstatic.com/firebasejs/10.7.1/firebase-database.js";

        // CONFIGURACIÓN (Copia esto de tu consola de Firebase)
        const firebaseConfig = {
            apiKey: "AIzaSyA0PtuzyRFtumwsl7XVZIAMBEuBiT5ijnY",
            authDomain: "proyecto-redes-8d766.firebaseapp.com",
            databaseURL: "https://proyecto-redes-8d766-default-rtdb.firebaseio.com/",
            projectId: "proyecto-redes-8d766",
            storageBucket: "proyecto-redes-8d766.appspot.com",
            messagingSenderId: "TU_ID_MENSAJERO", 
            appId: "TU_ID_APP"
        };

        // Inicializar
        const app = initializeApp(firebaseConfig);
        const db = getDatabase(app);

        // Referencias a tus rutas de Firebase
        const tempRef = ref(db, 'sensores/temperatura');

        // Escuchar datos
        onValue(tempRef, (snapshot) => {
            const data = snapshot.val();
            document.getElementById("temp").innerText = data ? data.toFixed(1) + " °C" : "-- °C";
        });
    </script>
</body>
</html>
