# Criterios de aceptación — HU1: Autenticación y gestión de usuarios

## 1. Objetivo

Definir las condiciones que debe cumplir la aplicación móvil de CheckU para autenticar a los usuarios y permitirles acceder de forma segura a las funcionalidades autorizadas según su rol.

## 2. Criterios de aceptación

### CA-01. Inicio de sesión exitoso

**Dado** que el usuario tiene una cuenta registrada y activa,  
**cuando** introduce sus credenciales correctas,  
**entonces** la aplicación debe autenticarlo y mostrar la pantalla correspondiente a su sesión.

### CA-02. Credenciales incorrectas

**Dado** que el usuario está en la pantalla de inicio de sesión,  
**cuando** introduce credenciales incorrectas,  
**entonces** la aplicación debe mostrar un mensaje de error y mantenerlo en la pantalla de inicio de sesión.

### CA-03. Validación de campos

**Dado** que el usuario intenta iniciar sesión,  
**cuando** deja vacíos los campos obligatorios,  
**entonces** la aplicación debe indicarle que complete la información requerida.

### CA-04. Acceso según el rol

**Dado** que el usuario se autentica correctamente,  
**cuando** la aplicación recibe la información de su cuenta,  
**entonces** debe permitirle acceder únicamente a las pantallas y funciones correspondientes a su rol.

### CA-05. Comunicación con el backend

**Dado** que el usuario envía sus credenciales,  
**cuando** la aplicación realiza la solicitud de autenticación,  
**entonces** debe comunicarse con la API de CheckU y procesar correctamente su respuesta.

### CA-06. Manejo de errores de conexión

**Dado** que la API no está disponible o existe un problema de conexión,  
**cuando** el usuario intenta iniciar sesión,  
**entonces** la aplicación debe mostrar un mensaje comprensible sin bloquearse.

### CA-07. Gestión de sesión y token

**Dado** que el usuario inició sesión correctamente,  
**cuando** la API devuelve un token de autenticación,  
**entonces** la aplicación debe gestionarlo de manera segura para las solicitudes que requieran autenticación.

### CA-08. Token inválido o expirado

**Dado** que el token de autenticación es inválido o ha expirado,  
**cuando** el usuario intenta realizar una operación protegida,  
**entonces** la aplicación debe impedir que continúe la operación y solicitar autenticación nuevamente cuando corresponda.

### CA-09. Cierre de sesión

**Dado** que existe una sesión activa,  
**cuando** el usuario cierra sesión,  
**entonces** la aplicación debe eliminar los datos de sesión que corresponda y regresar a la pantalla de inicio de sesión.

## 3. Resultado esperado

La aplicación móvil debe permitir que los usuarios inicien y cierren sesión correctamente, manejar los errores de autenticación y proteger las funcionalidades que requieren una sesión válida.

## 4. Consideraciones

- La interfaz debe ser clara y sencilla.
- Los mensajes de error deben ser comprensibles.
- Los tokens y datos de autenticación deben almacenarse de forma segura.
- La implementación debe ser compatible con los endpoints definidos en el backend de CheckU.