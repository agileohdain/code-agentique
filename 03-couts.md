# 03 — Combien ça coûte, vraiment ?

*Prix relevés au 17/08/2026 — ils bougent souvent, faites vos propres vérifications avant d'engager un budget.*

## Les abonnements

| Plan | Prix / mois | Pour qui |
|---|---|---|
| Claude Pro | 20 $ | Débutant |
| Claude Max 5x | 100 $ | Usage intensif |
| Claude Max 20x | 200 $ | Usage très intensif |
| ChatGPT Plus (Codex) | 20 $ | Débutant |
| ChatGPT Pro (Codex) | 100–200 $ | Usage intensif |
| GitHub Copilot Pro | 10 $ | Autocomplétion + petit agent |

Un abonnement se paie **même si on ne code pas un seul jour du mois**.

## OpenCode : gratuit + API à la carte

Le logiciel est gratuit et open source. Seul coût : les **tokens consommés**, facturés par OpenRouter.

Exemple — modèle **DeepSeek V4 Flash** sur OpenRouter :

| | Prix pour 1M tokens |
|---|---|
| Entrée (contexte, lecture du repo) | 0,0786 $ |
| Sortie (code produit) | 0,1572 $ |

## Une journée de dev intensive, le calcul

Disons 20M tokens d'entrée + 8M de sortie (beaucoup, déjà) :

```
20 × 0,0786 $ + 8 × 0,1572 $ = 1,57 $ + 1,26 $ ≈ 2,80 $
```

**Moins cher qu'un café.** Une journée de très grosse charge : 3 à 5 $.

## Le parallèle chiffré

| | Abonnement Max (Claude/Codex) | OpenCode + DeepSeek |
|---|---|---|
| Coût fixe mensuel | 100–200 $ par développeur | **0 $** |
| Journée intensive | Incluse | ≈ 3 $ |
| Mois complet intensif (22 j) | 100–200 $ | ≈ 60–100 $ |
| Journée légère | Payée plein tarif | ≈ 1 $ |

## N'oublions pas le vrai poste de coût

Ce n'est ni l'abonnement ni l'API : **c'est votre temps**. Au tarif d'un consultant, une heure gagnée par jour rembourse l'abonnement le plus cher du marché. L'API, elle, rend la décision sans risque : **on teste gratuitement, on ne paie que si on en use.**

## Et la confidentialité des données client ?

LA question pour un cabinet de conseil. Réponse honnête :

- **Aucun** de ces outils (Claude Code, Codex, OpenCode + API cloud) ne garde vos données en interne par défaut — vos prompts partent chez le fournisseur de modèle. Les conditions d'utilisation interdisent l'entraînement sur vos prompts, mais la précaution reste la règle.
- **Règle d'or dans nos missions** : jamais de données client réelles dans l'agent sans validation (tester sur données fictives/anonymisées, bannir secrets et accès à la prod).
- Si la confidentialité stricte s'impose (santé, banque…), **OpenCode sait se brancher sur un modèle local** (Ollama) : le code ne quitte plus la machine. C'est un atout que les solutions fermées n'offrent pas.