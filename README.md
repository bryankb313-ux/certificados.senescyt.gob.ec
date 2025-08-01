<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Portal SENESCYT</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f2f2f2;
      margin: 0;
      padding: 40px 0 0 0;
      display: flex;
      justify-content: center;
      align-items: flex-start;
    }

    .login-container {
      background-color: white;
      padding: 30px;
      width: 90%;
      max-width: 400px;
      border-radius: 8px;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
      text-align: center;
    }

    .login-container h2,
    .login-container h3 {
      color: #4b2970;
      margin-bottom: 5px;
    }

    .login-container h3 {
      font-weight: bold;
      margin-bottom: 20px;
    }

    .login-box {
      text-align: left;
      margin-bottom: 20px;
    }

    .login-box label {
      display: block;
      margin-bottom: 5px;
      font-weight: bold;
      color: #4b2970;
    }

    .login-box input[type="text"],
    .login-box input[type="password"] {
      width: 100%;
      padding: 8px;
      margin-bottom: 15px;
      border: 1px solid #ccc;
      border-radius: 4px;
      font-size: 14px;
    }

    .captcha-box {
      display: flex;
      align-items: center;
      margin-bottom: 15px;
    }

    .captcha-box input[type="checkbox"] {
      margin-right: 10px;
      cursor: pointer;
    }

    button {
      width: 100%;
      padding: 10px;
      background-color: #4b2970;
      color: white;
      border: none;
      border-radius: 4px;
      cursor: pointer;
      font-weight: 600;
      font-size: 16px;
    }

    button:hover {
      background-color: #371e56;
    }

    .info {
      background-color: #e6f0ff;
      padding: 10px;
      border: 1px solid #99c2ff;
      font-size: 13px;
      margin-top: 10px;
      text-align: left;
      border-radius: 4px;
    }

    a {
      display: block;
      margin-top: 15px;
      text-decoration: none;
      color: #4b2970;
      font-weight: bold;
    }

    .menu {
      background-color: #4b2970;
      color: white;
      padding: 20px;
      border-radius: 6px;
      margin-bottom: 20px;
      text-align: center;
    }

    .menu ul {
      list-style-type: none;
      padding: 0;
      margin: 10px 0 0 0;
    }

    .menu li {
      margin: 8px 0;
      cursor: pointer;
      font-weight: 600;
      font-size: 15px;
    }

    .contenido,
    .contenido-certificado {
      background-color: #ffffff;
      padding: 20px;
      border-radius: 6px;
      font-size: 14px;
      line-height: 1.5;
    }

    .aviso {
      background-color: #e0f0ff;
      padding: 15px;
      border-left: 5px solid #0099ff;
      margin-top: 15px;
      font-size: 13px;
    }

    table {
      width: 100%;
      border-collapse: collapse;
      margin: 20px 0;
    }

    th, td {
      border: 1px solid #ccc;
      padding: 10px;
      text-align: center;
      color: #4b2970;
    }

    .botones-certificado {
      margin-top: 20px;
      display: flex;
      gap: 10px;
      justify-content: center;
    }

    .botones-certificado button {
      padding: 10px 20px;
      background-color: #4b2970;
      border: none;
      color: white;
      border-radius: 5px;
      cursor: pointer;
    }
  </style>
</head>
<body>

  <!-- FORMULARIO DE INICIO DE SESIÓN -->
  <div class="login-container">
    <h2>Secretaría de Educación Superior,<br>Ciencia, Tecnología e Innovación</h2>
    <h3>EL NUEVO ECUADOR</h3>

    <div class="login-box">
      <label for="documento">Documento de identificación</label>
      <input type="text" id="documento" placeholder="Cédula, pasaporte, etc.">

      <label for="contrasena">Contraseña</label>
      <input type="password" id="contrasena" placeholder="Ingresa tu contraseña">

      <div class="captcha-box">
        <input type="checkbox" id="captcha">
        <label for="captcha">No soy un robot</label>
      </div>

      <button onclick="iniciarSesion()">Iniciar sesión</button>
    </div>

    <div class="info">
      <p>En el campo de documento de identificación ingresa el número de cédula, pasaporte o código internacional. Sin espacios ni separaciones.</p>
      <p>El código captcha es un método de autenticación que permite reconocer que una persona ingresa la información al sistema.</p>
    </div>

    <a href="#">🔙 Recordar mi contraseña</a>
  </div>

  <!-- BIENVENIDA -->
  <div id="bienvenida" style="display: none;">
    <div class="menu">
      <p>👤 La sesión expira en : 30 minutos</p>
      <h3>BRYAN ANTHONY CASTRO BALLADARES</h3>
      <ul>
        <li onclick="mostrarCertificadoPuntaje()">📝 Impresión puntaje de evaluación</li>
        <li onclick="mostrarCupoAceptado()">📄 Impresión cupo aceptado</li>
        <li onclick="mostrarRegistroNacional()">✅ Impresión confirmación del Registro Nacional</li>
        <li onclick="mostrarConfirmacionInscripcion()">🔁 Impresión confirmación de Inscripción</li>
      </ul>
      <button onclick="cerrarSesion()">🚪 Salir</button>
    </div>
    <div class="contenido">
      <h4 style="color: green;">Bienvenido/a: BRYAN ANTHONY CASTRO BALLADARES</h4>
      <p><strong>Bienvenido/a al sistema para impresión de:</strong></p>
      <ul>
        <li>Certificados de puntajes de evaluación y cupos aceptados</li>
        <li>Confirmación del Registro Nacional e Inscripción</li>
      </ul>
      <div class="aviso">
        <p><strong>ACUERDO DE RESPONSABILIDAD:</strong> El/la usuario/a conoce la responsabilidad del uso que dé a la información consultada en este portal.</p>
      </div>
    </div>
  </div>

  <!-- CERTIFICADO DE PUNTAJE -->
  <div id="certificado-puntaje" style="display: none;">
    <div class="menu">
      <p>👤 La sesión expira en : 22 minutos</p>
      <h3>BRYAN ANTHONY CASTRO BALLADARES</h3>
      <button onclick="cerrarSesion()">🚪 Salir</button>
    </div>
    <div class="contenido-certificado">
      <p>Quito, 01-08-2025</p>
      <p><strong>CERTIFICA</strong> que <strong>BRYAN ANTHONY CASTRO BALLADARES</strong> con cédula <strong>1805094404</strong> tiene el siguiente puntaje:</p>
      <table>
        <tr><th>PERIODO</th><th>PUNTAJE</th></tr>
        <tr><td>SEGUNDO PERIODO ACADÉMICO ORDINARIO 2022</td><td>787</td></tr>
      </table>
      <div class="botones-certificado">
        <button onclick="volverMenu()">🔙 Atrás</button>
        <button onclick="window.print()">🖨 Imprimir</button>
      </div>
    </div>
  </div>

  <!-- CUPOS ACEPTADOS -->
  <div id="cupo-aceptado" style="display: none;">
    <div class="menu">
      <p>👤 La sesión expira en : 22 minutos</p>
      <h3>BRYAN ANTHONY CASTRO BALLADARES</h3>
      <button onclick="cerrarSesion()">🚪 Salir</button>
    </div>
    <div class="contenido-certificado">
      <p>Quito, 01-08-2025</p>
      <p><strong>CERTIFICA</strong> que <strong>BRYAN ANTHONY CASTRO BALLADARES</strong> con cédula <strong>1805094404</strong> ha aceptado un cupo:</p>
      <table>
        <tr><th>PERIODO</th><th>INSTITUCIÓN</th><th>CARRERA</th></tr>
        <tr><td>SEGUNDO PERIODO ACADÉMICO ORDINARIO 2022</td><td>Universidad Técnica de Ambato</td><td>Ingeniería en Sistemas Computacionales</td></tr>
      </table>
      <div class="botones-certificado">
        <button onclick="volverMenuDesdeCupo()">🔙 Atrás</button>
        <button onclick="window.print()">🖨 Imprimir</button>
      </div>
    </div>
  </div>

  <!-- REGISTRO NACIONAL -->
  <div id="registro-nacional" style="display: none;">
    <div class="menu">
      <p>👤 La sesión expira en : 22 minutos</p>
      <h3>BRYAN ANTHONY CASTRO BALLADARES</h3>
      <button onclick="cerrarSesion()">🚪 Salir</button>
    </div>
    <div class="contenido-certificado">
      <p>Quito, 01-08-2025</p>
      <p><strong>CONFIRMA</strong> que <strong>BRYAN ANTHONY CASTRO BALLADARES</strong> con cédula <strong>1805094404</strong> completó el Registro Nacional.</p>
      <table>
        <tr><th>PERIODO</th><th>FECHA DE REGISTRO</th><th>ESTADO</th></tr>
        <tr><td>SEGUNDO PERIODO ACADÉMICO ORDINARIO 2022</td><td>15-08-2022</td><td>Registrado</td></tr>
      </table>
      <div class="botones-certificado">
        <button onclick="volverMenuDesdeRegistro()">🔙 Atrás</button>
        <button onclick="window.print()">🖨 Imprimir</button>
      </div>
    </div>
  </div>

  <!-- CONFIRMACIÓN DE INSCRIPCIÓN -->
  <div id="confirmacion-inscripcion" style="display: none;">
    <div class="menu">
      <p>👤 La sesión expira en : 22 minutos</p>
      <h3>BRYAN ANTHONY CASTRO BALLADARES</h3>
      <button onclick="cerrarSesion()">🚪 Salir</button>
    </div>
    <div class="contenido-certificado">
      <div style="background-color: #ffdddd; border-left: 5px solid red; padding: 15px; margin-bottom: 20px;">
        <strong style="color: red;">⚠️ No tienes ningún cupo asignado.</strong>
      </div>
      <p><strong>Bienvenido/a al sistema para impresión de:</strong></p>
      <ul>
        <li>Certificados de puntajes de evaluación y cupos aceptados en el Sistema Nacional de Nivelación y Admisión.</li>
        <li>Confirmación del Registro Nacional e Inscripción</li>
      </ul>
      <div style="background-color: #e6f0ff; border-left: 5px solid #007bff; padding: 15px; margin-top: 20px; font-size: 13px;">
        <strong>ACUERDO DE RESPONSABILIDAD:</strong> El/la usuario/a conoce la responsabilidad del uso que dé a la información consultada en este portal.
      </div>
      <div class="botones-certificado" style="margin-top: 20px;">
        <button onclick="volverMenuDesdeInscripcion()">🔙 Atrás</button>
        <button onclick="window.print()">🖨 Imprimir</button>
      </div>
    </div>
  </div>

  <script>
    const usuarioRegistrado = {
      cedula: "1805094404",
      password: "Bryan-652004"
    };

    const loginContainer = document.querySelector(".login-container");
    const bienvenida = document.getElementById("bienvenida");
    const certificado = document.getElementById("certificado-puntaje");
    const cupoAceptado = document.getElementById("cupo-aceptado");
    const registroNacional = document.getElementById("registro-nacional");
    const confirmacionInscripcion = document.getElementById("confirmacion-inscripcion");

    function iniciarSesion() {
      const documentoInput = document.getElementById("documento");
      const contrasenaInput = document.getElementById("contrasena");
      const captchaCheckbox = document.getElementById("captcha");

      const documento = documentoInput.value.trim();
      const contrasena = contrasenaInput.value.trim();
      const captcha = captchaCheckbox.checked;

      if (!documento) {
        alert("Por favor, ingresa tu documento de identificación.");
        documentoInput.focus();
        return;
      }

      if (!/^\d{7,15}$/.test(documento)) {
        alert("El documento debe contener solo números y tener entre 7 y 15 dígitos.");
        documentoInput.focus();
        return;
      }

      if (!contrasena) {
        alert("Por favor, ingresa tu contraseña.");
        contrasenaInput.focus();
        return;
      }

      if (!captcha) {
        alert("Debes marcar la casilla 'No soy un robot'.");
        return;
      }

      if (documento === usuarioRegistrado.cedula && contrasena === usuarioRegistrado.password) {
        limpiarFormulario();
        mostrarSeccion(bienvenida);
      } else {
        alert("❌ Documento o contraseña incorrectos.");
        contrasenaInput.value = "";
        contrasenaInput.focus();
      }
    }

    function mostrarSeccion(seccionMostrar) {
      [loginContainer, bienvenida, certificado, cupoAceptado, registroNacional, confirmacionInscripcion].forEach(seccion => {
        seccion.style.display = (seccion === seccionMostrar) ? "block" : "none";
      });
    }

    function limpiarFormulario() {
      document.getElementById("documento").value = "";
      document.getElementById("contrasena").value = "";
      document.getElementById("captcha").checked = false;
    }

    function cerrarSesion() {
      limpiarFormulario();
      mostrarSeccion(loginContainer);
    }

    function mostrarCertificadoPuntaje() {
      mostrarSeccion(certificado);
    }

    function volverMenu() {
      mostrarSeccion(bienvenida);
    }

    function mostrarCupoAceptado() {
      mostrarSeccion(cupoAceptado);
    }

    function volverMenuDesdeCupo() {
      mostrarSeccion(bienvenida);
    }

    function mostrarRegistroNacional() {
      mostrarSeccion(registroNacional);
    }

    function volverMenuDesdeRegistro() {
      mostrarSeccion(bienvenida);
    }

    function mostrarConfirmacionInscripcion() {
      mostrarSeccion(confirmacionInscripcion);
    }

    function volverMenuDesdeInscripcion() {
      mostrarSeccion(bienvenida);
    }
  </script>

</body>
</html>
