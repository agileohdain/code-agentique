# Code Agentique

> Votre futur collègue lit tout le dépôt, écrit le code, lance les tests — et ne se plaint jamais.

Guide de démarrage au **développement assisté par des agents IA** (agentic coding), pensé pour nos missions de conseil data. Zéro jargon, zéro blabla : lisez 30 secondes, testez 10 minutes.

## En 30 secondes

1. Un **chatbot** vous répond. Un **agent** travaille dans votre dépôt : il lit le code, le modifie, exécute les tests.
2. Claude Code et Codex en usage intensif coûtent **100–200 $/mois** par développeur. OpenCode est **gratuit** — vous ne payez que les tokens API, soit **quelques dollars par journée intense** avec DeepSeek.
3. OpenCode est **open source** et fonctionne avec n'importe quel LLM : vous n'êtes prisonnier d'aucun fournisseur.
4. **3 agents** : `build` écrit, `plan` réfléchit, `test` vérifie — l'arbitre n'est jamais le joueur.
5. Démarrage en **10 minutes**, sans abonnement ni engagement.

## Le dépôt

| Fichier | Vous y trouverez |
|---|---|
| [01-pourquoi-agent.md](01-pourquoi-agent.md) | Pourquoi une harness plutôt qu'un chatbot |
| [02-comparatif.md](02-comparatif.md) | Claude Code vs Codex vs OpenCode vs VS Code + Copilot |
| [03-couts.md](03-couts.md) | Le vrai prix : abonnements vs API à la carte |
| [04-guide-opencode.md](04-guide-opencode.md) | Installer OpenCode et configurer les 3 agents |
| [05-concepts.md](05-concepts.md) | Skills, plugins, MCP, LSP — expliqués simplement |
| [06-tips.md](06-tips.md) | Les raccourcis et bonnes pratiques qui changent tout |
| [config/](config/) | Fichiers de configuration prêts à copier |

## Démarrage en 10 minutes

```bash
# 1. Installer OpenCode
npm install -g opencode-ai

# 2. Copier la config d'équipe (modèle, 3 agents, permissions)
cp config/opencode.json opencode.json

# 3. Brancher votre clé OpenRouter
opencode auth login   # choisir OpenRouter, coller la clé

# 4. C'est parti
opencode
```

Détails pas à pas : [04-guide-opencode.md](04-guide-opencode.md)

## La promesse

- **Jour 1** : vous posez une question sur votre base de code, il répond avec les bonnes références.
- **Semaine 1** : vous lui déléguez une petite fonctionnalité de bout en bout (plan → code → tests).
- **Mois 1** : il est votre binôme sur chaque mission, et vos livrables sont plus propres qu'avant.

La confiance se donne par paliers : commencez petit, révérez tout, montez en gamme.

---

© 2026 Agile O'Dain — [Licence MIT](LICENSE)