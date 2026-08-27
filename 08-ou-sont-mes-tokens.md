# 🧾 08 — Où partent vos tokens ?

> Le quota atteint en quelques heures, avec l'impression d'à peine avoir travaillé ? Ce n'est pas (que) vous : c'est la mécanique de la harness. Voici où partent réellement vos tokens — et comment en économiser.

*Mesures indépendantes relevées en juillet–août 2026 (étude Systima.ai relayée sur Hacker News, benchmark comparatif Pi/OpenCode/Codex, issues GitHub). Elles bougent à chaque version — l'ordre de grandeur, lui, est stable.*

## 🫀 Anatomie d'une requête d'agent

Avant même que le modèle ne lise votre premier mot, la harness a déjà envoyé un paquet :

| Ingrédient | C'est quoi | Ça pèse combien |
|---|---|---|
| **System prompt** | Les instructions de la harness (rôles, règles, format) | 5–15k tokens |
| **Définitions d'outils** | Le schéma de chaque outil disponible (lecture, édition, bash…) | 5–15k tokens |
| **Fichiers de contexte** | `CLAUDE.md`, `AGENTS.md`, mémoire de session | Variable — 72 Ko ≈ 20k tokens |
| **Schémas MCP** | Chaque serveur MCP branché ajoute ses définitions d'outils | ≈ 1–2k par serveur |
| **Historique** | Tout ce qui s'est dit et fait depuis le début de la session | Croît à chaque tour |

Et le point clé : **à chaque tour, tout est renvoyé**. Un agent, ce n'est pas une conversation qui "continue" — c'est une conversation qui se **répète intégralement**, enrichie de votre dernier message. La facture est cumulative.

> Analogie : un consultant à qui on réexplique tout le dossier, de zéro, à chaque phrase qu'on lui adresse. Excellent consultant — mais chaque phrase vous coûte le prix du dossier complet.

## 📊 Les chiffres mesurés

Overhead initial = tokens consommés avant que le modèle ne lise votre prompt, dans un dossier propre :

| Harness | Overhead initial | Le détail |
|---|---|---|
| **Claude Code** | **16k–33k** (mesuré 16 063 dossier vide, ~23k en repo réel) | System prompt + 27 outils ; une issue GitHub documente 20–30k par requête |
| **Codex** | **≈ 12k** | 11 882 tokens mesurés sur un simple « Hi » |
| **OpenCode** | **≈ 6–7k** (4k en config minimale) | System prompt + 10 outils ; préfixes stables → cache efficace (~85 %) |
| **Copilot (VS Code)** | *Mécanique différente* | Pas un compteur de tokens mais des **premium requests** : 300/mois en Pro, multipliées par modèle (jusqu'à ×13) ; bascule en facturation au token depuis juin 2026 |

**En configuration réelle, Claude Code peut démarrer à 75 000–85 000 tokens** : instructions volumineuses (~20k) + serveurs MCP (+5–7k) par-dessus la base. Sur une fenêtre de contexte de 200k, **40 % est mangé avant d'avoir commencé**.

## 🔥 Pourquoi le quota Claude Code fond si vite

Cinq causes, toutes mesurées :

1. **Surcoût de base** : 3–5× plus d'overhead initial qu'OpenCode (33k vs 7k) — payé sur *chaque* requête.
2. **Appels d'outils agressifs** : un simple « commit » peut déclencher 30+ appels d'outils ; chaque appel est un aller-retour facturé.
3. **Cache défavorable** : Claude Code réécrit son cache en cours de session — jusqu'à **54× plus de cache-writes** qu'OpenCode, facturés au tarif premium. Le compteur grimpe d'autant plus vite.
4. **Historique cumulatif** : tout est renvoyé à chaque tour (voir l'anatomie ci-dessus) — une session longue devient quadratiquement chère.
5. **Sous-agents** : déléguer à un sous-agent duplique le contexte — mesuré à **×4,2** sur une même tâche (121k → 513k tokens).

> Nuance honnête : sur les grosses tâches multi-fichiers, Claude Code regroupe ses appels en parallèle et fait moins d'aller-retours — l'écart final se resserre. C'est sur les **petites tâches** que la surconsommation est la plus injustifiée. Le phénomène a un nom : la *tokenflation*.

## 🔧 Les leviers pour tenir dans le quota

| Levier | Effet |
|---|---|
| **Auditer** : `/context` dans Claude Code | Voir le vrai découpage — beaucoup découvrent 23k+ en session fraîche |
| **`/compact` entre chaque tâche** (cf. [06-tips.md](06-tips.md)) | Coupe l'historique cumulatif — le levier n°1 |
| **`CLAUDE.md` maigre** | 72 Ko de règles = ~20k tokens sur *chaque requête* ; garder l'essentiel |
| **Débrancher les MCP inutiles** | Chaque serveur facture ses schémas en continu |
| **Sous-agents avec parcimonie** | Chaque délégation multiplie le contexte (×4 mesuré) |
| **Basculez les tâches légères sur OpenCode** | Overhead 5× moindre, modèle au choix (DeepSeek…) — cf. [03-couts.md](03-couts.md) |

**Le combo qui marche chez nous** : Claude Code pour les grosses missions qui justifient sa qualité d'écriture, OpenCode + API à la carte pour tout le reste — questions ponctuelles, refactors légers, écriture de tests. Le quota Max respire, la facture API reste en café par jour.

---

[⬅️ 07 — LLM locaux](07-llm-locaux.md) · [Sommaire](README.md)
