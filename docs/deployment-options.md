# Options de déploiement (Vercel exclu)

Objectif: proposer plusieurs cibles, avec avantages/limites et cas d’usage. Le choix doit être justifié dans le Google Doc d’équipe.

## Front-end (static/SSR)
- Netlify (static/SSR via adapters limités)
  - + Simple, previews PR
  - − SSR limité selon framework
- GitHub Pages (static)
  - + Très simple pour sites statiques/docs
  - − Pas de SSR natif
- Cloudflare Pages (static/SSR Workers)
  - + Edge, SSR Workers, cache
  - − Modèle Workers à appréhender

## Back-end (API) et DB
- Render / Railway
  - + Déploiement rapide, logs, DB managée
  - − Ressources gratuites limitées, cold starts possibles
- Fly.io
  - + Déploiement proche utilisateur, Docker
  - − Courbe d’apprentissage
- Heroku (selon plans disponibles)
  - + Simplicité, add-ons DB
  - − Coûts, plans évolutifs
- VPS (OVH/Scaleway/Hetzner) + Docker Compose
  - + Contrôle total, PHP/Node/Java/Python au choix
  - − Maintenance, sécurité à gérer

## PHP (Laravel/Symfony)
- PaaS compatibles PHP (Render, Railway, Clever Cloud)
  - + Buildpacks PHP, déploiement simplifié
  - − Coûts/limitations selon plan
- VPS + Nginx/Apache + PHP-FPM
  - + Souplesse totale, SSR Blade/Twig
  - − Administration et CI à soigner

## Bonnes pratiques
- Séparer environnements (dev/staging/prod) 
- Variables d’environnement (secrets) gérées via la plateforme
- Health checks et logs accessibles
- Backups DB programmés

## Exemple: Dockerfile (Node API minimal)
```dockerfile
FROM node:lts-alpine AS deps
WORKDIR /app
COPY package*.json ./
RUN npm ci --only=production

FROM node:lts-alpine
WORKDIR /app
COPY --from=deps /app/node_modules ./node_modules
COPY . .
EXPOSE 3000
CMD ["node", "dist/server.js"]
```
