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

<!-- PANTALLA DE BIENVENIDA -->
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
    <p>La Secretaría de Educación Superior, Ciencia, Tecnología e Innovación, SENESCYT, a través de la Subsecretaría de Acceso a la Educación Superior, <strong>CERTIFICA</strong> que <strong>BRYAN ANTHONY CASTRO BALLADARES</strong>, con documento de identificación: <strong>1805094404</strong>, registra en la base de datos de la plataforma del Sistema Nacional de Nivelación y Admisión, la siguiente información:</p>
    
    <table>
      <tr>
        <th>PERIODO</th>
        <th>PUNTAJE</th>
      </tr>
      <tr>
        <td>SEGUNDO PERIODO ACADÉMICO ORDINARIO 2022</td>
        <td>787</td>
      </tr>
    </table>

    <p><strong>IMPORTANTE:</strong> Esta información es de uso exclusivo de la persona registrada en la plataforma. Cualquier alteración parcial o total de este documento puede conllevar sanciones.</p>

    <p>Este certificado contiene el puntaje obtenido por el aspirante en el Examen Nacional de Educación Superior. Válido por 30 días hábiles desde su generación.</p>

    <p><strong>GENERADO:</strong> 01-08-2025 01:15:22</p>

    <p><em>Documento firmado electrónicamente,</em></p>
    <p><strong>Stephany Mishell Pulles Tulcanaza</strong><br>
    Directora de Apoyo y Seguimiento Académico</p>

    <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/4/4d/Qr-2.png/240px-Qr-2.png" alt="QR" width="100">
    
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
    <p>La Secretaría de Educación Superior, Ciencia, Tecnología e Innovación, SENESCYT, a través de la Subsecretaría de Acceso a la Educación Superior, <strong>CERTIFICA</strong> que <strong>BRYAN ANTHONY CASTRO BALLADARES</strong>, con documento de identificación: <strong>1805094404</strong>, ha aceptado un cupo en el proceso de admisión correspondiente al siguiente detalle:</p>

    <table>
      <tr>
        <th>PERIODO</th>
        <th>INSTITUCIÓN</th>
        <th>CARRERA</th>
      </tr>
      <tr>
        <td>SEGUNDO PERIODO ACADÉMICO ORDINARIO 2022</td>
        <td>Universidad Técnica de Ambato</td>
        <td>Ingeniería en Sistemas Computacionales</td>
      </tr>
    </table>

    <p><strong>IMPORTANTE:</strong> Este documento certifica la aceptación oficial del cupo por parte del aspirante. Cualquier alteración parcial o total puede conllevar sanciones.</p>

    <p><strong>GENERADO:</strong> 01-08-2025 01:18:47</p>

    <p><em>Documento firmado electrónicamente,</em></p>
    <p><strong>Stephany Mishell Pulles Tulcanaza</strong><br>
    Directora de Apoyo y Seguimiento Académico</p>

    <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/4/4d/Qr-2.png/240px-Qr-2.png" alt="QR" width="100">

    <div class="botones-certificado">
      <button onclick="volverMenuDesdeCupo()">🔙 Atrás</button>
      <button onclick="window.print()">🖨 Imprimir</button>
    </div>
  </div>
</div>

<!-- CONFIRMACIÓN DEL REGISTRO NACIONAL -->
<div id="registro-nacional" style="display: none;">
  <div class="menu">
    <p>👤 La sesión expira en : 22 minutos</p>
    <h3>BRYAN ANTHONY CASTRO BALLADARES</h3>
    <button onclick="cerrarSesion()">🚪 Salir</button>
  </div>

  <div class="contenido-certificado">
    <p>Quito, 01-08-2025</p>
    <p>La Secretaría de Educación Superior, Ciencia, Tecnología e Innovación, SENESCYT, a través de la Subsecretaría de Acceso a la Educación Superior, <strong>CONFIRMA</strong> que <strong>BRYAN ANTHONY CASTRO BALLADARES</strong>, con documento de identificación <strong>1805094404</strong>, ha completado exitosamente el proceso de <strong>Registro Nacional</strong> en el Sistema Nacional de Nivelación y Admisión.</p>

    <table>
      <tr>
        <th>PERIODO</th>
        <th>FECHA DE REGISTRO</th>
        <th>ESTADO</th>
      </tr>
      <tr>
        <td>SEGUNDO PERIODO ACADÉMICO ORDINARIO 2022</td>
        <td>15-08-2022</td>
        <td>Registrado</td>
      </tr>
    </table>

    <p><strong>IMPORTANTE:</strong> Esta confirmación acredita que el aspirante ha cumplido con los requisitos establecidos por la SENESCYT para el proceso de admisión. Cualquier alteración parcial o total de este documento puede conllevar sanciones.</p>

    <p><strong>GENERADO:</strong> 01-08-2025 01:22:10</p>

    <p><em>Documento firmado electrónicamente,</em></p>
    <p><strong>Stephany Mishell Pulles Tulcanaza</strong><br>
    Directora de Apoyo y Seguimiento Académico</p>

    <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/4/4d/Qr-2.png/240px-Qr-2.png" alt="QR" width="100">

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
      <strong>ACUERDO DE RESPONSABILIDAD:</strong> El/la usuario/a conoce la responsabilidad del uso que dé a la información consultada en este portal, sin perjuicio de las acciones judiciales a que hubiere lugar en el caso de que dicha información fuera falsa o alterada, de conformidad a lo dispuesto en el primer inciso del artículo 270 del Código Orgánico Integral Penal.
    </div>

    <div class="botones-certificado" style="margin-top: 20px;">
      <button onclick="volverMenuDesdeInscripcion()">🔙 Atrás</button>
      <button onclick="window.print()">🖨 Imprimir</button>
    </div>
  </div>
</div>

