# ⚔️ 02 — Comparatif : Claude Code, Codex, OpenCode, VS Code + Copilot

*État des lieux au 17/08/2026 — les prix et fonctionnalités bougent vite, à revérifier. Prix en dollars canadiens (1 $ US ≈ 1,37 $ CA).*

## 📊 Le tableau

| | **Claude Code** | **OpenAI Codex** | **OpenCode** | **VS Code + Copilot** |
|---|---|---|---|---|
| Où ça tourne | Terminal (+ IDE) | Terminal + IDE + Web | Terminal + IDE + Web | Dans VS Code |
| Open source | Non | Non | **Oui** | Non |
| Fournisseur imposé | Anthropic | OpenAI | **Aucun** (BYOM*) | Microsoft / OpenAI |
| Entrée de gamme | ≈ 28 $ CA/mois | ≈ 28 $ CA/mois (Plus) | **Gratuit + API** | ≈ 15 $ CA/mois |
| Usage intensif | Max ≈ 140–275 $ CA/mois | Pro ≈ 140–275 $ CA/mois | Quelques $ CA/jour | Premium ≈ 55 $ CA/mois |
| Modèles | Claude uniquement | GPT uniquement | **Tous** : Claude, GPT, DeepSeek, Gemini, local | GPT (+ Claude limité) |

\* **BYOM = Bring Your Own Model** : vous choisissez le modèle, vous n'êtes pas prisonnier d'un fournisseur.

## 🟣 Claude Code

**+** Excellente qualité d'écriture de code, réputation la plus solide sur les grosses missions.
**+** Abonnements Max 5x/20x : prix fixe pour un usage très intensif.
**−** Écosystème fermé : Claude ou rien, le jour où vous voulez changer, vous changez tout.
**−** Le plus cher à l'échelle de l'équipe.

## 🟢 OpenAI Codex

**+** Très bon agent cloud, gère les tâches lourdes et le parallélisme.
**+** Intégration directe avec l'écosystème OpenAI.
**−** Verrouillé OpenAI, même rengaine que Claude Code mais en moins fourni hors écosystème.

## 🏆 OpenCode — le choix de ce dépôt

**+** **Open source et gratuit** : pas d'abonnement, vous payez uniquement les tokens (cf. [03-couts.md](03-couts.md)).
**+** **Multi-LLM** : un seul outil pour DeepSeek, Claude, GPT ou un [modèle local Ollama](07-llm-locaux.md) — on change de modèle comme on change de carte SIM.
**+** Léger et configurable par fichiers versionnables (`opencode.json`, agents, permissions).
**−** Finitions moins "commerciales" : petite config initiale à faire soi-même (2 minutes).

## 🔵 VS Code + Copilot Pro

**+** Zéro nouvelle habitude : c'est dans l'IDE que vous utilisez déjà ; idéal pour l'autocomplétion et les petites tâches.
**+** Prix d'entrée faible (≈ 15 $ CA/mois).
**−** L'agent est moins autonome et voit moins de contexte que les harness dédiées.
**−** Toujours verrouillé Microsoft/OpenAI pour le gros du travail.

## 🎯 Verdict en une ligne

- Vous voulez du **zéro friction dans l'IDE** pour des petites tâches → **VS Code + Copilot**.
- Vous voulez **la crème de l'écriture de code** et payez l'abonnement sans sourciller → **Claude Code**.
- Vous voulez **gratuit, ouvert, multi-LLM** et garder la main → **OpenCode**.
- **Combo gagnant** : OpenCode pour le travail agentique, Copilot (ou même le mode agent de VS Code) pour l'éditeur — ils cohabitent très bien.

---

[⬅️ 01 — Pourquoi](01-pourquoi-agent.md) · [Sommaire](README.md) · [03 — Coûts ➡️](03-couts.md)