# 🧠 Data Management, BI & Monitoring Stack

Este proyecto levanta un entorno integral de **bases de datos, análisis, inteligencia de negocios y monitoreo** con Docker Compose.

---

## 🧱 Servicios incluidos

| Tipo | Servicio | Puerto | Descripción |
|------|-----------|---------|-------------|
| 🗄️ Base de datos | PostgreSQL (pgVector) | 5432 | Base de datos avanzada con soporte para IA. |
| 🗄️ Base de datos | MySQL | 3306 | Base relacional clásica. |
| 🗄️ Base de datos | MariaDB | 3307 | Variante optimizada de MySQL. |
| ⚡ Cache | Redis | 6379 | Almacenamiento en memoria. |
| 🧩 Admin | pgAdmin | 8081 | GUI para PostgreSQL. |
| 🧩 Admin | phpMyAdmin | 8082 | GUI para MySQL/MariaDB. |
| 🧩 Admin | Adminer | 8083 | GUI SQL universal. |
| 📈 Monitoreo | Prometheus | 9090 | Métricas del sistema. |
| 📊 Visualización | Grafana | 3000 | Dashboards de monitoreo. |
| 💼 BI | Metabase | 3001 | Inteligencia de negocios y dashboards. |
| 🧮 Análisis SQL | Apache Superset | 8088 | Exploración y visualización avanzada. |
| ☁️ Storage | MinIO | 9000 / 9001 | Almacenamiento tipo S3. |
| 🗄️ Base de datos | ChromaDB | 8000 | Base de datos vectorial para embeddings y IA. |
| 🗄️ Base de datos | MongoDB | 27017 | Base documental NoSQL. |

---

## 🚀 Uso

### Levantar todos los servicios
```bash
docker compose up -d
````

### Verificar contenedores activos

```bash
docker ps
```

### Detener el entorno

```bash
docker compose down
```

### Eliminar todo (incluyendo volúmenes)

```bash
docker compose down -v
```

---

## 🧭 Accesos

| Herramienta       | URL                                            | Usuario                                   | Contraseña |
| ----------------- | ---------------------------------------------- | ----------------------------------------- | ---------- |
| **pgAdmin**       | [http://localhost:8081](http://localhost:8081) | [admin@admin.com](mailto:admin@admin.com) | admin      |
| **phpMyAdmin**    | [http://localhost:8082](http://localhost:8082) | user                                      | password   |
| **Adminer**       | [http://localhost:8083](http://localhost:8083) | —                                         | —          |
| **Prometheus**    | [http://localhost:9090](http://localhost:9090) | —                                         | —          |
| **Grafana**       | [http://localhost:3000](http://localhost:3000) | admin                                     | admin      |
| **Metabase**      | [http://localhost:3001](http://localhost:3001) | Configurar al iniciar                     |            |
| **Superset**      | [http://localhost:8088](http://localhost:8088) | admin                                     | admin      |
| **MinIO Console** | [http://localhost:9001](http://localhost:9001) | admin                                     | admin123   |
| **ChromaDB API**  | [http://localhost:8000](http://localhost:8000) | —                                         | —          |
| **MongoDB**       | mongodb://localhost:27017                       | —                                         | —          |

---

## 🔗 Conexiones entre servicios

Usa los nombres de los contenedores como **hosts internos** dentro de la red Docker.

| Servicio   | Host          | Puerto |
| ---------- | ------------- | ------ |
| PostgreSQL | `postgres_db` | 5432   |
| MySQL      | `mysql_db`    | 3306   |
| MariaDB    | `mariadb_db`  | 3306   |
| Redis      | `redis`       | 6379   |
| ChromaDB   | `croma_db`    | 8000   |
| MongoDB    | `mongo_db`    | 27017  |

---

## 💾 Volúmenes persistentes

Los datos se almacenan en volúmenes Docker:

| Volumen           | Servicio   | Descripción          |
| ----------------- | ---------- | -------------------- |
| `postgres_data`   | PostgreSQL | Datos de BD          |
| `mysql_data`      | MySQL      | Datos de BD          |
| `mariadb_data`    | MariaDB    | Datos de BD          |
| `redis_data`      | Redis      | Datos persistentes   |
| `pgadmin_data`    | pgAdmin    | Configuración        |
| `grafana_data`    | Grafana    | Dashboards           |
| `prometheus_data` | Prometheus | Configs              |
| `metabase_data`   | Metabase   | Configuración BI     |
| `superset_data`   | Superset   | Archivos internos    |
| `minio_data`      | MinIO      | Archivos almacenados |
| `cromadb_data`    | ChromaDB   | Datos vectoriales    |
| `mongo_data`      | MongoDB    | Datos de BD          |

---

## 🧠 pgVector — PostgreSQL para IA

El servicio usa la imagen `ankane/pgvector`, que incluye la extensión `pgvector` para almacenar y consultar **vectores de embeddings**, ideal para proyectos de **IA y NLP**.

Para activarla en tu base:

```sql
CREATE EXTENSION IF NOT EXISTS vector;
```

---

## 💡 Requisitos

* Docker Engine ≥ 20.10
* Docker Compose ≥ 2.5
* RAM mínima: **8 GB recomendada**

---

## 👨‍💻 Autor

**Alejandro Chipana**
📊 Enfoque: Gestión de datos, monitoreo y analítica avanzada con IA.
