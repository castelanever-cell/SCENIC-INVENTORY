<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SCENIC</title>

    <style>
        /* ESTILOS PARA EL VIDEO DE FONDO */
        #video-fondo {
            position: fixed;
            right: 0;
            bottom: 0;
            min-width: 100%;
            min-height: 100%;
            width: auto;
            height: auto;
            z-index: -100;
            background-size: cover;
        }

        /* ESTILOS GENERALES Y POSICIONAMIENTO DEL CONTENIDO */
        body {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            text-align: center;
        }

        /* CONTENEDOR DE TITULOS (EL CUADRO) */
        .titulo-container {
            padding: 20px;
            border: 2px solid #0624e4;
            background-color: rgba(2, 206, 36, 0.538);
            border-radius: 10px;
            margin-bottom: 20px;
        }
        
        .titulo-container h1, .titulo-container p {
            color: #f2eded;
            text-shadow: none;
        }
        
        .titulo-container h1 {
            font-size: xxx-large;
            margin: 0;
        }

        .titulo-container p {
            font-size: x-large;
            margin: 0;
        }

        /* ESTILOS PARA LOS BOTONES */
        .btn-container {
            display: flex;
            gap: 20px;
            justify-content: center;
            margin-top: 20px;
        }

        .btn-appsheet {
            display: inline-block;
            padding: 10px 20px;
            background-color: #007bff;
            color: white;
            text-decoration: none;
            border-radius: 5px;
            font-family: Arial, sans-serif;
            cursor: pointer;
        }
        
        .btn-appsheet:hover {
            background-color: #05a818;
        }

        /* ESTILOS PARA EL FORMULARIO DE INICIO DE SESIÓN */
        .login-form {
            position: absolute;
            display: none; /* Oculto por defecto */
            flex-direction: column;
            gap: 10px;
            padding: 20px;
            background-color: rgba(255, 255, 255, 0.9);
            border: 1px solid #ccc;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0,0,0,0.2);
            z-index: 200;
        }
        .login-form input {
            padding: 8px;
            border-radius: 4px;
            border: 1px solid #ccc;
        }
        .login-form button {
            padding: 10px;
            background-color: #007bff;
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }
        .login-form button:hover {
            background-color: #0056b3;
        }
    </style>
</head>
<body>

    <video autoplay muted loop id="video-fondo">
        <source src="C:\Users\everardo.castelan\Videos\Grabaciones de pantalla\Grabación de pantalla 2025-08-20 162515.mp4" type="video/mp4">
        Tu navegador no soporta el video de fondo.
    </video>

    <div class="titulo-container">
        <h1>INSPIRE SCENIC</h1>
        <p>WAREHOUSE INVENTORY</p>
    </div>

    <div class="btn-container">
        <button onclick="mostrarFormulario('Scenic1')" class="btn-appsheet">INVENTORY SCENIC 1</button>
        
        <button onclick="mostrarFormulario('Scenic2')" class="btn-appsheet">INVENTORY SCENIC 2</button>
    </div>

    <div class="login-form" id="loginForm">
        <input type="text" id="username" placeholder="Usuario">
        <input type="password" id="password" placeholder="Contraseña">
        <button id="submitBtn">Entrar</button>
    </div>

    <script>
        const credenciales = {
            'Scenic1': { 
                usuario: 'everardo.castelan', 
                contrasena: 'Mexico$2025',
                url: 'https://www.appsheet.com/start/89399593-dd40-42be-a0d5-431645d0912a' 
            },
            'Scenic2': { 
                usuario: 'everardo.castelan', 
                contrasena: 'Mexico$2025',
                url: 'https://www.appsheet.com/start/ed7c6cee-0845-4d94-8b49-f3ea3944fdea' 
            }
        };

        let botonActivo = ''; // Variable para saber qué botón se presionó

        function mostrarFormulario(botonId) {
            document.getElementById('loginForm').style.display = 'flex';
            botonActivo = botonId;
        }

        document.getElementById('submitBtn').addEventListener('click', () => {
            const usuarioInput = document.getElementById('username').value;
            const contrasenaInput = document.getElementById('password').value;

            const credencialesBoton = credenciales[botonActivo];

            if (usuarioInput === credencialesBoton.usuario && contrasenaInput === credencialesBoton.contrasena) {
                window.location.href = credencialesBoton.url;
            } else {
                alert('Usuario o contraseña incorrectos.');
            }
        });
    </script>
</body>
</html>
