# Proyecto Dockerizado: Node.js + PostgreSQL + Nginx + pgAdmin

Este proyecto incluye una app básica en Node.js con Express conectada a una base de datos PostgreSQL, gestionada con pgAdmin y expuesta al mundo a través de Nginx.

## 🧱 Estructura del proyecto

```
project-root/
├── app/
│   ├── Dockerfile
│   ├── index.js
│   └── package.json
├── nginx/
│   └── nginx.conf
└── docker-compose.yml
```

## 🚀 Tecnologías incluidas

- **Node.js**: Backend con Express.
- **PostgreSQL**: Base de datos relacional.
- **pgAdmin**: Cliente web para gestionar PostgreSQL.
- **Nginx**: Proxy reverso para exponer la app de forma profesional.
- **Docker Compose**: Orquestación de servicios.

## ⚙️ Instrucciones de uso

### 1. Clonar o descargar este repositorio

```bash
git clone <url-del-repo>
cd project-root
```

### 2. Construir y levantar los servicios

```bash
docker-compose up -d --build
```

### 3. Acceder a los servicios

- App Node.js: [http://localhost](http://localhost)
- pgAdmin: [http://localhost:8080](http://localhost:8080)
  - Usuario: `admin@admin.com`
  - Contraseña: `admin`

### 4. Configurar conexión en pgAdmin

1. Entrar a pgAdmin y crear un nuevo servidor.
2. Pestaña **General**:
   - Nombre: `PostgreSQL`
3. Pestaña **Connection**:
   - Host name: `db`
   - Username: `postgres`
   - Password: `postgres`
   - Database: `mydatabase`

## 🧪 Probar la conexión

Al entrar a [http://localhost](http://localhost), deberías ver la hora actual obtenida desde PostgreSQL.

## 🧼 Parar y limpiar

```bash
docker-compose down
```

Si querés borrar volúmenes y todo:

```bash
docker-compose down -v
```

## 📌 Notas

- El contenedor de Nginx actúa como proxy y redirige el tráfico a la app Node.js.
- Las variables de entorno están definidas directamente en `docker-compose.yml`. Podés externalizarlas con `.env` si lo preferís.

## 📄 Licencia

Este proyecto es de uso libre para fines educativos y profesionales.
