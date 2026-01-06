# 🐳 Entorno Multilenguaje con Docker Compose

Este proyecto levanta un entorno de desarrollo con múltiples lenguajes y frameworks usando **Docker Compose**.
Incluye contenedores configurados para **Node.js**, **Python**, **Golang**, **Java** y **Laravel**, además de una base de datos **MySQL** para Laravel.

## 📦 Servicios incluidos


| Servicio | Imagen Base         | Puerto Externo | Descripción                               |
| -------- | ------------------- | -------------- | ------------------------------------------ |
| Node.js  | node:20-alpine      | 3000           | Aplicación Node.js (Express, React, etc.) |
| Python   | python:3.11-slim    | 5000           | API o aplicación Flask / FastAPI          |
| Golang   | golang:1.22-alpine  | 8080           | API escrita en Go                          |
| Java     | openjdk:21-jdk-slim | 8081           | Aplicación Java simple                    |
| Laravel  | bitnami/laravel:10  | 8000           | Proyecto Laravel conectado a MySQL         |
| MySQL    | mysql:8             | 3306           | Base de datos para Laravel                 |

---

## 🗂️ Estructura del proyecto
  ```bash
  project-root/
  │
  ├── nodejs/
  │   ├── package.json
  │   └── index.js
  │
  ├── python/
  │   ├── requirements.txt
  │   └── app.py
  │
  ├── golang/
  │   └── main.go
  │
  ├── java/
  │   └── Main.java
  │
  ├── laravel/
  │   └── (proyecto Laravel aquí)
  │
  └── docker-compose.yml
  ```

## 🚀 Iniciar el entorno

1. **Clona este repositorio:**
   ```bash
   git clone <url-del-repo>
   cd       
   ```

2. **Levanta los contenedores:**

   ```bash
   docker-compose up -d
   ```
3. **Verifica que todos los servicios estén corriendo:**

   ```bash
   docker ps
   ```

---

## 🧩 Uso por servicio

### Node.js

* Carpeta: `./nodejs`
* El contenedor instala dependencias (`npm install`) y ejecuta `npm run dev`
* Acceso: [http://localhost:3000](http://localhost:3000/)

### Python

* Carpeta: `./python`
* Ejecuta `python app.py` después de instalar las dependencias
* Acceso: [http://localhost:5000](http://localhost:5000/)

### Golang

* Carpeta: `./golang`
* Ejecuta `go run main.go`
* Acceso: [http://localhost:8080](http://localhost:8080/)

### Java

* Carpeta: `./java`
* Compila y ejecuta `Main.java`
* Acceso: [http://localhost:8081](http://localhost:8081/)

### Laravel

* Carpeta: `./laravel`
* Conectado automáticamente a MySQL
* Acceso: [http://localhost:8000](http://localhost:8000/)

### MySQL

* Usuario: `laravel`
* Contraseña: `laravel`
* Base de datos: `laravel`
* Puerto: `3306`

Puedes acceder con un cliente SQL o desde tu aplicación Laravel.

---

## 🧹 Comandos útiles

* **Ver logs de un servicio:**
  ```bash
  docker-compose logs -f nombre_servicio
  ```
* **Reiniciar un servicio:**
  ```bash
  docker-compose restart nombre_servicio
  ```
* **Apagar todos los contenedores:**
  ```bash
  docker-compose down
  ```
* **Recrear el entorno desde cero:**
  ```bash
  docker-compose down -v
  docker-compose up -d --build
  ```
