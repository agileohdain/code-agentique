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

| Modèle | Licence | Conditions à connaître |
|---|---|---|
| **Qwen3**, **gpt-oss**, **Gemma 4** | Apache 2.0 | Quasi aucune — conserver la mention de licence |
| **DeepSeek V4 Flash** | MIT | Idem — mention de copyright |
| **Llama 3** | Community License | Interdit au-delà de 700M utilisateurs/mois, mention « Built with Llama », politique d'usage, et les dérivés héritent de la licence |

> 📌 **Pour un cabinet de conseil** : toutes ces licences autorisent l'usage commercial, le fine-tune et la redistribution — « open » ne veut pas dire « non commercial ». La vraie frontière est ailleurs : **propriétaire** (poids secrets, accès API uniquement) vs **open weight** (poids téléchargeables). La différence entre licences se joue dans les **conditions**, pas dans les droits.

## ⚖️ Local vs API : les vraies différences

| Critère | Local (open weight) | API (propriétaire) |
|---|---|---|
| **Confidentialité** | ✅ Les données ne quittent jamais la machine | ❌ Les données transitent chez le fournisseur |
| **Coût d'usage** | ✅ Nul après l'achat du matériel | ⚠️ Facturé au token (cf. [03-couts.md](03-couts.md)) |
| **Qualité brute** | ⚠️ Limitée par votre matériel | ✅ Généralement plus puissante |
| **Matériel requis** | ⚠️ GPU (ou CPU puissant) nécessaire | ✅ Aucun — tout tourne chez le fournisseur |
| **Mise à jour** | ⚠️ Installation manuelle | ✅ Automatique |

## 🦙 Ollama, LM Studio, llama.cpp : quel outil choisir ?

Faire tourner un modèle local demande un logiciel d'**inférence**. Trois grands choix, trois philosophies :

| Outil | C'est quoi | Interface | Open source | Pour qui |
|---|---|---|---|---|
| **llama.cpp** | Le moteur d'inférence (format GGUF, CPU ou GPU) | Ligne de commande | ✅ MIT | Les bidouilleurs — contrôle total |
| **Ollama** | Le gestionnaire clé en main construit sur llama.cpp | Ligne de commande + API locale | ✅ MIT | **Le choix par défaut**, surtout avec OpenCode |
| **LM Studio** | L'app graphique : boutique de modèles, chat, réglages | Interface graphique | ❌ Propriétaire, gratuit y compris au travail | Ceux qui ne veulent pas du terminal |
| **vLLM** | Serveur haute performance pour GPU | API (sans interface) | ✅ | Équipes, serveurs dédiés |
| **Jan** | L'alternative GUI open source à LM Studio | Interface graphique | ✅ MIT | Le GUI sans logiciel propriétaire |

> Analogie : **llama.cpp** est le moteur, **Ollama** la voiture clé en main, **LM Studio** le même modèle avec tableau de bord et GPS.

**Verdict en une ligne** : explorer sans terminal → LM Studio ; travailler avec OpenCode → **Ollama**, dont l'API locale (compatible OpenAI, sur `localhost:11434`) se branche nativement.

### ⚙️ Installer Ollama

```bash
# macOS / Linux
curl -fsSL https://ollama.com/install.sh | sh

# Windows : télécharger l'installateur sur ollama.com
```

Puis télécharger et discuter avec un premier modèle :

```bash
ollama run qwen3
```

Le modèle tourne sur votre machine — reste à le brancher dans OpenCode (section suivante).

## 🔌 Brancher OpenCode sur le modèle local

*À venir — la config `opencode.json` pour un provider local.*

## 🎚️ Quel modèle pour quel usage

*À venir — selon votre matériel et votre type de mission.*

---

[⬅️ 06 — Tips](06-tips.md) · [Sommaire](README.md) · [08 — Tokens ➡️](08-ou-sont-mes-tokens.md)