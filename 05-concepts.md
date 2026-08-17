# 05 — Skills, plugins, MCP, LSP : le glossaire sans jargon

| Terme | C'est quoi ? | Analogie |
|---|---|---|
| **Agent** | Un assistant spécialisé dans votre dépôt | Un binôme |
| **Harness** | L'outil qui héberge les agents | Le bureau de travail |
| **Modèle** | Le cerveau (Claude, DeepSeek, GPT…) | Le consultant senior |
| **Skill** | Fiche méthode chargée à la demande | La check-list du projet |
| **Plugin** | Code branché sur le cycle de vie de l'agent | Les macros du tableur |
| **MCP** | Protocole pour brancher des outils externes | La prise USB universelle |
| **LSP** | Protocole de "compréhension" du code | Le collègue qui sait où est chaque fonction |

## Skills — les fiches méthode

Une skill est un **fichier markdown** qui dit : *quand la tâche correspond à ceci, fais cela*. L'agent ne la charge **que si besoin** — pas de pavé inutile dans le contexte.

Exemple pour nous : une skill `sql-review` qui force la vérification des index avant une requête lourde, ou `streamlit-conventions` avec nos règles de dataviz. C'est la mémoire de l'équipe, écrite une fois, appliquée à chaque mission.

## Plugins — les macros

Un plugin est du **code qui se branche sur les événements** de l'agent : début de session, fin de tâche, commit, commande personnalisée. Exemples : publier un rapport à la fin de chaque session, ajouter une commande `/expliquer ce repo`, déclencher une action sur `git push`.

## MCP — la prise USB universelle

MCP (Model Context Protocol) est un **standard** pour brancher des outils sur les agents : base de données, Jira, navigateur, index de code… Une prise, mille appareils. L'agent ne lit plus un dump de contexte : il **va chercher** l'information quand il en a besoin.

Utile pour un cabinet data :

- **Serena** : indexe le code (symboles, définitions, références) — l'agent navigue dans un gros repo client sans tout relire ;
- un **MCP vers la base de test** : l'agent interroge la base en self-service pour valider ses requêtes SQL.

## LSP — comment l'agent "comprend" le code

C'est le protocole que votre IDE utilise déjà pour *aller à la définition*, *chercher les références*, *renommer proprement*. OpenCode branche les mêmes serveurs LSP que VS Code : l'agent ne **devine** pas où est la fonction, il **sait**.

## La règle d'or

Aucun de ces outils ne remplace un bon contexte. Un agent brillant sur un brief flou, c'est un consultant brillant sur un brief flou : **tout se joue sur la qualité de ce qu'on lui donne** (et les [06-tips.md](06-tips.md) sont faites pour ça).