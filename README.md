# Servicios Docker

![Docker Badge](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white) ![Docker Compose Badge](https://img.shields.io/badge/Docker--Compose-000000?style=for-the-badge&logo=docker-compose&logoColor=white)

Este proyecto centraliza y organiza configuraciones de Docker Compose para el despliegue rápido y eficiente de una amplia gama de bases de datos y entornos de servicios para diversas tecnologías de desarrollo. Su objetivo es simplificar la gestión de la infraestructura de desarrollo, proporcionando entornos aislados, consistentes y fáciles de usar.

---

## 🌟 Características Principales

*   **Modularidad:** Estructura de directorios clara que separa las configuraciones de bases de datos de los servicios de aplicación.
*   **Amplia Compatibilidad:** Soporte para bases de datos SQL y NoSQL, así como gestores web de bases de datos.
*   **Entornos de Desarrollo Versátiles:** Configuraciones predefinidas para tecnologías como Node.js, Java, Go, Laravel (PHP) y Python.
*   **Aislamiento de Entornos:** Cada servicio se ejecuta en su propio contenedor, garantizando la consistencia y evitando conflictos de dependencias.
*   **Despliegue Sencillo:** Utiliza Docker Compose para levantar entornos complejos con un solo comando.

---

## 🚀 Requisitos Previos

Antes de comenzar, asegúrate de tener instalado lo siguiente:

*   **Docker Desktop** (incluye Docker Engine y Docker Compose)
    *   [Descargar Docker Desktop](https://www.docker.com/products/docker-desktop/)

---

## 🛠️ Instrucciones de Instalación y Uso

El proyecto está organizado en dos directorios principales: `Dases de Datos` y `Servicios`. Cada directorio contiene sus propias configuraciones de `docker-compose.yml`.

### 1. Clonar el Repositorio
```bash
git clone https://github.com/alejav0240/Bases-de-datos  # Reemplaza con la URL real de tu repositorio
cd Bases-de-datos
```

### 2. Levantar Servicios de Bases de Datos

Para levantar un conjunto de bases de datos (por ejemplo, MySQL, PostgreSQL, MongoDB y phpMyAdmin), navega al directorio `Dases de Datos` y ejecuta Docker Compose:
```bash
cd Dases\ de\ Datos
docker-compose up -d
```
*   `up`: Inicia los contenedores.
*   `-d`: Ejecuta los contenedores en segundo plano (detached mode).

Para ver el estado de los servicios:
```bash
docker-compose ps
```

Para detener y remover los servicios:
```bash
docker-compose down
```

### 3. Levantar Servicios de Aplicación

Para levantar un entorno de desarrollo para una tecnología específica (por ejemplo, Node.js), navega al directorio `Servicios` y ejecuta Docker Compose:
```bash
cd ../Servicios # Si estás en Dases de Datos, o cd Servicios si estás en la raíz del proyecto
docker-compose up -d
```

**Nota:** Cada `docker-compose.yml` dentro de `Servicios` contendrá configuraciones específicas para diferentes tecnologías. Deberás revisar y ejecutar el `docker-compose.yml` correspondiente a la tecnología que deseas usar.

---

## 📁 Estructura del Proyecto
```
Servicios-Docker/
├── Dases de Datos/              # Configuraciones de Docker Compose para diversas bases de datos
│   ├── docker-compose.yml       # Define servicios de bases de datos (ej. MySQL, PostgreSQL, MongoDB, etc.)
│   └── readme.md                # Documentación específica para el módulo de bases de datos
└── Servicios/                   # Configuraciones de Docker Compose para entornos de desarrollo/aplicaciones
    ├── docker-compose.yml       # Define servicios para diferentes tecnologías (ej. Node.js, Java, Python, Laravel)
    └── readme.md                # Documentación específica para el módulo de servicios
```

---

## 💻 Tecnologías Utilizadas

*   **Docker:** Plataforma de contenedores para construir, ejecutar y gestionar aplicaciones.
*   **Docker Compose:** Herramienta para definir y ejecutar aplicaciones Docker multi-contenedor.
*   **Bases de Datos:** MySQL, PostgreSQL, MongoDB, Redis, etc. (según las configuraciones específicas).
*   **Lenguajes/Frameworks:** Node.js, Java, Go, Laravel (PHP), Python, etc. (según las configuraciones específicas).