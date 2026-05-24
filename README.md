<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>AuthentiQ - Sistema Protegido</title>
    <style>
        body {
            background-color: #050b14; /* Azul corporativo súper oscuro */
            color: #ffffff;
            font-family: 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
            text-align: center;
            padding: 20px;
            margin: 0;
            overflow-x: hidden;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
        }
        
        .shield-container {
            position: relative;
            width: 120px;
            height: 120px;
            margin: 0 auto 30px auto;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .pulse-ring {
            position: absolute;
            width: 100%;
            height: 100%;
            border-radius: 50%;
            box-shadow: 0 0 20px #00ff88;
            animation: pulse 2s infinite ease-out;
        }

        .shield-icon {
            font-size: 5rem;
            position: relative;
            z-index: 2;
            filter: drop-shadow(0 0 10px #00ff88);
        }

        @keyframes pulse {
            0% { transform: scale(0.8); opacity: 0.8; box-shadow: 0 0 0 0 rgba(0, 255, 136, 0.7); }
            100% { transform: scale(1.5); opacity: 0; box-shadow: 0 0 0 20px rgba(0, 255, 136, 0); }
        }

        h1 {
            font-size: 1.8rem;
            color: #00ff88;
            letter-spacing: 1px;
            margin-bottom: 5px;
        }

        .subtitle {
            color: #8ab4f8;
            font-size: 1rem;
            margin-bottom: 30px;
            text-transform: uppercase;
            letter-spacing: 2px;
        }

        .status-box {
            background: rgba(0, 255, 136, 0.05);
            border: 1px solid rgba(0, 255, 136, 0.3);
            border-radius: 12px;
            padding: 20px;
            width: 90%;
            max-width: 400px;
            text-align: left;
            margin-bottom: 30px;
        }

        .status-item {
            display: flex;
            justify-content: space-between;
            margin: 10px 0;
            font-size: 0.95rem;
            border-bottom: 1px solid rgba(255,255,255,0.1);
            padding-bottom: 8px;
        }

        .status-item:last-child {
            border-bottom: none;
            padding-bottom: 0;
        }

        .status-label { color: #a0aec0; }
        .status-value { color: #00ff88; font-weight: bold; }

        .btn {
            background: linear-gradient(90deg, #00C9FF 0%, #92FE9D 100%);
            color: #000;
            border: none;
            border-radius: 8px;
            padding: 16px 24px;
            font-size: 1.1rem;
            font-weight: bold;
            cursor: pointer;
            width: 90%;
            max-width: 400px;
            text-transform: uppercase;
            box-shadow: 0 4px 15px rgba(0, 255, 136, 0.3);
            transition: transform 0.2s;
        }

        .btn:active {
            transform: scale(0.98);
        }

        /* Efecto de escaneo inicial */
        #content-secure { display: none; }
        #content-scanning {
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        .spinner {
            border: 4px solid rgba(255,255,255,0.1);
            border-left-color: #00C9FF;
            border-radius: 50%;
            width: 50px;
            height: 50px;
            animation: spin 1s linear infinite;
            margin-bottom: 20px;
        }
        @keyframes spin { 0% { transform: rotate(0deg); } 100% { transform: rotate(360deg); } }
    </style>
</head>
<body>

    <div id="content-scanning">
        <div class="spinner"></div>
        <h2 style="color: #00C9FF; font-size: 1.2rem;">Motor de Inferencia Analizando...</h2>
        <p style="color: #a0aec0; font-size: 0.9rem;">Ejecutando heurística local</p>
    </div>

    <div id="content-secure">
        <div class="shield-container">
            <div class="pulse-ring"></div>
            <div class="shield-icon">🛡️</div>
        </div>

        <h1>ENTORNO SEGURO</h1>
        <div class="subtitle">Desplegado por AuthentiQ</div>

        <div class="status-box">
            <div class="status-item">
                <span class="status-label">Estado de Red</span>
                <span class="status-value">Encriptado (Local)</span>
            </div>
            <div class="status-item">
                <span class="status-label">Amenazas Neutralizadas</span>
                <span class="status-value">1 (Intento de Phishing)</span>
            </div>
            <div class="status-item">
                <span class="status-label">Soberanía de Datos</span>
                <span class="status-value">100% On-Premise</span>
            </div>
            <div class="status-item">
                <span class="status-label">Motor Forense</span>
                <span class="status-value">Gemma 3 Activo</span>
            </div>
        </div>

        <button class="btn" onclick="alert('Conexión corporativa establecida con éxito. Bienvenido al panel.')">CONTINUAR AL DASHBOARD</button>
    </div>

    <script>
        // Animación simple: Muestra el "escaneo" por 2.5 segundos y luego la pantalla verde
        setTimeout(() => {
            document.getElementById('content-scanning').style.display = 'none';
            document.getElementById('content-secure').style.display = 'block';
        }, 2500);
    </script>
</body>
</html>
