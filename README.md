# 🤖 Code Agentique

[![Licence](https://img.shields.io/badge/Licence-MIT-3DA639?style=flat-square)](LICENSE)
[![OpenCode](https://img.shields.io/badge/OpenCode-gratuit-2ea44f?style=flat-square)](04-guide-opencode.md)
[![Multi-LLM](https://img.shields.io/badge/Multi--LLM-aucun%20verrouillage-ff7a00?style=flat-square)](02-comparatif.md)
[![Made by](https://img.shields.io/badge/Made%20by-Oh%20da%20in-5865F2?style=flat-square)](https://github.com/agileohdain)

## ⚡ En 30 secondes

1. Un **chatbot** vous répond. Un **agent** travaille dans votre dépôt : il lit le code, le modifie, exécute les tests.
2. Claude Code et Codex en usage intensif coûtent **plus de 250 $ CA/mois** par développeur. OpenCode est **gratuit** — vous ne payez que les tokens API, soit **environ 4 $ CA par journée intense** avec DeepSeek.
3. OpenCode est **open source** et fonctionne avec n'importe quel LLM : vous n'êtes prisonnier d'aucun fournisseur.
4. **3 agents** : `build` écrit, `plan` réfléchit, `test` vérifie — l'arbitre n'est jamais le joueur.
5. Démarrage en **10 minutes**, sans abonnement ni engagement.

## 🆚 Le chatbot vs l'agent

| 🤖 Le chatbot | 🕵️ L'agent dans votre dépôt |
|---|---|
| Vous copiez-collez tout, fichier par fichier | Il lit le repo, modifie les fichiers, exécute les tests |
| Il ne connaît pas votre projet — vous lui racontez | Il ingère le code et ses conventions tout seul |
| Il se perd après 20 messages | `/compact` : il garde l'essentiel et continue |

[> 01 — Pourquoi un agent plutôt qu'un chatbot](01-pourquoi-agent.md)

## 💰 Le chiffre choc

| | Abonnement Max (Claude / Codex) | OpenCode + DeepSeek via API |
|---|---|---|
| Coût fixe mensuel | ≈ 140–275 $ CA | **0 $** |
| Journée de dev intensive | Inclus | **≈ 4 $ CA** |
| Engagement | Un mois minimum | **Aucun — vous payez ce que vous consommez** |

[> 03 — Le détail des coûts et la question confidentialité](03-couts.md)

## 📖 Le dépôt

| Fichier | Vous y trouverez |
|---|---|
| 🧠 [01-pourquoi-agent.md](01-pourquoi-agent.md) | Pourquoi une harness plutôt qu'un chatbot |
| ⚔️ [02-comparatif.md](02-comparatif.md) | Claude Code vs Codex vs OpenCode vs VS Code + Copilot |
| 💰 [03-couts.md](03-couts.md) | Le vrai prix : abonnements vs API à la carte |
| 🛠️ [04-guide-opencode.md](04-guide-opencode.md) | Installer OpenCode et configurer les 3 agents |
| 🔧 [05-concepts.md](05-concepts.md) | Skills, plugins, MCP, LSP — expliqués simplement |
| 💡 [06-tips.md](06-tips.md) | Les raccourcis et bonnes pratiques qui changent tout |
| ⚙️ [config/](config/) | Fichiers de configuration prêts à copier |

## 🚀 Démarrage en 10 minutes

<details>
<summary><b>Voir les commandes</b></summary>

```bash
# 1. Installer OpenCode
npm install -g opencode-ai

# 2. Récupérer la config d'équipe (un clone de ce dépôt suffit)
git clone https://github.com/agileohdain/code-agentique.git
cp code-agentique/config/opencode.json .    # macOS / Linux
copy code-agentique\config\opencode.json .  # Windows

# 3. Brancher votre clé OpenRouter
opencode auth login   # choisir OpenRouter, coller la clé

# 4. C'est parti
opencode
```

</details>

[> 04 — Le pas à pas complet](04-guide-opencode.md)

---

🤝 **Vous avez un retour, une astuce, un agent à partager ?** Les PR sont les bienvenues.

© 2026 Oh da in — [Licence MIT](LICENSE)