# Casos de prueba funcionales — CheckU Móvil

## HU5. Validación del código QR

| ID | Caso de prueba | Resultado esperado |
|---|---|---|
| MOV-HU5-01 | Abrir el escáner QR | Se muestra la interfaz de escaneo |
| MOV-HU5-02 | Escanear un código QR válido | El sistema procesa el código y muestra el resultado |
| MOV-HU5-03 | Escanear un código QR inválido | Se informa que el código no es válido |
| MOV-HU5-04 | Escanear un QR de una sesión cerrada o expirada | Se rechaza el registro de asistencia |
| MOV-HU5-05 | Intentar escanear sin conceder permiso a la cámara | Se informa que se necesita permiso para usar la cámara |

## Registro de ejecución

Los casos quedan pendientes de ejecución en la aplicación. Los resultados se documentarán después de realizar las pruebas.
