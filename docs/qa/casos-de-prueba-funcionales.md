# Casos de prueba funcionales — Login en la app (HU1)

## Objetivo
Verificar el inicio de sesión en la aplicación móvil de CheckU, la validación de credenciales y el control del acceso a funciones protegidas.

## Alcance
Pruebas funcionales de autenticación en la aplicación móvil. Ejecutar en un dispositivo o emulador configurado para el entorno de pruebas.

## Casos de prueba

| ID | Escenario | Precondiciones | Pasos | Resultado esperado | Prioridad |
|---|---|---|---|---|---|
| MOV-HU1-001 | Inicio de sesión correcto | La aplicación está instalada y existe una cuenta de prueba activa. | 1. Abrir la aplicación. 2. Ingresar credenciales válidas. 3. Pulsar el botón de acceso. | La aplicación permite el acceso y muestra la pantalla correspondiente al usuario. | Alta |
| MOV-HU1-002 | Contraseña incorrecta | Existe una cuenta de prueba. | 1. Abrir el login. 2. Ingresar una contraseña incorrecta. 3. Intentar acceder. | Se rechaza el acceso y se muestra un mensaje de error. | Alta |
| MOV-HU1-003 | Usuario inexistente | Se dispone de un identificador no registrado. | 1. Ingresar el identificador inexistente. 2. Ingresar una contraseña cualquiera. 3. Intentar acceder. | Se rechaza el acceso sin revelar información sensible. | Alta |
| MOV-HU1-004 | Campos obligatorios vacíos | La pantalla de login está disponible. | 1. Dejar vacíos los campos obligatorios. 2. Pulsar el botón de acceso. | Se indica que deben completarse los campos y no se inicia sesión. | Alta |
| MOV-HU1-005 | Cierre de sesión | Hay una sesión autenticada. | 1. Abrir las opciones de usuario. 2. Cerrar sesión. 3. Intentar entrar a una función protegida. | La sesión se cierra y se solicita autenticación para acceder nuevamente. | Alta |
| MOV-HU1-006 | Sesión al cambiar de pantalla | Hay una sesión autenticada. | 1. Iniciar sesión. 2. Navegar entre pantallas autorizadas. | La aplicación mantiene el estado de sesión según el comportamiento definido. | Media |
| MOV-HU1-007 | Acceso protegido sin autenticación | No hay una sesión activa. | 1. Abrir o intentar acceder a una función protegida. | La aplicación bloquea el acceso y solicita autenticación. | Alta |
| MOV-HU1-008 | Manejo de error de conexión | El entorno de pruebas permite simular una desconexión. | 1. Desactivar la conexión. 2. Intentar iniciar sesión. | La aplicación informa del problema y evita mostrar el acceso como exitoso. | Media |

## Registro de ejecución
Estado inicial: Pendiente de ejecución.

Registrar para cada caso: fecha, dispositivo o emulador, versión de la aplicación, datos de prueba, resultado real, estado (Aprobado/Reprobado/Bloqueado) y evidencia.

## Criterio de aceptación
Los casos deben ejecutarse en el entorno de pruebas. Se considera aprobada la validación cuando el resultado real coincide con el esperado y existe evidencia. No registrar como aprobadas pruebas que no se hayan ejecutado.
