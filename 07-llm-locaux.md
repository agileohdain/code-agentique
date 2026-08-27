# 🏠 07 — LLM locaux : open weight, licences et confidentialité maximale

> Pourquoi utiliser un modèle local ? Parce que vous ne payez rien pour l'inférence, parce que vos données ne quittent jamais la machine, et parce que vous êtes maître de votre outil.

## 🔓 Propriétaire, open weight, open source : les 3 niveaux d'ouverture

Quand on parle de modèles LLM (Large Language Models), il y a trois niveaux d'ouverture :

| Niveau | Poids public ? | Code d'entraînement ? | Données d'entraînement ? | Peut tourner en local ? |
|---|---|---|---|---|
| **Propriétaire** (closed) | Non | Non | Non | ❌ |
| **Open weight** | ✅ | ❌ | ❌ | ✅ |
| **Open source strict** | ✅ | ✅ | ✅ | ✅ |

### 🧠 Propriétaire (closed)

Les modèles propriétaires comme **GPT-5** ou **Claude** sont des outils SaaS : vous n'avez pas accès aux poids du modèle, ni au code d'entraînement, ni aux données utilisées. L'accès se fait via une API payante.

> Analogie : un logiciel SaaS comme Salesforce ou Slack.

### 🧱 Open weight

Les modèles "open weight" (ou open weights) ont leurs **poids téléchargeables** — c'est-à-dire le fichier qui contient le cerveau du modèle. On peut donc les faire tourner sur sa machine, mais **le code d'entraînement et les données ne sont pas publiés**.

> Analogie : un exécutable (.exe) fourni sans le code source.

### 🧩 Open source strict

Les modèles open source strict (selon la définition OSAID) ont **poids + code + données d'entraînement**. C'est très rare, mais cela permet une transparence totale.

> Analogie : un logiciel open source comme Linux.

> ⚠️ **Note importante pour les cabinets de conseil** : dans le langage courant, « open source » désigne souvent ce qu'on appelle ici « open weight ». La nuance est utile en mission client, notamment pour la confidentialité.

## 📜 Les licences, en pratique

La licence du *modèle* n'est pas celle de l'*outil*. **OpenCode** est sous licence MIT — c'est-à-dire qu'on peut l'utiliser librement, le modifier et le redistribuer. Le modèle branché dessus (ex. Qwen, Claude, DeepSeek) a sa propre licence.

### 🧾 Exemples de licences pour les modèles open weight

| Modèle | Licence | Usage commercial ? | Fine-tune ? | Redistribution ? |
|---|---|---|---|---|
| **Qwen3** | Apache 2.0 | ✅ | ✅ | ✅ |
| **gpt-oss** | Apache 2.0 | ✅ | ✅ | ✅ |
| **DeepSeek V4 Flash** | MIT | ✅ | ✅ | ✅ |
| **Llama 3** | Llama Community License | ✅ (sauf >700M MAU) | ✅ | ✅ avec mention « Built with Llama » |
| **Gemma 4** | Apache 2.0 | ✅ | ✅ | ✅ |

> 📌 **Pour un cabinet de conseil** : toutes ces licences permettent l'usage commercial en pratique. La contrainte des 700M utilisateurs mensuels ne concerne que les géants.

### 🧰 Les outils locaux

Les outils pour faire tourner des modèles localement (comme **Ollama** ou **llama.cpp**) sont eux aussi souvent open source, sous licence MIT. Ils permettent de gérer et exécuter les modèles sans avoir à les héberger soi-même.

## ⚖️ Local vs API : les vraies différences

| Critère | Local (open weight) | API (propriétaire) |
|---|---|---|
| **Confidentialité** | ✅ Les données ne quittent jamais la machine | ❌ Les données transitent chez le fournisseur |
| **Coût d'usage** | ✅ Nul après l'achat du matériel | ⚠️ Facturé au token (cf. [03-couts.md](03-couts.md)) |
| **Qualité brute** | ⚠️ Limitée par votre matériel | ✅ Généralement plus puissante |
| **Matériel requis** | ⚠️ GPU (ou CPU puissant) nécessaire | ✅ Aucun — tout tourne chez le fournisseur |
| **Mise à jour** | ⚠️ Installation manuelle | ✅ Automatique |

## 🦙 Installer un modèle local (Ollama)

*À venir — installation d'Ollama et téléchargement d'un premier modèle.*

## 🔌 Brancher OpenCode sur le modèle local

*À venir — la config `opencode.json` pour un provider local.*

## 🎚️ Quel modèle pour quel usage

*À venir — selon votre matériel et votre type de mission.*

---

[⬅️ 06 — Tips](06-tips.md) · [Sommaire](README.md)