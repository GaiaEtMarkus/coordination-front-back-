# Outils et versions (avec pourquoi)

Objectif: proposer des outils courants, expliquer pourquoi, et indiquer comment choisir la dernière version stable.

## Runtimes et langages
- Node.js (LTS/Current)
  - Pourquoi: écosystème riche FE/BE, intégration CI simple.
  - Vérifier la version: `node -v` / `nvm ls-remote --lts`
- Python (3.11+ / 3.12+)
  - Pourquoi: FastAPI/Django, tooling data/perf varié.
  - Vérifier: `python --version`
- Java (17/21 LTS)
  - Pourquoi: Spring, robustesse, tooling mature.
  - Vérifier: `java -version`
- PHP (8.2+ / 8.3+)
  - Pourquoi: Laravel, Symfony, SSR via Blade/Twig, écosystème web éprouvé.
  - Vérifier: `php -v`

## Frameworks front
- React / Vue / Angular / Svelte (libre)
  - Pourquoi: couvrir les paradigmes majoritaires FE.
  - SSR possible: Next.js (React), Nuxt (Vue).

## Frameworks back
- Node: Express / NestJS
  - Pourquoi: productivité, TypeScript, intégration OpenAPI facile.
- Python: FastAPI / Django (DRF)
  - Pourquoi: expressivité, outillage OpenAPI.
- Java: Spring Boot
  - Pourquoi: robustesse, écosystème entreprise.
- PHP: Laravel / Symfony
  - Pourquoi: MVC/SSR, API Platform (Symfony) utile pour REST.

## Bases de données
- Relationnelles: PostgreSQL (recommandé), MySQL/MariaDB
  - Pourquoi: transactions, intégrité, SQL mature.
- NoSQL: MongoDB
  - Pourquoi: schéma flexible, prototypage rapide.

## Spec et outils API
- OpenAPI 3.1 (contract-first)
  - Pourquoi: une source de vérité, génération de types, doc vivante.
- Swagger UI/Editor, Redoc/Stoplight, Postman
  - Pourquoi: conception, visualisation, tests rapides.
- Génération de types FE
  - Exemple Node: `npx openapi-typescript path/to/openapi.yaml -o src/types/api.d.ts`

## Tests
- FE: Jest/Vitest + Testing Library; E2E: Cypress/Playwright
- BE: Jest/Vitest/pytest/JUnit; intégration: Testcontainers (DB), supertest
- Pourquoi: couvrir unit/int/e2e avec tooling standard.

## CI/CD
- GitHub Actions
  - Pourquoi: intégré à GitHub, marketplace d’actions, checks PR.
  - Exemple Node CI (lint+test):
```yaml
name: ci
on: [push, pull_request]
jobs:
  node:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with:
          node-version: 'lts/*'
      - run: npm ci
      - run: npm run lint --if-present
      - run: npm test --if-present -- --ci
```

## Conseils de version
- Préférer LTS pour back-ends et CI; autoriser Current pour FE si besoin d’APIs récentes.
- Documenter les versions choisies dans le README de chaque repo.
