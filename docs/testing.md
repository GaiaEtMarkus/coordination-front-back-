# Tests FE/BE — unitaires, intégration, e2e

## FE vs BE — définitions rapides
- FE (Front-end): code exécuté côté client (navigateur/app), UI/UX, état local, appels API.
- BE (Back-end): code côté serveur, logique métier, accès base de données, sécurité, API.

Pourquoi distinguer ? Les risques et outils diffèrent: le FE teste interactions UI/DOM et flux utilisateurs, le BE teste règles métier, persistance et contrats d’API.

---

## Tests unitaires
- Quoi: tester une unité de code isolée (fonction, composant, service) sans dépendances externes réelles.
- Pourquoi: rapides, détectent les régressions locales, documentent la logique métier.
- FE exemples:
  - Valider un utilitaire de formatage de prix.
  - Tester un composant pur (render d’un titre selon props) avec mocks pour dépendances.
- BE exemples:
  - Valider une règle métier (calcul de remise, quotas) sans DB réelle.
  - Tester un service qui transforme un DTO.
- Outils typiques:
  - FE: Jest/Vitest + Testing Library (pour composants en isolation minimale).
  - BE: Jest/Vitest/pytest/JUnit, mocks/stubs.

## Tests d’intégration
- Quoi: tester l’interaction entre plusieurs modules réels (ex: service + DB, contrôleur + service) dans un environnement proche de la réalité.
- Pourquoi: attrapent les problèmes d’assemblage (schémas, transactions, configuration), valident les contrats d’API.
- FE exemples:
  - Tester un hook qui fait un fetch vers une API mockée locale.
  - Tester une page qui compose plusieurs composants et requêtes.
- BE exemples:
  - Tester un endpoint REST contre une DB ephemeral (SQLite in-memory, Testcontainers Postgres).
  - Vérifier validation, codes HTTP, modèle d’erreurs.
- Outils typiques:
  - FE: Testing Library avec MSW (Mock Service Worker).
  - BE: supertest/pytest + Testcontainers, bases de données temporaires.

## Tests end-to-end (e2e)
- Quoi: simuler le parcours utilisateur complet à travers l’app (FE) et le backend (ou un stub réaliste), dans un navigateur automatisé.
- Pourquoi: garantissent que le flux critique marche “de bout en bout” (auth, navigation, API, rendu, stockage).
- Exemples:
  - FE+BE: un utilisateur parcourt la liste → détail → ajoute au panier → passe commande.
  - BE isolé (API e2e): démarrer l’API, frapper les endpoints principaux via HTTP (sans navigateur) et vérifier side-effects.
- Outils typiques:
  - FE: Cypress, Playwright.
  - API: k6 pour perfs, mais pour e2e fonctionnel: Postman/Newman ou tests HTTP maison.

---

## Choisir le bon mix (et viser ≥ 50% de coverage)
- Règles métier complexes → prioriser les tests unitaires (BE) + quelques intégrations DB.
- Beaucoup d’intégrations externes → prioriser intégration (mocks contrôlés) + e2e smoke.
- Application très UI/UX → plus d’e2e ciblés sur parcours critiques, avec unitaires FE pour logique de présentation.

Stratégie type:
- 60% unit, 30% intégration, 10% e2e — ajuster selon risques.
- Quelques e2e “smoke” stables, plutôt que beaucoup de tests fragiles.

## Liens avec le contract-first
- La spec OpenAPI guide les tests d’intégration (codes, schémas, erreurs).
- Générer des clients/types depuis la spec réduit les mocks incohérents.
- Option avancée: tests de contrat (Pact) pour valider que le BE respecte ce que le FE consomme.
