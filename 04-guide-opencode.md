# 🛠️ 04 — OpenCode : installation et configuration

> Dix minutes chrono, zéro abonnement — et vous avez un agent qui lit votre dépôt.

## 🤔 Pourquoi OpenCode ?

- **Léger** : un outil en ligne de commande, pas un IDE imposé ;
- **Multi-LLM** : Claude, GPT, DeepSeek, Gemini, voire un modèle local ;
- **Open source**, gratuit, configurable par fichiers versionnables (toute l'équipe a la même config) ;
- **Pas de verrouillage** : changer de modèle = changer une ligne de config, pas changer d'outil.

## 1️⃣ Installation

Prérequis : Node.js 20 ou plus (ou Bun).

```bash
npm install -g opencode-ai
opencode --version
```

## 2️⃣ Premiers pas dans votre projet

```bash
cd votre-projet
opencode
```

Posez une question sur le code : il lit le dépôt, il répond avec les bonnes références. Testez d'abord sur un projet perso ou de démo.

## 3️⃣ Brancher OpenRouter (le passeport multi-LLM)

1. Créez un compte sur [openrouter.ai](https://openrouter.ai) et ajoutez des crédits — **≈ 15 $ CA suffisent largement pour tester** ;
2. Générez votre clé dans le tableau de bord (`API Keys`) ;
3. Dans votre terminal, à la racine du projet :

```bash
opencode auth login   # choisir OpenRouter, coller la clé
```

## 4️⃣ Copier la config d'équipe

```bash
git clone https://github.com/agileohdain/code-agentique.git
cp code-agentique/config/opencode.json .    # macOS / Linux
copy code-agentique\config\opencode.json .  # Windows
```

Le fichier contient : le provider OpenRouter, le modèle par défaut (DeepSeek V4 Flash), et **nos 3 agents**. Adaptez le nom du modèle précis si besoin (`opencode models` liste les modèles disponibles).

## 5️⃣ Les 3 agents : build, plan, test

Pourquoi 3 rôles séparés ? Parce qu'un agent qui écrit ne devrait pas être **le seul** à juger son propre travail.

| Agent | Rôle | Droits |
|---|---|---|
| **build** | Écrit le code, itère jusqu'au résultat | Tous les outils |
| **plan** | Analyse, propose un plan, revoit le code | Lecture seule (interdit d'éditer) |
| **test** | Écrit et exécute les tests | Édition + commandes, mais uniquement sur les tests |

**Le réflexe en 3 temps :**

```
1. plan  : "Propose un plan pour ajouter la colonne X à la table Y."
2. build : "Implémente le plan validé, sans en changer le périmètre."
3. test  : "Vérifie les tests, ajoute ceux qui manquent."
```

**Changer d'agent :** touche `Tab` (entre `build` et `plan`), ou `@test` dans votre message pour invoquer le sous-agent test.

[Voir la config complète](config/opencode.json)

## 6️⃣ Les fichiers de travail

| Fichier | Rôle |
|---|---|
| `opencode.json` | Modèle, provider, agents, permissions |
| `AGENTS.md` | Le mode d'emploi du repo que l'agent respecte (voir [06-tips.md](06-tips.md)) |
| `.opencode/skills/` | Fiches méthode à la demande (voir [05-concepts.md](05-concepts.md)) |

**À versionner dans le repo** : toute l'équipe démarre alors avec le même modèle, les mêmes agents et les mêmes règles — zéro friction à l'onboarding.

---

[⬅️ 03 — Coûts](03-couts.md) · [Sommaire](README.md) · [05 — Concepts ➡️](05-concepts.md)