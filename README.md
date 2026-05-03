# Manifeste Maury

*Une pratique du logiciel sobre, durable et transmissible*

**Par Farah et Gilles Maury — Bruxelles, version 0.9 de travail**

---

## Note de lecture

Ce document est une **version de travail** rassemblant l'ensemble des sections rédigées et des sections à venir. Les passages [À COMPLÉTER] sont des stubs explicites qui attendent vos précisions ou décisions. Les marqueurs [DÉCISION À DEUX] signalent des points qui appellent une validation conjointe avant ancrage définitif.

Le manifeste est volontairement structuré de façon explicite. Cette transparence architecturale n'est pas un choix esthétique — elle est cohérente avec un principe que nous défendons : un système qui rend visibles ses propres responsabilités est plus juste qu'un système qui les dissimule. Nous l'appliquons à l'architecture logicielle et nous nous l'appliquons à nous-mêmes.

**Changements de la version 0.9 par rapport à la 0.8 :** rédaction complète de la section 6 conclusive. Le manifeste est désormais destiné à devenir le README d'un dépôt GitHub épinglé à `github.com/gilmry/manifest`, et la section 6 est rédigée dans un format adapté à cette destination — clôture pratique plutôt qu'essai conclusif littéraire. Cinq sous-sections : invitation non-doctrinaire, mode de contribution via GitHub, liens consolidés vers les projets, licences et caractère vivant du document, clôture sobre. Les annexes A à E restent à rédiger ultérieurement comme fichiers séparés du dépôt. Le manifeste est désormais structurellement complet — toutes les sections du corps sont rédigées.

---

# Section 0 — Préambule

Nous sommes Farah et Gilles Maury, un couple installé à Bruxelles. Farah étudie l'informatique de gestion en promotion sociale. Gilles est *software craftsmanship advocate*, *security officer* et *IT support ambassador* à l'UCLouvain. Nous portons un même nom et nous travaillons ensemble.

Depuis plusieurs années, nous construisons des logiciels pour des communautés concrètes — la copropriété belge avec KoproGo, le banking tunisien avec BANKO, l'école de notre fils à Evere avec EcoleHub. Nous le faisons à deux, avec l'aide d'agents IA que nous supervisons étroitement, en respectant un ensemble de principes hérités de l'artisanat logiciel, de l'agilité originelle et de plusieurs sagesses du monde.

Ce site rassemble ce que nous avons appris. Nous l'écrivons d'abord pour transmettre — aux étudiants que Farah côtoie, aux stagiaires que Gilles encadre, à nos pairs développeurs, aux dirigeants d'ASBL ou d'écoles qui cherchent des outils faits pour eux. Nous le mettons à disposition sans demander qu'on s'en réclame. Prenez ce qui vous sert. Laissez le reste.

Vous trouverez ici :

- **Notre constat** sur ce qui ne va pas dans le numérique d'aujourd'hui, formulé sans agressivité mais sans complaisance
- **Les sources** auxquelles nous puisons : sagesses du monde, pensée critique contemporaine, traditions de résistance internes au logiciel
- **Nos convictions** en quelques phrases — c'est le cœur, lisez ça d'abord si vous êtes pressé
- **La Méthode Maury**, notre façon concrète de produire du logiciel avec des agents IA supervisés
- **Nos projets** comme preuves vivantes : KoproGo, BANKO, EcoleHub
- **Une invitation** à reprendre, critiquer, prolonger ce que nous proposons

Tout est sous licence libre. Le code est en AGPL-3.0 sur GitHub. Les textes sont en CC-BY-SA. Les vidéos sont sur YouTube. Nous ne vendons rien sur ce site.

Bonne navigation.

*Farah et Gilles Maury — Bruxelles, [DATE À COMPLÉTER]*

---

# Section 1 — Le constat

Avant d'expliquer comment nous travaillons, il faut dire honnêtement ce qui nous y a poussés. Le numérique tel qu'il fonctionne aujourd'hui pose cinq problèmes que nous voyons quotidiennement, dans nos métiers comme dans nos engagements. Nous les nommons sans agressivité, mais sans complaisance non plus. Il ne s'agit pas d'un procès — il s'agit d'un diagnostic partagé par beaucoup, formulé clairement.

## 1.1 — Le numérique consomme énormément, et l'on commence à peine à compter

Un grand modèle de langage entraîné aujourd'hui consomme l'équivalent énergétique de plusieurs centaines de foyers pendant un an. Un ERP industriel charge en mémoire des centaines de modules dont il n'utilisera presque rien. Un site web moyen pèse aujourd'hui plus de deux mégaoctets, contre quelques dizaines de kilooctets il y a vingt ans pour rendre les mêmes services. Les centres de données représentent désormais plusieurs pour cents de la consommation électrique mondiale, et leur croissance dépasse celle de la production d'énergie décarbonée.

Ces ordres de grandeur ne sont pas marginaux. Ils sont structurels. Le secteur du numérique est devenu, en silence, l'une des industries les plus consommatrices de la planète. Et la mesure publique de cette consommation reste lacunaire : peu d'éditeurs publient leurs métriques carbone par requête, peu de DSI suivent l'empreinte de leur stack, peu d'utilisateurs savent ce que coûte une recherche en ligne.

Nous mesurons cette empreinte sur nos propres logiciels, et nous publions les résultats. Nous pensons que ce qui n'est pas mesuré ne peut pas être amélioré.

## 1.2 — Les logiciels qu'on déploie aujourd'hui dureront moins longtemps que ceux d'hier

Un logiciel de comptabilité écrit en COBOL dans les années soixante-dix est encore en production dans certaines administrations. Un logiciel écrit en JavaScript moderne en 2020 a déjà besoin d'être entièrement refondu en 2026 parce que son framework n'est plus maintenu, ses dépendances sont obsolètes, son écosystème a changé.

Nous n'évaluons pas la durabilité d'un logiciel à sa modernité, mais à sa capacité à être maintenu, lu et corrigé par des développeurs qui n'étaient pas là quand il a été écrit. Cette capacité s'est dégradée. Les frameworks à la mode imposent des migrations permanentes. Les chaînes de dépendances explosent. Les bonnes pratiques d'il y a cinq ans deviennent les anti-patterns d'aujourd'hui.

Le résultat est une dette technique généralisée que personne n'assume vraiment, et qui se traduit par des coûts cachés considérables pour les organisations qui en héritent. Les communautés qui peuvent le moins se le permettre, comme les ASBL et les petites structures publiques, sont celles qui en souffrent le plus.

## 1.3 — Les outils dominants ne sont pas faits pour les communautés qu'ils prétendent servir

Un ERP global comme Odoo, SAP ou Salesforce est conçu pour s'adapter à toute organisation, partout. En conséquence, il n'est conçu pour aucune en particulier. Une copropriété belge qui veut respecter les articles 3.84 et suivants du Code civil belge sur les assemblées générales doit composer avec un produit qui ne connaît pas ces articles. Une école d'Evere qui veut organiser sa coopération avec les parents doit utiliser un outil pensé pour des entreprises californiennes. Une banque tunisienne qui veut respecter le droit local du financement participatif doit s'arranger avec une plateforme qui ne le modélise pas.

Ces écarts ne sont pas anecdotiques. Ils créent des angles morts juridiques, des contournements artisanaux, des contournements qui finissent par devenir l'usage réel mais que personne ne documente. Les communautés concrètes paient pour des outils qui ne les servent pas, et passent ensuite des années à les détourner pour qu'ils marchent à peu près.

Nous pensons qu'il vaut mieux écrire un outil étroitement adapté à un contexte donné que d'utiliser un outil large qui ne convient à personne. Cela suppose d'accepter de produire des logiciels qui ne s'adresseront pas au monde entier — mais qui serviront vraiment ceux à qui ils s'adressent.

## 1.4 — Les mouvements nés libres se sont laissé enfermer

Le Manifeste Agile a été signé en 2001 par dix-sept développeurs qui se définissaient eux-mêmes comme des anarchistes organisationnels. Ils refusaient les processus lourds de l'industrie logicielle de l'époque, ils défendaient la simplicité, le rythme soutenable, l'auto-organisation, le respect des individus.

Vingt-cinq ans plus tard, l'agilité est vendue en certifications coûteuses. Des frameworks comme SAFe imposent dix niveaux hiérarchiques aux entreprises qui les adoptent. Des cabinets de conseil facturent des centaines de milliers d'euros pour des transformations agiles qui produisent des organigrammes plus complexes que ceux qu'elles remplacent. Le vocabulaire originel a été préservé, l'esprit a été inversé.

Le même mouvement s'observe ailleurs. L'open source est devenu un argument marketing pour des entreprises qui contribuent peu et extraient beaucoup. Les pratiques DevOps sont devenues des produits SaaS payants. La sobriété numérique elle-même commence à être instrumentalisée comme outil de différenciation commerciale, sans que les pratiques changent vraiment.

Nous ne pensons pas que tous les frameworks soient mauvais. Nous pensons qu'il faut savoir distinguer ce qui dans ces cadres relève d'une sagesse pratique éprouvée, de ce qui relève de leur capture par des intérêts marchands.

## 1.5 — L'artisanat logiciel s'est éloigné, alors qu'on n'en a jamais eu autant besoin

Un développeur qui prend le temps de comprendre le métier qu'il modélise, qui écrit ses tests avant son code, qui se relit, qui refactorise, qui documente sobrement, qui pense aux développeurs qui hériteront de son travail dans dix ans — ce développeur est devenu l'exception. La pression industrielle pousse à livrer vite, à externaliser, à empiler les couches, à utiliser des bibliothèques sans les avoir lues, à coller des morceaux trouvés en ligne sans les avoir compris.

L'arrivée de l'intelligence artificielle générative aggrave cette tendance si elle est mal utilisée. Un développeur qui copie sans relire ce qu'un assistant lui propose ne fait pas de l'artisanat — il fait du remplissage. Mais l'IA peut aussi servir l'artisanat si elle est utilisée comme un outil supervisé : générer rapidement le code répétitif, suggérer des structures, identifier des patterns, en laissant à l'humain la responsabilité du jugement, de la cohérence et du sens.

Cette responsabilité ne peut pas être déléguée. Elle est ce qui distingue un métier d'une chaîne de production. Nous pensons qu'on a sous-estimé combien la dignité du travail de développeur dépend de la possibilité de bien faire, et combien cette possibilité a été grignotée par les vingt dernières années d'industrialisation.

---

Voilà ce que nous voyons. Ce constat n'est pas spécialement original — beaucoup de praticiens, de chercheurs et d'utilisateurs en font le même. Ce qui est plus rare, c'est de tenir ces cinq constats ensemble et d'en tirer une pratique cohérente, plutôt que de les énoncer en restant dans la plainte ou la critique extérieure.

Si vous partagez tout ou partie de ce constat, vous trouverez peut-être dans la suite des éléments qui vous serviront. Si vous le trouvez excessif ou injuste, dites-le nous : nous écrivons pour discuter, pas pour avoir raison.

---

# Section 2 — Nos sources

Avant de présenter nos convictions et notre méthode, nous devons dire honnêtement à qui nous devons ce que nous pensons. Aucune des idées que ce manifeste articule n'a été inventée par nous. Toutes nous viennent de traditions que nous avons rencontrées, lues, écoutées, et qui nous ont aidés à formuler ce que nous portions sans toujours savoir le nommer. Cette section présente trois familles de sources que nous voulons traiter avec le respect dû à chacune.

La première famille rassemble cinq sagesses du monde, venues de cultures très différentes, qui ont chacune formulé à leur manière des intuitions sur ce qu'est une activité humaine bien faite. Nous les présentons une à une, depuis leur tradition propre, sans les hiérarchiser et sans les fondre dans une synthèse qui les trahirait.

La deuxième famille rassemble la pensée critique contemporaine de Boaventura de Sousa Santos, sociologue portugais dont l'œuvre nous a aidés à articuler les apports des sagesses sans les dominer.

La troisième famille rassemble les traditions de résistance internes au logiciel, qui ont préservé contre vents et marées une pratique vivante du métier dont nous nous reconnaissons héritiers.

Une précaution liminaire avant d'entrer dans le détail. Présenter cinq sagesses non-européennes dans un manifeste sur le logiciel sobre expose à un risque que nous voulons nommer pour mieux l'éviter. Ce risque, c'est de **prendre des concepts d'autres cultures et de les utiliser comme arguments décoratifs** pour un projet qui leur reste fondamentalement étranger. Nous avons cherché à faire l'inverse — reconnaître ces sagesses comme des partenaires de pensée, nommer leurs penseurs, respecter leur contexte d'émergence, et dire clairement ce qu'elles apportent que la pensée occidentale moderne ne nous apporte pas seule. Si nous y avons échoué malgré ces précautions, nous l'apprendrons avec gratitude des lecteurs qui voudront bien nous le dire.

## 2.1 — Ubuntu : l'ontologie relationnelle

Ubuntu est un mot des langues nguni d'Afrique australe, principalement le zulu et le xhosa, dont la formule la plus citée dit *"umuntu ngumuntu ngabantu"* — une personne est une personne par et à travers les autres personnes. Cette formule n'est pas un proverbe parmi d'autres. Elle énonce une **ontologie**, c'est-à-dire une conception fondamentale de ce qu'est une chose, et plus particulièrement de ce qu'est un être humain.

Le philosophe sud-africain Mogobe Bernard Ramose a consacré une œuvre majeure à l'élucidation de cette ontologie, notamment dans son livre *African Philosophy Through Ubuntu* (1999). Ramose insiste sur un point qui résiste à la traduction occidentale : ubuntu n'est pas un *humanisme africain* au sens d'un substantif désignant un état stable. C'est un mot verbal qui désigne un **processus** — le devenir-personne par les relations. Le préfixe *ubu-* indique la généralité ouverte, le *-ntu* le point nodal où l'être prend forme. Ensemble, ubuntu désigne le processus par lequel une humanité concrète advient à travers ses relations avec les autres et avec le monde.

Cette ontologie a des conséquences profondes que la pensée européenne moderne, atomiste et individualiste, n'avait pas formulées avec la même clarté. Une personne n'est pas d'abord un atome qui entrerait ensuite en relation. Elle est, dès l'origine, ce que ses relations font d'elle — sa famille, ses ancêtres, sa communauté, ses descendants, le monde naturel qu'elle habite. Une décision qui blesse les relations blesse la personne elle-même. Une décision qui prend soin des relations prend soin de la personne. Cette intuition ontologique fonde une éthique dans laquelle la séparation entre intérêt individuel et bien commun est moins tranchée que dans la tradition libérale occidentale.

Pour notre manifeste, ubuntu n'est pas une métaphore décorative. C'est une thèse philosophique précise qui éclaire pourquoi le Domain-Driven Design fonctionne quand il fonctionne — un concept métier comme *Copropriétaire* n'a pas de sens en dehors de ses relations avec *Bâtiment*, *Lot*, *Tantième*, *Assemblée générale*. C'est aussi pourquoi nous tenons aux modules communautaires de KoproGo plutôt qu'à un cœur transactionnel pur — parce qu'une copropriété n'est pas une collection de propriétaires individuels, c'est un tissu de relations dont les outils numériques doivent prendre soin.

## 2.2 — Sumak kawsay : vivre en plénitude

Sumak kawsay est une expression kichwa, langue quechua de la cordillère des Andes, que l'on traduit habituellement par *"bien vivre"* ou *"vivre en plénitude"*. La traduction littérale serait plus proche de *"la vie pleine"* — sumak signifiant à la fois le plein, le beau et le juste, et kawsay désignant l'acte même de vivre. L'expression a été reformulée et systématisée à partir des années 1990 par des intellectuels et organisations indigènes équatoriens et boliviens, notamment dans le mouvement CONAIE en Équateur, comme proposition politique et culturelle face aux modèles de développement extractivistes qui ravageaient leurs territoires.

Le sumak kawsay a été inscrit dans la **Constitution équatorienne de 2008** comme principe fondateur d'une nouvelle forme de coexistence publique en harmonie avec la nature, et dans la **Constitution bolivienne de 2009** sous des formulations apparentées (suma qamaña en aymara, ñandereko en guarani). L'Équateur est devenu, avec cette Constitution, le premier pays au monde à inscrire les *droits de la nature* dans son texte fondamental — la Pachamama, la Terre-Mère, devient une entité à laquelle la Constitution reconnaît des droits propres à exister, persister et se régénérer.

Des théoriciens comme Alberto Acosta, Magdalena León ou Javier Lajo soulignent que le sumak kawsay n'est pas une théorie aboutie — c'est une **proposition sociale ouverte** qui peut être enrichie. Elle articule trois dimensions inséparables que la pensée andine désigne comme *Allin Munay* (sentir bien), *Allin Yachay* (penser bien) et *Allin Ruay* (faire bien) — l'harmonie n'est pas seulement une pensée, c'est aussi un sentiment et un acte. Cette intégration entre savoir, sentir et agir refuse la séparation occidentale entre raison, émotion et pratique.

Pour notre manifeste, sumak kawsay éclaire ce que nous voulons dire par *sobriété* sans tomber dans l'ascétisme culpabilisant. La sobriété n'est pas la privation. Elle est la **plénitude** atteinte quand on cesse de courir après un développement infini et quand on prend soin des conditions concrètes qui permettent à la vie de tenir. Un logiciel sobre, dans cet horizon, n'est pas un logiciel qui se prive — c'est un logiciel qui prend la juste mesure de ce qu'il consomme et qui restitue à sa communauté ce qu'il prend à son environnement.

## 2.3 — Les sept générations : la responsabilité transgénérationnelle

Le principe des sept générations vient de la **Grande Loi de la Paix** (*Kaianere'kó:wa* en mohawk), constitution orale puis écrite de la Confédération Haudenosaunee, dont les origines remonteraient selon les estimations entre le XIIe et le XVe siècle. Cette confédération, longtemps appelée Iroquoise par les colons français, rassemble historiquement cinq nations — Mohawk, Oneida, Onondaga, Cayuga, Seneca — rejointes plus tard par les Tuscarora pour former les Six Nations. Elle est reconnue comme l'une des plus anciennes démocraties participatives au monde, et son fonctionnement a influencé, par l'intermédiaire de Benjamin Franklin notamment, la rédaction de la Constitution des États-Unis.

La Grande Loi de la Paix énonce un principe que les chefs des nations confédérées doivent garder présent à l'esprit dans toutes leurs délibérations : *"Look and listen for the welfare of the whole people and have always in view not only the present but also the coming generations, even those whose faces are yet beneath the surface of the ground — the unborn of the future Nation."* La formule des **visages encore sous la surface du sol** désigne ceux qui ne sont pas encore nés et que la décision actuelle affectera pourtant. Le chiffre sept correspond à un horizon de plusieurs siècles — environ cent quarante ans — au-delà duquel les conséquences d'une décision deviennent imprévisibles mais où la responsabilité ne s'éteint pas pour autant.

Ce principe énonce une **responsabilité transgénérationnelle** qui dépasse de loin ce que la pensée politique occidentale moderne avait formulé avant les théories contemporaines du développement durable. On ne décide pas seulement pour soi. On ne décide pas seulement pour ses contemporains. On décide pour ceux qui ne pourront jamais voter, jamais protester, jamais nous demander des comptes — et c'est précisément cette asymétrie qui appelle un soin particulier. La justice intergénérationnelle, telle que la philosophie contemporaine la formule depuis Hans Jonas et plus récemment Iris Marion Young, retrouve une intuition que les Haudenosaunee avaient codifiée plusieurs siècles auparavant.

Pour notre manifeste, les sept générations éclairent notre rapport au temps long du logiciel. Un système informatique que nous écrivons aujourd'hui sera maintenu, modifié, lu par des développeurs qui ne sont pas encore nés à la profession quand nous l'écrivons. Une dette technique que nous laissons sera payée par eux. Une documentation que nous écrivons soigneusement leur économisera des semaines de travail. Cette responsabilité ne doit pas être déléguée à un futur indéterminé — elle est notre responsabilité maintenant, exactement comme un chef de clan haudenosaunee porte aujourd'hui la responsabilité des visages encore sous la surface du sol.

## 2.4 — Mottainai : le respect des choses

Mottainai (もったいない) est une expression japonaise qui mêle des racines bouddhistes zen et shintoïstes, et qui exprime un **regret face au gaspillage**. Étymologiquement, l'expression dérive de *mottai* (impertinence, sacrilège) et *nai* (négation, absence) — quelque chose qui est mottainai est quelque chose dont on aurait honte de gaspiller la valeur intrinsèque. La traduction française approchée serait *"quel dommage de gaspiller cela"*, mais la formule perd alors la dimension presque religieuse du regret qu'elle porte en japonais.

Le concept a une histoire longue dans la culture japonaise, associé aux pratiques de réparation (*kintsugi*, l'art de réparer la céramique brisée à l'or, qui rend visible la cassure plutôt que de la dissimuler), de réutilisation (*boro*, les textiles rapiécés des paysans qui devenaient parfois plus beaux que neufs), et de soin des objets ordinaires. La militante kényane Wangari Maathai, lauréate du prix Nobel de la paix, a popularisé mottainai à l'échelle internationale dans les années 2000 comme principe écologique applicable au-delà du Japon — réduire, réutiliser, recycler, et y ajouter le respect.

Ce qui distingue mottainai d'une éthique purement utilitaire de la non-gaspillage, c'est sa dimension **affective et presque spirituelle**. Il ne s'agit pas seulement de calculer qu'on perd de la valeur économique en jetant. Il s'agit de ressentir qu'une chose mérite plus de respect que ce qu'on lui accorde. Une chose mottainai est une chose qui appelle un soin qu'on ne lui donne pas. Cette dimension du sentiment fait de mottainai bien plus qu'une règle de gestion — c'est une **disposition intérieure** à l'égard du monde.

Pour notre manifeste, mottainai éclaire ce que nous voulons dire par *sobriété logicielle* dans sa dimension la plus quotidienne. Le code spéculatif que nous n'écrivons pas, les bibliothèques que nous n'ajoutons pas sans raison, les serveurs que nous ne sur-dimensionnons pas, les commits que nous écrivons proprement plutôt qu'à la va-vite — toutes ces pratiques relèvent de mottainai avant de relever d'une optimisation technique. Elles expriment un regret face au gaspillage qui est plus précieux que la règle qu'elles produisent.

## 2.5 — Le Cantique des créatures : la fraternité étendue

Le *Cantique des créatures* (*Cantico delle creature* en italien, parfois appelé *Cantico di frate Sole*, Cantique de frère Soleil) est un poème écrit par François d'Assise vers 1224-1226, peu avant sa mort, en dialecte ombrien. Il est considéré comme l'un des premiers grands textes de la littérature italienne, antérieur à Dante, et comme un texte fondateur d'une **spiritualité écologique** dans la tradition chrétienne.

Le Cantique loue Dieu à travers les créatures — frère soleil, sœur lune, frères vents, sœur eau, frère feu, sœur notre mère la terre, et même sœur la mort corporelle. Cette utilisation systématique du vocabulaire familial pour désigner les éléments naturels n'est pas un trope poétique — elle énonce une **ontologie de la fraternité étendue** dans laquelle l'humain n'est pas séparé de la nature mais en fait partie au même titre que les autres créatures, comme les membres d'une même famille. François d'Assise refuse explicitement la posture de domination de la nature qui caractérisera plus tard une certaine modernité européenne, et il préfigure ce que la pensée écologique contemporaine appelle l'éthique du vivant.

Cette spiritualité a marqué l'ordre franciscain qu'il a fondé, et continue d'inspirer la pensée chrétienne contemporaine sur l'écologie. L'encyclique *Laudato si'* du pape François, publiée en 2015, tire son titre du premier vers du Cantique (*Laudato si', mi' Signore* — Loué sois-tu, mon Seigneur) et reprend explicitement la posture de fraternité avec la nature comme principe d'une écologie intégrale. Cette filiation montre que le Cantique n'est pas un texte clos du XIIIe siècle — c'est une source vivante qui continue de nourrir la pensée contemporaine.

Pour notre manifeste, le Cantique des créatures éclaire la dimension écologique de la sobriété logicielle dans sa racine européenne et chrétienne. Tous les lecteurs de ce manifeste ne se reconnaissent pas dans cette tradition, et c'est bien ainsi. Mais beaucoup en sont issus, qu'ils s'y reconnaissent explicitement ou non. Pour ceux-là, le Cantique propose un ancrage qui rend l'attention écologique au logiciel non pas comme une contrainte importée d'autres cultures, mais comme un héritage qui leur appartient déjà et qu'ils n'avaient pas suffisamment activé. La sobriété logicielle, dans cet horizon, n'est pas un ascétisme — c'est une **fraternité étendue** qui s'applique aussi aux serveurs qui consomment l'électricité, aux mineurs qui extraient le lithium des batteries, aux développeurs futurs qui hériteront du code.

## 2.6 — Boaventura de Sousa Santos : un partenaire de pensée contemporain

Boaventura de Sousa Santos est un sociologue portugais né en 1940, professeur émérite à l'université de Coimbra et professeur à l'université du Wisconsin-Madison. Son œuvre, qui couvre plusieurs décennies, est une des contributions majeures à ce qu'on appelle aujourd'hui les *épistémologies du Sud* — un effort pour reconnaître la légitimité des savoirs produits hors du canon académique européen et nord-américain, et pour faire dialoguer ces savoirs avec la pensée occidentale sur un pied d'égalité.

Plusieurs concepts de Santos nous ont aidés à articuler les apports des sagesses présentées plus haut sans les dominer ni les hiérarchiser.

**L'épistémicide** désigne la destruction systématique des savoirs non-occidentaux opérée par la colonisation et poursuivie par la mondialisation académique contemporaine. Les sagesses ubuntu, sumak kawsay, sept générations et autres ne sont pas des reliques exotiques d'un passé révolu — elles sont des savoirs vivants qui ont été activement étouffés par cinq siècles de domination européenne, et leur résurgence contemporaine est un acte de résistance épistémique autant qu'une contribution philosophique.

**Les cinq monocultures et les cinq écologies correspondantes**. Santos identifie cinq formes de réduction de la diversité humaine à un standard unique qui produisent ce qu'il appelle la *non-existence* — c'est-à-dire le rejet hors du champ de la légitimité de tout ce qui n'entre pas dans ce standard. À chacune de ces monocultures, il oppose une *écologie* qui restaure la pluralité. La monoculture du savoir scientifique rigoureux est contestée par l'**écologie des savoirs**. La monoculture du temps linéaire progressiste par l'**écologie des temporalités**. La monoculture de l'échelle universelle par l'**écologie des échelles**. La monoculture de la productivité capitaliste par l'**écologie des productivités**. La monoculture de la classification naturelle des hiérarchies humaines par l'**écologie des reconnaissances**.

**La sociologie des absences et des émergences**. Santos propose de rendre visible ce que les monocultures rendent invisible — les pratiques, les savoirs, les modes de vie qui existent mais que le système dominant traite comme s'ils n'existaient pas. Et de faire émerger les **possibles** qui sont déjà en germe dans le présent — ce qu'il appelle le *Pas Encore* en référence à Ernst Bloch. Cette sociologie est un outil pour repérer ce qui se passe vraiment dans le monde, par-delà ce que le récit dominant raconte.

Ces concepts ne sont pas pour nous une grille de lecture qui chapeauterait les sagesses présentées plus haut. Santos lui-même refuserait cette posture qui reproduirait à son insu la monoculture épistémique qu'il critique. Les concepts de Santos sont des **outils contemporains** qui nous aident à entendre ce que les sagesses disent, sans nous dispenser de les écouter chacune dans sa propre langue.

Pour notre manifeste, l'apport de Santos est principalement méthodologique. Il nous donne un vocabulaire pour articuler la convergence par la diversité que nous avons observée empiriquement entre KoproGo et BANKO, et pour comprendre pourquoi les sept invariants techniques que nous respectons traduisent en pratique des principes que des cultures très différentes ont chacune formulés à leur manière.

## 2.7 — Les traditions de résistance internes au logiciel

Notre dernière famille de sources rassemble des traditions qui ont préservé, à l'intérieur même de l'industrie logicielle, une pratique vivante du métier. Nous nous reconnaissons héritiers de ces traditions et nous voulons les nommer parce qu'elles ont permis que la transmission ne s'éteigne pas, malgré les pressions industrielles qui auraient pu la faire disparaître.

**Le Manifeste Agile original (2001).** Signé en février 2001 à Snowbird, Utah, par dix-sept développeurs venus de différentes traditions méthodologiques — Kent Beck pour l'eXtreme Programming, Ken Schwaber et Jeff Sutherland pour Scrum, Alistair Cockburn pour les méthodes Crystal, Robert C. Martin, Martin Fowler et d'autres — le Manifeste Agile énonce quatre valeurs et douze principes qui décrivent une manière humaine de produire du logiciel. Les valeurs privilégient les individus et leurs interactions sur les processus et les outils, le logiciel qui fonctionne sur la documentation exhaustive, la collaboration avec le client sur la négociation contractuelle, et l'adaptation au changement sur le suivi d'un plan. Les douze principes formulent des règles concrètes — livrer fréquemment, accueillir le changement, rythme soutenable, simplicité comme art de maximiser le travail non fait, rétrospectives régulières. Vingt-cinq ans plus tard, ces valeurs et principes restent **plus radicaux et plus pertinents** que la plupart des frameworks qui prétendent les industrialiser, et nous y revenons régulièrement comme à une source.

**Le mouvement Software Craftsmanship.** Lancé en 2009 par un groupe de développeurs autour de Robert C. Martin (auteur de *Clean Code*) avec le *Manifesto for Software Craftsmanship*, ce mouvement complète le Manifeste Agile en insistant sur la qualité technique du code lui-même. Là où l'agilité originelle parlait de processus humain, le craftsmanship parle de **dignité du métier** — un développeur n'est pas un fournisseur de fonctionnalités, c'est un artisan qui porte une responsabilité envers ceux qui hériteront de son travail. Le mouvement promeut les pratiques de TDD, de refactoring continu, de revue de code par les pairs, et défend l'idée qu'un développeur a le devoir professionnel de refuser de livrer du code de mauvaise qualité même si le client ou la hiérarchie l'exigent. Cette posture éthique du métier nous est essentielle.

**Le mouvement du logiciel libre.** Fondé en 1983 par Richard Stallman avec le projet GNU et la création de la Free Software Foundation en 1985, le mouvement du logiciel libre a énoncé que le logiciel, parce qu'il structure désormais une part croissante de la vie humaine, doit respecter quatre libertés fondamentales — exécuter le programme pour tout usage, étudier son fonctionnement et l'adapter à ses besoins, redistribuer des copies, améliorer le programme et publier les améliorations. La GPL et plus tard l'AGPL, licences que Stallman a promues, sont conçues comme des **licences-vaccins** qui propagent ces libertés à toutes les œuvres dérivées. Nous publions tous nos projets — KoproGo, BANKO, EcoleHub — sous AGPL-3.0, et nous nous reconnaissons dans la filiation politique du mouvement du logiciel libre, même si notre vocabulaire diffère parfois de celui de Stallman.

**Les commons numériques européens.** Une tradition plus diffuse rassemble des associations et fondations européennes qui défendent les **biens communs numériques** comme alternative aux plateformes extractivistes américaines. Framasoft en France, avec son projet *Dégooglisons Internet* et la suite Framacloud, a démontré qu'on pouvait offrir des alternatives libres et hébergées en Europe à la plupart des services Google. La Fondation NLnet aux Pays-Bas finance depuis des décennies des projets de logiciels libres d'intérêt public — du protocole SMTP à des outils contemporains de souveraineté numérique. La Fondation Wikimedia, bien que d'origine américaine, est largement soutenue en Europe et incarne l'idée d'un savoir partagé comme bien commun. Cette tradition européenne nous parle parce qu'elle articule la défense du logiciel libre avec une conscience explicite des enjeux de souveraineté politique, de protection des données personnelles et de durabilité écologique.

**La tradition open source européenne plus large.** Au-delà des organisations militantes, une tradition européenne plus large existe dans le tissu industriel et académique. Des projets comme Linux (initié en Europe par Linus Torvalds en 1991), PostgreSQL, le langage Rust (dont la fondation prolonge le travail initié par Mozilla), nginx, et tant d'autres briques fondamentales de l'infrastructure numérique mondiale sont nés ou ont prospéré dans l'écosystème européen. Cette tradition n'est pas idéologique au sens du logiciel libre stallmanien, mais elle partage avec lui une **éthique de qualité technique** et un refus pragmatique des modèles propriétaires fermés. Elle fournit la matière concrète sur laquelle nos projets s'appuient — sans Linux, sans PostgreSQL, sans Rust, sans les milliers de bibliothèques que nous utilisons quotidiennement, KoproGo et BANKO ne pourraient simplement pas exister.

## 2.8 — Comment ces sources tiennent ensemble

Onze sources présentées dans cette section — cinq sagesses du monde, un sociologue contemporain, cinq traditions de résistance internes au logiciel. Cette diversité pourrait sembler éclectique. Elle ne l'est pas, à condition de comprendre comment ces sources dialoguent sans se confondre.

Les **cinq sagesses** apportent une fondation **anthropologique et éthique** que la pensée européenne moderne n'a pas formulée seule. Elles disent quelque chose de ce qu'est une activité humaine bien faite, de ce qu'est une responsabilité tenue, de ce qu'est un soin véritable des choses, des personnes et du temps. Elles ne sont pas substituables les unes aux autres — chacune apporte sa précision propre — mais elles convergent sur une intuition partagée : l'humain n'est pas un atome isolé, l'activité productive n'est pas une extraction, le temps n'est pas un calcul de court terme.

**Santos** apporte un **vocabulaire contemporain** pour articuler ces sagesses sans les dominer. Sans lui, on risquerait soit de les juxtaposer sans comprendre ce qui les fait dialoguer, soit de les fondre dans une synthèse qui les trahirait. Avec lui, on peut reconnaître que chacune apporte un accès local à des principes qui se laissent retrouver dans plusieurs traditions, sans qu'aucune tradition ne soit l'arbitre des autres.

Les **traditions internes au logiciel** apportent la **pratique située** où ces principes peuvent s'incarner. Le Manifeste Agile, le Software Craftsmanship, le logiciel libre, les commons numériques, l'open source européen — toutes ces traditions ont préservé contre les pressions industrielles une pratique vivante du métier, et leurs apports techniques précis sont ce qui rend possible la traduction des principes éthiques en pratiques opérationnelles que la section 4 du manifeste a décrites.

L'agencement de ces trois familles n'est pas linéaire. Les sagesses fondent éthiquement, Santos articule méthodologiquement, les traditions techniques exécutent pratiquement. Mais en réalité, chaque famille nourrit les deux autres en retour. Les pratiques techniques que nous menons sur KoproGo et BANKO nous ont aidés à comprendre ubuntu mieux que la lecture théorique seule. Les sagesses non-occidentales nous ont aidés à voir dans l'agilité originelle des dimensions que nous n'avions pas perçues. Santos nous a aidés à formuler ce que nos pratiques contiennent comme ressources critiques inexploitées. Cette circulation entre les trois familles est ce qui fait la vitalité de notre articulation.

C'est cette articulation que les convictions de la section 3 expriment de manière condensée, et que la méthode de la section 4 met en œuvre opérationnellement. La section 2 est donc le **fondement philosophique** sur lequel tout le manifeste repose. Elle peut être lue après les autres sections, comme un retour réflexif sur ce qui a permis le reste. Elle peut aussi être lue avant, comme une mise en condition de la lecture. Les deux ordres se justifient.

---

# Section 3 — Nos convictions

Voici, en quelques phrases, ce que nous croyons à propos du logiciel. Ces convictions ne sont pas des dogmes. Elles sont le précipité de nos expériences, de nos lectures et de nos erreurs. Elles évolueront. Si vous en partagez certaines et pas d'autres, c'est normal et c'est sain.

## Conviction 1 — Un logiciel qui dure trente ans vaut mieux que dix logiciels qui durent trois ans

Le numérique consomme énormément parce qu'il jette en permanence. Refaire, migrer, refondre, réécrire — chaque itération coûte en ressources humaines, en énergie, en mémoire collective perdue. Nous écrivons du code conçu pour être lisible et maintenable longtemps, par d'autres que nous, dans des langues que nous ne parlons pas encore.

## Conviction 2 — L'intelligence artificielle génère, l'humain valide

Nous utilisons des agents IA tous les jours. Ils accélèrent considérablement notre travail. Mais ils n'ont pas de jugement métier, pas de sens des invariants, pas de responsabilité juridique. Toute production d'un agent IA passe par une validation humaine impitoyable avant d'être intégrée. Cette règle ne souffre aucune exception. Elle est ce qui distingue une utilisation respectueuse de l'IA d'une délégation dangereuse.

## Conviction 3 — Les communautés concrètes méritent des outils faits pour elles

Une copropriété belge n'est pas un département d'une multinationale américaine. Une école d'Evere n'est pas une école californienne. Une banque tunisienne n'est pas une banque suisse. Les ERP globaux trahissent ces communautés en leur imposant des modèles étrangers. Nous construisons des outils qui partent du contexte local et qui parlent la langue du métier réel.

## Conviction 4 — La transparence du code est une condition de la confiance

Nous publions tout sous licence libre AGPL-3.0. Le code est lisible, auditable, modifiable par quiconque. Quand un logiciel touche au droit, à l'argent ou aux enfants, nous estimons que la confiance ne peut pas reposer sur la promesse d'un éditeur — elle doit reposer sur la possibilité de vérifier.

## Conviction 5 — Les rituels de l'agilité originelle sont une sagesse à préserver

Le rythme soutenable, les revues régulières, les rétrospectives, l'auto-organisation des équipes, la simplicité comme art de maximiser le travail non fait — ces principes énoncés dans le Manifeste Agile de 2001 décrivent une manière humaine de produire du logiciel. Nous les pratiquons et nous les enseignons, indépendamment des frameworks coûteux qui prétendent les industrialiser.

## Conviction 6 — Le travail bien fait est une dignité, pas une option

Le software craftsmanship n'est pas une posture esthète. C'est la conviction qu'un ouvrier qui pose mal une pierre porte une responsabilité envers ceux qui habiteront la maison. Un développeur qui livre du code bâclé porte la même responsabilité envers ceux qui l'utiliseront, le maintiendront et en hériteront. Nous tenons à cette responsabilité.

## Conviction 7 — Faire bien du premier coup en itérant peu, c'est aussi écologique

Chaque appel à un modèle d'IA consomme. Chaque cycle de développement raté gaspille. Chaque migration coûte. Nous cherchons donc à formuler nos besoins clairement, à construire nos prompts avec soin, à valider chaque étape avant la suivante. Ce n'est pas un retour au Waterfall — c'est une agilité responsable, qui respecte les ressources humaines et matérielles qu'elle mobilise.

---

Ces sept convictions tiennent ensemble. Elles forment un système. On peut en discuter chacune, mais on les comprend mieux les unes par les autres.

---

# Section 4 — La Méthode Maury

## 4.0 — Vue d'ensemble : deux histoires, une architecture

La Méthode Maury n'a pas été décrétée. Elle a émergé du travail concret sur deux projets que nous avons menés successivement, dans deux contextes radicalement différents, et qui ont convergé vers la même architecture par des chemins opposés.

Cette section raconte cette double émergence et la convergence qui en a résulté. Elle est organisée en cinq sous-sections qui suivent une progression précise :

- **4.1** raconte la naissance de **KoproGo** dans une logique ascendante : nous sommes partis du droit belge concret et de problèmes vécus, et nous avons remonté la chaîne jusqu'à découvrir une architecture, puis une méthode, puis une thèse.
- **4.2** raconte la naissance de **BANKO** dans une logique descendante : forts de l'expérience KoproGo, nous avons cette fois posé les principes d'abord et descendu jusqu'au code.
- **4.3** examine **la convergence** des deux récits sur les mêmes invariants architecturaux, couche par couche, et tire de cette convergence sa portée philosophique.
- **4.4** présente le **pipeline complet** TOGAF → BMAD → Scrum → Nexus → SAFe → ITIL et la place de l'intelligence artificielle supervisée dans ce pipeline.
- **4.5** propose une **réflexion conclusive** sur les invariants qui rendent la convergence possible et sur ce que cette double trajectoire nous enseigne.

L'organisation explicite de cette section — elle-même reflet de l'architecture explicite que nous prônons — est délibérée. Un manifeste qui défend la transparence des structures doit lui-même rendre visible la sienne.

---

## 4.1 — KoproGo : l'émergence ascendante

### 4.1.1 — Un constat structurel partagé

Pour comprendre comment KoproGo est né, il faut commencer par dire ce que nous voyions autour de nous, et que beaucoup voyaient avec nous.

La copropriété en Belgique concerne plus de quatre millions de personnes, propriétaires ou locataires. Elle représente déjà près d'un logement sur trois dans le pays, contre moins d'un sur cinq il y a trente ans. C'est une forme d'habitat qui ne cesse de croître sous l'effet de l'urbanisation, du vieillissement de la population et de la diminution de la taille des ménages.

Or, sur les quelque deux cent mille immeubles concernés, environ quatre-vingt-onze mille seulement sont gérés par un syndic inscrit officiellement. Le reste — plus de la moitié du parc — est géré autrement : par des syndics bénévoles, c'est-à-dire des copropriétaires qui ont accepté la responsabilité d'organiser la vie collective de leur immeuble, le plus souvent sans formation, sans temps dédié, et avec des outils inadaptés à leur situation.

Quant au métier de syndic professionnel lui-même, il est officiellement classé en pénurie par les services de l'emploi belges depuis 2021. Une enquête menée par l'Institut Professionnel des Agents Immobiliers en collaboration avec l'UCLouvain a révélé qu'un syndic actif sur deux envisage de quitter la profession, principalement à cause de l'épuisement, du manque de reconnaissance, et de la charge émotionnelle d'un métier où trois praticiens sur quatre se retrouvent quotidiennement confrontés à des problématiques qui ne relèvent pas de leur mandat — troubles de voisinage, solitude des copropriétaires âgés, petits tracas qui débordent sur leur vie privée.

Le diagnostic est donc clair et documenté. Le métier de syndic est en crise. La majorité du parc immobilier belge en copropriété est gérée par des bénévoles peu outillés. Les charges augmentent en moyenne de quinze pour cent par an depuis 2023. Et l'industrie logicielle propose des outils pensés essentiellement pour les syndics professionnels, qui constituent une minorité du parc et qui sont eux-mêmes en train de quitter le navire.

Nous n'avons pas vécu de drame personnel particulier dans ce contexte. Mais comme beaucoup d'autres, nous avons constaté que ce système ne tournait pas rond. Et nous avons commencé à nous demander pourquoi les outils dominants ne résolvaient pas le problème — voire l'aggravaient.

### 4.1.2 — Notre thèse : la logique extractive et son dépassement

Une lecture rapide pourrait conclure que la crise du métier de syndic est une crise de profession isolée, qu'il suffirait de réformer par plus de formations, plus de candidats, plus de communication sur l'image du métier. C'est ce que recommandent la plupart des rapports.

Nous portons une thèse différente, que nous formulons explicitement parce qu'elle structure tout ce qui suit. Cette thèse se développe en quatre temps.

**Temps 1 — La logique extractive du SaaS classique produit ce qu'elle ne sait pas reconnaître.**

Le modèle SaaS PropTech classique pense la copropriété comme un objet à gérer, un flux de transactions à optimiser, un marché à conquérir. Il transforme le syndic en client, le copropriétaire en utilisateur final, l'immeuble en portefeuille de lots. Il extrait de la valeur sous forme d'abonnements et de données, et restitue un service précisément délimité par son business model. Tout ce qui ne rentre pas dans la grille transactionnelle — la solitude du voisin du quatrième, le coup de main entre copropriétaires lors d'une fuite, le service d'entraide informelle, la délibération collective qui dépasse le strict ordre du jour de l'AG — est invisible pour le système.

**Temps 2 — Cette invisibilité est structurelle, pas accidentelle.**

Le sociologue portugais Boaventura de Sousa Santos a nommé ce phénomène la **monoculture de la productivité capitaliste** : un système qui ne reconnaît comme légitime que ce qui rentre dans sa grille marchande, et qui produit comme **non-existence** tout ce qu'il ne sait pas coder. Appliqué au PropTech, cela donne un constat précis : la pénurie de syndics et leur épuisement ne sont pas des accidents locaux, ils sont la conséquence prévisible d'un outillage qui les laisse seuls face à toutes les dimensions humaines qu'aucun système amont n'a modélisées. Le syndic devient le réceptacle de tout ce que la plateforme ignore — et son métier devient invivable.

**Temps 3 — Une philosophie qui pense pour les communautés englobe naturellement ce que l'autre exclut.**

Une approche qui part du bien commun et de la communauté concrète ne se contente pas d'ajouter des modules communautaires comme bonus à un cœur transactionnel. Elle reconnaît dès la conception que le syndic, le copropriétaire, le voisin, l'enfant qui joue dans la cour, le retraité isolé au quatrième étage ne sont pas des entités séparées à gérer chacune dans son silo — ce sont les **fibres d'un tissu de cohabitation**. Cette reconnaissance change tout : elle ne se traduit pas en fonctionnalités supplémentaires, elle se traduit en architecture. Les modules communautaires deviennent constitutifs et non décoratifs.

**Temps 4 — La maturation, pas la rupture.**

Nous tenons à un point qui distingue notre posture d'une posture militante facile : **le SaaS PropTech extractif n'est pas une ignominie, c'est une étape de maturation**. Il a permis d'investir dans la digitalisation d'un secteur qui en avait besoin. Il a motivé des entrepreneurs à concevoir des solutions. Il a produit beaucoup de concepts et d'outils dont nous héritons aujourd'hui. La recherche d'un modèle économiquement rentable et d'une économie de ressources est en soi une discipline utile.

Mais cette étape porte en elle ses propres limites, et c'est en les éprouvant qu'on peut penser ce qui vient ensuite. La maturation n'est pas la destruction du modèle précédent — c'est la reconnaissance qu'il a fait son travail historique et qu'il a rendu possible une étape suivante qui n'était pas pensable sans lui. Cette logique de maturation par dépassement est précisément celle qui a permis au Manifeste Agile de naître en 2001 : non en détruisant les méthodes lourdes qui l'avaient précédé, mais en reconnaissant qu'elles avaient révélé par leurs limites le besoin d'une autre manière de faire.

[DÉCISION À DEUX — La formule « passer de l'économie de ressources d'une plateforme à l'économie de la planète d'un commun » est forte. Elle vient de la dernière intervention de Gilles. Il faut la valider à deux avant publication, ou la reformuler ensemble.]

### 4.1.3 — Trois besoins, trois choix techniques

De ce constat ont émergé trois besoins simultanés, qui ont structuré dès le départ tous les choix de KoproGo. Chaque besoin a appelé un choix technique précis, et la cohérence entre les trois est ce qui fait l'unité du projet.

**Premier besoin : structurer.**

Le chaos régnait. Le droit belge de la copropriété est précis — articles 3.84 et suivants du Code civil, règles de quorum, majorités qualifiées, sommes des tantièmes égales à 100 %, plafonds de procurations, délais légaux de convocation. Mais cette précision juridique ne se retrouvait dans aucun outil grand public. Les syndics bénévoles s'arrangeaient avec des tableurs, les professionnels avec des logiciels qui exigeaient des heures de paramétrage pour reconnaître les particularités locales.

Notre choix technique : le **Domain-Driven Design**. Les concepts du droit belge — *Bâtiment*, *Lot*, *Copropriétaire*, *Tantième*, *Assemblée générale*, *Résolution*, *Procuration* — ne sont pas des paramètres dans une application générique. Ce sont des entités du domaine, avec leurs invariants codés dans leurs constructeurs. Une copropriété dont les tantièmes ne totalisent pas 100 % ne peut pas exister en mémoire. Une assemblée tenue sans le quorum requis ne peut pas voter validement. **Le code lui-même devient gardien du droit.**

**Deuxième besoin : transparenter.**

L'opacité protégeait les abus. Les copropriétaires ne savent souvent pas comment les charges sont calculées, pourquoi tel devis a été retenu, comment le fonds de roulement est utilisé. Cette opacité n'est pas malveillante — elle est structurelle, parce que les outils existants n'imposent pas la transparence, ils l'autorisent au mieux.

Notre choix technique : l'**architecture explicite**. Des architectes comme Herberto Graça ont mené un travail intellectuel patient pour unifier plusieurs traditions souvent présentées comme rivales — DDD, hexagonal, onion, clean, CQRS. Le schéma à anneaux concentriques où le domaine métier occupe le cœur et où les dépendances pointent toujours vers l'intérieur n'est pas seulement une discipline d'ingénieur. C'est une **incarnation visuelle d'une thèse plus large** : différentes traditions, pensées dans différents contextes, peuvent converger sur les mêmes principes quand elles répondent au même problème humain. Ce schéma a été pour nous un point d'appui, parce qu'il rendait visibles les responsabilités, qu'il forçait à expliciter ce qui d'ordinaire reste implicite, et qu'il préfigurait à l'échelle du code ce que nous voulions à l'échelle du produit : faire voir.

Notre deuxième choix technique pour ce besoin : la **licence AGPL-3.0**. Quand un logiciel touche au droit, à l'argent et au quotidien de plusieurs millions de personnes, la transparence ne peut pas reposer sur la promesse d'un éditeur. Elle doit reposer sur la possibilité de vérifier.

**Troisième besoin : transmettre.**

Ce que nous apprenions méritait d'être partageable. Pas seulement par posture militante de l'open source, mais parce que nous voulions que d'autres puissent reprendre, critiquer, prolonger. Pour des étudiants en informatique de gestion. Pour des stagiaires en cybersécurité. Pour des syndics bénévoles débordés. Pour des développeurs d'autres pays qui voudraient adapter notre architecture à leur droit local.

Notre choix technique : la **documentation vivante**. Les scénarios BDD écrits en Gherkin servent simultanément de spécifications, de tests automatisés, et de documentation lisible par des non-développeurs. KoproGo en compte plus de deux cents. C'est aussi pour répondre à ce troisième besoin que nous avons écrit la Méthode Maury elle-même — un blueprint reproductible que d'autres pourront adapter à leurs propres écosystèmes.

### 4.1.4 — Le choix de Rust comme acte cohérent

Si nous voulions un logiciel sobre, durable, transparent et transmissible, le choix du langage devenait stratégique. Nous avons retenu Rust pour des raisons qui se tiennent ensemble.

**Sobriété d'exécution.** Un binaire Rust consomme considérablement moins de mémoire et de processeur qu'un service équivalent en JVM ou en langage interprété. KoproGo soutient 287 requêtes par seconde sur un seul vCPU avec 2 GB de RAM, avec une médiane de latence à 69 millisecondes et une empreinte mesurée à 0,12 grammes de CO₂ par requête. Ces chiffres ne sont pas un slogan — ils sont vérifiables sur le dépôt et auditables par quiconque veut les reproduire.

**Sobriété de l'écosystème.** L'écosystème Cargo de Rust impose une discipline plus prudente que d'autres environnements. Moins de dépendances transitives, moins de mises à jour cassantes, moins de dérive des versions au fil des années. Un projet Rust de 2018 compile encore aujourd'hui avec des ajustements mineurs. C'est une dimension écologique qu'on sous-estime — la sobriété ne se mesure pas qu'à l'exécution, elle se mesure aussi à l'effort de maintenance que le logiciel imposera à ceux qui le reprendront.

**Durabilité du code.** La fondation Rust, héritière du travail initial de la fondation Mozilla, fait de la rétrocompatibilité une priorité explicite. Cela suppose un investissement institutionnel à long terme, sans pression commerciale immédiate. Cette dimension nous paraît importante au-delà du langage lui-même : elle dit quelque chose sur l'**écosystème institutionnel** que nous voulons soutenir — un commun numérique financé par des fondations, des entreprises et des contributeurs qui acceptent de penser à trente ans plutôt qu'à trois.

**Sécurité mémoire.** Rust élimine par construction toute une classe de vulnérabilités logicielles — usages après libération, débordements de tampon, conditions de concurrence — qui sont à l'origine de la majorité des failles critiques dans les langages traditionnels. Pour KoproGo qui touche à des données personnelles, à des transactions financières et au droit, et pour nous qui pratiquons la cybersécurité au quotidien, cette dimension n'était pas négociable.

Ces quatre dimensions ne sont pas indépendantes. Elles dérivent toutes d'une même conviction : **un logiciel responsable est un logiciel qui prend au sérieux ce qu'il consomme, ce qu'il transmet, ce qu'il protège, et combien de temps il durera.**

### 4.1.5 — L'émergence méthodologique

La Méthode Maury n'a pas été décrétée. Elle est apparue progressivement, au fil du travail, comme la reconnaissance d'un emboîtement qui s'imposait de lui-même.

Au fil de la construction de KoproGo, plusieurs constats se sont imposés.

**Premier constat.** Les rituels de l'agilité originelle — sprints courts, rétrospectives bi-hebdomadaires, simplicité comme art de maximiser le travail non fait — fournissaient une discipline de **sobriété méthodologique**. Ils nous protégeaient de la sur-ingénierie, qui est l'équivalent au logiciel de la dispersion permanente dans des micro-décisions qui empêchent de voir l'ensemble.

**Deuxième constat.** La méthode TOGAF, pourtant née dans un univers très différent de l'agile, fournissait un cadre puissant pour répondre à la question du **quoi** — quels sont les drivers, qui sont les parties prenantes, quels sont les invariants stratégiques — sans laquelle l'agilité tourne à vide.

**Troisième constat.** L'IA générative, utilisée avec discipline et supervision humaine, permettait d'accélérer considérablement le travail sans en compromettre la qualité, à condition que l'humain garde toujours le dernier mot.

**Le constat fondateur de TOGAF dans notre pratique.**

Plus précisément, la Méthode Maury s'est cristallisée autour d'un constat que le travail sur KoproGo a rendu visible. Les dettes techniques et les défauts structurels d'un système d'information ne naissent presque jamais d'un mauvais choix isolé. Ils naissent par **couches successives**, accumulées au fil du temps sans qu'aucune instance ne reprenne périodiquement la vue d'ensemble pour vérifier que chaque couche reste cohérente avec les drivers initiaux et avec les couches qui l'ont précédée. Au bout de quelques années, le système est encombré de décisions oubliées, d'options techniques que personne ne sait plus justifier, de dépendances dont l'origine remonte à un besoin qui a depuis disparu. C'est cette accumulation silencieuse qui produit la dette technique — pas les mauvais développeurs, pas les contraintes de planning ponctuelles, mais l'absence d'instance de relecture stratégique périodique.

TOGAF répond précisément à ce constat. Il propose une boussole qui aligne la stratégie avec le métier, des **gate reviews** régulières où l'on vérifie cet alignement, des **ADR** — *Architecture Decision Records* — qui tracent chaque choix d'architecture significatif avec ses raisons et ses alternatives écartées, et des **RFC** — *Requests for Comments* — qui formalisent les questions ouvertes pour qu'elles soient discutées avant d'être tranchées. Tout cela s'inscrit dans le cycle ADM de TOGAF — *Architecture Development Method* — qui parcourt huit phases successives en boucle, de la définition de la vision à la gestion du changement, et qui est conçu pour être adapté en continu plutôt que figé.

**TOGAF et l'agilité dans une écologie des savoirs.**

TOGAF et l'agilité originelle sont souvent présentés comme deux mondes séparés — l'un orienté vers la stratégie d'entreprise et la planification long terme, l'autre vers la pratique de développement et le rythme court terme. En réalité, ils répondent à des questions différentes mais complémentaires, et ils peuvent dialoguer dès lors qu'on les laisse parler depuis ce qu'ils savent faire le mieux. TOGAF apporte la boussole, la traçabilité des décisions par les ADR, le formalisme des questions ouvertes par les RFC, et le cycle ADM qui parcourt en continu les phases d'architecture. L'agilité originelle apporte le rythme soutenable, la rétrospective qui interroge la pratique, l'auto-organisation des équipes et la simplicité comme art de maximiser le travail non fait. Aucun des deux ne suffit seul, et aucun ne contredit l'autre lorsqu'on respecte ce que chacun sait.

C'est cette reconnaissance qui rapproche la Méthode Maury de ce que nous appelons une **écologie des savoirs** au sens où Boaventura de Sousa Santos l'entend. Au lieu de hiérarchiser les traditions et de chercher laquelle a raison, on les fait dialoguer en respectant la spécificité de chacune. Les méthodes ne sont pas des dogmes en compétition. Ce sont des **outils situés** qui répondent à des problèmes situés. Un projet logiciel a besoin d'une stratégie d'architecture sur cinq à dix ans, et il a besoin d'un rythme de livraison sur deux à quatre semaines. Vouloir traiter ces deux échelles avec un seul cadre, c'est forcer un outil hors de son terrain naturel et perdre ce qu'il a de plus précieux. Articuler TOGAF avec les cadres agiles, c'est reconnaître que les échelles temporelles différentes méritent des réponses méthodologiques différentes — et que ces réponses sont compatibles dès lors qu'on les pense ensemble plutôt qu'en concurrence.

**L'IA comme paradigm shift, et les enseignements de la révolution industrielle.**

L'arrivée de l'intelligence artificielle générative dans le développement logiciel est un paradigm shift comparable, en proportion, à ce que furent en leur temps l'imprimerie, l'électricité ou la révolution industrielle. Comme tous les paradigm shifts, elle ouvre des possibilités productives inédites et elle expose à des risques d'usage qui n'apparaissent qu'à mesure de sa diffusion. La révolution industrielle nous a appris quelque chose à ce sujet, et il vaut mieux le retenir que le redécouvrir au prix fort. Les premières décennies de l'industrialisation ont démultiplié la capacité productive humaine, mais elles ont aussi produit des conséquences sociales et écologiques durables que les acteurs de l'époque n'avaient pas anticipées et qu'il a fallu deux ou trois générations de régulation patiente, de luttes sociales et de vigilance collective pour réparer.

L'enseignement n'est pas que l'IA est dangereuse et qu'il faudrait la freiner. Ce serait passer à côté de ce qu'elle permet. L'enseignement n'est pas non plus qu'elle est neutre et qu'il suffirait d'en faire bon usage individuellement. Ce serait ignorer les effets systémiques qui dépassent toute pratique individuelle. L'enseignement, c'est qu'un paradigm shift de cette ampleur appelle **simultanément trois choses** qui ne se substituent pas mais s'additionnent : un usage individuel discipliné, une régulation collective lucide, et une vigilance écologique et sociale qui surveille les effets non intentionnels avant qu'ils s'installent durablement.

La Méthode Maury prend acte de la première de ces trois conditions. Elle ne prétend pas régler les questions de régulation collective — qui relèvent des États, des institutions et des mouvements sociaux — ni les questions de vigilance écologique et sociale globale — qui relèvent du débat démocratique. Elle propose une **discipline d'usage individuel et collectif au sein d'un projet de développement** qui rend l'accélération de l'IA salutaire plutôt que destructrice. Cette discipline est ce que nous transmettons. Elle ne suffit pas à elle seule à orienter le paradigm shift, mais elle est ce que chacun peut faire à son échelle pour ne pas en aggraver les effets indésirables et pour en récolter les bénéfices.

**La formule à conserver.**

De cette maturation est née une formule simple que nous voudrions garder telle quelle :

> **TOGAF définit le quoi, et tout ce qui en découle.**

Tout le reste — BMAD, Scrum, Nexus, SAFe, ITIL — vient s'emboîter dans cette définition initiale du quoi, comme autant de réponses au comment à différentes échelles temporelles. La sous-section 4.4 décrira en détail cet emboîtement.

### 4.1.6 — Les modules communautaires comme différenciation

Il reste un dernier élément, et c'est probablement le plus important pour saisir ce qui fait de KoproGo autre chose qu'un logiciel PropTech ordinaire.

Une copropriété n'est pas seulement une collection administrative de propriétaires individuels qui se partagent les charges. C'est une **communauté de cohabitation**. Les voisins se croisent dans l'ascenseur, se prêtent un outil, gardent un colis, organisent une fête de quartier, s'entraident en cas de difficulté, partagent une cour ou un jardin. Ces dimensions ne figurent dans aucun ERP de gestion immobilière, parce qu'elles n'entrent pas dans la grille transactionnelle. Elles sont pourtant ce qui fait qu'un immeuble est habitable plutôt qu'invivable.

Nous avons fait le choix d'intégrer dans KoproGo des modules qui reconnaissent et soutiennent cette dimension communautaire. Concrètement, KoproGo intègre aujourd'hui six modules communautaires, soit déjà implémentés, soit inscrits en cours sur la roadmap par capacité du projet :

- **Le SEL, Système d'Échange Local**, qui permet aux voisins de troquer des compétences sans recourir à une transaction monétaire. Une voisine donne un cours de cuisine, un voisin répare un vélo, une retraitée garde un enfant pendant deux heures. Les échanges sont valorisés en heures, pas en euros.
- **Le partage d'objets**, qui transforme un immeuble en bibliothèque d'outils. Une perceuse, une échelle, une tondeuse, un nettoyeur haute-pression — autant d'objets que dix copropriétaires possèdent en double aujourd'hui et qu'un seul suffirait à fournir si la confiance était outillée.
- **Le bazar de troc**, qui facilite le don ou l'échange d'objets dont on ne se sert plus, sans passer par les plateformes commerciales d'occasion qui captent une commission ou exposent les utilisateurs à des inconnus distants.
- **L'annuaire des compétences**, qui répertorie qui sait faire quoi dans l'immeuble. Un retraité électricien à la retraite, une mère architecte d'intérieur, un étudiant développeur — autant de ressources humaines qui restent invisibles tant qu'elles ne sont pas répertoriées.
- **Le covoiturage et la garde d'enfants**, qui prennent en charge ces deux usages quotidiens où le voisinage est naturellement pertinent mais où l'organisation manque presque toujours.
- **Le tableau d'affichage numérique**, qui remplace les affiches scotchées dans les halls par un canal de communication local lisible par tous les résidents.

**Ces modules peuvent être utilisés seuls.**

Ces modules ne sont pas réservés aux copropriétés qui adoptent KoproGo pour leur gestion administrative. Ils peuvent être utilisés **indépendamment**, en parallèle d'une solution PropTech existante ou d'un outil interne maison. Une copropriété de trente lots peut garder le SaaS payant qu'elle utilise pour la gestion officielle, et installer KoproGo uniquement pour le SEL et le partage d'objets. Ce choix architectural — la possibilité d'utiliser les modules communautaires seuls — est la traduction technique de notre conviction qu'ils ne sont pas un complément aux fonctions administratives, mais une dimension autonome du logiciel d'habitat collectif.

**Les ordres de grandeur de l'impact projeté.**

Les ordres de grandeur projetés à un horizon où KoproGo serait adopté par plusieurs milliers de copropriétés sont substantiels : économie circulaire générée par les échanges en heures du SEL, consommation évitée par le partage d'objets qui se chiffre en centaines de milliers d'euros, milliers d'objets effectivement partagés au lieu d'être achetés en doublon, et réduction d'émissions carbone qui se mesure en centaines de tonnes par an. Ces chiffres ne sont pas une projection commerciale destinée à séduire un investisseur — ils sont une mesure des externalités positives qu'un outil bien pensé permet de matérialiser, et ils constituent la réponse opérationnelle à la dimension écologique du manifeste. La sobriété logicielle ne se mesure pas seulement à l'empreinte carbone par requête, elle se mesure aussi aux gestes collectifs qu'elle rend possibles.

Mais ces ordres de grandeur ne sont pas atteints en se fixant des dates. Ils sont atteints en suivant une **progression organique par jalons de capacité**, où chaque palier débloque le suivant lorsqu'il est effectivement validé. C'est une logique que nous tenons de TOGAF, et qui distingue notre pratique d'une grande partie de ce qui se présente aujourd'hui sous le nom d'agilité industrielle. Là où la pression d'une date arbitraire pousse mécaniquement à la dette technique — on livre un produit imparfait pour tenir un calendrier, et on accumule du coût latent qui ressortira plus tard — la pression d'un jalon de capacité pousse à la qualité. On ne franchit le palier suivant qu'à condition que le palier actuel tienne. Cette inversion change tout. Elle permet à la roadmap d'être réelle plutôt que cosmétique, et elle protège la durabilité du système contre les réflexes industriels qui le saperaient.

**Une précision essentielle sur la notion de capacité.** Le mot *capacité* au sens TOGAF ne désigne pas seulement un état du code. Il désigne l'**ensemble des conditions** qui doivent être réunies pour qu'un palier soit effectivement disponible — non seulement le code lui-même, mais aussi l'organisation qui le porte, la gouvernance qui le pilote, l'impact écologique mesuré, l'écosystème qui l'accueille, la conformité juridique vérifiée, et les premiers usages réels qui en valident la pertinence. Cette définition large de la capacité est ce qui distingue radicalement la roadmap par capacités d'une roadmap classique pilotée par fonctionnalités. Une fonctionnalité codée n'est pas une capacité disponible. Une capacité disponible exige que tout l'environnement du code ait suivi.

C'est cette définition large qui permet à la roadmap par capacités de **connecter le logiciel à son environnement et à son impact**. Un projet peut avoir un code substantiellement avancé tout en restant officiellement à un jalon initial, parce que les autres dimensions de la capacité ne sont pas encore au niveau requis. Loin d'être une contradiction, cette dissociation est précisément le bénéfice de l'approche : elle empêche de confondre la maturité technique avec la maturité opérationnelle, et elle empêche le projet de prendre de l'avance sur son écosystème au point de devenir hors-sol. La section 5 du manifeste illustrera concrètement comment cette dissociation se vit sur KoproGo.

**Les gate reviews comme rituel de progression.**

Cette logique de progression par capacité s'articule avec la pratique des **gate reviews** héritée de TOGAF. Chaque jalon n'est pas seulement un objectif de capacité — il est aussi un point de revue où l'on vérifie collectivement que les fondations tiennent, que les choix d'architecture restent cohérents avec les drivers business, que les ADR produits jusque-là continuent de faire sens, et que les questions ouvertes formalisées en RFC ont reçu des réponses claires ou ont été explicitement reportées au jalon suivant. Ces points de revue sont ce qui permet à un projet de durer longtemps sans dériver.

Deux images peuvent en rendre compte selon la sensibilité du lecteur. Pour les uns, ils sont l'équivalent du suivi médical au long cours qu'une personne consciente de son terrain entretient avec son médecin — pas le check-up de formalité annuelle, mais le rendez-vous régulier où l'on compare l'état actuel au précédent et où l'on ajuste avant que ne s'installe un déséquilibre. Pour d'autres, ils sont le point de sauvegarde du jeu vidéo : ce moment où l'on consolide les acquis, vérifie l'inventaire, ajuste la stratégie pour la suite du chapitre, et obtient la garantie qu'en cas de difficulté on pourra reprendre depuis ce point plutôt que tout recommencer. Dans les deux cas, l'idée est la même : la fréquence n'est ni le maximum ni le minimum, elle est calibrée sur la nature de l'étape qu'on traverse. C'est cette calibration qui distingue la pratique vivante du rituel bureaucratique.

**Les modules communautaires comme expression directe de la philosophie.**

Ces modules ne sont pas un ajout cosmétique à un cœur transactionnel. Ils sont une **expression directe** de la philosophie du projet. Ils reconnaissent que les copropriétaires sont aussi des voisins, et que les outils numériques doivent servir l'épaisseur de cette relation, pas l'aplatir.

C'est ici que se joue la différenciation la plus profonde de KoproGo.

- Un outil PropTech classique est conçu pour rendre le métier de syndic plus efficient en automatisant ce qui peut l'être, et en laissant le reste — c'est-à-dire l'humain — en dehors du système.
- KoproGo prend le pari inverse : reconnaître l'humain dans le système, soutenir le voisinage, valoriser le bénévolat, et accepter que toute fonction administrative s'inscrit dans un tissu communautaire qui doit être servi en même temps qu'elle.

Cette posture n'est pas seulement éthique. Elle est aussi opérationnellement juste. Là où le PropTech classique laisse le syndic seul face à la solitude des résidents âgés, KoproGo permet aux voisins de se voir et de se connaître. Là où le PropTech classique extrait des données pour mieux cibler des publicités, KoproGo facilite des achats groupés pour réduire les charges. Là où le PropTech classique fait du copropriétaire un client, KoproGo le reconnaît comme co-habitant, co-décideur et co-responsable.

C'est cette intuition qui nous donne aussi la confiance qu'au-delà de KoproGo, ce qui s'y est construit constitue un **blueprint** que d'autres pourront adapter à leurs propres écosystèmes — banking communautaire avec BANKO, vie scolaire avec EcoleHub, et tout autre domaine où des communautés concrètes méritent des outils faits pour elles plutôt qu'adaptés à elles depuis des produits globaux.

### 4.1.7 — Bilan de l'émergence ascendante

KoproGo est né d'un constat structurel partagé, d'une thèse en quatre temps sur les limites du modèle PropTech extractif et son dépassement, et de trois besoins simultanés qui ont guidé chacun nos choix techniques. Ce parcours a été ascendant : nous sommes partis du droit belge concret, des frustrations observées, de la documentation des syndics épuisés, et nous avons remonté la chaîne jusqu'à ce qu'apparaisse une architecture, puis une méthode, puis une thèse plus large sur ce qu'est un logiciel responsable.

Forts de cette expérience, nous avons abordé le projet suivant — BANKO, dans un contexte tunisien et bancaire — différemment. Non plus en remontant du droit vers l'architecture, mais en descendant des principes vers le code. La sous-section 4.2 raconte ce mouvement inverse.

---

## 4.2 — BANKO : la maturation descendante

### 4.2.1 — Un nouveau contexte, une nouvelle douleur structurelle

KoproGo nous avait appris à lire les douleurs structurelles. BANKO est né d'une douleur de même nature, mais inscrite dans un secteur radicalement différent et dans un autre pays.

Les banques tunisiennes, comme la plupart des banques des pays émergents, dépendent largement de systèmes propriétaires d'éditeurs internationaux comme Temenos ou Finastra. Ces plateformes sont techniquement solides et fonctionnellement complètes, mais leur modèle économique repose sur l'extraction durable de valeur : licences coûteuses, dépendance technologique forte, customisations facturées à part, contrats de maintenance pluriannuels qui captent une fraction significative du budget IT des établissements bancaires. Pour une économie de taille modeste comme la Tunisie, cette dépendance pose une question de souveraineté autant que de coût.

La Banque Centrale de Tunisie a manifesté depuis plusieurs années une volonté explicite de souveraineté technologique. Elle a publié un référentiel réglementaire dense — la loi bancaire de 2016, sept circulaires couvrant la division des risques, l'adéquation des fonds propres selon Bâle III, le ratio crédits-dépôts, la gouvernance bancaire, la lutte contre le blanchiment — qui fixe des exigences précises auxquelles tout système bancaire opérant en Tunisie doit se conformer. Mais cette densité réglementaire est mal servie par des systèmes étrangers qui doivent être paramétrés à grands frais pour reconnaître chaque spécificité locale.

C'est à cette douleur que BANKO entend répondre. Et comme pour KoproGo, nous voulons être clairs : nous ne pensons pas que Temenos ou Finastra soient des entreprises malveillantes. Elles ont permis à des banques du monde entier d'accéder à des outils sophistiqués qu'elles n'auraient pas pu développer seules. Elles font, dans leur registre, un travail historiquement utile. Mais comme dans le cas du PropTech belge, il existe une **étape de maturation** qui consiste à reconnaître les limites structurelles d'un modèle d'outillage et à proposer autre chose à côté de lui — pas contre lui.

### 4.2.2 — Une origine relationnelle incarnée

KoproGo était né d'un constat structurel diffus que nous portions à deux. BANKO est né autrement : d'une rencontre humaine.

Une experte fintech tunisienne, dont nous tairons le nom dans cette version du manifeste mais dont nous revendiquons l'apport décisif, porte depuis des années une vision lucide des besoins du système bancaire de son pays. Farah l'a rencontrée et nous a mis en relation. De cette rencontre est née la conviction que la Méthode Maury, mûrie sur KoproGo, pourrait contribuer à matérialiser cette vision. Elle a apporté l'expertise métier, la connaissance fine de la régulation BCT, la compréhension des contraintes opérationnelles d'une banque tunisienne. Nous avons apporté la capacité d'exécution architecturale et la discipline méthodologique. Le projet repose sur cette triangulation.

Cette origine relationnelle change la nature de BANKO. Là où KoproGo était une réponse à un problème observé, BANKO est une **co-construction** entre une expertise métier ancrée localement et une expertise technique délocalisée mais enracinée dans le même souci du bien commun. Cette configuration illustre concrètement ce que nous appelons une **micro-écologie de savoirs** au sens où Boaventura de Sousa Santos l'entend : des savoirs situés dans des contextes différents qui se reconnaissent une préoccupation commune et qui se mettent en dialogue sans hiérarchie a priori.

Cette dimension relationnelle a aussi une conséquence pratique sur la conduite du projet. Là où KoproGo s'appuie sur notre lecture du droit belge, BANKO s'appuie sur la lecture experte d'une praticienne de la place de Tunis. Nous ne nous substituons pas à son expertise — nous la traduisons en code en respectant ce qu'elle nous transmet. Cette posture d'humilité épistémique est essentielle. Elle est aussi cohérente avec la conviction n°2 du manifeste : ce qui vaut pour l'IA — *générer mais valider par l'humain* — vaut a fortiori entre humains de cultures différentes : *le développeur étranger code, l'experte locale valide*.

### 4.2.3 — Une filiation revendiquée : le mouvement open source de la fintech

BANKO ne naît pas dans un désert. Il s'inscrit dans un mouvement plus large, plus ancien et plus mature que ce que nous pouvions soupçonner avant de nous y plonger : le mouvement open source de la fintech. Nous voulons le citer explicitement parce qu'il est inspirant et parce qu'il préfigure beaucoup de ce que nous tentons.

Trois projets méritent d'être nommés en première mention.

**Apache Fineract** est une plateforme bancaire open source démarrée en 2002 par James Dailey pour répondre aux besoins de la microfinance. Elle est aujourd'hui un projet phare de la fondation Apache, utilisée par des institutions de microfinance, des ONG et des banques digitales dans de nombreux pays émergents. Elle vise explicitement à fournir un *core banking system* qui rende les services financiers numériques accessibles aux populations non-bancarisées et sous-bancarisées. Sa philosophie fondatrice — *"making financial services a right, not a privilege"* — résonne fortement avec l'écologie des savoirs que nous portons.

**Mojaloop** est une plateforme open source de paiement instantané inclusif, soutenue notamment par la fondation Bill & Melinda Gates et par un large écosystème d'intégrateurs et de fintechs. Elle vise à abaisser le coût de construction et de maintenance des systèmes de paiement interopérables dans les pays émergents, et à rendre accessibles des services financiers numériques à toute personne disposant d'un téléphone mobile. Mojaloop et Fineract sont fréquemment intégrés ensemble pour fournir une architecture de bout en bout pour les services financiers numériques inclusifs.

**OpenBank Project**, porté par la société allemande TESOBE, propose un framework open source d'API bancaires aligné sur le standard britannique d'open banking. Il permet à des institutions financières d'exposer des API standardisées à des tiers, dans une logique de souveraineté des données et d'interopérabilité. Ce projet a inspiré l'adoption du standard UK Open Banking par plusieurs pays d'Afrique sub-saharienne et d'Amérique latine.

Ces trois projets ne sont pas des concurrents de BANKO. Ils sont des **prédécesseurs** dont nous tirons des leçons et avec lesquels nous pourrions un jour interopérer. Ils démontrent qu'un commun bancaire numérique est possible, qu'il est défendu par des communautés actives depuis plus de vingt ans pour les plus anciennes, et qu'il sert effectivement des populations que les systèmes propriétaires ne servaient pas. BANKO s'inscrit dans cette filiation tout en en différant par des choix techniques propres — Rust plutôt que Java, hexagonale stricte plutôt que microservices, ancrage tunisien plutôt qu'inclusion financière globale — et par une articulation explicite avec une méthodologie complète de production logicielle.

### 4.2.4 — Trois besoins, trois choix techniques

Comme pour KoproGo, BANKO répond à trois besoins simultanés. Mais ces besoins sont différents, et les choix techniques qu'ils ont appelés en portent la marque.

**Premier besoin : la souveraineté.**

Une banque tunisienne qui veut maîtriser son système d'information ne peut pas accepter que son cœur métier dépende d'un éditeur étranger qui peut décider unilatéralement de prix, de roadmap ou de conditions contractuelles. Elle ne peut pas non plus accepter que ses données soient hébergées hors de son territoire juridique.

Notre choix technique : un système entièrement open source sous licence **AGPL-3.0**, hébergeable localement en Tunisie, avec une stack maîtrisée de bout en bout. Le README de BANKO le dit explicitement : *"hébergement local, données en Tunisie, conformité INPDP"* (l'autorité tunisienne de protection des données personnelles). La souveraineté n'est pas un slogan — elle est inscrite dans l'architecture, dans la licence et dans le choix d'infrastructure.

**Deuxième besoin : la conformité traçable.**

Le système bancaire tunisien est soumis à un référentiel réglementaire dense qui s'étend de la loi bancaire de 2016 aux circulaires BCT les plus récentes, en passant par les normes comptables tunisiennes (NCT 21, 22, 24, 25), les standards internationaux Bâle III, les recommandations GAFI sur la lutte anti-blanchiment et les standards ISO 20022 et 27001. Une banque doit pouvoir démontrer à tout moment que chaque opération qu'elle réalise est conforme à ce référentiel — et un superviseur doit pouvoir auditer cette conformité.

Notre choix technique : la **traçabilité juridique systématique**. Chaque fonctionnalité de BANKO est traçable vers un texte légal ou normatif précis, documenté dans un référentiel public sur le dépôt. Cette discipline n'est pas seulement déclarative — elle est codée dans la structure même du projet, où les règles métier liées à la régulation sont identifiées comme telles et associées aux articles qui les fondent. C'est l'équivalent BANKO de ce que sont les invariants du Code civil belge dans KoproGo, mais en plus systématique encore.

**Troisième besoin : la transmissibilité institutionnelle.**

BANKO ne sera pas adopté s'il n'est pas auditable par les institutions qui régulent le secteur — au premier rang desquelles la BCT elle-même. Cette auditabilité ne peut pas être un argument commercial — elle doit être une propriété structurelle du système.

Notre choix technique : la **piste d'audit intégrale et signée cryptographiquement**. Chaque opération est journalisée, horodatée et signée. Le code source est intégralement public. La documentation associe chaque module à ses fondements réglementaires. Un auditeur de la BCT, un commissaire aux comptes, un superviseur du gouvernement peuvent littéralement remonter de n'importe quelle ligne de code à son fondement légal, et de n'importe quelle opération à sa trace cryptographique. Cette propriété structurelle change la nature de la relation entre la banque et son régulateur : elle remplace la confiance déclarative par la vérification possible.

### 4.2.5 — Le choix de la cohérence stack et la maturation méthodologique

BANKO réutilise la même stack technique que KoproGo : Rust avec Actix-web pour le backend, Astro avec Svelte pour le frontend, PostgreSQL pour la persistance, Docker et Traefik pour l'orchestration locale. Cette cohérence n'est pas un manque d'imagination — c'est une **démonstration empirique** que les choix techniques de KoproGo n'étaient pas accidentels mais qu'ils traduisent des principes universalisables.

Mais BANKO va plus loin que KoproGo sur plusieurs dimensions, parce qu'il bénéficie de ce que nous y avons appris.

**Le Cargo workspace dès le départ.** Là où KoproGo a évolué progressivement vers une structure modulaire au fur et à mesure que le projet grossissait, BANKO démarre avec une structure de Cargo workspace divisé en *crates/domain*, *crates/application* et *crates/infrastructure* dès les premières heures de code. Ce n'est pas de la sur-ingénierie — c'est la reconnaissance qu'une certaine maturité architecturale ne se découvre qu'une fois et peut ensuite être anticipée.

**La traçabilité juridique inscrite dans le squelette.** Là où KoproGo a documenté progressivement ses invariants juridiques au fil de leur découverte, BANKO publie dès son README la liste exhaustive des treize textes réglementaires qu'il implémente. Le référentiel légal précède le code — c'est la posture descendante au sens littéral.

**La frugalité de prompt acquise.** C'est ici que se mesure la maturation la plus visible. KoproGo a nécessité plus de mille cent commits pour atteindre son état actuel. BANKO en a, à ce jour, environ cent douze, et couvre déjà près de quatre-vingt-cinq pour cent des fonctionnalités d'un système bancaire commercial reconnu, sans omettre aucune des fonctions essentielles d'une banque de détail. Cette différence ne traduit pas une supériorité brute du second projet — BANKO est plus jeune que KoproGo et n'est pas encore en production. Elle traduit une **maturation méthodologique mesurable** : ce que nous avons mis cent commits à formuler la première fois sur KoproGo, nous le posons en quelques commits sur BANKO parce que la Méthode Maury est désormais une matrice exécutable plutôt qu'un savoir tacite à formaliser au fil de l'eau.

Cette frugalité a une dimension écologique directe. Chaque commit représente du temps de développement, des appels à des modèles d'IA, de la consommation d'énergie. Réduire le nombre de commits nécessaires pour produire la même valeur fonctionnelle, c'est littéralement réduire l'empreinte carbone du processus de développement. Et c'est cohérent avec la conviction n°7 du manifeste : *faire bien du premier coup en itérant peu, c'est aussi écologique*.

### 4.2.6 — Une démonstration vivante : créer avec discipline et avec joie

Il y a un point que nous voulons formuler clairement parce qu'il nous tient à cœur. La sobriété logicielle ne peut pas être un nouvel ascétisme culpabilisant. Elle ne doit pas non plus être un produit d'élite réservé à ceux qui auraient appris la discipline méthodologique avant d'oser créer.

Tout le monde a le droit de penser une solution s'il le veut. À condition de la penser avec discipline.

Cette articulation entre **liberté de créer** et **discipline d'exécution** est probablement ce que la Méthode Maury a de plus singulier à transmettre. Elle protège contre les deux dérives symétriques qui guettent le secteur. La création débridée qui gaspille — celle qui multiplie les itérations, qui teste à l'aveugle, qui consomme sans mesurer. Et l'ascétisme stérile qui culpabilise — celui qui paralyse l'envie de bâtir au nom de l'empreinte écologique, ou qui réserve la création à une avant-garde initiée.

BANKO est aussi, pour nous, une **démonstration vivante** que cette articulation tient. Nous avons assumé le projet pour répondre à un vrai besoin métier, mais nous avons aussi assumé qu'il était pour nous un terrain d'expérimentation de la méthode. Nous avons éprouvé le plaisir de créer en le faisant avec une discipline qui nous protégeait de la culpabilité. Le résultat est mesurable : moins de commits, moins de tokens IA consommés, moins de migrations à venir, plus de fonctionnalités utiles par unité de ressource investie.

Ce double mouvement — la rigueur qui rend la joie possible, et la joie qui motive la rigueur — n'est pas propre à nous. Il est ce qu'aucun framework imposé d'en haut ne peut décréter et que toute pratique vivante peut redécouvrir.

### 4.2.7 — Bilan de la maturation descendante

BANKO est né d'une rencontre humaine, d'une douleur structurelle inscrite dans un secteur souverain, et d'une volonté de matérialiser dans le banking tunisien ce que KoproGo avait fait éclore dans la copropriété belge. Ce parcours a été descendant : nous sommes partis des principes acquis sur le projet précédent, nous avons posé l'architecture avant le code, nous avons inscrit la traçabilité juridique dans le squelette du projet, et nous avons réduit drastiquement le nombre d'itérations nécessaires pour produire la même valeur fonctionnelle.

Ce parcours nous a appris trois choses que KoproGo ne pouvait pas nous apprendre seul.

**Premièrement**, la Méthode Maury fonctionne dans un autre contexte juridique et culturel. Elle n'est pas spécifiquement belge — elle traite de structures profondes du logiciel responsable qui se laissent transposer.

**Deuxièmement**, la frugalité méthodologique acquise est mesurable. Nous l'éprouvions sur KoproGo sans pouvoir la quantifier — la comparaison avec BANKO la rend visible.

**Troisièmement**, la méthodologie elle-même est **en train de devenir un bien commun**, au même titre que le code que nous publions. Cette dimension dépasse les deux projets. Elle ouvre une perspective que nous formulons avec prudence : nous travaillons à formaliser ce qui pourrait devenir, si d'autres veulent bien la critiquer, l'améliorer et la prolonger, **une contribution à une épistémologie de l'ingénierie de solution pour le bien commun**. C'est une ambition qui ne s'auto-proclame pas — qui ne se révèle telle qu'après que d'autres s'en seront effectivement saisis. Nous l'inscrivons ici comme horizon de travail, pas comme acquis.

La sous-section 4.3 examine maintenant la convergence entre KoproGo et BANKO couche par couche — c'est cette convergence qui fait la force de la Méthode Maury comme matrice transposable.

[DÉCISION À DEUX — Plusieurs points dans cette sous-section 4.2 méritent une validation explicite avec Farah avant publication :
1. La désignation de l'experte fintech tunisienne sans la nommer (4.2.2) — il faudra de toute façon la consulter avant publication finale
2. La formulation tempérée de l'épistémologie en 4.2.7 — choix B confirmé
3. Le ratio 112/1100 commits avec sa nuance honnête (4.2.5) — option B confirmée
4. La formule "tout le monde a le droit de penser une solution s'il le veut, à condition de la penser avec discipline" (4.2.6) — à vérifier que la nuance "à condition de" ne dénature pas la formule originale]

---

## 4.3 — La convergence : sept couches communes par deux chemins

### 4.3.1 — Pourquoi cette convergence est la démonstration centrale du manifeste

Les deux récits qui précèdent ont chacun leur intérêt propre. Pris isolément, ils racontent comment KoproGo et BANKO sont nés. Pris ensemble, ils démontrent quelque chose de plus important : **les principes architecturaux qui ont émergé sur KoproGo se retrouvent intacts sur BANKO, alors que les contextes, les chemins et les domaines métier sont radicalement différents**.

Cette persistance n'est ni un hasard ni un dogmatisme. Elle ne tient pas au fait que nous appliquerions volontairement les mêmes choix par habitude — nous aurions pu ne pas le faire, et la liberté technique de BANKO le permettait. Elle tient au fait que les deux projets répondent à des problèmes humains qui partagent une structure commune, et que les principes architecturaux qui survivent à cette transposition sont précisément ceux qui rendent compte de cette structure commune. C'est cette convergence qui fait de la Méthode Maury une matrice transposable plutôt qu'une recette particulière.

Cette sous-section examine cette convergence couche par couche, en parcourant les sept couches qui composent un système full-stack moderne. Pour chaque couche, nous montrons ce qui converge dans les deux projets, ce qui diffère pour des raisons légitimes liées au domaine, et ce que cette convergence démontre. La conclusion en tire la portée philosophique pour l'ensemble du manifeste.

### 4.3.2 — Couche Domain : les invariants métier au cœur

**Ce qui converge.** Les deux projets placent leurs invariants métier au cœur de la couche domain, sous forme d'entités dont les constructeurs garantissent la validité. Dans KoproGo, une instance de `Building` ne peut pas exister si la somme de ses tantièmes ne fait pas exactement cent pour cent — l'invariant est codé dans le constructeur, et toute tentative de création qui violerait cette règle échoue à la compilation logique. Dans BANKO, une opération bancaire ne peut pas exister si elle viole les règles de division des risques inscrites dans la circulaire BCT 91-24 — l'invariant est codé de la même manière, dans le constructeur de l'entité concernée.

**Ce qui diffère pour des raisons légitimes.** Le contenu juridique est radicalement différent. KoproGo encode le Code civil belge sur la copropriété, BANKO encode treize textes réglementaires tunisiens et internationaux. Mais la **forme d'encodage** est identique : un texte juridique précis se traduit en invariant exécutable, validé par les tests unitaires, vérifié par les scénarios BDD écrits en Gherkin.

**Ce que cela démontre.** Un domaine métier qui repose sur du droit ou de la régulation se laisse traiter de la même manière indépendamment du domaine, dès lors qu'on accepte l'effort de traduction du texte juridique en invariant codé. Cette traduction est ce que le Domain-Driven Design appelle le *langage ubiquitaire* — un vocabulaire commun entre l'expert métier et le développeur, où chaque terme du droit a son équivalent exact dans le code. KoproGo et BANKO démontrent que ce langage ubiquitaire fonctionne quel que soit le droit considéré, et qu'il est l'outil principal pour transformer un texte normatif en système informatique fiable.

### 4.3.3 — Couche Application : ports, use cases et DTOs

**Ce qui converge.** Les deux projets organisent leur couche application selon le même triptyque. Les **ports** définissent les interfaces dont le domaine a besoin sans connaître leur implémentation — repository de persistance, services externes, adaptateurs de notification. Les **use cases** orchestrent les opérations métier en composant les entités du domaine et en s'appuyant sur les ports. Les **DTOs**, *Data Transfer Objects*, forment la couche anti-corruption qui sépare le domaine des formats d'entrée et de sortie.

Concrètement, dans BANKO la séparation est inscrite dans la structure du Cargo workspace lui-même : `crates/domain` ne dépend de personne, `crates/application` dépend uniquement de `crates/domain`, et `crates/infrastructure` implémente les ports définis par l'application. Dans KoproGo, la même séparation existe au niveau des modules Rust de `src/`, avec les sous-dossiers `domain/`, `application/` et `infrastructure/` qui respectent rigoureusement la même règle de dépendance.

**Ce qui diffère pour des raisons légitimes.** BANKO utilise une séparation par crates, KoproGo une séparation par modules dans une crate unique. Cette différence est l'effet direct de la maturation : ce que KoproGo a découvert progressivement et qu'il aurait pu refactoriser en workspace, BANKO l'a posé d'emblée. Le contenu des ports et des use cases diffère radicalement — un repository de copropriété n'a rien à voir avec un orchestrateur de paiement SWIFT — mais la grammaire architecturale est identique.

**Ce que cela démontre.** L'architecture hexagonale n'est pas un cadre conceptuel abstrait que l'on plaque sur un projet. C'est un **outil de séparation des responsabilités** qui produit des bénéfices concrets dans tous les projets qui l'adoptent : la possibilité de tester le domaine en isolation, la capacité à changer de base de données ou de framework web sans toucher à la logique métier, la lisibilité du code pour des développeurs qui n'étaient pas là quand il a été écrit. Ces bénéfices ne dépendent pas du domaine — ils dépendent de la discipline avec laquelle l'architecture est respectée.

### 4.3.4 — Couche Infrastructure backend : adaptateurs, handlers, middleware

**Ce qui converge.** Les deux projets implémentent leur couche infrastructure avec la même stack technique : Rust avec Actix-web pour le serveur HTTP, SQLx pour l'accès PostgreSQL, des middlewares pour l'authentification et la traçabilité, des handlers qui font le pont entre les requêtes HTTP et les use cases. La structure des dépendances dans les Cargo.toml des deux projets est presque identique — Actix-web 4.9, SQLx 0.8, Serde, Tokio, tracing, async-trait.

**Ce qui diffère pour des raisons légitimes.** BANKO ajoute des dépendances spécifiques au banking comme `rust_decimal` pour les calculs monétaires précis et `sha2` pour les signatures cryptographiques de la piste d'audit. KoproGo a son propre ensemble de dépendances spécifiques au métier de la copropriété. Mais le **squelette** des deux applications backend est interchangeable.

**Ce que cela démontre.** Les choix techniques sur cette couche dérivent directement des choix faits sur les couches supérieures. Si l'on a décidé du domaine et de l'application, l'infrastructure backend devient en grande partie déterministe — Rust pour la sobriété et la sécurité, Actix-web pour la performance, PostgreSQL pour l'ACID et l'auditabilité, SQLx pour l'accès typé à la base. Cette détermination n'est pas un appauvrissement — elle est la conséquence d'avoir fait des choix supérieurs cohérents. La Méthode Maury en tire un enseignement opérationnel : un projet bien commencé en haut produit des choix techniques en bas qui s'imposent presque d'eux-mêmes, ce qui réduit considérablement le temps de délibération sur les détails et permet de se concentrer sur les invariants qui comptent vraiment.

### 4.3.5 — Couche Frontend : Astro, Svelte, hexagonale light

**Ce qui converge.** Les deux projets utilisent la même stack frontend — Astro pour le rendu statique des pages, Svelte pour les composants interactifs en *islands architecture*, TypeScript pour le typage, Tailwind ou un système équivalent pour le style. Et plus important, les deux appliquent une **hexagonale light** au frontend : les composants n'effectuent jamais d'appels API directs, ils passent par des clients API dédiés ; les stores encapsulent l'état partagé ; les validateurs côté client miroir des invariants du domaine côté serveur.

**Ce qui diffère pour des raisons légitimes.** Les composants concrets sont entièrement différents — un formulaire de saisie d'AG dans KoproGo n'a rien à voir avec un dashboard de calcul prudentiel dans BANKO. La langue des interfaces diffère aussi : KoproGo est multilingue avec le français comme langue principale, BANKO est principalement en français pour la place de Tunis avec une perspective de support de l'arabe.

**Ce que cela démontre.** Le principe de séparation des responsabilités s'applique au frontend tout autant qu'au backend. Une équipe qui aborde un projet web sans cette séparation finit par accumuler de la dette dans des composants qui mélangent la présentation, l'état applicatif et la communication réseau. La hexagonale light frontend n'est pas une sur-ingénierie — elle est la condition pour qu'un changement de framework ou un ajout de canal d'accès (mobile, terminal, API publique) ne déclenche pas une réécriture complète. Elle est aussi ce qui permet à un développeur backend qui rejoint le frontend de comprendre rapidement la structure, parce qu'il y retrouve des concepts familiers.

### 4.3.6 — Couche IaC : Terraform, Ansible, conteneurs, GitOps

**Ce qui converge.** Les deux projets traitent l'infrastructure comme du code à part entière — versionné, revu, testé. Terraform pour le provisionnement des ressources cloud, Ansible pour la configuration des serveurs, Docker et docker-compose pour l'environnement de développement et la stack de staging, des manifestes Kubernetes pour les phases ultérieures de mise à l'échelle. Les deux projets prévoient une progression d'infrastructure cohérente avec leur jalon de capacité — Docker compose pour le développement, VPS avec Traefik pour les premiers déploiements, K3s puis K8s managé quand l'échelle l'exige.

**Ce qui diffère pour des raisons légitimes.** KoproGo est hébergé chez OVH en France pour des raisons de conformité RGPD européenne, BANKO est conçu pour être hébergé localement en Tunisie pour des raisons de souveraineté et de conformité INPDP. Les rôles Ansible diffèrent en fonction de cette localisation et des exigences de sécurité spécifiques à chaque secteur. Mais la **discipline** d'avoir une infrastructure entièrement décrite en code, reproductible, et pouvant être détruite et reconstruite à l'identique est la même dans les deux projets.

**Ce que cela démontre.** L'infrastructure as code n'est pas une optimisation pour les très grandes équipes — c'est une exigence de transparence et de reproductibilité qui s'applique dès le premier serveur. Pour des projets open source qui veulent que d'autres puissent les reprendre, c'est aussi la garantie que la documentation d'exploitation est à jour : si elle ne l'est pas, le code Terraform ou Ansible ne fonctionnerait pas. La Méthode Maury en tire une exigence : **chaque environnement de production que nous opérons doit pouvoir être reconstruit depuis zéro à partir du dépôt Git en moins d'une journée**. Cette exigence n'est pas négociable — elle est la condition de la souveraineté que nous prônons.

### 4.3.7 — Couche CI/CD : qualité automatisée et hooks Git

**Ce qui converge.** Les deux projets utilisent GitHub Actions pour leur CI/CD avec une structure de workflows quasi-identique : un pipeline principal qui fait le lint, les tests unitaires, les tests d'intégration, les tests BDD et les tests E2E ; un workflow de sécurité qui audite les dépendances avec `cargo audit` et `npm audit` ; un workflow de build et publication des images Docker. Tous ces workflows sont déclenchés sur chaque pull request et bloquent la fusion si l'un d'eux échoue. Les deux projets utilisent aussi des hooks Git locaux — pre-commit pour le formatage et le linting, pre-push pour les tests — qui font la même vérification que la CI mais en feedback immédiat.

**Ce qui diffère pour des raisons légitimes.** BANKO a des contraintes de sécurité plus strictes liées au secteur bancaire — audits de dépendance plus fréquents, vérification des CVE en continu, scan de secrets dans le code. KoproGo a des workflows additionnels pour la documentation et les tests de charge avec wrk2. Mais la **logique** est la même : aucune fusion de code sans que la qualité ait été automatiquement vérifiée.

**Ce que cela démontre.** La CI/CD bien faite est ce qui permet à un projet open source d'accepter des contributions externes sans craindre la dégradation. Elle est aussi ce qui permet à l'IA générative supervisée d'être utilisée à pleine puissance : un agent IA peut produire du code, il sera systématiquement passé au crible des mêmes vérifications qu'un développeur humain. Cette vérification automatisée est le **garde-fou opérationnel de la conviction n°2** du manifeste — *l'IA génère, l'humain valide* — parce qu'elle objective ce que valider veut dire et qu'elle empêche la dérive vers une acceptation passive de code généré.

### 4.3.8 — Couche Monitoring et Sécurité : Prometheus, Loki, Suricata, CrowdSec

**Ce qui converge.** Les deux projets déploient la même stack d'observabilité — Prometheus pour les métriques applicatives, Grafana pour la visualisation, Loki pour l'agrégation des logs, Alertmanager pour les notifications. Et la même stack de sécurité — chiffrement LUKS du disque pour les données au repos, Suricata comme système de détection d'intrusion, CrowdSec comme pare-feu applicatif communautaire, fail2ban pour les attaques par force brute, audits Lynis et rkhunter, vérification d'intégrité avec AIDE, sauvegardes chiffrées avec GPG.

**Ce qui diffère pour des raisons légitimes.** BANKO ajoute une piste d'audit cryptographique signée pour chaque opération bancaire, qui est exigée par la réglementation. KoproGo ajoute des métriques carbone par requête qui sont propres à son engagement écologique affiché. Mais le **socle de sécurité et d'observabilité** est dimensionné selon les mêmes principes : équivalence ISO 27001 sans certification formelle, transparence des métriques, surveillance permanente des intrusions.

**Ce que cela démontre.** La sécurité et l'observabilité ne sont pas des fonctionnalités optionnelles qu'on ajoute à la fin d'un projet. Elles sont des couches qui doivent être construites en parallèle des couches métier, dès le sprint zéro. Les deux projets l'ont fait — BANKO depuis le tout premier commit grâce à la maturation de KoproGo. Cette discipline a un coût initial mais elle évite des coûts ultérieurs bien supérieurs : reprendre la sécurité d'un système déjà en production demande des semaines de travail pour des résultats inférieurs à ce qu'on aurait eu en la pensant en amont.

### 4.3.9 — Le tableau de synthèse

| Couche | Ce qui converge | Ce qui diffère légitimement | Ce que cela démontre |
|---|---|---|---|
| Domain | Invariants dans constructeurs, langage ubiquitaire | Contenu juridique (Code civil belge / régulation BCT) | DDD se transpose à tout domaine régulé |
| Application | Ports, use cases, DTOs comme triptyque | Workspace BANKO vs modules KoproGo (effet de maturation) | L'hexagonale n'est pas conceptuelle, elle structure |
| Infrastructure backend | Rust + Actix-web + SQLx + PostgreSQL | Dépendances métier spécifiques | Les choix bas dérivent des choix hauts |
| Frontend | Astro + Svelte + hexagonale light | Composants et langues | La séparation de responsabilités vaut côté client |
| IaC | Terraform + Ansible + Docker + K3s/K8s progressif | Hébergement OVH France vs Tunisie locale | Souveraineté et reproductibilité sont indissociables |
| CI/CD | GitHub Actions, lint, tests, audits, hooks Git | Workflows additionnels selon le secteur | La CI/CD est le garde-fou de la conviction n°2 |
| Monitoring & Sécurité | Prometheus + Loki + Suricata + CrowdSec + LUKS | Piste d'audit cryptographique pour BANKO | Sécurité et observabilité sont structurelles |

### 4.3.10 — Ce que la convergence démontre philosophiquement

Cette comparaison couche par couche n'est pas un exercice technique gratuit. Elle prouve quelque chose qui dépasse les deux projets et qui touche au cœur de la thèse du manifeste.

**La convergence n'est pas une uniformisation.** Les contextes, les domaines, les communautés, les langues, les juridictions, les contraintes — tout cela est radicalement différent entre KoproGo et BANKO. Si la convergence des sept couches techniques tenait à une homogénéisation forcée, elle serait suspecte. Elle tient au contraire au fait que les deux projets, partis de problèmes humains analogues — outiller une communauté concrète sans la trahir, encoder un droit local pour qu'il devienne gardien des opérations, transmettre une pratique pour qu'elle puisse être reprise par d'autres — arrivent à des solutions architecturales analogues parce que les principes architecturaux pertinents sont les mêmes. C'est rigoureusement ce que Boaventura de Sousa Santos appelle l'**écologie des savoirs** : différents accès locaux à des principes universels qui répondent à des problèmes humains communs.

**La convergence est ce qui rend la matrice transposable.** Si les sept couches convergent malgré la diversité des contextes, alors la Méthode Maury n'est pas une recette pour un cas particulier. Elle est un **patron** réutilisable. Un autre projet, dans un autre domaine — l'agriculture coopérative, la santé associative, la gestion d'écoles, la gouvernance d'ASBL, le banking communautaire dans un autre pays — peut reprendre cette même architecture en adaptant uniquement le contenu juridique et fonctionnel. L'effort de traduction est important mais la grammaire est connue. Cette transposabilité est ce qui justifie l'ambition que nous formulons avec prudence en sous-section 4.2.7 — la possibilité d'une contribution à une épistémologie de l'ingénierie de solution pour le bien commun, qui ne s'auto-proclame pas mais qui se vérifie à mesure que d'autres projets reprennent la matrice.

**La convergence valide rétroactivement les choix de KoproGo.** Quand nous avons fait les choix architecturaux de KoproGo, nous ne savions pas s'ils étaient accidentels ou universalisables. Nous avons cru qu'ils étaient cohérents avec nos principes, mais nous ne pouvions pas le démontrer. BANKO le démontre. Le fait que les mêmes choix s'imposent dans un contexte radicalement différent prouve qu'ils ne tenaient pas au hasard belge, à notre culture personnelle ou à la stack que nous connaissions déjà. Ils tenaient à des structures architecturales qui sont vraies du logiciel responsable en tant que tel.

**La convergence rend la Méthode Maury enseignable.** C'est peut-être la conséquence la plus importante. Tant que nous n'avions qu'un seul projet, transmettre la méthode revenait à transmettre une expérience. Avec deux projets convergents, transmettre la méthode revient à transmettre une **structure** dont les exemples concrets sont vérifiables sur deux dépôts publics. Un étudiant en informatique de gestion comme Farah, un stagiaire en cybersécurité, un développeur indépendant qui voudrait monter son propre écosystème pour une communauté locale — tous peuvent désormais ouvrir KoproGo et BANKO côte à côte, comparer les sept couches dans le code lui-même, et apprendre la méthode sans avoir besoin de notre présence. C'est le sens premier que nous donnons à la transmission.

### 4.3.11 — Bilan de la convergence et clôture de l'arc narratif

Cette sous-section 4.3 clôt l'arc narratif des trois sous-sections qui composent le cœur démonstratif de la section 4. La sous-section 4.1 a raconté l'émergence ascendante de KoproGo. La sous-section 4.2 a raconté la maturation descendante de BANKO. La sous-section 4.3 a montré que les deux récits, malgré leurs trajectoires opposées, convergent sur les mêmes invariants architecturaux — et que cette convergence est le signe distinctif d'une matrice transposable plutôt que d'une recette particulière.

Les sous-sections 4.4 et 4.5, qui restent à rédiger dans des versions ultérieures du manifeste, prolongeront ce travail en deux directions complémentaires. La sous-section 4.4 présentera le pipeline complet TOGAF → BMAD → Scrum → Nexus → SAFe → ITIL et la place précise de l'IA supervisée dans ce pipeline. La sous-section 4.5 examinera les sept invariants de qualité — SOLID, DDD, BDD, TDD, hexagonal, YAGNI, DRY — comme traductions opérationnelles des sagesses énoncées en section 2 du manifeste, refermant ainsi la boucle entre les principes éthiques et les pratiques techniques.

Pour cette première proposition, l'arc démonstratif de KoproGo, BANKO et leur convergence est suffisant. Il établit que la Méthode Maury existe comme objet identifiable, qu'elle a été éprouvée dans deux contextes radicalement différents, et qu'elle produit des résultats reproductibles. Le reste du travail méthodologique et philosophique pourra être rédigé à mesure que la pratique elle-même se précisera.

---

## 4.4 — Le pipeline complet et l'IA comme copilote responsable

### 4.4.1 — Pourquoi un pipeline complet, et pourquoi celui-ci

Les sous-sections précédentes ont raconté l'émergence et la convergence de la Méthode Maury à partir de deux projets concrets. Cette sous-section change de registre : elle décrit le pipeline méthodologique tel qu'il s'applique à un projet, du moment où la vision stratégique se formule jusqu'au moment où le système est en production et exploité durablement. Nous le décrivons in extenso plutôt qu'en condensé, parce qu'un lecteur qui voudrait s'en saisir pour son propre projet a besoin de la grammaire complète et pas seulement de l'esprit.

Le pipeline articule six cadres méthodologiques qui sont souvent présentés comme rivaux et que nous traitons comme complémentaires : **TOGAF, BMAD, Scrum, Nexus, SAFe et ITIL**. Cette articulation n'est pas une accumulation. Chaque cadre répond à une question précise à une échelle temporelle précise, et l'agencement entre eux est conçu pour qu'aucune question ne reste orpheline et qu'aucune échelle ne soit traitée par un cadre inadapté.

Avant d'examiner chaque étape, posons l'agencement d'ensemble. **TOGAF** définit le quoi à l'échelle stratégique, sur trois à dix ans. **BMAD** traduit le quoi en backlog d'épopées et de capacités, sur six à vingt-quatre mois. **Scrum** orchestre le développement à l'échelle d'une équipe sur deux à quatre semaines. **Nexus** coordonne plusieurs équipes Scrum quand le projet l'exige. **SAFe** apporte la cadence des Program Increments à l'échelle d'un programme sur huit à douze semaines, dans sa version essentielle et non dans sa version industrielle dénaturée. **ITIL** prend le relais en exploitation, une fois le système en production, et garantit la qualité de service au long cours.

À chacune de ces étapes, **l'intelligence artificielle générative est présente comme copilote**. Pas comme remplaçant. Pas comme oracle. Comme partenaire d'écriture, de génération, de relecture, qui accélère le travail de l'humain et qui force l'explicitation de ce que l'humain savait sans le formaliser. La règle qui traverse tout le pipeline est sans exception : **l'IA propose, l'humain dispose. La responsabilité de l'output est entièrement humaine, à toute échelle et à toute étape.**

### 4.4.2 — TOGAF : la boussole stratégique

**Fonction.** TOGAF, l'*Open Group Architecture Framework*, fournit la boussole stratégique du projet. Il répond à la question fondatrice du quoi : quels sont les drivers business, qui sont les parties prenantes, quelles sont les contraintes réglementaires et techniques structurantes, quels sont les invariants à long terme. Sans cette boussole, tout ce qui suit risque de tourner à vide.

**Échelle temporelle.** Trois à dix ans. La vision TOGAF n'est pas révisée tous les sprints — elle est révisée lors des gate reviews majeures du projet, généralement tous les six à douze mois, ou lors d'un changement structurel du contexte (nouvelle réglementation, nouveau marché, pivot stratégique).

**Cycle ADM.** Le cycle *Architecture Development Method* parcourt en boucle huit phases successives : phase préliminaire, vision d'architecture (Phase A), architecture métier (Phase B), architectures de système et technique (Phases C et D), opportunités et solutions (Phase E), planification de migration (Phase F), gouvernance de la mise en œuvre (Phase G), gestion du changement (Phase H). Le cycle n'est pas linéaire — il est itératif et chaque phase peut renvoyer à la précédente si une découverte le justifie.

**Artefacts produits.** Les *ADR*, *Architecture Decision Records*, tracent chaque choix structurant avec son contexte, ses alternatives écartées et ses conséquences attendues. Les *RFC*, *Requests for Comments*, formalisent les questions ouvertes pour qu'elles soient discutées collectivement avant d'être tranchées. Les *gate reviews* ponctuent le cycle ADM par des points de revue obligatoires où l'on vérifie que les choix tiennent et que la stratégie reste alignée avec les drivers business.

**Invariants de qualité préservés.** Cohérence stratégique au long cours, traçabilité des décisions, capacité à répondre à un audit, alignement business-IT.

**Rôle de l'humain.** L'humain est l'auteur de la vision. Il discute avec les parties prenantes, il pose les questions difficiles, il accepte les compromis lucides, il formule les ADR et il anime les gate reviews. Aucune de ces activités ne peut être déléguée — elles supposent une responsabilité que seul un humain peut porter face à des humains.

**Rôle de l'IA comme copilote.** L'IA accélère trois choses précises à cette échelle. Premièrement, **l'élaboration et la mise en forme** des ADR : à partir d'une décision orale prise en réunion, l'IA peut produire une première version d'ADR structurée selon le canevas Michael Nygard, que l'humain corrige et valide. Deuxièmement, **l'exploration des alternatives** : confronté à un choix stratégique, l'humain peut demander à l'IA de générer trois ou quatre variantes argumentées, ce qui aide à expliciter ce que l'humain savait déjà tacitement et à découvrir ce qu'il n'avait pas encore considéré. Troisièmement, **la rédaction des RFC** : formuler une question ouverte de manière à ce qu'elle puisse être discutée par d'autres demande un effort de clarification que le dialogue avec l'IA accélère.

C'est ici que l'IA agit comme une **accoucheuse socratique** au sens le plus précis. Une vision stratégique mal explicitée ne peut pas être discutée, ne peut pas être révisée, ne peut pas être transmise. L'IA, en demandant des précisions, en proposant des reformulations, en mettant en évidence les implicites, force l'humain à formaliser ce qu'il portait sans le savoir. Ce n'est pas l'IA qui produit la vision — c'est l'humain. Mais c'est le dialogue avec l'IA qui rend la vision dicible.

### 4.4.3 — BMAD : l'agile architecturé

**Fonction.** BMAD, *Business Model Agile Development*, traduit la vision stratégique TOGAF en backlog produit structuré. Il répond à la question : par où commencer concrètement, et dans quel ordre. C'est l'étape charnière entre le quoi stratégique et le comment opérationnel.

**Échelle temporelle.** Six à vingt-quatre mois. Un BMAD couvre généralement la durée nécessaire pour atteindre un jalon majeur de capacité — par exemple, dans BANKO, le passage du jalon 0 (Fondations) au jalon 1 (Core banking + sécurité).

**Méthode.** BMAD organise le travail en **épopées** (*epics*), elles-mêmes décomposées en **capacités**, elles-mêmes décomposées en **fonctionnalités** (*features*), elles-mêmes décomposées en **user stories** prêtes à être prises en sprint. Chaque niveau de granularité a son propre format, ses propres critères d'acceptation et ses propres validations. Cette décomposition garantit que rien n'est pris en sprint qui n'ait été préalablement aligné avec une capacité, qui n'ait été préalablement alignée avec une épopée, qui n'ait été préalablement alignée avec la vision TOGAF.

**Artefacts produits.** Backlog produit hiérarchisé, *roadmap par capacité* qui documente la progression organique du projet, *Definition of Ready* et *Definition of Done* explicites pour chaque niveau de granularité.

**Invariants de qualité préservés.** Alignement permanent entre la stratégie et le travail au quotidien, refus de prendre en sprint ce qui n'a pas été pensé en amont, possibilité de re-prioriser à chaque jalon sans perdre la cohérence d'ensemble.

**Rôle de l'humain.** L'humain — généralement le *product manager* ou le rôle équivalent — décompose les épopées, valide les capacités, écrit les user stories en collaboration avec les développeurs et les experts métier. Il anime les ateliers de raffinement de backlog et il arbitre les priorités quand des tensions apparaissent.

**Rôle de l'IA comme copilote.** L'IA accélère plusieurs activités à cette échelle. **La génération de premières versions de user stories** à partir d'une description orale d'une fonctionnalité, en respectant le format *En tant que… je veux… afin de…* avec ses critères d'acceptation Gherkin. **La détection des dépendances oubliées** entre fonctionnalités, en analysant le backlog dans son ensemble. **La proposition de découpages alternatifs** pour des épopées trop grosses, ce qui aide l'humain à choisir un découpage parmi plusieurs au lieu d'inventer le sien à partir de zéro. **La vérification de cohérence** entre la roadmap par capacité et la vision TOGAF, par exemple en repérant qu'une capacité prévue ne correspond à aucun ADR.

L'humain garde la responsabilité de chaque user story acceptée dans le backlog. Une user story générée par l'IA et non relue par l'humain est une faute professionnelle au sens de la Méthode Maury — elle viole la conviction n°2 et elle prépare une dette technique inévitable.

### 4.4.4 — Scrum : la cadence de l'équipe

**Fonction.** Scrum orchestre le travail d'une équipe de développement à l'échelle d'un sprint. C'est le cadre qui transforme un backlog priorisé en logiciel livré.

**Échelle temporelle.** Deux à quatre semaines par sprint. Chez nous, le sprint est de deux semaines pour les phases actives de développement et de quatre semaines pour les phases de consolidation ou de préparation de jalon.

**Cérémonies.** Les quatre cérémonies classiques — *sprint planning*, *daily stand-up*, *sprint review*, *sprint retrospective* — sont préservées telles que le Manifeste Agile et le Scrum Guide originel les ont définies, sans surcharge. Le *sprint planning* sélectionne les user stories du sprint à partir du backlog raffiné en BMAD. Le *daily stand-up* synchronise l'équipe en quinze minutes. La *sprint review* présente l'incrément à des parties prenantes et collecte leur feedback. La *sprint retrospective* interroge la pratique de l'équipe et identifie une ou deux améliorations à expérimenter au sprint suivant.

**Artefacts produits.** *Sprint backlog*, incrément de produit livrable, *burndown chart*, notes de rétrospective avec actions de progrès.

**Invariants de qualité préservés.** Rythme soutenable, livraison fréquente, transparence sur l'avancement, capacité d'adaptation à mi-parcours, *Definition of Done* respectée pour chaque user story livrée.

**Rôle de l'humain.** Toute l'équipe est humaine et doit le rester aux moments-clés. Le *Scrum Master* facilite, le *Product Owner* clarifie les priorités, les développeurs et les testeurs produisent et relisent. Les rétrospectives en particulier ne peuvent pas être déléguées — elles sont le moment où l'équipe prend conscience de sa propre dynamique et c'est cette prise de conscience qui fait la différence entre une équipe vivante et une équipe productive en surface.

**Rôle de l'IA comme copilote.** L'IA est présente massivement à cette échelle, parce que c'est à cette échelle que se fait l'essentiel de la production de code. **Génération de squelettes** de classes, de fonctions, de tests à partir d'une description en langage naturel. **Refactoring assisté** quand un module devient trop touffu. **Génération des tests unitaires** à partir d'un cas concret oralement décrit. **Rédaction des commits** suivant les conventions du projet, des descriptions de pull requests, des changelogs. **Relecture critique** d'un morceau de code dont on n'est pas sûr, où l'IA agit comme un *pair reviewer* qui pose des questions et propose des améliorations.

À cette échelle, la dimension d'accouchement socratique de l'IA est particulièrement visible. Un développeur qui demande à l'IA de générer un test pour son code se retrouve à formuler ce que son code est censé faire, et cette formulation lui révèle souvent une ambiguïté ou une omission qu'il n'avait pas vue. Le bénéfice n'est pas seulement le test généré — il est aussi la clarification que la demande de génération a forcée.

La règle de responsabilité humaine tient évidemment ici aussi. **Aucun commit ne part en pull request sans qu'un humain ait relu intégralement le code, compris ce qu'il fait, vérifié qu'il respecte la *Definition of Done* et l'ait approuvé.** Le *pair programming* avec l'IA n'est jamais une délégation — c'est une coopération.

### 4.4.5 — Nexus : la coordination multi-équipes

**Fonction.** Nexus coordonne plusieurs équipes Scrum qui travaillent sur le même produit. Il répond à la question : comment éviter que l'addition d'équipes performantes individuellement produise un système incohérent collectivement.

**Échelle temporelle.** Identique à Scrum — deux à quatre semaines par sprint Nexus, qui correspond aux sprints des équipes individuelles synchronisés.

**Méthode.** Nexus ajoute trois éléments au Scrum classique. Un *Nexus Sprint Planning* qui aligne les équipes sur ce qu'elles vont produire et sur les dépendances entre elles. Un *Nexus Daily Scrum* quotidien qui synchronise les *Scrum Masters* ou des représentants désignés des équipes. Un *Nexus Integration Team*, équipe transverse responsable de la cohérence d'ensemble, qui détecte les conflits, qui identifie les dépendances oubliées, qui maintient l'intégrité de l'incrément intégré.

**Artefacts produits.** *Nexus Sprint Backlog* qui visualise les dépendances entre équipes, incrément intégré qui combine les contributions de toutes les équipes Scrum.

**Invariants de qualité préservés.** Cohérence d'ensemble malgré la parallélisation, détection précoce des conflits d'architecture, capacité à livrer un produit qui se tient à plusieurs équipes.

**Rôle de l'humain.** Le *Nexus Integration Team* est composé d'humains expérimentés capables de tenir simultanément la vision technique d'ensemble et la dynamique des équipes. C'est probablement le rôle le moins automatisable du pipeline parce qu'il repose sur un jugement contextuel permanent.

**Rôle de l'IA comme copilote.** L'IA peut fournir une **détection automatique des conflits** entre branches de plusieurs équipes au-delà des classiques conflits de merge — par exemple, deux équipes qui modifient indépendamment la même API en introduisant des incohérences sémantiques. Elle peut aussi **synthétiser les statuts** des différentes équipes pour produire un rapport quotidien lisible par le *Nexus Integration Team*. Elle peut enfin **détecter les divergences** par rapport aux ADR qui ont été produits en TOGAF — par exemple si une équipe utilise une bibliothèque qui contredit un choix architectural global.

À cette échelle, la responsabilité humaine s'élargit : l'humain n'est plus seulement responsable de son propre code mais aussi de l'incrément intégré. Une décision de merge dans Nexus engage plusieurs équipes et la cohérence du produit. L'IA peut signaler, l'humain doit trancher.

### 4.4.6 — SAFe essentiel : la cadence des Program Increments

**Fonction.** SAFe, le *Scaled Agile Framework*, est utilisé chez nous **dans sa version essentielle** uniquement, et non dans sa version industrielle qui empile dix niveaux hiérarchiques et qui est précisément ce que nous critiquons dans la sous-section 1.4. La version essentielle de SAFe se résume à introduire une cadence de *Program Increments* (PI) qui rythme le projet à une échelle intermédiaire entre le sprint Scrum et l'année stratégique TOGAF.

**Échelle temporelle.** Huit à douze semaines par PI. Un PI correspond généralement à quatre à cinq sprints Scrum consécutifs, avec une cérémonie de planification au début (*PI Planning*) et une cérémonie de revue à la fin (*Inspect & Adapt*).

**Méthode.** Le *PI Planning* rassemble toutes les équipes pour deux jours afin de planifier le PI à venir, d'identifier les dépendances inter-équipes, d'aligner les objectifs avec les capacités BMAD, et d'engager des objectifs collectifs mesurables. L'*Inspect & Adapt* à la fin du PI fait le bilan, mesure l'atteinte des objectifs, identifie les *systemic issues* et engage les actions de progrès pour le PI suivant.

**Artefacts produits.** *PI Objectives* mesurables, *Program Board* qui visualise les fonctionnalités planifiées et leurs dépendances, *Inspect & Adapt Report* avec les actions de progrès.

**Invariants de qualité préservés.** Alignement à moyen terme, mesure de l'atteinte des engagements, identification systémique des dysfonctionnements, capacité à corriger sur deux à trois mois plutôt qu'à attendre la gate review TOGAF suivante.

**Rôle de l'humain.** Le *PI Planning* est un événement intensément humain — deux jours de discussion collective où l'on confronte les besoins, les contraintes, les capacités. Sa qualité dépend entièrement de la qualité de la préparation humaine en amont et de la dynamique de groupe pendant l'événement.

**Rôle de l'IA comme copilote.** Avant le PI Planning, l'IA peut **synthétiser les éléments du backlog** que les équipes auront à arbitrer, **détecter les tensions probables** entre les capacités prévues et les ressources disponibles, et **préparer des propositions d'objectifs PI** que les équipes ajusteront pendant l'événement. Pendant et après le PI Planning, l'IA peut **mettre en forme** les *PI Objectives* exprimés oralement, **rédiger** le *Program Board* sous forme structurée, et **produire** un premier jet d'*Inspect & Adapt Report* à la fin du PI.

La règle reste la même : aucun *PI Objective* n'est validé sans qu'un humain l'ait porté et compris. L'IA accélère la mise en forme, jamais l'engagement.

### 4.4.7 — ITIL : la qualité de service au long cours

**Fonction.** ITIL, *Information Technology Infrastructure Library*, prend le relais quand le système est en production. Il répond à la question : comment garantir la qualité de service au long cours, comment gérer les incidents, comment faire évoluer le système sans le casser, comment mesurer la satisfaction des utilisateurs.

**Échelle temporelle.** Permanente, à partir de la mise en production et pour toute la durée de vie du système. Les jalons ITIL sont rythmés par les *Service Level Agreements* (SLA) qui se mesurent typiquement au mois ou au trimestre.

**Méthode.** ITIL définit une série de processus opérationnels — gestion des incidents, gestion des problèmes, gestion des changements, gestion des configurations, gestion des niveaux de service. Chez nous, ces processus sont allégés par rapport à la version industrielle d'ITIL, mais leurs principes sont respectés.

**Artefacts produits.** *Tickets d'incident* avec leur cycle de vie complet, *Change Advisory Board* (CAB) léger pour les changements significatifs, *runbooks* opérationnels documentant la conduite à tenir face aux situations connues, *post-mortems* après les incidents majeurs.

**Invariants de qualité préservés.** Continuité de service, traçabilité des incidents et de leur résolution, mémoire collective de l'équipe d'exploitation, amélioration continue par capitalisation sur les incidents passés.

**Rôle de l'humain.** L'astreinte est humaine, la décision de basculer une production sur un site de secours est humaine, la communication avec les utilisateurs en cas de panne majeure est humaine. Ces responsabilités ne sont pas négociables — elles définissent la confiance qu'une organisation place dans son équipe d'exploitation.

**Rôle de l'IA comme copilote.** L'IA est très utile à cette échelle. **Détection précoce d'anomalies** dans les métriques Prometheus en croisant des indicateurs que l'humain ne corrèle pas spontanément. **Première hypothèse de diagnostic** quand un incident survient, à partir des logs Loki et des traces, que l'humain valide ou écarte. **Génération de runbooks** à partir d'incidents passés et de leurs résolutions. **Rédaction de post-mortems** structurés selon un canevas standard, à partir des notes prises pendant l'incident. **Réponse de premier niveau** aux utilisateurs sur des questions courantes, avec escalade humaine pour tout ce qui sort du périmètre prévu.

La responsabilité humaine ITIL est particulièrement importante parce que les utilisateurs voient l'effet direct de l'exploitation au quotidien. Une réponse d'IA mal calibrée envoyée à un utilisateur en détresse peut détruire en quelques secondes la confiance qu'on a mis des années à construire.

### 4.4.8 — Le tableau d'alignement des cérémonies

L'agencement des six cadres méthodologiques produit un alignement de cérémonies à différentes échelles temporelles. Ce tableau récapitule l'ensemble pour qu'un lecteur puisse en saisir la cohérence d'un coup d'œil.

| Cadre | Échelle | Cérémonie principale | Fréquence | Sortie principale |
|---|---|---|---|---|
| TOGAF | 3-10 ans | Gate Review ADM | 6-12 mois | ADR validés, RFC tranchés |
| BMAD | 6-24 mois | Raffinement de backlog | Hebdomadaire | Capacités prêtes pour Scrum |
| SAFe essentiel | 8-12 semaines | PI Planning / Inspect & Adapt | Trimestriel | PI Objectives engagés / Actions de progrès |
| Scrum | 2-4 semaines | Sprint Review / Retrospective | Bi-hebdomadaire | Incrément livré / Améliorations équipe |
| Nexus | 2-4 semaines | Nexus Daily Scrum | Quotidien | Synchronisation multi-équipes |
| ITIL | Permanent | CAB léger / Post-mortem | Mensuel / À l'incident | Changements validés / Apprentissages capitalisés |

Cette superposition des cadences est ce qui permet au projet de respirer. À l'échelle quotidienne, le *daily stand-up* Scrum et le *Nexus Daily* synchronisent. À l'échelle bi-hebdomadaire, les rétrospectives Scrum interrogent la pratique. À l'échelle trimestrielle, le PI Planning aligne les équipes. À l'échelle annuelle, la gate review TOGAF vérifie que la stratégie tient. Aucune décision importante n'est prise au mauvais niveau temporel, et aucun niveau temporel ne reste sans instance de relecture.

### 4.4.9 — La place de l'IA, transversale et disciplinée

L'IA traverse tout le pipeline mais elle ne le pilote nulle part. Cette distinction est centrale. Reformulons-la avec précision parce qu'elle est au cœur de ce que la Méthode Maury a de plus singulier.

L'IA **accélère la mise en forme** à toutes les échelles. Un ADR, une user story, un test, un commit, un post-mortem — tous ces artefacts peuvent être produits plus vite avec l'aide de l'IA qu'à la main. Cette accélération est précieuse parce qu'elle libère du temps humain pour les activités qui ne peuvent pas être déléguées : la délibération stratégique, la discussion métier, la décision de priorisation, la relation avec les utilisateurs.

L'IA **force l'explicitation** des pratiques tacites à toutes les échelles. Quand un développeur demande à l'IA un test pour son code, il doit formuler ce que son code est censé faire. Quand un *product manager* demande à l'IA une user story à partir d'une fonctionnalité, il doit clarifier la valeur business. Quand un architecte demande à l'IA un ADR à partir d'une décision orale, il doit nommer les alternatives écartées. Cette dimension d'**accouchement socratique** est probablement le bénéfice de l'IA le moins reconnu et le plus précieux. Elle transforme un savoir tacite en savoir transmissible, ce qui est exactement la définition de ce que nous voulons faire avec la Méthode Maury elle-même.

L'IA **ne porte aucune responsabilité finale** à aucune échelle. Pas dans les ADR, pas dans les user stories, pas dans les commits, pas dans les *PI Objectives*, pas dans les *post-mortems*. La responsabilité reste intégralement humaine, à toute échelle et à toute étape. Cette règle n'est pas une posture morale abstraite — elle est une exigence opérationnelle. Une équipe qui délègue sa responsabilité à l'IA perd la capacité d'apprendre de ses erreurs, parce qu'elle ne sait plus qui a décidé quoi et pourquoi. La responsabilité est ce qui rend l'expérience capitalisable.

C'est cette articulation — accélération de la mise en forme, explicitation des pratiques tacites, responsabilité humaine intégrale — qui distingue la Méthode Maury d'une utilisation paresseuse de l'IA. Toute organisation qui voudrait reprendre la méthode doit accepter ces trois conditions ensemble. Aucune ne suffit seule, et aucune n'est négociable.

### 4.4.10 — L'humain a le dernier mot, et il a aussi le premier

Une dernière clarification mérite d'être posée explicitement, parce qu'elle est souvent mal comprise. Quand nous disons que l'humain valide ce que l'IA produit, on pourrait croire que l'humain n'intervient qu'en aval, après que l'IA a généré quelque chose. C'est faux.

L'humain a le **dernier mot** parce qu'il valide. Mais il a aussi le **premier mot** parce que c'est lui qui formule la demande. La qualité de ce que l'IA produit dépend directement de la qualité du *prompt* que l'humain construit. Un *prompt* mal formulé produit une sortie inutilisable, qu'il faut jeter, ce qui consomme des ressources pour rien et qui contredit la conviction n°7 sur l'écologie de l'itération.

C'est ici que la Méthode Maury rejoint la **frugalité de prompt** que nous avons mesurée comme un bénéfice de la maturation entre KoproGo et BANKO. La frugalité n'est pas seulement un effet de l'expérience — elle est aussi une discipline d'écriture. Un *prompt* bien construit décrit le contexte, formule l'attendu, précise les contraintes, donne des exemples, et reste suffisamment ouvert pour que l'IA puisse contribuer plutôt que se contenter de reformuler. Cette discipline d'écriture s'apprend. Elle est probablement l'une des compétences les plus importantes du développeur des dix prochaines années, et elle reste largement implicite dans la formation actuelle.

Nous voudrions que la Méthode Maury contribue à formaliser cette compétence et à la rendre transmissible. C'est l'une des raisons pour lesquelles nous écrivons ce manifeste.

### 4.4.11 — Bilan du pipeline et pont vers la sous-section 4.5

Cette sous-section a présenté in extenso le pipeline méthodologique de la Méthode Maury. Six cadres articulés, six échelles temporelles superposées, une discipline d'IA comme copilote responsable à toutes les étapes, et une exigence d'humanité intégrale à chacune.

Ce que nous n'avons pas encore traité, c'est la question de fond : **pourquoi cet agencement précis tient-il, plutôt qu'un autre**. La sous-section 4.5, qui clôt la section 4, examinera cette question en mettant les sept invariants de qualité — SOLID, DDD, BDD, TDD, hexagonal, YAGNI, DRY — en correspondance avec les sagesses du monde présentées en section 2 du manifeste. Cette mise en correspondance révélera que la cohérence du pipeline n'est pas accidentelle : elle traduit en pratiques techniques des principes éthiques que des cultures très différentes ont chacune formulés à leur manière. C'est cette continuité entre éthique et technique qui fait la transmissibilité de la méthode.

Mais cette correspondance demande un travail de validation à deux que nous voulons mener avec le calme nécessaire. La sous-section 4.5 sera donc l'objet d'une prochaine version du manifeste.

---

## 4.5 — Pourquoi ça tient : les invariants comme traductions des sagesses

### 4.5.1 — Le pari de cette sous-section conclusive

Les quatre sous-sections précédentes ont raconté l'émergence et la convergence de la Méthode Maury, et elles ont décrit son pipeline opérationnel. Ce qui n'a pas encore été examiné, c'est la question de fond : pourquoi cet agencement précis tient-il, plutôt qu'un autre. Pourquoi les sept invariants techniques que nous respectons — SOLID, DDD, BDD, TDD, hexagonal, YAGNI, DRY — sont-ils ceux-là, et pas d'autres choisis arbitrairement parmi les centaines de pratiques recensées dans la littérature de l'ingénierie logicielle.

Notre réponse à cette question prend la forme d'une thèse que nous voulons formuler avec prudence parce qu'elle est forte. Les sept invariants techniques que nous respectons ne sont pas des règles arbitraires. Ils sont les **traductions opérationnelles**, dans le langage de l'ingénierie logicielle, de principes éthiques qui ont été formulés par des cultures très différentes les unes des autres, à des époques très différentes, dans des langues très différentes — et qui se rejoignent sur ce que nous pourrions appeler des **invariants anthropologiques** de ce qu'est une activité collective bien faite.

Cette thèse n'est pas une justification décorative ajoutée après coup. Elle est, au contraire, ce qui permet de comprendre pourquoi la Méthode Maury est transmissible. Si nos invariants techniques traduisaient des préférences contingentes, ils ne se laisseraient transmettre qu'aux personnes qui partagent ces préférences. Mais s'ils traduisent des principes anthropologiques universels, alors ils peuvent être appropriés par des praticiens venus de toutes traditions, à condition que chacun les retrouve dans la sagesse qui lui est familière.

Examinons donc les sept correspondances une par une, en montrant pour chacune ce qui justifie le rapprochement plutôt qu'en plaquant des images.

### 4.5.2 — SOLID et l'écologie des savoirs

**Le principe SOLID en ingénierie.** Les cinq principes SOLID — *Single Responsibility, Open/Closed, Liskov Substitution, Interface Segregation, Dependency Inversion* — formulés par Robert C. Martin à partir de travaux antérieurs de Bertrand Meyer et Barbara Liskov, énoncent que chaque entité de code devrait avoir une responsabilité unique, être ouverte à l'extension mais fermée à la modification, respecter ses contrats d'héritage, exposer des interfaces ciblées plutôt que monolithiques, et dépendre d'abstractions plutôt que d'implémentations concrètes. Le fil conducteur de ces cinq principes est le **refus de la concentration** : refus du *god object* qui ferait tout, refus de la classe omnipotente, refus du module qui devient indispensable à tous les autres.

**L'écologie des savoirs chez Santos.** Boaventura de Sousa Santos décrit la *monoculture du savoir scientifique rigoureux* comme l'une des cinq monocultures qui produisent l'épistémicide contemporain. À cette monoculture, il oppose une *écologie des savoirs* qui reconnaît la légitimité de plusieurs traditions de connaissance, sans les hiérarchiser a priori et sans en privilégier une seule comme arbitre des autres. Le fil conducteur est le **refus de la concentration épistémique** : refus de la science occidentale comme seul savoir légitime, refus de l'expertise unique qui jugerait toutes les autres, refus de la voix qui prétendrait parler pour toutes les autres.

**Pourquoi la correspondance tient.** Les deux principes traduisent la même intuition à des échelles différentes. À l'échelle du code, SOLID dit que la concentration de responsabilités dans une seule entité produit de la fragilité, de la rigidité et de la dette. À l'échelle des savoirs, l'écologie des savoirs dit que la concentration de la légitimité épistémique dans une seule tradition produit de la fragilité, de la rigidité et de l'épistémicide. Ce qui est en jeu dans les deux cas, c'est la **distribution des responsabilités** comme condition de la résilience.

**Ce que cela change opérationnellement.** Un développeur qui pratique SOLID parce qu'il y voit la traduction de l'écologie des savoirs ne pratique pas SOLID de la même manière qu'un développeur qui le pratique par discipline technique abstraite. Le premier comprend pourquoi la règle existe — parce que toute concentration finit par devenir oppressive — et il sait quand la transgresser légitimement. Le second l'applique mécaniquement et risque de la transformer en bureaucratie. La traduction donne le sens, et le sens donne le jugement.

### 4.5.3 — DDD et Ubuntu

**Le principe du Domain-Driven Design.** Le DDD, formulé par Eric Evans, propose de placer le domaine métier au cœur de la conception logicielle et d'établir un *langage ubiquitaire* commun entre développeurs et experts métier. Il introduit des concepts comme les *bounded contexts* (qui délimitent les zones de cohérence sémantique), les *aggregates* (qui regroupent des entités liées par des invariants), et les *value objects* (qui n'ont d'identité que par leurs attributs et leurs relations). Le fil conducteur est l'idée qu'un concept métier **n'existe pas en isolation** — il existe par les relations qu'il entretient avec les autres concepts du même contexte borné.

**Le principe Ubuntu.** L'expression Ubuntu, qui vient du nguni en Afrique australe, est souvent traduite par la formule *"Je suis parce que nous sommes"* (umuntu ngumuntu ngabantu en zulu). Elle désigne une ontologie relationnelle dans laquelle une personne n'a d'existence pleine que par ses relations avec les autres personnes de sa communauté. Cette intuition philosophique a été développée par des penseurs sud-africains comme Desmond Tutu et a influencé profondément la transition post-apartheid. Le fil conducteur est l'idée qu'**une entité n'a d'existence que par ses relations** — elle n'est pas d'abord un atome qui entrerait ensuite en relation, elle est dès l'origine ce que ses relations font d'elle.

**Pourquoi la correspondance tient.** Les deux principes énoncent la même thèse ontologique à des échelles différentes. À l'échelle du domaine logiciel, le DDD dit qu'une entité métier comme *Copropriétaire* n'a pas de sens en dehors de ses relations avec *Bâtiment*, *Lot*, *Tantième*, *Assemblée générale* — elle n'existe que dans la trame de ces relations. À l'échelle anthropologique, Ubuntu dit qu'une personne n'a pas de sens en dehors de ses relations avec sa famille, sa communauté, ses ancêtres, ses descendants. Dans les deux cas, ce qui est rejeté, c'est l'**atomisme** — l'idée qu'on pourrait commencer par définir des entités isolées et ajouter ensuite leurs relations comme des propriétés secondaires.

**Ce que cela change opérationnellement.** Un développeur qui pratique le DDD parce qu'il y voit la traduction d'Ubuntu modélise son domaine en commençant par les relations et non par les entités. Il refuse de créer une classe *Copropriétaire* sans l'avoir d'abord pensée comme participant à plusieurs *bounded contexts* — celui de la propriété, celui de l'AG, celui des charges, celui de la communauté. Cette posture relationnelle dès la conception évite l'écueil classique des modèles de domaine qui empilent des attributs sur des entités isolées et qui perdent la cohérence à mesure que le système grandit.

### 4.5.4 — BDD et la documentation vivante comme bien commun

**Le principe du Behavior-Driven Development.** Le BDD, formulé par Dan North à partir des travaux sur le TDD, propose d'écrire les spécifications fonctionnelles d'un système sous forme de scénarios exécutables exprimés dans une syntaxe lisible par des non-développeurs (typiquement Gherkin avec ses *Given/When/Then*). Ces scénarios servent simultanément de spécifications, de tests automatisés et de documentation vivante du système. Le fil conducteur est l'idée que **le savoir métier doit être partagé** entre tous les acteurs du projet, et que ce partage doit être inscrit dans des artefacts qui restent à jour automatiquement.

**Le partage du savoir comme principe transversal.** Le BDD ne correspond pas à une seule sagesse particulière mais à un principe que plusieurs traditions formulent à leur manière. Ubuntu déjà, parce que le savoir n'est pas la propriété d'un individu mais la production d'une communauté. Mottainai aussi, parce que laisser le savoir métier dans la tête d'une seule personne est un gâchis qui produit de la dette quand cette personne quitte le projet. Et les sept générations de la confédération Haudenosaunee, parce que le savoir doit être transmissible aux générations futures qui ne pourront pas interroger les ancêtres.

**Pourquoi la correspondance tient.** Le BDD est une réponse pratique à la question : comment éviter que le savoir métier se concentre dans quelques têtes et disparaisse avec elles. Cette question est exactement celle que posent les traditions communautaires et transgénérationnelles. Un scénario Gherkin est, à sa manière, un acte de partage et de transmission — il met en commun ce qui sans lui resterait privé.

**Ce que cela change opérationnellement.** Un développeur qui pratique le BDD parce qu'il y voit la traduction de la transmission communautaire écrit ses scénarios pour les non-développeurs et non pour la machine. Il les rend lisibles par l'expert métier, par la copropriétaire bénévole, par l'auditrice de la BCT, par le développeur qui rejoindra l'équipe dans cinq ans. Cette discipline de lisibilité transforme le BDD d'un outil de test en un outil de souveraineté collective sur le système.

### 4.5.5 — TDD et les sept générations

**Le principe du Test-Driven Development.** Le TDD, formulé par Kent Beck dans le cadre de l'eXtreme Programming, propose d'écrire le test avant le code qu'il valide, dans un cycle court : red (test qui échoue), green (code minimum qui fait passer le test), refactor (amélioration du code en gardant les tests verts). Au-delà de cette mécanique, le TDD produit une accumulation de tests qui survivent au code initial et qui protègent toutes les évolutions futures. Le fil conducteur est l'idée que **les anciens tests survivent et protègent les futurs développements** — ils incarnent une mémoire opérationnelle du système qui ne peut pas être perdue.

**Le principe des sept générations.** Le principe des sept générations vient de la *Great Law of Peace* de la confédération Haudenosaunee (Iroquoise) et énonce que toute décision importante doit prendre en compte ses conséquences sur les sept générations à venir. C'est une discipline de **responsabilité transgénérationnelle** : on ne décide pas seulement pour soi, on décide pour ceux qui n'existent pas encore et qui ne pourront pas voter. Cette intuition, formulée plusieurs siècles avant les théories contemporaines du développement durable, anticipe ce que nous appelons aujourd'hui la justice intergénérationnelle.

**Pourquoi la correspondance tient.** Le TDD est une discipline transgénérationnelle à l'échelle du code. Quand un développeur écrit un test aujourd'hui, ce test sera là dans cinq ans, dans dix ans, peut-être dans trente ans. Il protégera des développeurs qui ne sont pas nés à la profession quand le test a été écrit. Il évitera qu'une régression ne casse silencieusement une fonctionnalité que personne ne sait plus expliquer. Cette discipline traduit, à l'échelle d'un projet logiciel, exactement ce que les sept générations énoncent à l'échelle d'une civilisation : prendre soin de ceux qui viendront après nous, en leur transmettant des fondations qui tiennent.

**Ce que cela change opérationnellement.** Un développeur qui pratique le TDD parce qu'il y voit la traduction des sept générations ne le pratique pas pour atteindre un taux de couverture chiffré — il le pratique pour léguer un système qui se défend contre la dérive future. Cette posture change la nature des tests qu'il écrit. Il privilégie les tests qui expriment des invariants métier sur les tests qui valident des détails d'implémentation. Il préfère vingt tests bien choisis qui survivront au code, à deux cents tests fragiles qui devront être réécrits à chaque refactoring.

### 4.5.6 — Hexagonal et l'écologie des échelles

**Le principe de l'architecture hexagonale.** L'architecture hexagonale, formulée par Alistair Cockburn, propose de séparer le cœur métier d'une application des adaptateurs qui le connectent au monde extérieur (bases de données, interfaces utilisateur, services tiers, files de messages). Le métier ne dépend de personne, les adaptateurs implémentent des interfaces (les *ports*) définies par le métier. Le fil conducteur est l'idée que **le local et le global doivent cohabiter sans se confondre** — le métier reste local et stable, le monde extérieur change et se diversifie.

**L'écologie des échelles chez Santos, et le kaitiakitanga maori.** Santos décrit la *monoculture de l'échelle universelle* comme l'une des cinq monocultures de l'épistémicide. Cette monoculture privilégie l'universel au détriment du local et considère le local comme particulier, anecdotique, sans valeur générale. À cette monoculture, il oppose une *écologie des échelles* qui reconnaît que le local et le global ont chacun leur légitimité. Le concept maori de *kaitiakitanga* — la responsabilité d'être gardien d'un territoire spécifique tout en étant relié au monde plus large — exprime concrètement cette articulation : on n'est pas responsable du monde abstrait, on est responsable d'un lieu précis, et c'est par cette responsabilité située qu'on participe à une responsabilité plus large.

**Pourquoi la correspondance tient.** L'architecture hexagonale est une écologie des échelles à l'échelle du logiciel. Le cœur métier — qui correspond au local, à la spécificité du domaine — est protégé des changements d'infrastructure — qui correspondent au global, à ce qui change indépendamment de notre projet. Mais les deux cohabitent dans la même application, articulés par des ports qui respectent l'autonomie de chaque échelle. C'est rigoureusement ce que prônent Santos et le kaitiakitanga : ni la dissolution du local dans le global, ni la fermeture du local sur lui-même, mais l'articulation respectueuse des deux.

**Ce que cela change opérationnellement.** Un développeur qui pratique l'hexagonale parce qu'il y voit la traduction de l'écologie des échelles tient à la stabilité du domaine quand l'infrastructure change. Quand la base de données passe de PostgreSQL à autre chose, quand le framework HTTP est remplacé, quand l'interface utilisateur est refondue, le cœur métier ne bouge pas. Cette stabilité est ce qui permet à un projet de durer trente ans malgré les cycles de mode technologique. Et elle est aussi ce qui permet aux contextes locaux — la copropriété belge, le banking tunisien, l'école d'Evere — de garder leur spécificité sans être balayés par la prochaine vague d'industrialisation.

### 4.5.7 — YAGNI et Mottainai

**Le principe YAGNI.** YAGNI, *You Aren't Gonna Need It*, est un principe d'eXtreme Programming énoncé par Ron Jeffries qui dit qu'il ne faut pas écrire de code spéculatif pour des besoins futurs hypothétiques. On code ce dont on a besoin maintenant, exactement ce dont on a besoin maintenant, et on ajoute le reste si et quand le besoin se présentera réellement. Le fil conducteur est le **refus du gaspillage spéculatif** — ne pas produire ce qui ne servira peut-être jamais.

**Le principe Mottainai.** Mottainai (もったいない) est une expression japonaise qui mêle le bouddhisme zen et le shintoïsme, et qui exprime un sentiment de **regret face au gaspillage** — de nourriture, de matière, de ressources, mais aussi de potentiel non actualisé. Une chose mottainai est une chose qui mérite plus de respect que ce qu'on lui accorde, qu'on ne devrait pas jeter, qu'on devrait utiliser pleinement avant de s'en débarrasser. Cette sensibilité a influencé profondément les pratiques japonaises de réparation, de réutilisation et de soin des objets.

**Pourquoi la correspondance tient.** YAGNI est mottainai appliqué au code. Le code spéculatif est un gaspillage : il consomme du temps de développement, des appels à l'IA, de l'énergie de serveur, de l'attention de relecture, de la mémoire collective de l'équipe — tout cela pour quelque chose qui n'a peut-être pas de raison d'exister. Mottainai dit qu'il faudrait ressentir un regret face à ce gaspillage. YAGNI traduit ce regret en règle opérationnelle : ne produis pas ce dont tu n'as pas besoin maintenant, parce que ce sera très probablement perdu.

**Ce que cela change opérationnellement.** Un développeur qui pratique YAGNI parce qu'il y voit la traduction de mottainai n'est pas paresseux — il est attentif à la valeur de ce qu'il produit. Il préfère ajouter une fonctionnalité quand elle est demandée plutôt que de l'anticiper, parce qu'il sait que l'anticipation produit en moyenne plus de code mort que de code utile. Cette posture est aussi écologique au sens fort : moins de code spéculatif, c'est moins de tokens IA consommés, moins de tests à maintenir, moins de surface d'attaque sécurité, moins de poids dans le binaire compilé.

### 4.5.8 — DRY et l'écologie des productivités

**Le principe DRY.** DRY, *Don't Repeat Yourself*, est un principe formulé par Andy Hunt et Dave Thomas dans *The Pragmatic Programmer*. Il énonce que toute pièce de connaissance dans un système doit avoir une seule représentation autoritative et non ambiguë. Si une règle métier est codée à plusieurs endroits, elle finira par diverger, et la divergence produira des bugs. Le fil conducteur est l'idée qu'il faut **factoriser plutôt que dupliquer** — reconnaître les similarités et les exprimer une seule fois.

**L'écologie des productivités chez Santos.** Santos décrit la *monoculture de la productivité capitaliste* comme l'une des cinq monocultures de l'épistémicide. Cette monoculture mesure tout selon un critère unique — le rendement marchand — et produit comme non-existence tout ce qui ne rentre pas dans cette mesure. À cette monoculture, il oppose une *écologie des productivités* qui reconnaît plusieurs formes de production de valeur — économique, écologique, communautaire, symbolique — et qui refuse de les réduire à une seule.

**Pourquoi la correspondance tient.** Cette correspondance est probablement la plus subtile des sept et mérite qu'on s'y arrête. DRY semble être une règle purement technique d'économie de code, et l'écologie des productivités semble être une thèse philosophique sur la pluralité des valeurs. Le rapprochement tient pourtant à un point précis : DRY refuse l'**extraction répétitive** de la même connaissance dans plusieurs endroits. Dupliquer une règle métier, c'est extraire la même valeur plusieurs fois pour des produits qui finissent par se contredire. Factoriser, c'est reconnaître que la valeur est unique et qu'elle mérite d'être inscrite une fois pour toutes, comme un bien commun du système.

L'écologie des productivités fait le même geste à l'échelle économique : elle refuse l'extraction répétitive de la même ressource — naturelle, humaine, communautaire — par plusieurs acteurs qui finissent par épuiser ce qu'ils prétendent valoriser. Elle préfère reconnaître la valeur multiple d'une ressource et organiser sa préservation comme bien commun.

**Ce que cela change opérationnellement.** Un développeur qui pratique DRY parce qu'il y voit la traduction de l'écologie des productivités refuse de copier-coller une règle métier en se disant qu'il refactorisera plus tard. Il sait que cette copie produira de la divergence, et que la divergence produira des bugs qui consommeront du temps humain pour être corrigés — exactement comme l'extraction répétitive d'une ressource produit son épuisement et coûte ensuite à réparer. La factorisation est une discipline de soin, pas seulement une optimisation technique.

### 4.5.9 — Le tableau de synthèse

Pour permettre au lecteur de tenir l'ensemble des correspondances en mémoire, ce tableau les récapitule en format condensé.

| Invariant technique | Sagesse / Écologie correspondante | Principe partagé |
|---|---|---|
| SOLID | Écologie des savoirs (Santos) | Refus de la concentration (de responsabilités, d'autorité épistémique) |
| DDD | Ubuntu (Afrique australe) | Une entité n'existe que par ses relations |
| BDD | Documentation vivante (transversal : Ubuntu, mottainai, sept générations) | Le savoir est partagé, transmissible, préservé du gaspillage |
| TDD | Sept générations (Haudenosaunee) | Responsabilité transgénérationnelle, soin pour ceux qui viendront |
| Hexagonal | Écologie des échelles (Santos) et kaitiakitanga (maori) | Articulation respectueuse du local et du global |
| YAGNI | Mottainai (Japon) | Refus du gaspillage spéculatif |
| DRY | Écologie des productivités (Santos) | Refus de l'extraction répétitive, préservation comme bien commun |

### 4.5.10 — Ce que ces correspondances démontrent

Ces sept correspondances ne sont pas des analogies décoratives. Elles démontrent quelque chose de précis sur la nature de l'ingénierie logicielle bien faite.

**Premièrement**, elles montrent que les principes techniques que nous respectons ne sont pas arbitraires. Ils traduisent dans le langage du code des intuitions anthropologiques que des cultures humaines très différentes ont chacune formulées à leur manière. Cette convergence est de même nature que celle observée en sous-section 4.3 entre KoproGo et BANKO : différents accès locaux à des principes universels qui répondent à des problèmes humains communs. La Méthode Maury n'invente pas ces principes — elle les retrouve, les nomme, les articule.

**Deuxièmement**, elles donnent à la Méthode Maury sa **transmissibilité interculturelle**. Un développeur formé dans la tradition européenne du software craftsmanship trouvera les correspondances avec les écologies de Santos enrichissantes. Un développeur formé dans une tradition africaine trouvera Ubuntu comme racine de DDD éclairant. Une développeuse japonaise trouvera mottainai comme racine de YAGNI naturel. Chacun peut s'approprier la méthode depuis sa propre tradition, sans avoir à abandonner ce qui lui est familier pour adopter une grille étrangère.

**Troisièmement**, elles donnent au manifeste sa **cohérence interne**. La section 1 a énoncé un constat sur ce qui ne va pas dans le numérique d'aujourd'hui. La section 2, encore en stub, présentera les sources philosophiques sur lesquelles nous nous appuyons. La section 3 a posé sept convictions. La section 4, qui se termine ici, a montré comment ces convictions se traduisent en pratique technique articulée. La cohérence entre ces sections n'est pas affirmée — elle est démontrée par la chaîne de traductions qui relie les sagesses du monde aux invariants techniques en passant par les choix architecturaux observés sur KoproGo, BANKO et leur convergence.

**Quatrièmement**, elles ouvrent la possibilité d'un travail à venir. Les sept correspondances proposées ici ne sont pas exhaustives. D'autres traditions, d'autres principes techniques pourraient être mis en correspondance. Une autrice formée dans la tradition andine pourrait proposer une lecture du *sumak kawsay* comme racine de la sobriété logicielle. Un auteur formé dans la tradition franciscaine pourrait proposer une lecture du *Cantique des créatures* comme racine de l'attention écologique du code. Ce travail nous dépasse et nous l'appelons de nos vœux. La Méthode Maury n'est pas close — elle est une matrice qui demande à être enrichie par d'autres apports.

### 4.5.11 — Bilan général de la section 4 : l'arc complet de la Méthode Maury

Cette sous-section 4.5 referme la section 4 entière. Faisons le bilan de l'arc complet pour que le lecteur puisse en saisir l'unité.

La sous-section **4.0** a posé l'agencement de la section et expliqué pourquoi elle était structurée explicitement.

La sous-section **4.1** a raconté l'émergence ascendante de KoproGo — du droit belge concret de la copropriété vers une architecture, puis une méthode, puis une thèse en quatre temps sur la maturation de l'extractivisme PropTech. Elle a aussi formulé l'articulation TOGAF/agile en écologie des savoirs et a proposé le parallèle de la révolution industrielle pour comprendre l'IA comme paradigm shift.

La sous-section **4.2** a raconté la maturation descendante de BANKO — d'une rencontre humaine triangulaire avec une experte fintech tunisienne vers la matérialisation d'une vision de souveraineté pour le banking tunisien, en s'inscrivant dans la filiation du mouvement open source de la fintech (Apache Fineract, Mojaloop, OpenBank Project). Elle a aussi documenté la frugalité de prompt acquise comme maturation méthodologique mesurable.

La sous-section **4.3** a démontré la convergence des deux récits sur sept couches architecturales communes (Domain, Application, Infrastructure backend, Frontend, IaC, CI/CD, Monitoring et Sécurité), prouvant ainsi que la Méthode Maury est une matrice transposable plutôt qu'une recette particulière.

La sous-section **4.4** a présenté in extenso le pipeline méthodologique articulant TOGAF, BMAD, Scrum, Nexus, SAFe essentiel et ITIL, avec l'IA comme copilote responsable à toutes les étapes — accélératrice de mise en forme, accoucheuse socratique des pratiques tacites, sans jamais porter la responsabilité finale qui reste intégralement humaine.

La sous-section **4.5** vient de montrer que les sept invariants techniques que nous respectons traduisent en pratique des principes éthiques que des cultures humaines très différentes ont chacune formulés à leur manière, ce qui donne à la méthode sa transmissibilité interculturelle et sa cohérence interne.

Cet arc complet — émergence, maturation, convergence, pipeline, justification — constitue ce que nous voulions transmettre comme contribution méthodologique. Il reste maintenant au lecteur à se l'approprier, à le critiquer, à le prolonger.

Les sections suivantes du manifeste — la section 2 sur les sources, la section 5 sur les projets concrets, la section 6 sur l'invitation à reprendre — viendront accompagner cette section 4 dans des versions futures. Elles ne contredisent pas la complétude de l'arc présenté ici. Elles l'ancrent dans des contextes précis et l'ouvrent à des appropriations multiples.

---

# Section 5 — Nos projets

## 5.0 — Note préliminaire

Cette section présente nos projets concrets comme **preuves vivantes** de la méthode décrite en section 4. Elle est volontairement courte et factuelle. Les détails philosophiques et architecturaux figurent en section 4 ; les sources philosophiques sur lesquelles nous nous appuyons figurent en section 2. Cette section 5 a une fonction différente : elle donne au lecteur les liens, les métriques et les éléments de statut nécessaires pour aller voir par lui-même ce que nous décrivons.

Nous présentons aujourd'hui deux projets : **KoproGo**, notre projet principal sur la copropriété belge, et **BANKO**, notre proposition technique offerte à une partenaire fintech tunisienne. D'autres projets ont existé ou pourront exister dans cette section à l'avenir — par exemple EcoleHub que nous mentionnons dans le manifeste mais qui est aujourd'hui en suspens et n'est plus open source. Cette liste n'est donc ni close ni définitive. Elle reflète l'état actuel de notre engagement public.

## 5.1 — KoproGo

### Statut, cadence, repository

KoproGo est notre projet principal. Il vise à doter la copropriété belge — quatre millions de personnes concernées, plus de la moitié du parc géré par des syndics bénévoles — d'un outil libre, sobre et adapté au droit local. Son contexte philosophique et architectural est développé en sous-sections 4.1.1 à 4.1.7 du manifeste.

Au moment où nous écrivons ces lignes, KoproGo est officiellement au **jalon 0** de sa roadmap par capacités, et la version **v0.1.0** est en préparation dans nos cartons. Nous y consacrons environ **dix heures par semaine**.

- **Dépôt GitHub** : [https://github.com/gilmry/koprogo](https://github.com/gilmry/koprogo)
- **Chaîne YouTube** : [https://youtube.com/@koprogo](https://youtube.com/@koprogo) — *"Un projet pour réinventer l'habitat collectif"*
- **Licence** : AGPL-3.0
- **Langues principales** : Rust (backend), TypeScript et Svelte (frontend), Gherkin (scénarios BDD)

### Stack technique en synthèse

| Couche | Choix |
|---|---|
| Backend | Rust + Actix-web 4.9 |
| Persistance | PostgreSQL 15 + SQLx 0.8 |
| Frontend | Astro 4 + Svelte (architecture islands) |
| Infrastructure | Terraform + Ansible sur OVH France, Docker, Traefik |
| Sécurité | LUKS at-rest, GPG backups S3, CrowdSec, Suricata, fail2ban, audits Lynis/rkhunter/AIDE |
| Observabilité | Prometheus + Grafana + Loki + Alertmanager |
| CI/CD | GitHub Actions, hooks Git, cargo audit, clippy, Tarpaulin coverage |
| Tests | Pyramide complète : unitaires, intégration (testcontainers), BDD Cucumber, E2E Playwright, load wrk2, benchmarks Criterion |

### Métriques publiques vérifiables

Les métriques suivantes sont publiées sur le dépôt et reproductibles par quiconque veut les vérifier :

- **Performance mesurée** : 287 requêtes par seconde soutenues sur un seul vCPU avec 2 Go de RAM, sur trois minutes de test de charge wrk2
- **Latence** : médiane 69 ms, P99 752 ms
- **Taux de succès** sous charge : 99,74 % (47 681 requêtes, 125 erreurs)
- **Empreinte carbone mesurée** : 0,12 g CO₂ par requête, contre un objectif annoncé de moins de 0,5 g
- **Empreinte mémoire** : 128 Mo maximum, sans recours au swap

Ces chiffres ne sont ni des projections ni des arguments commerciaux. Ils sont le résultat de tests reproductibles, et nous les publions en sachant que d'autres projets afficheront mieux sur certains axes. Notre intention n'est pas de les battre — c'est de mettre en circulation des ordres de grandeur honnêtes auxquels d'autres puissent se confronter.

### Le paradoxe apparent code/jalon : une démonstration vivante de la méthode

KoproGo se prête à un paradoxe apparent que nous voulons nommer explicitement, parce qu'il illustre concrètement ce que la sous-section 4.1.6 explique théoriquement.

Le code de KoproGo est **substantiellement avancé**. Architecture hexagonale stricte avec séparation domain/application/infrastructure, plus de deux cents scénarios BDD, des entités métier qui encodent directement le droit belge de la copropriété (articles 3.84 et suivants du Code civil, règles de quorum, tantièmes, procurations, conseil de copropriété pour les immeubles de plus de vingt lots), une stack de sécurité qui dépasse l'état de l'art habituel pour un projet de cette taille, une documentation Sphinx publiée. Plusieurs revues de code automatisées, dont nous parlerons ci-dessous, l'ont noté.

Pourtant, **le jalon officiel reste à 0**. Cette dissociation entre l'avancement du code et le franchissement de capacité n'est ni une contradiction ni une coquetterie. Elle est précisément ce que la roadmap par capacités produit. Le jalon 0 ne sera officiellement franchi que quand l'ensemble des conditions seront réunies : le code, mais aussi l'organisation qui le porte (l'ASBL en cours de constitution), la gouvernance qui le pilote, l'impact écologique mesuré dans des conditions d'usage réel, l'écosystème qui l'accueille (premières copropriétés volontaires, partenaires institutionnels, juristes consultés), la conformité juridique pleinement vérifiée. Tant que ces dimensions ne sont pas alignées, le code peut prendre de l'avance sans pour autant déclarer la capacité disponible.

Cette discipline a un coût immédiat — elle impose une humilité affichée sur l'état réel du projet, là où d'autres affichent des roadmaps optimistes. Elle a aussi un bénéfice de long terme considérable : elle empêche le projet de devenir hors-sol et elle prépare les conditions de son adoption durable. KoproGo, à son rythme, illustre la méthode plutôt qu'il ne contredit son discours.

### Le dispositif de revue de code croisée par quatre IA

Pour garantir la qualité du code dans une cadence contrainte (dix heures par semaine, sans équipe dédiée à la relecture), nous avons mis en place un dispositif que nous appelons une **revue de code croisée par quatre intelligences artificielles**. Le code de KoproGo a été soumis à quatre modèles différents — ChatGPT, Grok, Gemini et Claude — pour analyse indépendante de son architecture, de sa qualité, de sa rigueur méthodologique et de sa compréhension du domaine métier.

Ce dispositif n'est pas un audit au sens professionnel strict du terme. Il ne remplace ni un audit ISO 27001, ni une revue par des pairs humains, ni un test de pénétration mené par une équipe spécialisée. Il est une **démarche de validation croisée** qui s'inscrit naturellement dans la méthode du manifeste : si l'IA est un copilote responsable à toutes les étapes du pipeline (sous-section 4.4), alors elle peut aussi être mobilisée comme dispositif de relecture, à condition que ses verdicts soient eux-mêmes validés par l'humain et qu'aucun d'eux ne soit accepté comme parole d'autorité.

L'intérêt de croiser quatre modèles plutôt qu'un seul est précisément l'**écologie des savoirs** appliquée à la relecture algorithmique. Quatre modèles entraînés différemment sur des corpus différents par des équipes différentes ne hallucinent pas aux mêmes endroits, ne valorisent pas les mêmes aspects, ne ratent pas les mêmes problèmes. Leurs convergences renforcent la confiance, leurs divergences alertent sur des points qui méritent une délibération humaine spécifique.

Cette démarche est cohérente avec ce que la sous-section 4.4 énonce comme principe fondamental : l'IA propose, l'humain dispose. Quatre IA proposent quatre angles. L'humain — ici, principalement Gilles avec la relecture critique de Farah — décide ce qui est repris, écarté, approfondi.

## 5.2 — BANKO

### Statut, cadence, repository

BANKO est notre proposition technique offerte à une partenaire fintech tunisienne. Son contexte est développé en sous-section 4.2 du manifeste, notamment la configuration relationnelle triangulaire entre cette partenaire, Farah qui a fait le pont, et Gilles qui a apporté la capacité d'exécution architecturale.

BANKO est aujourd'hui en **early stage**, avec une progression douce. Nous y consacrons au maximum **cinq heures par semaine**. Le projet n'est pas en suspens au sens d'une pause complète — il avance — mais sa cadence est volontairement modérée parce que son statut est celui d'une **proposition technique offerte**, dont l'évolution dépend autant de la dynamique de notre partenaire que de notre propre disponibilité.

- **Dépôt GitHub** : [https://github.com/gilmry/BANKO](https://github.com/gilmry/BANKO)
- **Licence** : AGPL-3.0
- **Statut au commit count actuel** : environ 112 commits

### Stack technique en synthèse

BANKO réutilise la même stack technique que KoproGo, en démontrant que les choix architecturaux ne sont pas accidentels mais transposables (la sous-section 4.3 traite cette convergence en détail).

| Couche | Choix |
|---|---|
| Backend | Rust + Actix-web 4.9 organisé en Cargo workspace : *crates/domain*, *crates/application*, *crates/infrastructure* |
| Persistance | PostgreSQL + SQLx 0.8, avec rust_decimal pour les calculs monétaires précis et sha2 pour les signatures cryptographiques de la piste d'audit |
| Référentiel juridique | Treize textes réglementaires tunisiens et internationaux explicitement traçables depuis le code (loi bancaire 2016, sept circulaires BCT, deux lois anti-blanchiment, loi sur les données personnelles, normes comptables NCT, standards Bâle III, GAFI, ISO 20022 et 27001) |
| Hébergement prévu | Localement en Tunisie, conformité INPDP, cohérent avec l'exigence de souveraineté |

### Une dimension d'offre, pas un produit en course

Il faut nommer explicitement ce que BANKO est et ce qu'il n'est pas. BANKO n'est pas un produit que nous cherchons à imposer dans le secteur bancaire tunisien. Il n'est pas un MVP en course commerciale. Il n'est pas un actif que nous valorisons pour notre portefeuille. Il est une **proposition technique offerte** à une experte fintech qui porte une vision lucide des besoins du système bancaire de son pays, et qui pourra ou non choisir de la mobiliser dans ses propres démarches.

Cette posture d'offre, plutôt que de course, est cohérente avec ce que le manifeste défend depuis le début. Nous ne construisons pas BANKO contre Temenos ou Finastra. Nous ne construisons pas BANKO pour nous installer sur le marché bancaire tunisien — nous n'en avons ni la légitimité culturelle, ni la connaissance fine du contexte local, ni l'envie. Nous construisons BANKO pour que notre partenaire, et au-delà d'elle l'écosystème fintech open source international, dispose d'un point de référence supplémentaire qui démontre qu'une alternative souveraine, conforme et techniquement solide est possible avec une stack moderne et sobre.

Cette posture explique aussi la cadence modérée. Cinq heures par semaine sur une proposition offerte n'est pas le rythme d'un produit en compétition. C'est le rythme d'un **don méthodologique** dont la valeur réside dans la qualité de ce qui est offert plutôt que dans la rapidité de sa diffusion.

## 5.3 — Une note sur la liste

Cette liste de deux projets n'est pas exhaustive. Elle reflète l'état actuel de notre engagement public à dimension open source. Plusieurs projets ont existé dans notre parcours et n'apparaissent pas ici — soit parce qu'ils sont en suspens, soit parce qu'ils ne sont plus libres, soit parce qu'ils relèvent du cadre professionnel non-publiable. EcoleHub, mentionné en préambule du manifeste comme l'un des projets que nous avons construits pour notre fils et l'école d'Evere, en fait partie aujourd'hui — il est en suspens et n'est plus open source.

Cette section 5 s'enrichira à mesure que de nouveaux projets atteindront la maturité publique nécessaire pour y figurer. La progression organique par capacités s'applique aussi au manifeste lui-même : nous ne mentionnerons pas un projet ici tant que l'ensemble des conditions ne sont pas réunies pour qu'il y soit honnêtement présenté.

---

# Section 6 — Reprenez ce qui vous sert

## 6.1 — Une invitation, pas un appel

Ce manifeste n'est ni un programme à signer, ni une communauté à rejoindre, ni une certification à acquérir. Il n'a pas de membres et il n'en aura pas. Il ne demande aucune adhésion. Il ne réclame aucune fidélité. Il ne distribue aucun titre.

Ce qu'il propose est plus modeste et plus exigeant à la fois : un ensemble de principes, de pratiques et de preuves vivantes que nous mettons à disposition de qui voudra s'en servir. **Reprenez ce qui vous sert. Laissez le reste. Contestez ce qui vous semble faux.** Si une de nos convictions résonne avec votre pratique, prenez-la — vous n'avez pas à nous citer, et vous n'avez surtout pas à nous attendre. Si une autre vous semble erronée ou mal formulée, dites-le-nous publiquement ou en privé, nous tâcherons d'écouter sérieusement.

Cette posture n'est pas de la fausse modestie. Elle est cohérente avec ce que tout le manifeste a défendu : l'écologie des savoirs au sens de Boaventura de Sousa Santos refuse qu'une tradition prétende parler pour toutes les autres. Ce manifeste est l'expression située de notre pratique à un moment donné, dans un contexte donné, depuis Bruxelles, à deux. Il n'a pas vocation à se substituer à votre propre pratique située, dans votre contexte, à votre rythme. Il a vocation à dialoguer avec elle.

## 6.2 — Comment contribuer

Le manifeste vit comme dépôt GitHub à l'adresse [`github.com/gilmry/manifest`](https://github.com/gilmry/manifest). Vous pouvez interagir avec lui par les mécanismes habituels de la collaboration open source.

**Pour signaler une erreur factuelle, une coquille, une imprécision sur une source citée ou un lien cassé**, ouvrez une *issue* avec le label `correction`. Nous traiterons ces signalements comme prioritaires, parce qu'un manifeste qui invoque la transmission ne peut pas se permettre d'erreurs factuelles non corrigées.

**Pour proposer une critique de fond, un désaccord argumenté, une contre-proposition ou un ajout substantiel**, ouvrez une *issue* avec le label `discussion`. Nous tenons à ce que les désaccords sérieux trouvent leur place visible plutôt que d'être étouffés ou réservés à des échanges privés. Une critique publique bien formulée nous est plus utile qu'un compliment privé.

**Pour proposer une correction directe ou une amélioration rédactionnelle ponctuelle**, vous pouvez ouvrir une *pull request*. Nous la lirons et nous expliciterons notre décision. Une PR refusée n'est pas une attaque personnelle — c'est un retour qui clarifie ce que le manifeste veut dire et ce qu'il ne veut pas dire.

**Pour engager une discussion plus longue qui ne tient pas dans une issue**, ouvrez une *discussion* GitHub plutôt qu'une issue. Le format se prête mieux aux échanges qui demandent du temps et plusieurs voix.

Nous ne maintenons volontairement pas d'adresse de contact email pour le manifeste. Cette discipline n'est pas une distance — elle vise à ce que les échanges intellectuels qui méritent d'être archivés et consultables le soient effectivement, plutôt que de se perdre dans des fils privés. Nos adresses professionnelles existent pour des contextes où la conversation publique n'est pas appropriée, mais elles ne sont pas le canal naturel pour discuter du manifeste lui-même.

## 6.3 — Liens consolidés

Pour faciliter la navigation, voici les liens vers tout ce que ce manifeste évoque ou produit.

**Le manifeste lui-même**
- Dépôt : [`github.com/gilmry/manifest`](https://github.com/gilmry/manifest)
- Issues et discussions : sur le dépôt ci-dessus
- Suivi de version : section dédiée plus haut dans ce document

**Les projets présentés en section 5**
- KoproGo (copropriété belge) : [`github.com/gilmry/koprogo`](https://github.com/gilmry/koprogo)
- KoproGo, chaîne YouTube : [`youtube.com/@koprogo`](https://youtube.com/@koprogo)
- BANKO (proposition technique fintech tunisienne) : [`github.com/gilmry/BANKO`](https://github.com/gilmry/BANKO)

**Les sources citées en section 2**

Pour les références bibliographiques précises de chacune des sources mobilisées — Mogobe Ramose, Boaventura de Sousa Santos, le Manifeste Agile original, le mouvement Software Craftsmanship, le mouvement du logiciel libre, et toutes les autres — une **bibliographie commentée** sera publiée dans une annexe séparée du dépôt. Cette annexe permettra à un lecteur d'aller lire les textes originaux sans dépendre de notre lecture.

## 6.4 — Licences et caractère vivant du document

**Le code** des projets KoproGo et BANKO est publié sous licence **AGPL-3.0**. Cette licence-vaccin garantit que toute amélioration ou utilisation en service en ligne devra elle-même être publiée sous la même licence, ce qui propage les libertés du logiciel libre dans toutes les œuvres dérivées.

**Le texte du manifeste** est publié sous licence **Creative Commons Attribution-ShareAge 4.0 (CC-BY-SA 4.0)**. Vous pouvez le copier, le distribuer, le traduire, l'adapter, le modifier — y compris pour un usage commercial — à condition de citer son origine et de partager vos versions dérivées sous la même licence. Cette licence est cohérente avec notre invitation : reprenez ce qui vous sert, à condition que vos propres reprises restent disponibles pour d'autres.

**Le manifeste est un document vivant.** Il évoluera. Il se trompera parfois. Il se corrigera. Le suivi de version inclus plus haut dans ce document permet à un lecteur d'identifier précisément ce qui a changé entre deux versions, et donc de tracer la maturation de notre pensée sur la durée. Les versions précédentes restent accessibles via l'historique Git du dépôt — rien n'est effacé, tout est archivé, conformément à ce que nous disons en sous-section 4.5.5 sur la responsabilité transgénérationnelle qui s'applique aussi aux textes que nous écrivons.

Les **annexes** mentionnées en début de manifeste — glossaire technique, bibliographie commentée, mapping ISO 27001, estimation chiffrée d'un projet type, FAQ — seront publiées comme **fichiers séparés** du dépôt à mesure de leur rédaction. Elles ne font pas partie de ce README et leur absence ne le rend pas incomplet. Elles sont des compléments documentaires destinés à des lecteurs spécifiques — un débutant pour le glossaire, un chercheur pour la bibliographie, un RSSI pour le mapping ISO, un dirigeant d'ASBL pour l'estimation, un sceptique pour la FAQ. Quand elles existeront, elles seront liées depuis cette section.

## 6.5 — Pour finir

Si vous êtes arrivé jusqu'ici en lisant le manifeste de bout en bout, vous avez consacré un temps réel à notre travail. Nous vous en remercions sobrement.

Ce que nous espérons que vous emporterez n'est pas une adhésion à la Méthode Maury. C'est plutôt l'idée qu'**une pratique du logiciel à la fois sobre, durable, transmissible et joyeuse est possible**, à condition de la cultiver avec discipline et de la nourrir des sagesses qui nous précèdent. Si cette idée vous accompagne quelques jours après la lecture, nous aurons fait notre travail. Le reste vous appartient.

---

# Annexes — fichiers séparés du dépôt

Les annexes mentionnées en début de manifeste seront publiées comme fichiers séparés du dépôt `github.com/gilmry/manifest` à mesure de leur rédaction. Elles ne font pas partie de ce README. Quand elles existeront, elles seront liées depuis la section 6.4.

Annexes prévues :

- **GLOSSAIRE.md** — Glossaire technique et conceptuel : DDD, TDD, BDD, hexagonal, ASBL, AGPL-3.0, et autres termes techniques ou belges qui peuvent être inconnus du lecteur.
- **BIBLIOGRAPHIE.md** — Bibliographie commentée des sources mobilisées en section 2 : références bibliographiques précises pour Mogobe Ramose, Boaventura de Sousa Santos, le Manifeste Agile, le mouvement Software Craftsmanship, le mouvement du logiciel libre, et les autres traditions citées.
- **MAPPING_ISO_27001.md** — Mapping entre les pratiques de sécurité de KoproGo et BANKO et les contrôles ISO 27001, pour les RSSI qui voudraient évaluer la conformité du dispositif.
- **ESTIMATION_PROJET_TYPE.md** — Estimation chiffrée pour un projet type qui voudrait reprendre la Méthode Maury : ordres de grandeur de durée, de coût, de ressources humaines nécessaires selon la complexité du domaine visé.
- **FAQ.md** — Foire aux questions, qui sera enrichie à mesure que de vraies questions seront posées par des lecteurs sur les issues GitHub.

---

# Suivi de version

| Version | Date | Auteurs | Changements |
|---|---|---|---|
| 0.1 | [À DATER] | Farah & Gilles Maury | Version de travail initiale. Sections 0, 1, 3 rédigées. Section 4.1 rédigée avec deux marqueurs à compléter. Sections 2, 4.2, 4.3, 4.4, 4.5, 5, 6 et annexes en stub. |
| 0.2 | [À DATER] | Farah & Gilles Maury | Ajout de la sous-section 4.2 complète sur BANKO en sept paragraphes parallèles à 4.1. Citation des projets inspirants Apache Fineract, Mojaloop et OpenBank Project. Désignation non-nominative de l'experte fintech tunisienne. Formulation tempérée de l'ambition épistémologique en 4.2.7. |
| 0.3 | [À DATER] | Farah & Gilles Maury | Finalisation de la sous-section 4.1. Marqueur 4.1.5 résolu : récit d'émergence méthodologique avec le constat fondateur de TOGAF (dette technique par couches successives), articulation TOGAF/agile en écologie des savoirs, IA comme paradigm shift comparé à la révolution industrielle avec ses trois conditions simultanées. Marqueur 4.1.6 résolu : inventaire des six modules communautaires avec nuance roadmap, possibilité d'utilisation autonome, ordres de grandeur d'impact, progression organique par jalons de capacité, gate reviews illustrées par les images du suivi médical et du point de sauvegarde. |
| 0.4 | [À DATER] | Farah & Gilles Maury | **Proposition finale.** Rédaction complète de la sous-section 4.3 sur la convergence entre KoproGo et BANKO en onze paragraphes. Examen couche par couche des sept couches techniques communes (Domain, Application, Infrastructure backend, Frontend, IaC, CI/CD, Monitoring et Sécurité). Pour chaque couche : ce qui converge, ce qui diffère légitimement, ce que cela démontre. Tableau de synthèse récapitulatif. Conclusion philosophique sur l'écologie des savoirs au sens de Santos, la transposabilité de la matrice, la validation rétroactive des choix de KoproGo, et l'enseignabilité accrue de la Méthode Maury. Cette version 0.4 clôt l'arc narratif des sous-sections 4.1, 4.2 et 4.3. |
| 0.5 | [À DATER] | Farah & Gilles Maury | Rédaction complète de la sous-section 4.4 sur le pipeline méthodologique in extenso. Présentation des six cadres TOGAF, BMAD, Scrum, Nexus, SAFe essentiel et ITIL avec pour chacun sa fonction, son échelle temporelle, ses cérémonies, ses artefacts, ses invariants de qualité, le rôle de l'humain et le rôle de l'IA comme copilote. Tableau d'alignement des cérémonies. Articulation transversale de l'IA comme accélérateur de mise en forme, accoucheuse socratique des pratiques tacites et copilote sans responsabilité finale. Précision sur le double rôle de l'humain (premier et dernier mot) et la frugalité de prompt comme discipline d'écriture. Pont vers la sous-section 4.5 conclusive. |
| 0.6 | [À DATER] | Farah & Gilles Maury | Rédaction complète de la sous-section 4.5 conclusive de la section 4. Mise en correspondance des sept invariants techniques (SOLID, DDD, BDD, TDD, hexagonal, YAGNI, DRY) avec les sagesses du monde et les écologies de Santos. Pour chaque correspondance : le principe technique en ingénierie, la sagesse correspondante, ce qui justifie le rapprochement, ce que cela change opérationnellement. Tableau de synthèse des sept correspondances. Démonstration que les invariants techniques ne sont pas arbitraires mais traduisent des principes anthropologiques universels, ce qui donne à la Méthode Maury sa transmissibilité interculturelle. Bilan général de la section 4 entière retraçant l'arc complet de 4.0 à 4.5. La section 4 est désormais entièrement rédigée. |
| 0.7 | [À DATER] | Farah & Gilles Maury | Rédaction complète de la section 2 sur les sources philosophiques. Présentation en huit sous-sections des cinq sagesses du monde (Ubuntu avec Mogobe Ramose, sumak kawsay avec ses ancrages constitutionnels équatorien et bolivien, sept générations Haudenosaunee avec la Grande Loi de la Paix, mottainai japonais, Cantique des créatures de François d'Assise), de Boaventura de Sousa Santos comme partenaire de pensée contemporain (épistémicide, cinq monocultures et cinq écologies, sociologie des absences et émergences), et des cinq traditions de résistance internes au logiciel (Manifeste Agile 2001, Software Craftsmanship, mouvement du logiciel libre stallmanien, commons numériques européens avec Framasoft et NLnet, tradition open source européenne plus large). Précaution liminaire sur le risque d'extractivisme épistémique. Sous-section conclusive sur l'articulation des trois familles de sources. Voix neutre que Farah et Gilles pourront retravailler ensemble. |
| 0.8 | [À DATER] | Farah & Gilles Maury | Rédaction complète de la section 5 sur les projets concrets, avec présentation factuelle de KoproGo (jalon 0, v0.1.0 dans les cartons, dix heures par semaine, dépôt GitHub, chaîne YouTube, métriques publiques vérifiables, dispositif de revue de code croisée par quatre IA) et de BANKO (early stage en progression douce, cinq heures par semaine, dépôt GitHub, posture explicite de proposition technique offerte à une partenaire fintech). EcoleHub retiré pour le moment car en suspens et plus open source, avec mention dans la note préliminaire et dans une note de clôture. Précision rétroactive ajoutée dans la sous-section 4.1.6 explicitant que la capacité au sens TOGAF intègre dimensions techniques, organisationnelles, écologiques et d'écosystème — ce qui éclaire le paradoxe apparent entre l'avancement du code et le franchissement officiel de jalons, paradoxe ensuite illustré concrètement dans la présentation de KoproGo. |
| 0.9 | [À DATER] | Farah & Gilles Maury | Rédaction complète de la section 6 conclusive en cinq sous-sections : invitation non-doctrinaire, modes de contribution via GitHub uniquement (issues, PR, discussions), liens consolidés vers les dépôts et la chaîne YouTube, licences (AGPL-3.0 pour le code, CC-BY-SA 4.0 pour le texte) et caractère vivant du document, clôture sobre en écho au préambule. Stub des annexes A à E remplacé par une mention indiquant qu'elles seront publiées comme fichiers séparés du dépôt à mesure de leur rédaction. Le manifeste est désormais structurellement complet — toutes les sections du corps sont rédigées et seul le travail des annexes reste optionnel pour des versions ultérieures. Destination du document confirmée : README du dépôt `github.com/gilmry/manifest`. |

---

# Décisions à prendre à deux

Liste consolidée des points qui appellent une discussion explicite entre Farah et Gilles avant ancrage dans la version publique :

1. **La formule « passer de l'économie de ressources d'une plateforme à l'économie de la planète d'un commun »** (sous-section 4.1.2, temps 4). Forte mais engageante. À valider, reformuler ou retirer.

2. **L'experte fintech tunisienne à l'origine de BANKO** (sous-section 4.2.2). Désignation non-nominative dans la version 0.3. Pour la version publique, vérifier qu'elle accepte explicitement le cadre du manifeste et décider si on la nomme ou non.

3. **Le statut de BANKO et de la relation avec la BCT** (sous-section 4.2). La version actuelle évoque "une volonté explicite de souveraineté technologique" de la BCT mais n'affirme pas un partenariat formel. À vérifier que la formulation est juste et pas surévaluée.

4. **L'ambition épistémologique tempérée** (sous-section 4.2.7). Formulation actuelle : "contribution à une épistémologie de l'ingénierie de solution pour le bien commun" comme horizon, pas comme acquis. Validée au choix B.

5. **L'inscription biographique** (préambule). La version actuelle gomme la dimension religieuse et migratoire évoquée précédemment. À confirmer.

6. **Les sept invariants comme traductions des sagesses** (sous-section 4.5, à rédiger). Le tableau de correspondance proposé (SOLID ↔ écologie des savoirs, etc.) doit être validé conceptuellement avant rédaction.

7. **La place exacte de Santos et de Graça dans la version publique**. Santos est désormais traité explicitement en sous-section 2.6 comme partenaire de pensée contemporain, avec ses concepts d'épistémicide, des cinq monocultures et écologies, et de sociologie des absences et émergences. Graça reste mentionné en sous-section 4.1.3 comme architecte ayant unifié les traditions DDD, hexagonal, onion, clean et CQRS. Cette répartition à valider à deux : Santos est-il bien à sa place comme partenaire en section 2, ou voulez-vous le déplacer ailleurs ? Graça mérite-t-il une mention plus développée quelque part ?

8. **L'idée de l'IA comme accoucheuse socratique** (note mémoire). Cette dimension a été intégrée à la sous-section 4.4 comme l'une des trois fonctions transversales de l'IA dans le pipeline (accélération de la mise en forme, accouchement socratique des pratiques tacites, copilote sans responsabilité finale). Elle reste en outre disponible pour intégration ponctuelle en sous-section 1.5 si vous le jugez utile.

---

# Points résolus en version 0.3

Pour mémoire, les points qui figuraient comme "à compléter" en versions 0.1 et 0.2 et qui sont désormais consolidés :

- ✅ **Marqueur 4.1.5** — Émergence méthodologique avec TOGAF comme constat fondateur, articulation en écologie des savoirs, IA comme paradigm shift
- ✅ **Marqueur 4.1.6** — Inventaire des six modules communautaires, possibilité d'usage autonome, gate reviews illustrées
- ✅ **Sous-section 4.2 entière** — Récit BANKO en sept paragraphes parallèles à 4.1
- ✅ **Question des chiffres d'impact** — Reformulés en ordres de grandeur prudents et mis en perspective avec la progression organique par jalons
- ✅ **Sous-section 4.3 entière** — Convergence sept couches en onze paragraphes, tableau de synthèse, portée philosophique
- ✅ **Sous-section 4.4 entière** — Pipeline méthodologique in extenso, IA comme copilote responsable à toutes les étapes, dimension d'accouchement socratique intégrée naturellement
- ✅ **Sous-section 4.5 entière** — Sept invariants techniques comme traductions des sagesses du monde et écologies de Santos, tableau de synthèse, bilan général de la section 4
- ✅ **Section 4 dans son ensemble** — La méthode Maury est désormais entièrement rédigée et clôturée. L'arc 4.0 → 4.5 forme un ensemble cohérent et autonome.
- ✅ **Section 2 entière** — Sources philosophiques rédigées en huit sous-sections : cinq sagesses du monde présentées chacune depuis sa tradition propre, Santos comme partenaire de pensée contemporain, cinq traditions de résistance internes au logiciel, articulation conclusive entre les trois familles de sources.
- ✅ **Section 5 entière** — Projets concrets KoproGo (jalon 0, v0.1.0 dans les cartons, dix heures par semaine, dispositif de revue par quatre IA) et BANKO (early stage en progression douce, cinq heures par semaine, posture de proposition technique offerte). EcoleHub retiré comme en suspens.
- ✅ **Précision rétroactive en 4.1.6** — La notion de capacité au sens TOGAF intègre dimensions techniques, organisationnelles, écologiques et d'écosystème, ce qui éclaire la dissociation possible entre avancement du code et franchissement officiel de jalons.
- ✅ **Section 6 entière** — Conclusion ouverte rédigée pour un README GitHub : invitation non-doctrinaire, modes de contribution via GitHub, liens consolidés, licences précisées, clôture sobre.
- ✅ **Manifeste structurellement complet** — Toutes les sections du corps (0 à 6) sont rédigées. Seules les annexes optionnelles restent à traiter comme fichiers séparés du dépôt.

---

*Manifeste Maury — Version 0.3 de travail — Document vivant — Licence CC-BY-SA*
