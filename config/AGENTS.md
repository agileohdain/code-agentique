---
description: Consignes d'équipe que l'agent doit respecter dans ce dépôt. Personnalisez pour chaque projet.
---

# Consignes du dépôt

## Commandes à connaître

- Tester : `pytest` (ou la commande du projet)
- Linter : `ruff` (ou équivalent)

## Règles d'équipe

- Lire le contexte du fichier touché (imports, usages) avant toute modification.
- Ne pas ajouter de dépendance sans justification écrite dans la PR.
- Suivre les conventions de nommage et de style déjà présentes (ne pas réécrire dans un autre style).
- Pas de secrets dans le code : config par variables d'environnement.
- Après une modification, vérifier que les tests passent et le signaler.
- Commentaires en français, code et messages de commit en français (ou selon convention du client).

## Pièges connus (à compléter au fil des missions)

- (Exemple) : les migrations de base se font via `alembic`, jamais à la main.
- (Exemple) : ne pas toucher au dossier `notebooks/` sans accord.