<p align="center">
  <img src="assets/cafe-app.svg" alt="Coffee cup icon for Cafe App" width="160">
</p>

<h1 align="center">Cafe App</h1>

<p align="center">
  <img alt="TypeScript" src="https://img.shields.io/badge/language-TypeScript-3178C6?logo=typescript&logoColor=white">
  <img alt="Turborepo" src="https://img.shields.io/badge/monorepo-Turborepo-EF4444?logo=turborepo&logoColor=white">
  <img alt="PostgreSQL" src="https://img.shields.io/badge/database-PostgreSQL-4169E1?logo=postgresql&logoColor=white">
</p>

> Cafe App is a pnpm/Turborepo workspace containing a Next.js web client and an Express API.

The current web page is a starter screen, and the API currently exposes a greeting and health check. PostgreSQL is configured through Docker Compose.

## Projects

| Directory | Purpose | Stack |
| --- | --- | --- |
| apps/web/ | Next.js client; the current home page is a Hello World placeholder. | Next.js, React, TypeScript |
| apps/api/ | Express API with PostgreSQL connection setup. | Express, TypeScript, pg |
| packages/eslint-config/ | Shared ESLint configurations. | ESLint |
| packages/typescript-config/ | Shared TypeScript configurations. | TypeScript |

## Requirements

- Node.js 20 or newer
- pnpm 9, available through Corepack
- Docker Compose for PostgreSQL

## Run locally

Create a repository-root .env file for Docker Compose, with the database values:

<pre><code>DATABASE_NAME=ecommerce-cafe
DATABASE_USER=cafe
DATABASE_PASSWORD=change-me</code></pre>

Start PostgreSQL and install the workspace dependencies:

<pre><code>corepack enable
pnpm install
docker compose up -d db</code></pre>

For the API process running on your host, put the same database name, user, and password in apps/api/.env and set DATABASE_HOST=127.0.0.1 and DATABASE_PORT=5432. In separate terminals, run:

<pre><code>pnpm --filter api dev
pnpm --filter web dev</code></pre>

The API listens on port 3001; the web client runs at [http://localhost:3000](http://localhost:3000). The current Docker Compose API service is not part of these local run instructions; its host binding needs configuration before exposing it through the published port.

## API routes

| Method | Route | Purpose |
| --- | --- | --- |
| GET | /api/v1/ | Returns the API greeting. |
| GET | /api/v1/healthy | Returns a health status. |

## Workspace commands

| Command | Purpose |
| --- | --- |
| pnpm dev | Run package development tasks through Turborepo. |
| pnpm build | Build workspace packages. |
| pnpm lint | Lint workspace packages. |
| pnpm check-types | Run workspace type checks. |
| pnpm format | Format TypeScript and Markdown files. |

## Git workflow

The permanent branches are main and test. Create feature or fix branches from main, merge them into test for validation, and merge approved changes into main.

<pre><code>git checkout main
git checkout -b feature/name
# develop and commit the change
git checkout test
git merge feature/name
git push origin test
# after approval:
git checkout main
git merge feature/name
git push origin main</code></pre>
