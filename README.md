# Reachyn

Sistema distribuido de mensajería en tiempo real inspirado en Discord/WhatsApp/Uber, construido con una arquitectura moderna enfocada en escalabilidad, concurrencia y comunicación realtime.

## Objetivo del proyecto

Este proyecto fue creado para demostrar conocimientos reales de:

* WebSockets
* Sistemas distribuidos
* Networking
* Comunicación realtime
* Redis Pub/Sub
* Concurrencia
* Escalabilidad horizontal
* Backend architecture
* TypeScript estricto
* Docker

La idea no es construir un clon visual de Discord, sino una infraestructura realtime moderna y escalable.

---

# Stack Tecnológico

## Backend

* Node.js 22 LTS
* TypeScript (strict mode)
* Fastify
* WebSockets con `@fastify/websocket`
* PostgreSQL 16
* Redis 7
* Drizzle ORM
* Zod
* JOSE (JWT)
* bcryptjs

## Frontend

* React
* TypeScript
* Vite
* Tailwind CSS
* TanStack Query

## Infraestructura

* Docker
* Docker Compose

---

# Arquitectura

```text
Frontend React
       |
       | HTTP + WebSockets
       v
Fastify Backend
       |
       | Redis Pub/Sub
       v
Multiple Backend Nodes
       |
       v
PostgreSQL
```

---

# Características Planeadas

## Auth

* Registro de usuarios
* Login
* JWT Authentication
* Password hashing
* Middleware de autenticación

## Realtime

* WebSocket connections
* Presence system
* Typing indicators
* Realtime messaging
* Rooms/channels
* Heartbeat & ping/pong
* Reconnection handling

## Distribuido

* Redis Pub/Sub
* Multiple backend instances
* Horizontal scaling
* Distributed event broadcasting

---

# Estructura del proyecto

```text
reachyn/
├── docker-compose.yml
├── README.md
├── .env.example
├── .gitignore
├── backend/
│   ├── package.json
│   ├── tsconfig.json
│   ├── src/
│   │   ├── server.ts
│   │   ├── routes/
│   │   ├── db/
│   │   └── lib/
│   └── drizzle/
└── frontend/
    ├── package.json
    ├── vite.config.ts
    └── src/
```

---

# Instalación

## 1. Clonar el repositorio

```bash
git clone <repo-url>
cd reachyn
```

---

## 2. Variables de entorno

Crear un archivo `.env` en la raíz del proyecto:

```env
DATABASE_URL=postgresql://reachyn:dev_password@localhost:5432/reachyn
REDIS_URL=redis://localhost:6380
JWT_SECRET=super_secret_dev_key
```

---

## 3. Levantar infraestructura

```bash
docker compose up -d
```

Verificar:

```bash
docker compose ps
```

Los servicios deben aparecer como `healthy`.

---

## 4. Backend

```bash
cd backend
npm install
npm run dev
```

Servidor:

```text
http://localhost:3000
```

Healthcheck:

```text
GET /health
```

---

## 5. Frontend

```bash
cd frontend
npm install
npm run dev
```

Frontend:

```text
http://localhost:5173
```

---

# Scripts

## Backend

```bash
npm run dev
npm run build
npm run start
```

## Frontend

```bash
npm run dev
npm run build
npm run preview
```

---

# Roadmap

## Fase 0

* [x] Monorepo setup
* [x] Docker infrastructure
* [x] PostgreSQL
* [x] Redis
* [x] Fastify server
* [x] Frontend setup

## Fase 1

* [ ] Database schema
* [ ] Drizzle configuration
* [ ] User authentication
* [ ] JWT auth

## Fase 2

* [ ] WebSocket server
* [ ] Connection manager
* [ ] Presence system
* [ ] Rooms/channels

## Fase 3

* [ ] Realtime messaging
* [ ] Persistent messages
* [ ] Typing indicators
* [ ] Reconnection handling

## Fase 4

* [ ] Redis Pub/Sub
* [ ] Distributed events
* [ ] Horizontal scaling
* [ ] Multi-node architecture

---

# Filosofía del proyecto

Este proyecto prioriza:

* Simplicidad
* Arquitectura limpia
* Type safety
* Realtime systems
* Escalabilidad
* Backend engineering

Evita complejidad innecesaria y frameworks excesivos para enfocarse en fundamentos sólidos de sistemas distribuidos.

---

# Estado actual

Proyecto en desarrollo.

Actualmente se encuentra en construcción de la infraestructura base y arquitectura backend.

---

# Licencia

MIT
