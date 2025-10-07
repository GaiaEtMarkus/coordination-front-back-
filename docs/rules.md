# Règles et attentes

## Équipes et dépôts
- Groupes de 4: 2 front, 2 back. Pas de rotation de rôles imposée.
  - Pourquoi: favoriser la spécialisation et la responsabilité claire.
- Repos: un repo par équipe front et un repo par équipe back, sauf monorepo si l’équipe le décide explicitement.
  - Pourquoi: multi-repo simule des frontières d’équipe réelles; monorepo facilite le partage de types et la CI commune.

## Cérémonies
- Daily au début de chaque session de travail.
  - Pourquoi: synchroniser, détecter tôt les risques, planifier la journée.
- Travail en groupe ensuite, revues de code mutuelles (PR reviews obligatoires).
  - Pourquoi: qualité, partage de connaissance, traçabilité des décisions.
- Rétro au cours suivant.
  - Pourquoi: boucle d’amélioration continue sur process et technique.

## Contrats d’API
- REST, contract-first (OpenAPI 3.1).
  - Pourquoi: spécifier avant de coder, aligner FE/BE, permettre génération de types et doc vivante.
- Types partagés côté front générés depuis la spec (solution simple recommandée). Alternatives permises si argumentées.
  - Pourquoi: une source de vérité, moins d’ambiguïtés et de divergences.

## Qualité et tests
- Tests unitaires, d’intégration et/ou e2e: libre, mais justifier la stratégie.
  - Pourquoi: adapter l’effort de test aux risques spécifiques du projet.
- Couverture cible: ≥ 50% en fin de parcours (global, indicatif minimal).
  - Pourquoi: seuil réaliste qui force un minimum d’automatisation sans figer les choix.

## Git et gouvernance
- Branches de features, PR obligatoires, reviews requises.
  - Pourquoi: prévenir les régressions et encourager le design collaboratif.
- Conventional Commits recommandés.
  - Pourquoi: générer des changelogs clairs et standardiser l’historique.
- Protections de branches (au minimum: checks CI et 1 review).
  - Pourquoi: instaurer des garde-fous automatiques.

## Tech et rendu serveur
- Back-end: libre (Node/Express/Nest, Python/FastAPI/Django, Java/Spring, PHP/Laravel ou Symfony).
  - Pourquoi: exposer les étudiants à des choix réels, contraintes et arbitrages.
- SSR autorisé (Next.js/Nuxt, Laravel/Symfony) si justifié par SEO/TTFB/expérience produit.

## Traçabilité et livrables annexes
- Google Doc par équipe: comptes rendus de cérémonies, décisions, risques, liens vers PR majeures.
  - Pourquoi: trace consultable par toutes les parties prenantes.
- Vidéos de présentation: 10 min équipe back + 10 min équipe front (YouTube non répertorié).
  - Pourquoi: capacité à communiquer les choix techniques et résultats.

## Déploiement
- CI: GitHub Actions conseillé.
  - Pourquoi: intégration facile avec GitHub et checks PR standard.
- Déploiement: au choix (PaaS/IaaS/container), Vercel exclu.
  - Pourquoi: diversifier la compréhension des plateformes; éviter un lock-in unique.
