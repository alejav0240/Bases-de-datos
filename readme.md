## 🗄️ Data Management & Monitoring Stack

Este proyecto levanta un entorno completo para la **gestión, visualización y monitoreo de datos** usando contenedores Docker.
Incluye bases de datos SQL, herramientas gráficas de administración y plataformas de análisis y métricas.

---

### 🧱 **Servicios incluidos**

| Servicio       | Imagen            | Puerto | Descripción                                        |
| -------------- | ----------------- | ------ | -------------------------------------------------- |
| **PostgreSQL** | `postgres:14`     | `5432` | Base de datos relacional avanzada.                 |
| **MySQL**      | `mysql:8.0`       | `3306` | Motor SQL clásico ampliamente soportado.           |
| **MariaDB**    | `mariadb:10.6`    | `3307` | Fork de MySQL, rápido y ligero.                    |
| **Redis**      | `redis:7.2`       | `6379` | Almacenamiento en memoria para caché y sesiones.   |
| **pgAdmin**    | `dpage/pgadmin4`  | `8081` | Panel web para administrar PostgreSQL.             |
| **phpMyAdmin** | `phpmyadmin`      | `8082` | Panel web para administrar MySQL/MariaDB.          |
| **Adminer**    | `adminer`         | `8083` | Panel SQL universal para todas las bases de datos. |
| **Prometheus** | `prom/prometheus` | `9090` | Sistema de monitoreo y scraping de métricas.       |
| **Grafana**    | `grafana/grafana` | `3000` | Plataforma de visualización y dashboards.          |

---

### 🚀 **Iniciar el entorno**

```bash
# 1️⃣ Clonar el repositorio (si aplica)
git clone <URL_DEL_REPOSITORIO>
cd <CARPETA_DEL_PROYECTO>

# 2️⃣ Levantar los servicios
docker compose up -d

# 3️⃣ Verificar que todo esté corriendo
docker ps
```

---

### 🧭 **Accesos a los paneles web**

| Herramienta    | URL de acceso                                  | Usuario           | Contraseña |
| -------------- | ---------------------------------------------- | ----------------- | ---------- |
| **pgAdmin**    | [http://localhost:8081](http://localhost:8081) | `admin@admin.com` | `admin`    |
| **phpMyAdmin** | [http://localhost:8082](http://localhost:8082) | `user`            | `password` |
| **Adminer**    | [http://localhost:8083](http://localhost:8083) | —                 | —          |
| **Prometheus** | [http://localhost:9090](http://localhost:9090) | —                 | —          |
| **Grafana**    | [http://localhost:3000](http://localhost:3000) | `admin`           | `admin`    |

---

### 🧩 **Datos de conexión a bases de datos**

#### 🔹 PostgreSQL

```
Host: postgres_db
Port: 5432
Database: mydatabase
User: user
Password: password
```

#### 🔹 MySQL

```
Host: mysql_db
Port: 3306
Database: mydatabase
User: user
Password: password
```

#### 🔹 MariaDB

```
Host: mariadb_db
Port: 3306
Database: mydatabase
User: user
Password: password
```

#### 🔹 Redis

```
Host: redis
Port: 6379
```

> 💡 *Usa los nombres de servicio (`postgres_db`, `mysql_db`, etc.) como host cuando conectes desde otro contenedor del mismo network.*

---

### 📊 **Configuración inicial de Grafana**

1. Accede a Grafana en [http://localhost:3000](http://localhost:3000)
2. Inicia sesión con `admin / admin`
3. Añade una fuente de datos:

   * PostgreSQL → Host: `postgres_db:5432`
   * MySQL → Host: `mysql_db:3306`
   * Prometheus → URL: `http://prometheus:9090`
4. Crea tus dashboards personalizados 🔥

---

### 🧹 **Comandos útiles**

```bash
# Ver logs de todos los servicios
docker compose logs -f

# Reiniciar todos los contenedores
docker compose restart

# Detener el entorno
docker compose down

# Detener y eliminar volúmenes persistentes
docker compose down -v
```

---

### 💾 **Volúmenes persistentes**

| Volumen           | Servicio   | Descripción               |
| ----------------- | ---------- | ------------------------- |
| `postgres_data`   | PostgreSQL | Datos de la base de datos |
| `mysql_data`      | MySQL      | Datos de la base de datos |
| `mariadb_data`    | MariaDB    | Datos de la base de datos |
| `redis_data`      | Redis      | Datos persistentes        |
| `pgadmin_data`    | pgAdmin    | Configuración del panel   |
| `prometheus_data` | Prometheus | Archivos de configuración |
| `grafana_data`    | Grafana    | Dashboards y conexiones   |

---

### ⚡ **Requisitos**

* Docker Engine ≥ 20.10
* Docker Compose ≥ 2.5
* 4 GB de RAM mínimo (recomendado: 8 GB)

---

### 🧠 **Sugerencias de expansión**

Puedes extender este stack con:

* **Metabase** → `metabase/metabase` para dashboards tipo BI.
* **Apache Superset** → `apache/superset` para análisis SQL avanzados.
* **MinIO** → almacenamiento tipo S3.
* **pgVector** → para IA o embeddings en PostgreSQL.

---

### 🧑‍💻 **Autor**

**Alejandro Chipana**
Estudiante de Ingeniería de Sistemas — Universidad del Valle (Univalle), Bolivia.
💡 Proyecto orientado a la gestión de datos, análisis y monitoreo en entornos modernos de desarrollo.