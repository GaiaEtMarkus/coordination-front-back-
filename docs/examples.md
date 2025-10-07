# Exemples et sujets de discussion

Cette page propose des idées de projets et des points de discussion pour animer la coordination FE/BE.

## Idées de projets (périmètre libre)
- Marketplace de services (ex: freelancing local)
- Système de réservation (ex: salles, événements)
- Helpdesk/CRM léger (tickets, commentaires, rôles)
- SaaS de to-do partagé avec rôles et notifications
- Mini-ERP stock/commandes (scopes réduits)

Pour chaque idée, discutez:
- Entités métier clés et relations
- Parcours utilisateur critique (Happy path) et cas limites
- Contraintes: SEO, temps de réponse, sécurité, conformité

## Choix techniques — sujets de discussion
- REST contract-first vs code-first
  - Contract-first: alignment initial, types générés, doc vivante
  - Code-first: vitesse de prototypage, mais risque de divergence spec/code
- Front SPA vs SSR/SSG (Next/Nuxt, Laravel/Symfony SSR)
  - SSR: SEO et TTFB meilleurs, complexité de déploiement accrue
  - SPA: DX rapide, SEO plus complexe sans SSR
- DB relationnelle (PostgreSQL/MySQL) vs NoSQL (MongoDB)
  - Relationnelle: intégrité, transactions, SQL puissant
  - NoSQL: agilité sur schéma, scalabilité horizontale (scénarios spécifiques)
- Authentification
  - Session/cookies vs JWT stateless; impacts CORS, rotation de tokens
- Gestion des erreurs
  - Modèle d’erreurs unifié: code interne, message, trace id, mapping HTTP

## Exemple de spec OpenAPI (extrait)
```yaml
openapi: 3.1.0
info:
  title: Example Shop API
  version: 0.1.0
paths:
  /products:
    get:
      summary: List products
      parameters:
        - in: query
          name: q
          schema: { type: string }
      responses:
        '200':
          description: OK
          content:
            application/json:
              schema:
                type: array
                items:
                  $ref: '#/components/schemas/Product'
components:
  schemas:
    Product:
      type: object
      required: [id, name]
      properties:
        id: { type: string }
        name: { type: string }
        price: { type: number }
```

Questions:
- Quels filtres supplémentaires sont nécessaires (pagination, catégories) ?
- Quelles erreurs renvoyer si les paramètres sont invalides ?

## Exemple de stratégie de tests (mix ≥ 50% coverage)
- Unit (BE): validation des DTO, règles métier (prix mini, quotas)
- Intégration (BE): repository + DB, endpoints happy path
- e2e (FE): parcours achat minimal (liste → détail → panier)
- Justification: la majorité des risques étant métier côté back, priorité unit/int; e2e pour parcours critique.

## PHP Laravel/Symfony — discussion SSR/REST
- Laravel
  - Avantages: écosystème riche, Blade/SSR possible, Eloquent productif
  - Inconvénients: SSR + SPA hybride complexifie le déploiement
- Symfony
  - Avantages: structure claire, API Platform, Twig/SSR
  - Inconvénients: courbe d’apprentissage plus raide

Points à trancher si Laravel/Symfony:
- SSR complet (Blade/Twig) ou API REST + front séparé ?
- Auth: session/cookies (CSR/SSR) vs JWT (front séparé)
- Déploiement: PHP-FPM + Nginx/Apache, DB managée; runners CI adaptés
