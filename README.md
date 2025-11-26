# SLCP
(SISTEMA DE LIMPIEZA DE COMPUTADORAS PROGRAMADO)
# 💾 App de Resguardo de Textos para Laboratorios
**Actividad 3: Modelado de Datos y Arquitectura de la Base de Datos (MongoDB)**

**Autor:** Sergio Salazar  
**Estado:** MVP  
**Stack:** MERN (MongoDB, Express, React, Node.js)

---

## 📌 Descripción
Aplicación web para que estudiantes almacenen textos y documentos en la nube, evitando la pérdida de archivos en computadoras de laboratorio. Permite crear, editar, descargar y restaurar copias de seguridad de textos. Diseñada para alumnos de nivel media superior y superior.

---

## ✅ Funcionalidades (MVP)
- Registro e inicio de sesión de usuarios.
- Crear, editar y eliminar documentos de texto.
- Generación y restauración de copias de seguridad por documento.
- Clasificación por categoría y búsqueda básica por título.
- Logs de operaciones (creación/edición/eliminación) — opcional.

---

## 🧰 Tecnologías
- **Backend:** Node.js, Express
- **Base de datos:** MongoDB (recomendado: MongoDB Atlas)
- **ODM/Validación:** Mongoose
- **Frontend:** React (Create React App o Vite)
- **Autenticación:** JWT (jsonwebtokens) / bcrypt para contraseñas
- **Deploy (suggested):** Vercel (frontend), Render/Heroku/Render for backend, MongoDB Atlas

---

## 🗂 Estructura de la Base de Datos (Parte A — Schemas)

> Tip: usa Mongoose para definir los schemas y validaciones.

### `users`
```js
{
  username: { type: String, required: true, unique: true },
  email: { type: String, required: true, unique: true },
  passwordHash: { type: String, required: true },
  role: { type: String, enum: ["student","admin"], default: "student" },
  createdAt: { type: Date, default: Date.now }
}
