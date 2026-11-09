# Taller API REST: Libros (Node.js, Express, SQLite, JWT)

Entidad: libros (id, titulo, autor, anio).

## Requisitos
Node.js 18 o superior y Postman.

## Instalación y ejecución
```
npm install
copy .env.example .env
```
Edite `.env` y reemplace `JWT_SECRET` por un valor largo y aleatorio.

## Cuenta de prueba
```
npm run seed -- admin MiClave123
```
Crea la base `data/libros.db` con las tablas y el usuario (contraseña guardada con hash bcrypt).

## Iniciar la API
```
npm start
```
Disponible en http://localhost:3000

## Obtener y usar el JWT
1. POST /auth/login con `{"username":"admin","password":"MiClave123"}`
2. Copiar el valor de `token`.
3. Enviar en las demás rutas el encabezado `Authorization: Bearer <token>`.

El token vence a los 15 minutos (`JWT_EXPIRES_IN`).

## Rutas
POST /auth/login (pública). POST, GET, GET /:id, PUT /:id y DELETE /:id bajo /libros (requieren JWT).

## Postman
Importar `postman/` (colección y entorno).
