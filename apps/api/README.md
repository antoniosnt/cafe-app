<p align="center">
  <img src="../../assets/cafe-app.svg" alt="Cafe App API icon" width="140">
</p>

<h1 align="center">Cafe App API</h1>

<p align="center">
  <img alt="Express" src="https://img.shields.io/badge/API-Express-000000?logo=express&logoColor=white">
  <img alt="TypeScript" src="https://img.shields.io/badge/language-TypeScript-3178C6?logo=typescript&logoColor=white">
  <img alt="PostgreSQL" src="https://img.shields.io/badge/database-PostgreSQL-4169E1?logo=postgresql&logoColor=white">
</p>

> Express API starter for the Cafe App workspace.

## Usage

Start PostgreSQL with Docker Compose from the repository root. Configure the root .env values for the database, and create apps/api/.env for the host-run API process with the same credentials plus DATABASE_HOST=127.0.0.1 and DATABASE_PORT=5432.

From the cafe-app root:

<pre><code>corepack enable
pnpm install
docker compose up -d db
pnpm --filter api dev</code></pre>

The API listens on port 3001.

## Routes

| Method | Route | Purpose |
| --- | --- | --- |
| GET | /api/v1/ | Returns a short API greeting. |
| GET | /api/v1/healthy | Returns a health status. |

Other paths return a JSON 404 response. The API is currently a starting point; cafe-specific business endpoints are not implemented yet.
