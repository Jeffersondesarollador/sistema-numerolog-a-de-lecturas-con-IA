# API REST – Gestión de Usuarios, Pagos y Lecturas con IA
# 📌 Descripción del proyecto

Este proyecto consiste en una API REST desarrollada en JavaScript, utilizando Node.js, Express y MySQL, implementada bajo una arquitectura en capas (MVC).

El sistema permite la gestión de usuarios, pagos de membresía y lecturas personalizadas basadas en numerología, integrando una IA generativa (Gemini) para generar respuestas automáticas a partir de la fecha de nacimiento del usuario.

Las peticiones fueron probadas y validadas utilizando Postman Agent.

# 🧱 Arquitectura del proyecto

El proyecto está organizado en las siguientes capas:

Routes: definición y agrupación de endpoints.

Controllers: lógica de negocio y control de las solicitudes.

Models: acceso e interacción con la base de datos MySQL.

Validators: validación de datos de entrada para evitar inconsistencias.

Config: configuración de conexión a la base de datos mediante pool MySQL.

Las operaciones asíncronas se manejan con async / await, utilizando req y res para la gestión de solicitudes HTTP.

# 🗄️ Base de datos

Se utiliza MySQL con tres tablas principales:
usuarios
pagos
lecturas

# Estas tablas se relacionan para controlar:
.La información del usuario
.El estado de su membresía
.El historial de lecturas generadas por la IA

🔗 Endpoints del proyecto
👤 Usuarios
Método	Endpoint	Descripción
GET	/api/usuarios	Listar todos los usuarios
GET	/api/usuarios/:id	Obtener un usuario por ID
POST	/api/usuarios	Registrar un nuevo usuario
PUT	/api/usuarios/:id	Actualizar información del usuario
PATCH	/api/usuarios/:id/estado	Cambiar estado (activo / inactivo)
DELETE	/api/usuarios/:id	Eliminar un usuario

💳 Pagos (Membresías)
Método	Endpoint	Descripción
GET	/api/pagos	Listar todos los pagos
GET	/api/pagos/:usuario_id	Consultar pagos de un usuario
POST	/api/pagos	Registrar un pago mensual
GET	/api/pagos/estado/:usuario_id	Consultar estado del usuario (activo o vencido)
🔮 Lecturas (IA – Numerología)

Método	Endpoint	Descripción
POST	/api/lecturas/principal/:usuario_id	Generar lectura principal
POST	/api/lecturas/diaria/:usuario_id	Generar lectura diaria (usuario activo)
GET	/api/lecturas/usuario/:usuario_id	Consultar lecturas del usuario
GET	/api/lecturas/:id	Consultar una lectura específica

Las lecturas se generan a partir de la fecha de nacimiento del usuario, y el contenido es producido mediante IA generativa (Gemini) con un enfoque de numerología.

⚙️ Funcionamiento general
Se registra un usuario mediante una petición POST enviando los datos en formato JSON.

El usuario realiza pagos de membresía, los cuales determinan su estado.

Si el usuario está activo, puede generar lecturas mediante la integración con la IA.

Todas las peticiones se procesan en un servidor Node.js.

Postman se utiliza para probar y validar cada endpoint.

🛠️ Tecnologías utilizadas

JavaScript

Node.js

Express

MySQL

Postman Agent

API Gemini (IA generativa)

Arquitectura en capas (MVC)

🎯 Objetivo del proyecto

Este proyecto fue desarrollado con fines académicos y de aprendizaje, con el objetivo de fortalecer conocimientos en:

Desarrollo de APIs REST

Arquitectura en capas

Manejo de bases de datos relacionales

Programación asíncrona

Integración básica de IA

📌 Autor

Jefferson Rojas
Aprendiz – Análisis y Desarrollo de Software
SENA
