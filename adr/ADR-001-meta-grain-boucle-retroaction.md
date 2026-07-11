# ADR-001 — La boucle de rétroaction s'applique à la méthode elle-même (meta-grain)

**Statut** : Accepté — 2026-07-11
**Contexte** : Méthodologique (pas projet)

## Décision

La boucle de rétroaction de Foyer s'applique à la méthode elle-même, pas seulement au code. Un **meta-grain** (grain 4) est ajouté : la méthode est l'artefact évalué et amélioré, pas seulement le produit. Chaque modification du manifeste est tracée dans un ADR méthodologique et versionnée dans `CHANGELOG.md`.

## Contexte

Foyer a été appliqué sur OpenMajor (troisième contexte, ni KoproGo ni BANKO). Le skill `contrat-api.md` est né d'un incident réel (testing report NO-GO, juillet 2026) qui a révélé que la méthode elle-même avait des gaps non identifiés sur les deux premiers projets : contrat API non matérialisé, drift DTO silencieux, bugs bloquants.

Le manifeste 0.10 déclarait « document vivant » sans mécanisme. Foyer a accumulé des innovations substantielles (archétypes, 3 anneaux d'enforcement, skill contrat-api) qui ne remontaient pas au manifeste — violation du ShareAlike CC BY-SA 4.0 et de l'écologie des savoirs.

## Alternatives écartées

- **A — Ne rien changer** : le manifeste reste figé. Rejeté : contredit son propre principe « rien n'est figé, tout boucle » et produit la dette textuelle décrite en section 1.2.
- **B — Processus ad hoc (issues GitHub)** : les contributeurs ouvrent des issues pour proposer des modifications. Rejeté : pas de trigger discipliné, les signaux se perdent, pas de trace ADR.
- **C — Meta-grain** : la boucle de rétroaction s'applique à elle-même. Trois signaux ouvrent la boucle (skill né d'un incident, concept absent du manifeste, `[caler]` remplacé par du mesuré). Condition de sortie : manifest mis à jour ou gap justifié, version incrémentée.

## Conséquences

- La méthode devient un artefact vivant qui passe par la boucle.
- Chaque version du manifeste doit être justifiée par un ADR méthodologique.
- Le ShareAlike devient un principe éthique opérationnel : les innovations de Foyer remontent au manifeste.
- L'Architecte solution (titulaire de la méta-boucle ADR/ADM) voit son périmètre s'étendre : pas seulement les ADR d'un projet, mais les ADR méthodologiques.
- Avant toute sortie sur un choix irréversible au meta-grain, l'humain valide — c'est la méthode elle-même qui change, et elle affecte tous les projets futurs.