# Pruebas de integración Móvil ↔ API – HU1 (Login y sesión)

Documento de pruebas de integración entre la aplicación móvil (React Native) y el backend (Flask) correspondiente a la Historia de Usuario 1.

Fecha: 8 de octubre de 2026  
Responsable: Brenda Veranea Gutierrez (QA Integración)

---

## 1. Objetivo

Verificar que el flujo de login, manejo de sesión JWT y persistencia de token en la app móvil funciona correctamente contra la API real.

---

## 2. Casos de prueba de integración

### 2.1 Login

| ID     | Caso                                      | Resultado esperado                                      | Estado |
|--------|-------------------------------------------|---------------------------------------------------------|--------|
| INT-M1 | Login con matrícula válida de alumno      | 200 + `access_token` + rol `alumno`                     |        |
| INT-M2 | Login con matrícula inválida              | 401 o 404 + mensaje de error                            |        |
| INT-M3 | Login de profesor/admin desde móvil       | 200 + token + rol correspondiente                       |        |
| INT-M4 | Login sin matrícula                       | 400 + mensaje de campo obligatorio                      |        |

### 2.2 Manejo de sesión y token

| ID     | Caso                                      | Resultado esperado                                      | Estado |
|--------|-------------------------------------------|---------------------------------------------------------|--------|
| INT-M5 | Token se guarda correctamente después del login | El token persiste al cerrar y reabrir la app         |        |
| INT-M6 | Token válido permite acceso a pantallas protegidas | Usuario entra directamente a Home                   |        |
| INT-M7 | Token expirado                            | 401 + redirección a pantalla de Login                   |        |
| INT-M8 | Token inválido / manipulado               | 401 + redirección a Login                               |        |
| INT-M9 | Cerrar sesión (logout)                    | Se elimina el token y vuelve a Login                    |        |

### 2.3 Endpoint de verificación

| ID     | Caso                                      | Resultado esperado                                      | Estado |
|--------|-------------------------------------------|---------------------------------------------------------|--------|
| INT-M10| `/api/auth/verify` con token válido       | 200 + `valid: true` + rol correcto                     |        |
| INT-M11| `/api/auth/me` con token válido           | 200 + datos del usuario                                 |        |

---

## 3. Notas de integración

- La app móvil usa el header `Authorization: Bearer <token>`.
- El token se almacena de forma segura (AsyncStorage o SecureStore según implementación).
- Los códigos de error del backend (`TOKEN_EXPIRED`, `INVALID_TOKEN`) deben ser manejados para redirigir al login.
- Se verificó que el CORS del backend permite las peticiones desde la app móvil.

---

## 4. Conclusión HU1

Las pruebas de integración de login y sesión en la aplicación móvil se consideran **cubiertas** para el alcance de HU1.