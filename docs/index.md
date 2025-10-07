# Coordination Front & Back — Course Home

Bienvenue. Ce site regroupe les règles, attentes et livrables du module. Le périmètre du projet fil rouge est libre; une V1 est exigée en fin de parcours.

## Navigation
- [Règles et attentes](./rules.md)
- [Livrables V1](./deliverables.md)
- [Workflow Git/GitHub](./github-workflow.md)
- [Outils et versions](./tools-and-versions.md)
- [Options de déploiement](./deployment-options.md)
- [Exemples et sujets de discussion](./examples.md)
- [Tests FE/BE (unit, intégration, e2e)](./testing.md)

## Ressources
- [Guide – API First avec OpenAPI (PDF)](./ressources/openApi.pdf)

## Objectifs pédagogiques (synthèse)
- Superviser la coordination FE/BE (réunions, décisions, traçabilité, PR reviews).
- Concevoir des contrats d’API REST en mode contract-first (OpenAPI 3.1).
- Mettre en place CI/CD et déployer des services front et back.
- Garantir la qualité (tests unitaires/intégration/e2e, coverage ≥ 50%).
- Documenter et présenter les livrables (Google Doc de sprint, vidéos FE/BE).

## Pourquoi ces exigences ?
- Contract-first (OpenAPI 3.1): aligne FE/BE avant le code, réduit les reworks, permet la génération de types côté front, facilite tests de contrat et documentation vivante. Alternative code-first possible, mais souvent source de dérives et de specs obsolètes.
- Types partagés générés depuis la spec: une seule source de vérité, moins d’ambiguïtés, DX plus fluide côté front. Alternatives (modèles manuels, Zod/JSON Schema) OK si argumentées.
- Coverage ≥ 50%: seuil réaliste en contexte pédagogique avec périmètre libre; l’important est de choisir un mix pertinent (unit/int/e2e) selon les risques (ex: règles métier complexes → unit, intégrations DB→int, parcours critique→e2e).
- PR reviews + protections de branches: forcent la discussion technique, la relecture et la qualité continue; évitent les merges cassants.

## Organisation des équipes
- Groupes de 4: 2 front, 2 back. Rôles stables (pas de rotation imposée).
- Repos: un repo par équipe front et un repo par équipe back, sauf monorepo si choisi.
- Cérémonies: daily en début de session; revues de code mutuelles; rétro au cours suivant.

## Stacks et styles d’app
- Front: libre (React, Vue, Angular, Svelte, etc.).
- Back: libre (Node/Express/Nest, Python/FastAPI/Django, Java/Spring, PHP/Laravel ou Symfony).
- Rendu côté serveur (SSR): autorisé (ex: Next.js/Nuxt, Laravel/Symfony SSR) si justifié par SEO, TTFB ou contraintes produit.
- Base de données: libre (PostgreSQL recommandé, MySQL, MongoDB, etc.).

## Contrats et types
- API REST, contract-first (OpenAPI 3.1). Types partagés générés côté front à partir du contrat (solution simple recommandée).

## Qualité
- Tests: unitaires et/ou intégration et/ou e2e, avec justification du mix.
- Couverture cible: au moins 50% en fin de parcours.

## Déploiement
- CI: GitHub Actions recommandé.
- Déploiement: au choix (PaaS/IaaS/container), Vercel exclu.
