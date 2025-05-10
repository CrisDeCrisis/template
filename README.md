# Template para documentar endpoints.

## [Funcionalidad]

`[MÉTODO HTTP] [RUTA]`

### Descripción:

- [Breve descripción del propósito del endpoint]

---

> **Headers:**

```
 Lista de headers requeridos
```

> **Body:**

```json
{
 "Ejemplo": "del cuerpo de la solicitud"
}
```

> **Parámetros:**

| CAMPO 	| TIPO | REQUERIDO | DESCRIPCIÓN 			|
|-----------|------|-----------|-------------
| [campo] 	|[tipo]|  [Sí/No]  | [descripción]

> **Respuesta exitosa ([Código HTTP]):**

```json
{
 "Ejemplo": "de respuesta exitosa"
}
```

> **Respuesta de error ([Código HTTP]):**

```json
{
 "Ejemplo": "de respuesta de error"
}
```

# Ejemplo

## Registrar usuario

`POST /api/auth/register`

### Descripción:

- Registra un nuevo usuario en el sistema.

---

> **Headers:**

```http
Content-Type: application/json
```

> **Body:**

```json
{
 "username": "nuevo_usuario",
  "email": "usuario@example.com",
  "password": "contraseñaSegura123",
  "nombre": "Juan",
  "apellido": "Pérez"
}
```

> **Parámetros:**

| Campo | Tipo | Requerido | Descripción
|-------|------|-----------|------------
| [username] | [stirng] | [Sí] | [Nombre de usuario unico]
| [email] | [stirng] | [Sí] | [Email válido]
| [password] | [stirng] | [Sí] | [Mínimo 8 caracteres]
| [nombre] | [stirng] | [No] | [Nombre real del usuario]
| [apellido] | [stirng] | [No] | [Apellido del usuario]

> **Respuesta exitosa (201 Created):**

```json
{
  "id": "12345",
  "username": "nuevo_usuario",
  "email": "usuario@example.com",
  "createdAt": "2023-05-10T12:00:00Z"
}
```

> **Respuesta de error (400 Bad Request):**

```json
{
  "error": "ValidationError",
  "message": "El email ya está registrado",
  "details": {
    "email": "Debe ser único"
  }
}
```
