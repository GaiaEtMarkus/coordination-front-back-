# Compte Rendu - Module Coordination Front & Back
**Date :** Octobre 2025  
**Formateur :** Akram Boukhers  
**Reprise :** [Nom du collègue]

---

## 🎯 Vue d'ensemble du module

### Objectif principal
Ce module vise à former les étudiants à la **coordination entre équipes front-end et back-end** dans un contexte de développement web moderne, en mettant l'accent sur les bonnes pratiques industrielles.

### Durée et organisation
- **Équipes :** Groupes de 4 étudiants (2 front + 2 back)
- **Rôles :** Spécialisation stable (pas de rotation imposée)
- **Livrable :** Une V1 fonctionnelle en fin de parcours

---

## 📋 Objectifs pédagogiques détaillés

### 1. Coordination d'équipe
- Superviser la coordination FE/BE (réunions, décisions, traçabilité)
- Mettre en place des revues de code (PR reviews obligatoires)
- Gérer la communication inter-équipes

### 2. Architecture et contrats
- Concevoir des contrats d'API REST en mode **contract-first** (OpenAPI 3.1)
- Générer des types partagés côté front à partir du contrat
- Éviter les dérives entre spécification et implémentation

### 3. Qualité et tests
- Mettre en place une stratégie de tests adaptée (unitaires, intégration, e2e)
- Atteindre une couverture de code ≥ 50%
- Justifier le choix du mix de tests selon les risques

### 4. Déploiement et CI/CD
- Configurer l'intégration continue (GitHub Actions recommandé)
- Déployer des services front et back
- Diversifier les plateformes de déploiement (Vercel exclu)

### 5. Documentation et communication
- Documenter les décisions techniques
- Présenter les livrables (vidéos de 10 min par équipe)
- Maintenir un Google Doc de sprint

---

## 🛠️ Stack technique (libre)

### Front-end
- **Technologies :** React, Vue, Angular, Svelte, etc.
- **Rendu :** SPA autorisé, SSR possible si justifié (SEO, TTFB)

### Back-end
- **Technologies :** Node/Express/Nest, Python/FastAPI/Django, Java/Spring, PHP/Laravel/Symfony
- **Architecture :** API REST contract-first

### Base de données
- **Recommandée :** PostgreSQL
- **Alternatives :** MySQL, MongoDB, etc.

### Outils de développement
- **Versioning :** Git avec GitFlow
- **CI/CD :** GitHub Actions
- **Gestion de projet :** Jira recommandé
- **Tests :** Outils libres selon la stack

---

## 📚 Ressources pédagogiques disponibles

### Site web créé
Un site web complet a été développé avec les ressources suivantes :

#### Pages principales
- **Accueil :** Vue d'ensemble du programme
- **Guide API First :** Méthodologie contract-first avec OpenAPI
- **GitFlow & Agile :** Organisation des branches et philosophie agile
- **Gestion de projet :** Outils (Jira), CI/CD, étapes pré-développement
- **Livrables V1 :** Checklist complète des exigences
- **Tests :** Stratégies FE/BE (unit, intégration, e2e)
- **Déploiement :** Options et bonnes pratiques
- **GitHub Workflow :** Processus Git et GitHub

#### Contenu technique
- **Exemples concrets** de spécifications OpenAPI
- **Stratégies de tests** avec justification du mix
- **Options de déploiement** (Netlify, GitHub Pages, Cloudflare, Render, Railway, Fly.io, Heroku, VPS)
- **Bonnes pratiques** pour chaque technologie

---

## 🎯 Projet fil rouge

### Périmètre libre
Les étudiants choisissent leur projet parmi les suggestions suivantes :
- Marketplace de services (freelancing local)
- Système de réservation (salles, événements)
- Helpdesk/CRM léger (tickets, commentaires, rôles)
- SaaS de to-do partagé avec rôles et notifications
- Mini-ERP stock/commandes (scopes réduits)

### Exigences techniques
1. **API REST contract-first** avec OpenAPI 3.1
2. **Types partagés** générés côté front
3. **Tests** avec couverture ≥ 50%
4. **CI/CD** opérationnel
5. **Déploiement** fonctionnel (Vercel exclu)
6. **Documentation** complète

---

## 📋 Livrables V1 (checklist complète)

### Repos et gouvernance
- [ ] Dépôts Git créés (front + back ou monorepo)
- [ ] Protection des branches principales
- [ ] CI/CD configuré et fonctionnel
- [ ] Structure de projet initialisée

### Contrat d'API
- [ ] Spécification OpenAPI 3.1 complète
- [ ] Types partagés générés côté front
- [ ] Documentation API accessible
- [ ] Validation des contrats

### Implémentation
- [ ] API REST fonctionnelle
- [ ] Front-end connecté à l'API
- [ ] Authentification implémentée
- [ ] Gestion d'erreurs unifiée

### Qualité
- [ ] Tests unitaires (BE)
- [ ] Tests d'intégration (BE)
- [ ] Tests e2e (FE)
- [ ] Couverture ≥ 50%
- [ ] Linting et formatage

### Déploiement
- [ ] Environnement de production
- [ ] Base de données déployée
- [ ] Monitoring basique
- [ ] Documentation de déploiement

### Documentation & présentations
- [ ] Google Doc de sprint
- [ ] Vidéo présentation back (10 min)
- [ ] Vidéo présentation front (10 min)
- [ ] README complet

---

## 🔄 Cérémonies et processus

### Daily
- **Fréquence :** Début de chaque session
- **Objectif :** Synchronisation et planification

### Revues de code
- **Obligatoire :** PR reviews pour chaque modification
- **Protection :** Branches protégées avec checks CI

### Rétrospectives
- **Fréquence :** Cours suivant
- **Objectif :** Amélioration continue

---

## 🎓 Points pédagogiques clés

### Pourquoi contract-first ?
- Aligne FE/BE avant le code
- Réduit les reworks
- Permet la génération de types
- Facilite les tests de contrat
- Documentation vivante

### Pourquoi GitFlow ?
- Séparation claire des environnements
- Travail en parallèle sans conflits
- Gestion des releases et hotfixes
- Traçabilité des modifications

### Pourquoi tests ≥ 50% ?
- Seuil réaliste en contexte pédagogique
- Force l'automatisation
- Adapte le mix selon les risques
- Bonnes pratiques industrielles

---

## 📊 Évaluation

### Critères techniques
- Fonctionnalité de la V1
- Qualité du code (tests, couverture)
- Architecture et contrats
- Déploiement opérationnel

### Critères de coordination
- Communication inter-équipes
- Documentation des décisions
- Gestion des risques
- Respect des processus

### Critères de présentation
- Vidéos de démonstration
- Documentation complète
- Justification des choix techniques

---

## 🚀 Prochaines étapes pour le collègue

### À faire immédiatement
1. **Prendre connaissance** du site web créé
2. **Lire les ressources** disponibles
3. **Comprendre** les exigences techniques
4. **Préparer** les premières sessions

### Points d'attention
- **Contract-first** est une exigence forte
- **Tests ≥ 50%** doivent être justifiés
- **Vercel exclu** pour le déploiement
- **PR reviews** obligatoires

### Support disponible
- Site web complet avec toutes les ressources
- Exemples concrets de spécifications
- Checklist détaillée des livrables
- Bonnes pratiques par technologie

---

## 📞 Contact et ressources

- **Site web :** [URL du site]
- **Documentation :** Dossier `docs/` avec tous les détails
- **Exemples :** Fichiers de spécifications OpenAPI
- **Support :** Akram Boukhers (transition)

---

*Ce compte rendu synthétise l'ensemble du module et des ressources créées. Le site web contient tous les détails techniques et pédagogiques nécessaires pour la reprise du cours.*
