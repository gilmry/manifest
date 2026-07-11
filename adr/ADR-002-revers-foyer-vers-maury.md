# ADR-002 — Revers Foyer → Maury : 8 concepts opérationnels + alignement convictions

**Date** : 2026-07-11
**Statut** : Accepté
**Auteur** : Gilles Maury (superviseur)
**Supersède** : —
**Voir aussi** : ADR-001 (meta-grain de la Boucle de rétroaction)

---

## Contexte

Foyer a été créé comme une version générique de la Méthode Maury, dépourvue du narratif centré sur Gilles/Farah/KoproGo/BANKO. Par le dogfooding sur OpenMajor, Foyer a découvert des concepts opérationnels absents du Manifeste Maury :

- La Boucle de rétroaction comme primitive unificatrice (auto-similarité entre grains)
- Les archétypes de composant (stateless/stateful × API-first/full-stack)
- Les trois anneaux d'enforcement (permissions, plugin, substrat)
- Les garde-fous L0-L2 (contexte propre, sécurité runtime, discipline validation)
- L'abaque coût et capacité (discipline `[caler]`)
- L'adoption et la priorisation (RACE/RICE)
- L'arbitrage hybride (louer le réversible, posséder l'irréversible)
- Le contrat API matérialisé (4 éléments non optionnels)

Ces concepts vivaient dans `foyer/skills/` sans être remontés dans le Manifeste Maury comme principes canoniques. C'était ShareAlike en action — mais dans le sens inverse de ce qui avait été fait jusqu'ici.

Parallèlement, les convictions des deux manifests divergeaient : Foyer avait 8 convictions (dont la conviction 3 sur le binôme/mob programming) tandis que le Manifeste Maury en avait 7.

## Décision

**Deux mouvements simultanés :**

1. **Revers des 8 concepts Foyer → Manifeste Maury** — Section 4.4 enrichie de 8 nouvelles sous-sections (4.4.11 à 4.4.18), chacune comme principe philosophique. Le « comment » opérationnel est dans `Methode-Maury.md` Phase 0 (8 sous-sections 0.1 à 0.8).

2. **Alignement des convictions** — Manifeste Maury passe de 7 à 8 convictions. Foyer conserve ses 8 convictions, alignées sur le Manifeste.

3. **Dé-narrativisation de Foyer** — Manifeste Foyer §2 (sagesses) et Annexe pointent vers Manifeste Maury §2. Boucle-de-réaction pointe vers §4.4.11. Foyer devient un persona opérationnel qui hérite du Manifeste Maury pour la philosophie.

## Alternatives écartées

- **Foyer comme corpus autonome** — écarté : violerait le ShareAlike (CC BY-SA 4.0) et créerait une divergence de maintenance.
- **Remplacer Foyer par une section du Manifeste** — écarté : Foyer sert un usage différent (persona agent, portable ≤ 5k tokens, chargeable comme AGENTS.md).
- **Ne pas remonter les concepts** — écarté : reproduirait le piège que le skill `contrat-api.md` a identifié — un concept découvert par la pratique mais non remonté au manifeste est une dette textuelle.

## Conséquences

- **Manifeste Maury** : corpus unique et canonique, avec le narratif. Toutes les convictions et principes philosophiques y vivent.
- **Methode-Maury.md** : pratiques opérationnelles « comment », Phase 0 ajoutée.
- **Foyer** : hérite du Manifeste, dé-narrativisé, portable. Les sagesses, les convictions et les principes pointent vers le Manifeste.
- **Skills Foyer** : inchangés, restent les instances opérationnelles. Chaque skill mentionne le concept canonique du Manifeste qu'il implémente.
- **ShareAlike** : le mécanisme est maintenant documenté. Quand un skill Foyer naîtra d'un futur incident, il remontera dans le Manifeste (ADR méthodologique, version incrémentée).

## Racine philosophique

L'écologie des savoirs appliquée à la méthode elle-même : Foyer n'est pas un concurrent du Manifeste, c'est son terrain de dogfooding. Les innovations qu'il découvre par la pratique remontent au manifeste — c'est le ShareAlike comme principe Ubuntu, pas seulement obligation juridique.