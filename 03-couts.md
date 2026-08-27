# 💰 03 — Combien ça coûte, vraiment ?

*Prix relevés au 17/08/2026, convertis en dollars canadiens (1 $ US ≈ 1,37 $ CA). Ils bougent souvent — faites vos propres vérifications avant d'engager un budget.*

## 📋 Les abonnements

| Plan | Prix / mois | Pour qui |
|---|---|---|
| Claude Pro | ≈ 28 $ CA | Débutant |
| Claude Max 5x | ≈ 140 $ CA | Usage intensif |
| Claude Max 20x | ≈ 275 $ CA | Usage très intensif |
| ChatGPT Plus (Codex) | ≈ 28 $ CA | Débutant |
| ChatGPT Pro (Codex) | ≈ 140–275 $ CA | Usage intensif |
| GitHub Copilot Pro | ≈ 15 $ CA | Autocomplétion + petit agent |

> Un abonnement se paie **même si on ne code pas un seul jour du mois**. Et certains fondent plus vite que d'autres : voir [08-ou-sont-mes-tokens.md](08-ou-sont-mes-tokens.md).

## 🎁 OpenCode : gratuit + API à la carte

Le logiciel est gratuit et open source. Seul coût : les **tokens consommés**, facturés par OpenRouter.

Exemple — modèle **DeepSeek V4 Flash** sur OpenRouter :

| | Prix pour 1M tokens |
|---|---|
| Entrée (contexte, lecture du repo) | ≈ 0,11 $ CA |
| Sortie (code produit) | ≈ 0,22 $ CA |

## 🧮 Une journée de dev intensive, le calcul

Disons 20M tokens d'entrée + 8M de sortie (beaucoup, déjà) :

```
20 × 0,11 $ + 8 × 0,22 $ = 2,20 $ + 1,76 $ ≈ 3,96 $ CA
```

**Moins cher qu'un café.** Une journée de très grosse charge : 4 à 7 $ CA.

## ⚖️ Le parallèle chiffré

| | Abonnement Max (Claude/Codex) | OpenCode + DeepSeek |
|---|---|---|
| Coût fixe mensuel | ≈ 140–275 $ CA par développeur | **0 $** |
| Journée intensive | Incluse | **≈ 4 $ CA** |
| Mois complet intensif (22 j) | ≈ 140–275 $ CA | **≈ 85–135 $ CA** |
| Journée légère | Payée plein tarif | **≈ 1,50 $ CA** |

## ⏳ N'oublions pas le vrai poste de coût

Ce n'est ni l'abonnement ni l'API : **c'est votre temps**. Au tarif d'un consultant, une heure gagnée par jour rembourse l'abonnement le plus cher du marché. L'API, elle, rend la décision sans risque : **on teste gratuitement, on ne paie que si on en use.**

## 🔒 Et la confidentialité des données client ?

LA question pour un cabinet de conseil. Réponse honnête :

- **Brancher une clé API OpenAI ou Anthropic sur OpenCode vous donne les mêmes garanties contractuelles que l'abonnement** : les données API ne servent pas à l'entraînement des modèles, quel que soit l'outil utilisé. La sécurité ne dépend pas de l'outil, mais du canal (API) et du fournisseur.
- **Nuance OpenRouter** : dans notre config, la clé passe par OpenRouter, un intermédiaire. Leur politique est bonne (pas d'entraînement, pas de log des prompts par défaut), mais les données transitent chez un tiers. Pour une sensibilité maximale : brancher la clé OpenAI/Anthropic **en direct** dans OpenCode, sans passer par OpenRouter.
- **Le vrai critère n'est pas "open source ou pas", c'est *où tourne le modèle*** :

  | Cas | Confidentialité |
  |---|---|
  | DeepSeek via OpenRouter (API) | Les données sortent de l'infrastructure — fournisseur chinois, juridiction différente. Réservé aux données **non sensibles**. |
  | Modèle open source **en local** (Ollama) | Les données **ne quittent jamais la machine** → l'option la plus confidentielle qui existe, parfaite pour les données client sensibles. |

  Un modèle open source local est donc **plus sûr que GPT-5 via API**. Et la prudence ne se mesure pas au volume : **c'est la classification des données qui décide, pas la parcimonie**. Une donnée sensible copiée une seule fois est une donnée exposée.
- **Règle d'or dans nos missions** : jamais de données client réelles dans l'agent sans validation (tester sur données fictives/anonymisées, bannir secrets et accès à la prod).
- Si la confidentialité stricte s'impose (santé, banque…), **OpenCode sait se brancher sur un modèle local** (Ollama) : le code ne quitte plus la machine. C'est un atout que les solutions fermées n'offrent pas. **Voir aussi [07-llm-locaux.md](07-llm-locaux.md)**.

---

[⬅️ 02 — Comparatif](02-comparatif.md) · [Sommaire](README.md) · [04 — Guide OpenCode ➡️](04-guide-opencode.md)
