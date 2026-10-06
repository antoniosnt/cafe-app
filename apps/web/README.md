<p align="center">
  <img src="../../assets/cafe-app.svg" alt="Cafe App icon" width="140">
</p>

<h1 align="center">Cafe App Web</h1>

<p align="center">
  <img alt="Next.js" src="https://img.shields.io/badge/web-Next.js-000000?logo=next.js&logoColor=white">
  <img alt="React" src="https://img.shields.io/badge/UI-React-61DAFB?logo=react&logoColor=black">
  <img alt="TypeScript" src="https://img.shields.io/badge/language-TypeScript-3178C6?logo=typescript&logoColor=white">
</p>

> Next.js frontend workspace for Cafe App.

## Usage

From the cafe-app repository root:

<pre><code>corepack enable
pnpm install
pnpm --filter web dev</code></pre>

Open [http://localhost:3000](http://localhost:3000). The current home page displays a placeholder greeting.

## Scripts

| Command | Purpose |
| --- | --- |
| pnpm --filter web dev | Start the Next.js development server. |
| pnpm --filter web build | Build the web app. |
| pnpm --filter web lint | Run ESLint. |
| pnpm --filter web check-types | Generate route types and check TypeScript. |

The app uses the shared workspace packages @repo/eslint-config and @repo/typescript-config.
