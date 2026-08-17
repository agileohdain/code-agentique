# 🧠 01 — Pourquoi une harness, pas un chatbot ?

> Vous avez déjà collé du code dans ChatGPT. Voici pourquoi ce n'est pas la même expérience.

## 🔴 Le problème

ChatGPT, Claude en ligne, DeepSeek web : vous avez essayé, ça écrit du code. Mais :

- ❌ vous copiez-collez tout à la main, fichier par fichier ;
- ❌ il ne connaît pas votre dépôt — vous devez tout lui expliquer à chaque message ;
- ❌ il ne peut ni exécuter le code ni lancer les tests ;
- ❌ le contexte s'effondre dès que la conversation s'allonge.

> **Résultat : vous passez plus de temps en coursier qu'en développeur.**

## 🟢 La solution : un agent dans votre dépôt

Une **harness** (Claude Code, Codex, OpenCode…) héberge des **agents** qui tournent directement dans votre projet, avec les mêmes droits que votre terminal :

- ✅ il **lit** le dépôt (code, historique git, conventions) ;
- ✅ il **écrit** les fichiers et **applique** les modifications ;
- ✅ il **exécute** les commandes (tests, lint, build) ;
- ✅ il **itère** tout seul jusqu'au critère de fin que vous avez fixé.

## 🆚 Chatbot vs Agent

| Capacité | Chatbot | Agent (harness) |
|---|---|---|
| Connaît votre dépôt | Non — vous lui racontez | Oui — il lit le code |
| Modifie les fichiers | Vous copiez-collez | Il édite directement |
| Lance les tests | Impossible | Oui, comme votre terminal |
| Gère un long contexte | Se perd après 20 messages | Compacte et garde l'essentiel |
| Votre rôle | La dictée | La revue et l'arbitrage |

## 💬 L'analogie

> Le chatbot, c'est le stagiaire au téléphone : il ne voit rien, vous dictez tout, il vous renvoie du texte à recopier.
> L'agent, c'est le binôme installé dans votre IDE : il a tout le contexte, il fait le travail, vous validez.

## 🔐 Le seul vrai frein : la confiance

On ne la donne pas d'un coup. On commence par une petite PR, on relit le diff, on monte en gamme. Tout le reste de ce dépôt est là pour vous y aider.

---

[⬅️ Sommaire](README.md) · [02 — Comparatif ➡️](02-comparatif.md)