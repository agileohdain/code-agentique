# 💡 06 — Tips et bonnes pratiques

> Les réflexes qui séparent "j'ai testé un agent" de "je travaille avec un agent".

## 🔁 La routine qui change tout (par tâche)

1. **`/compact` (ou nouvelle session) avant chaque nouvelle tâche** — un contexte à moitié oublié produit des résultats à moitié bons. Un agent frais sur une question précise bat un agent fatigué sur une question vague.
2. **Plan avant code** : demandez d'abord *"Propose un plan"*, validez, puis *"Implémente le plan"*. Vous arbitrez en amont au lieu de corriger en aval.
3. **Une session = une tâche** : ne mélangez pas "ajouter une feature" et "débugger l'existant".
4. **Donnez un critère de fin explicite** : *"fini, c'est quand les tests passent et que la PR est sous 200 lignes"* — pas *"fais ça"*.

## 🧰 Les outils à activer dès le départ

- **Ponytail** (skill anti-sur-ingénierie) : lit vos demandes comme un senior un peu paresseux — la solution la plus simple qui marche. À activer pour éviter le code sur-architecturé qui coûte cher à maintenir.
- **MCP Serena** : indexation symbolique du code. Indispensable dès que le repo dépasse quelques milliers de lignes. À ajouter dans `opencode.json` :

```json
"mcp": {
  "serena": {
    "type": "local",
    "command": ["npx", "-y", "@serena-ai/serena-mcp"],
    "enabled": true
  }
}
```

- **Config d'équipe versionnée** : `opencode.json` dans le repo = tout le monde a le même setup, aucun onboarding à refaire.

## 🧼 Hygiène de travail

- **Révisez toujours le diff** avant de valider : l'agent accélère, **vous restez responsable** du livrable (et c'est comme ça qu'on apprend à lui faire confiance).
- **Commits petits et fréquents** : l'agent travaille mieux avec des points de contrôle, et vous pouvez revenir en arrière sans drame.
- **Si ça patine** : après 3 essais infructueux, ne laissez pas tourner — reformulez ou découpez la tâche. L'agent fait ce qu'on lui **dit**, pas ce à quoi on **pense**.
- **Jamais de données client réelles** sans validation : données fictives ou anonymisées pour les démos (détails et alternatives dans [03-couts.md](03-couts.md)).
- **Interrompez tôt, redirigez souvent** : c'est votre super-pouvoir de conseiller — le cadrage.

## ⌨️ Les commandes à connaître

| Commande | Effet |
|---|---|
| `/compact` | Re-synthétise le contexte avant une nouvelle tâche |
| `Tab` | Changer d'agent principal (`build` ↔ `plan`) |
| `@test` (ou `@agent`) | Invoquer un sous-agent dans le message |
| `/agents` | Lister et gérer les agents |
| `opencode models` | Lister les modèles disponibles |
| `/help` | Rappel de toutes les commandes |

---

[⬅️ 05 — Concepts](05-concepts.md) · [Sommaire](README.md) · [07 — LLM locaux ➡️](07-llm-locaux.md)
