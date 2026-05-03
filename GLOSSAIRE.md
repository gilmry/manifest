# Glossaire

Ce glossaire rassemble les termes techniques, méthodologiques,
juridiques et conceptuels mobilisés dans le manifeste. Il s'adresse
à un lecteur intéressé mais non-spécialiste — par exemple un
dirigeant d'ASBL, un étudiant en informatique de gestion, un
juriste curieux d'architecture logicielle, un praticien d'un autre
secteur.

Les définitions sont volontairement courtes. Pour aller plus loin
sur une notion, le manifeste lui-même développe le contexte dans la
sous-section indiquée entre parenthèses. Une bibliographie
commentée des sources philosophiques sera publiée séparément dans
`BIBLIOGRAPHIE.md`.

L'ordre est strictement alphabétique, sans tri par catégorie. Cette
mise à plat est délibérée : les notions techniques, juridiques et
philosophiques dialoguent dans la pratique, et un glossaire qui les
sépare reproduirait une cloison que la Méthode Maury cherche
précisément à éviter.

---

## A

**ADR — *Architecture Decision Record***
Note brève, datée, qui consigne une décision d'architecture
significative, ses raisons, les alternatives écartées et les
conséquences attendues. La pratique a été formalisée par Michael
Nygard en 2011 et est intégrée à la pratique TOGAF pour assurer la
traçabilité dans le temps long. (Mobilisé en sous-section 4.1.5 et
4.4.2.)

**Agile (Manifeste Agile, 2001)**
Texte fondateur signé en février 2001 à Snowbird, Utah, par
dix-sept développeurs venus de différentes traditions (eXtreme
Programming, Scrum, Crystal). Il énonce quatre valeurs et douze
principes qui privilégient les individus sur les processus, le
logiciel qui fonctionne sur la documentation exhaustive,
l'adaptation au changement sur le suivi d'un plan. (Sous-section
2.7.)

**AGPL-3.0 — *GNU Affero General Public License***
Licence libre dite « licence-vaccin » publiée par la Free Software
Foundation en 2007. Elle exige que toute version modifiée d'un
logiciel utilisée pour fournir un service en ligne soit elle-même
publiée sous la même licence — propageant ainsi les libertés du
logiciel libre aux services SaaS. C'est la licence des projets
KoproGo et BANKO. (Sous-section 6.4.)

**ASBL — Association Sans But Lucratif**
Personne morale de droit belge dont les membres ne peuvent se
partager les bénéfices et qui poursuit un but désintéressé. Régie
en Belgique par le Code des sociétés et des associations de 2019.
Beaucoup de copropriétés, écoles, structures culturelles ou
associatives sont organisées sous cette forme. (Sous-sections 1.3
et 5.1.)

## B

**BDD — *Behavior-Driven Development***
Pratique de tests qui décrit le comportement attendu d'un système
en langage proche du métier, le plus souvent au format **Gherkin**
(`Given... When... Then...`). Dans la Méthode Maury, les scénarios
BDD servent de spécification exécutable et de pont entre les
expert·e·s métier et les développeur·e·s. (Sous-sections 4.3.2 et
4.5.)

**BMAD — *Business Model Agile Development***
Cadre méthodologique qui traduit une vision stratégique en backlog
produit structuré, en s'appuyant sur des agents IA spécialisés
(Analyste, Product Manager, Architecte, Scrum Master). Il fait le
pont entre TOGAF (le « quoi » stratégique) et Scrum (le « comment »
opérationnel). (Sous-section 4.4.3.)

**Bounded Context (contexte délimité)**
Notion centrale du Domain-Driven Design qui désigne une frontière
explicite à l'intérieur de laquelle un modèle de domaine est
cohérent et un vocabulaire précis. Deux contextes différents
peuvent utiliser le même mot avec des sens différents — par exemple
*Compte* en comptabilité et *Compte* en authentification — sans que
cela pose problème, à condition que la frontière soit nommée et
respectée. (Sous-section 4.3.2.)

## C

**Cantique des créatures (François d'Assise)**
Poème écrit par François d'Assise vers 1224-1226 en dialecte
ombrien, parfois appelé *Cantico di frate Sole*. Loue Dieu à
travers les créatures — frère soleil, sœur lune, sœur notre mère
la terre — et énonce ainsi une *ontologie de la fraternité étendue*
qui inclut le vivant non-humain. L'encyclique *Laudato si'* du pape
François (2015) en tire son titre et le prolonge en éthique
écologique contemporaine. (Sous-section 2.5.)

**Cargo workspace**
Mécanisme du gestionnaire de paquets `cargo` (Rust) qui permet de
regrouper plusieurs *crates* (unités de compilation) dans un même
dépôt avec leurs dépendances partagées. BANKO l'utilise pour
matérialiser physiquement la séparation entre couches du domaine,
de l'application et de l'infrastructure. (Sous-section 4.3.3.)

**CC BY-SA 4.0 — *Creative Commons Attribution-ShareAlike 4.0***
Licence libre de Creative Commons qui autorise la copie, la
modification et la diffusion d'une œuvre, y compris commercialement,
à condition de créditer l'auteur et de partager les versions
dérivées sous la même licence. C'est la licence du manifeste
lui-même et des documents de ce dépôt. (Sous-section 6.4.)

**CI/CD — *Continuous Integration / Continuous Delivery***
Ensemble de pratiques et d'outils qui automatisent la compilation,
les tests et le déploiement d'un logiciel à chaque modification du
code. La CI vérifie que le code reste sain en permanence, la CD
permet de livrer une nouvelle version en production sans rupture
manuelle. (Sous-section 4.3.7.)

**Code civil belge (articles 3.84 et suivants)**
Articles du Livre 3 du Code civil belge issus de la réforme de
2018-2019, qui régissent la copropriété forcée des immeubles bâtis
— quorums d'assemblée générale, majorités qualifiées, calcul des
tantièmes, procurations, conseil de copropriété. KoproGo encode ces
règles directement dans le code Rust de son domaine. (Sous-sections
1.3 et 4.1.3.)

**Conseil de copropriété**
Organe de surveillance obligatoire dans les copropriétés belges de
plus de vingt lots, prévu par le Code civil (Livre 3). Il assiste
le syndic et veille à l'exécution des décisions de l'assemblée
générale. (Sous-section 5.1.)

## D

**DDD — *Domain-Driven Design***
Approche de conception logicielle formalisée par Eric Evans en
2003, qui consiste à structurer le code autour des concepts du
métier modélisé plutôt que des contraintes techniques. Le langage
des spécialistes du métier — *langage ubiquitaire* — devient le
langage du code. (Sous-sections 2.1 et 4.5.)

**DRY — *Don't Repeat Yourself***
Principe formulé par Andy Hunt et Dave Thomas dans *The Pragmatic
Programmer* (1999) : chaque fait de connaissance doit avoir une
représentation unique, sans ambiguïté, dans un système. À ne pas
confondre avec la déduplication mécanique de fragments de code qui
se ressemblent sans porter le même sens. (Sous-section 4.5.)

## E

**Écologie des savoirs**
Concept de Boaventura de Sousa Santos qui désigne l'attitude
consistant à reconnaître la légitimité de plusieurs traditions de
savoir et à les faire dialoguer sans hiérarchie. Elle s'oppose à
la *monoculture du savoir scientifique rigoureux* qui rejette tout
ce qui ne suit pas les protocoles académiques occidentaux.
(Sous-sections 2.6 et 4.5.2.)

**Épistémicide**
Concept de Boaventura de Sousa Santos qui désigne la destruction
systématique des savoirs non-occidentaux, opérée par la
colonisation et prolongée par la mondialisation académique
contemporaine. (Sous-section 2.6.)

## G

**Gate review**
Point de revue formel, hérité de la pratique TOGAF, où l'on vérifie
collectivement, à un jalon donné, que les fondations d'un projet
tiennent, que les choix d'architecture restent cohérents avec les
drivers business et que les décisions consignées en ADR continuent
de faire sens. Ni un check-up annuel de formalité, ni un audit
externe : un rendez-vous régulier de calibrage. (Sous-section
4.1.6.)

## H

**Hexagonale (architecture)**
Style d'architecture proposé par Alistair Cockburn (2005), aussi
appelé *ports and adapters*. Le domaine métier occupe un cœur
isolé ; toutes les communications avec l'extérieur (base de
données, API HTTP, interface utilisateur) passent par des *ports*
(interfaces) que des *adapters* implémentent. Cela permet de
remplacer un adaptateur sans toucher au domaine. (Sous-sections
4.3.4 et 4.5.)

## I

**IaC — *Infrastructure as Code***
Pratique consistant à décrire l'infrastructure d'un système
(serveurs, réseau, configurations) sous forme de fichiers texte
versionnés, plutôt que par configuration manuelle. Permet de
reconstruire un environnement à l'identique, de tracer ses
changements et de les relire. KoproGo et BANKO utilisent Terraform
et Ansible. (Sous-section 4.3.6.)

**ITIL — *Information Technology Infrastructure Library***
Référentiel de bonnes pratiques de gestion des services
informatiques, né au Royaume-Uni dans les années 1980 et structuré
en versions successives jusqu'à ITIL 4 (2019). Couvre la gestion
des incidents, des changements, des problèmes et des releases. La
Méthode Maury le mobilise pour la phase d'exploitation, après mise
en production. (Sous-section 4.4.7.)

## M

**Mottainai (もったいない)**
Expression japonaise mêlant des racines bouddhistes zen et
shintoïstes, exprimant un regret face au gaspillage. Plus qu'une
règle de gestion, une disposition intérieure qui voit dans le
gaspillage une atteinte à la valeur intrinsèque d'une chose. La
militante kényane Wangari Maathai l'a popularisée internationalement
dans les années 2000. (Sous-section 2.4.)

## N

**Nexus**
Cadre de scaling de Scrum publié par Scrum.org en 2015, conçu pour
coordonner trois à neuf équipes Scrum travaillant sur un même
produit. Plus léger que SAFe, il ajoute un *Nexus Integration Team*
et quelques événements de coordination sans imposer de hiérarchie
nouvelle. (Sous-section 4.4.5.)

## P

**PCMN — Plan Comptable Minimum Normalisé**
Plan comptable obligatoire en droit belge pour les entreprises et
nombre d'associations, fixé par arrêté royal et structuré en sept
classes (capitaux, immobilisés, stocks, créances et dettes,
trésorerie, charges, produits). KoproGo le respecte pour la gestion
financière des copropriétés. (Préliminaire de `Methode-Maury.md` et
sous-section 5.1.)

**PR — Pull Request**
Demande d'intégration de modifications dans une branche cible d'un
dépôt Git, qui ouvre un espace de revue, de commentaires et de
discussion avant fusion. C'est le mécanisme principal de
contribution proposé par ce dépôt. (Sous-section 6.2.)

## Q

**Quorum, majorité qualifiée, tantième**
Trois notions juridiques structurantes du droit belge de la
copropriété. Le *quorum* est le nombre minimum de copropriétaires
ou de tantièmes nécessaires pour qu'une assemblée générale puisse
valablement délibérer. La *majorité qualifiée* (par exemple les
deux tiers ou les quatre cinquièmes des tantièmes présents) est
exigée pour certaines décisions importantes. Le *tantième* exprime
la quote-part de chaque lot dans les parties communes ; la somme
des tantièmes d'un immeuble doit toujours être égale à 100 %.
(Sous-section 4.1.3.)

## R

**RFC — *Request for Comments***
Document, hérité de la culture des standards Internet, qui formule
une question ouverte ou une proposition pour qu'elle soit discutée
publiquement avant d'être tranchée. Dans la pratique TOGAF, les RFC
formalisent les décisions encore en suspens, complémentairement aux
ADR qui consignent les décisions prises. (Sous-section 4.1.5.)

## S

**SAFe — *Scaled Agile Framework* (essentiel)**
Cadre de scaling de l'agile à grande échelle créé par Dean
Leffingwell, le plus largement diffusé dans les grandes entreprises.
La Méthode Maury en mobilise la version *essentielle* — la couche
*Essential SAFe*, centrée sur la cadence des Program Increments
toutes les huit à douze semaines — et écarte les couches
supérieures (Large Solution, Portfolio, Full SAFe) considérées
comme des dérives industrielles éloignées de l'esprit du Manifeste
Agile original. (Sous-sections 1.4 et 4.4.6.)

**Santos, Boaventura de Sousa**
Sociologue portugais né en 1940, professeur émérite à l'université
de Coimbra. Une des figures majeures des *épistémologies du Sud*.
Le manifeste mobilise plusieurs de ses concepts — épistémicide,
cinq monocultures et cinq écologies, sociologie des absences et
des émergences — comme outils pour articuler les sagesses du monde
sans les hiérarchiser. (Sous-section 2.6.)

**Scrum**
Cadre agile formalisé par Ken Schwaber et Jeff Sutherland dans les
années 1990 puis publié en 2010 dans le *Scrum Guide*. Organise le
travail d'une équipe en *sprints* de durée fixe (typiquement deux
à quatre semaines) avec quatre événements (Sprint Planning, Daily
Scrum, Sprint Review, Sprint Retrospective) et trois rôles
(Product Owner, Scrum Master, Developers). (Sous-section 4.4.4.)

**Sept générations**
Principe issu de la *Grande Loi de la Paix* (*Kaianere'kó:wa*) de
la Confédération Haudenosaunee, qui demande aux décideurs de garder
en vue les conséquences de leurs choix sur les sept générations à
venir — environ cent quarante ans. Énonce une responsabilité
transgénérationnelle qui dépasse de loin ce que la pensée
politique occidentale moderne avait formulé avant les théories
contemporaines du développement durable. (Sous-section 2.3.)

**SOLID**
Acronyme regroupant cinq principes de conception orientée objet
formulés par Robert C. Martin (Single Responsibility, Open/Closed,
Liskov Substitution, Interface Segregation, Dependency Inversion).
Ces principes sont indissociables de la pratique du *Software
Craftsmanship* et structurent la couche domaine des projets de la
Méthode Maury. (Sous-sections 4.5 et 4.5.2.)

**Sumak kawsay**
Expression kichwa (langue quechua de la cordillère des Andes)
souvent traduite par *bien vivre* ou *vivre en plénitude*.
Reformulée à partir des années 1990 par les mouvements indigènes
équatoriens et boliviens comme proposition politique face aux
modèles extractivistes ; inscrite dans la Constitution équatorienne
de 2008 et la Constitution bolivienne de 2009. (Sous-section 2.2.)

**Syndic, syndic bénévole**
Personne mandatée par l'assemblée générale d'une copropriété belge
pour en assurer la gestion administrative, financière et technique.
Il peut être *professionnel* (inscrit auprès de l'Institut
Professionnel des Agents Immobiliers, métier officiellement classé
en pénurie depuis 2021) ou *bénévole* (un copropriétaire qui
accepte cette responsabilité, le plus souvent sans formation
spécifique). Plus de la moitié des copropriétés belges sont gérées
par des syndics bénévoles. (Sous-section 4.1.1.)

## T

**TDD — *Test-Driven Development***
Pratique de développement formalisée par Kent Beck (eXtreme
Programming, fin des années 1990) qui consiste à écrire un test
qui échoue avant d'écrire le code qui le fait passer, puis à
refactoriser. Cycle dit « Red — Green — Refactor ». La discipline
n'est pas le test pour le test : elle est l'usage du test comme
outil de conception. (Sous-section 4.5.)

**TOGAF — *The Open Group Architecture Framework***
Cadre d'architecture d'entreprise publié et maintenu par The Open
Group, dont la première version date de 1995. Il propose une
méthode de développement d'architecture (*Architecture Development
Method*, ADM) en huit phases bouclées, et formalise les notions
d'ADR, de gate review et de capacités. La Méthode Maury le mobilise
pour la dimension stratégique du « quoi ». (Sous-sections 4.1.5 et
4.4.2.)

## U

**Ubuntu**
Mot des langues nguni d'Afrique australe (zulu, xhosa) dont la
formule la plus citée dit *umuntu ngumuntu ngabantu* — une personne
est une personne par et à travers les autres personnes. Désigne une
ontologie relationnelle, élucidée notamment par le philosophe
sud-africain Mogobe Bernard Ramose dans *African Philosophy
Through Ubuntu* (1999). (Sous-section 2.1.)

## Y

**YAGNI — *You Aren't Gonna Need It***
Principe de l'eXtreme Programming qui invite à ne pas écrire de
code spéculatif pour des besoins futurs hypothétiques. Une
fonctionnalité s'écrit quand elle est utile, pas quand on imagine
qu'elle pourrait l'être un jour. (Sous-section 4.5.)

---

*Glossaire vivant — corrections et compléments bienvenus via les
mécanismes décrits dans [CONTRIBUTING.md](CONTRIBUTING.md).*
