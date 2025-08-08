# BridgeFit (Demo Compleja, Similar a BridgeAthletic)

Aplicación web full-stack con Next.js (App Router), Prisma + SQLite, NextAuth (credenciales), Tailwind CSS, Zustand, dnd-kit, Recharts y react-big-calendar.

Incluye:
- Autenticación de usuarios (registro e inicio de sesión).
- Roles: ADMIN, COACH, ATHLETE (con middleware de protección).
- CRUD de ejercicios (públicos y privados).
- Constructor de programas (drag & drop) con guardado en JSON.
- Dashboard con calendario y gráficas de progreso (demo).
- Seed de datos con usuarios y ejercicios.

## Requisitos

- Node.js 18 o superior
- npm 9 o superior

## Instalación y ejecución

1) Clonar este repo (o copiar los archivos):
   - Asegúrate de tener todos los archivos tal cual.

2) Instalar dependencias:
   ```
   npm install
   ```

3) Variables de entorno:
   - Copia `.env.example` a `.env` y ajusta si es necesario:
   ```
   cp .env.example .env
   ```
   - Asegúrate de definir `NEXTAUTH_SECRET` (si no, NextAuth genera uno aleatorio en dev).

4) Preparar Prisma (DB SQLite local):
   ```
   npx prisma generate
   npx prisma migrate dev --name init
   npm run prisma:seed
   ```

5) Ejecutar en desarrollo:
   ```
   npm run dev
   ```
   App en: http://localhost:3000

### Usuarios seed

- Admin:
  - Email: admin@example.com
  - Password: Password123!
- Coach:
  - Email: coach@example.com
  - Password: Password123!
- Athlete:
  - Email: athlete@example.com
  - Password: Password123!

## Scripts útiles

- `npm run dev` — Desarrollo
- `npm run build` — Build producción
- `npm start` — Iniciar en producción
- `npm run prisma:studio` — Prisma Studio
- `npm run prisma:seed` — Seed base de datos

## Estructura

- `app/` — Rutas y páginas (App Router)
- `app/api/` — Endpoints (route handlers)
- `components/` — Componentes UI
- `lib/` — Utilidades (Prisma, NextAuth config)
- `prisma/` — Esquema y Seed
- `store/` — Estado global (Zustand)
- `types/` — Tipos expandidos (NextAuth)

## Notas

- La subida de imágenes en ejercicios, para simplificar, se maneja como URL (campo `mediaUrl`). Puedes ampliar con uploads locales o a S3.
- La estructura del plan de programa se guarda en `Program.plan` (JSON). Puedes normalizar a más tablas si lo deseas.
- Cambiar a Postgres: Ajusta `provider` en `schema.prisma`, variables de entorno `DATABASE_URL` y ejecuta migraciones.

¡Disfruta construyendo sobre esta base!