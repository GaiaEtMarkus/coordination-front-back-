# Workflow Git/GitHub

## Branching
- Branche `main` protégée (pas de commit direct).
- Branches de features par tâche: `feat/...`, `fix/...`, `chore/...`, `docs/...`, `refactor/...`.
- PR obligatoires depuis une branche de feature vers `main`.

## Reviews et protections
- Au moins 1 review approuvée.
- Checks CI requis (lint, tests, build) avant merge.
- Interdire push forcé sur `main`. Option: « Require linear history ».

## Conventional Commits (exemples)
- `feat(items): add pagination to list endpoint`
- `fix(api): handle 400 on invalid payload`
- `docs(readme): add usage instructions`
- `refactor(front): simplify state handling`
- `chore(ci): add coverage upload`

## Checklist PR (minimum)
- Motif du changement clair (issue/story liée si possible)
- Impact FE/BE/DB mentionné
- Tests ajoutés/ajustés + couverture inchangée ou en hausse
- Documentation mise à jour (spec, README, Postman)

## Releases
- Tag `v1.0.0` pour la V1
- Notes de version: changements, breaking changes, migrations

## Bonnes pratiques
- Petites PRs, atomiques et fréquentes
- Discuter tôt les breaking changes (PR de spec d’abord)
- Lier les PR importantes dans le Google Doc d’équipe
