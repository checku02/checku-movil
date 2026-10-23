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
---

# Criterios de aceptación — HU5: Escaneo QR y registro de asistencia

## 5. Criterios de aceptación de HU5

### CA-10. Escaneo de QR válido

**Dado** que el alumno dispone de un código QR válido,
**cuando** escanea el código desde la aplicación móvil,
**entonces** la aplicación debe procesar la solicitud y mostrar la confirmación del registro con la materia, el grupo y la hora.

### CA-11. Código QR expirado

**Dado** que el código QR ha expirado,
**cuando** el alumno intenta escanearlo,
**entonces** la aplicación debe rechazar el registro y mostrar un mensaje claro que indique que el QR ha expirado.

### CA-12. Código QR inválido o manipulado

**Dado** que el código QR es inválido o ha sido manipulado,
**cuando** el alumno intenta escanearlo,
**entonces** la aplicación debe rechazar la operación y mostrar un mensaje de error comprensible.

### CA-13. Registro de asistencia duplicado

**Dado** que el alumno ya registró su asistencia para el mismo registro,
**cuando** intenta registrar nuevamente su asistencia mediante el mismo flujo,
**entonces** la aplicación debe informar que la asistencia ya fue registrada y evitar un registro duplicado.

### CA-14. Confirmación oportuna del registro

**Dado** que el alumno escanea un código QR válido y la API puede procesar la solicitud,
**cuando** se realiza el registro de asistencia,
**entonces** la aplicación debe proporcionar la confirmación en menos de cinco segundos, mostrando la materia, el grupo y la hora.

### CA-15. Error de conexión durante el escaneo

**Dado** que el dispositivo no tiene conexión o se produce un error de red,
**cuando** el alumno intenta registrar su asistencia mediante el escaneo de un QR,
**entonces** la aplicación debe mostrar un mensaje de error comprensible y evitar presentar una confirmación de registro que no haya sido recibida de la API.

## 6. Resultado esperado de HU5

La aplicación móvil debe permitir escanear códigos QR válidos y confirmar el registro de asistencia, rechazar códigos expirados o inválidos, detectar registros duplicados y comunicar los errores de conexión de forma clara.

## 7. Consideraciones de HU5

- La confirmación debe mostrar la materia, el grupo y la hora.
- Deben manejarse los errores del backend relacionados con códigos QR expirados, inválidos y registros duplicados.
- El tiempo de confirmación esperado es inferior a cinco segundos.
- Los errores de conexión deben comunicarse mediante mensajes comprensibles.
