<p align="center">
  <img src="../../assets/cafe-app.svg" alt="Shared Cafe App tooling icon" width="130">
</p>

<h1 align="center">@repo/eslint-config</h1>

<p align="center">
  <img alt="ESLint" src="https://img.shields.io/badge/tooling-ESLint-4B32C3?logo=eslint&logoColor=white">
  <img alt="TypeScript" src="https://img.shields.io/badge/language-TypeScript-3178C6?logo=typescript&logoColor=white">
</p>

> Shared ESLint presets for packages in the Cafe App pnpm workspace.

## Exports

The package exposes three workspace presets:

| Import path | Intended use |
| --- | --- |
| @repo/eslint-config/base | Base JavaScript and TypeScript lint rules. |
| @repo/eslint-config/next-js | Next.js-specific rules. |
| @repo/eslint-config/react-internal | React library rules. |

## Use in the workspace

Add the package as a workspace development dependency, then import the preset from the package's ESLint configuration file. The Cafe App web package already depends on this shared config.

## Maintenance

Edit the preset files in this directory when shared lint rules need to change. Keep framework-specific rules in their matching preset.
