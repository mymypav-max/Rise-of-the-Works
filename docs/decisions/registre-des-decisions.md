# Référentiel unique des décisions de conception — Rise of the Works

> **Document de référence vivant — phase de conception**
>
> Ce document est la source unique de vérité pour les décisions de conception de Rise of the Works. Il rassemble les décisions validées, les principes retenus dont certains paramètres restent à définir, les hypothèses de travail et les questions encore ouvertes.
>
> Pendant la phase actuelle, toute évolution de la conception doit être vérifiée par rapport à ce document et intégrée ici. Aucun document parallèle de décisions ne doit être créé ou maintenu. Les autres documents de conception déjà présents dans le dépôt sont des supports initiaux et ne prévalent pas sur le présent référentiel.
>
> Le cahier des charges détaillé ne sera rédigé qu'après la clôture de cette phase : lorsque la liste des éléments à concevoir sera suffisamment détaillée, cohérente et débarrassée de ses contradictions.

---

## 1. Règles de lecture et de mise à jour

### 1.1 Statuts

- **Validé** : décision explicitement retenue.
- **Principe validé — paramètres à définir** : l'orientation est retenue, mais les valeurs, modalités ou détails restent à déterminer.
- **Hypothèse de travail** : piste proposée pour avancer, qui ne doit pas être considérée comme une décision.
- **Ouvert** : aucune décision n'a encore été prise.
- **Remplacé** : ancienne formulation abandonnée au profit d'une décision plus récente. Elle est conservée dans l'historique pour assurer la traçabilité.

### 1.2 Règles de gouvernance

1. Toute nouvelle décision doit être comparée aux décisions déjà consignées.
2. En cas de contradiction, le conflit doit être présenté explicitement avant de modifier le référentiel.
3. Une décision remplacée n'est jamais effacée sans trace : le changement et sa raison sont consignés.
4. Les valeurs industrielles, économiques ou temporelles ne doivent pas être inventées et présentées comme réalistes. Elles devront être documentées, puis adaptées au gameplay.
5. Une proposition de l'assistant n'est pas une décision tant qu'elle n'a pas été acceptée explicitement.
6. Le présent document reste le seul document de référence des décisions pendant cette phase. Il sera enrichi au fil des échanges.

### 1.3 Historique du document

| Version | Date | Évolution |
|---|---|---|
| 0.1 | 18/11/2026 | Consolidation des décisions issues de la phase initiale de conception et des échanges sur la sucrerie betteravière, ses infrastructures, ses stockages et son approvisionnement. |

---

## 2. Vision et identité du jeu

### 2.1 Concept général

**Validé**

Rise of the Works est un jeu solo de gestion et de développement industriel. Le joueur construit, organise et fait évoluer un site de production afin d'assurer son fonctionnement, d'améliorer ses performances et de développer sa rentabilité.

La première industrie jouable est une sucrerie betteravière. Le concept général doit pouvoir accueillir d'autres secteurs industriels dans de futures évolutions, sans élargir artificiellement le périmètre de la première expérience.

Le jeu doit associer :
- une gestion économique et entrepreneuriale ;
- la construction et l'agrandissement visibles du site ;
- l'organisation d'une chaîne de production ;
- l'optimisation des capacités et des ressources ;
- la gestion du personnel, des approvisionnements, des incidents et des investissements.

Le jeu doit rester agréable et accessible. Il ne s'agit pas d'un simulateur d'ingénierie exhaustive : le procédé industriel est simplifié, mais doit conserver une logique crédible.

### 2.2 Principes directeurs

**Validé**

- Le gameplay prime sur la simulation technique exhaustive.
- Le joueur doit voir son usine grandir et évoluer visuellement.
- Les ateliers et infrastructures sont interdépendants.
- Les capacités et les ressources disponibles créent des goulets d'étranglement.
- Les investissements doivent être réfléchis : augmenter la capacité d'un atelier peut être inutile si une autre installation limite la production.
- Les systèmes de gestion doivent rester lisibles et ne pas devenir inutilement complexes.

### 2.3 Plateforme et mode de jeu

**Validé**
- Jeu solo.
- Fonctionnement hors ligne.
- Sauvegardes locales.
- Cible initiale : PC Windows 10/11.
- Utilisation au clavier et à la souris.
- Distribution envisagée sous forme d'un programme Windows installable (.exe), sans dépendance initiale à Steam.

**Ouvert**
- Modalités précises de distribution et de mise à jour du jeu.

### 2.4 Représentation et construction

**Validé**
- Graphismes 2D isométriques pour la première version.
- Vue générale du site permettant d'observer les bâtiments et leur évolution.
- Les bâtiments sont construits sur des emplacements prédéfinis ; pas de placement entièrement libre.
- Les ateliers de production sont des bâtiments distincts.
- Le joueur doit pouvoir construire de nouveaux bâtiments ou augmenter certaines capacités au fil de sa progression.

**Validé — contrainte de production des ressources graphiques**
- Le joueur ne souhaite pas devoir apprendre un logiciel de dessin ou réaliser manuellement les cartes du jeu.
- La création du moteur et l'intégration des ressources seront prises en charge dans le développement, notamment avec Claude Code.
- Les ressources graphiques pourront provenir de bibliothèques libres ou d'images générées par IA, en veillant à conserver une cohérence visuelle.

**Ouvert**
- Direction artistique définitive, style des bâtiments, interface graphique et méthode précise de production des sprites.
- Résolution et comportement détaillé de l'interface.

---

## 3. Organisation temporelle et campagnes

### 3.1 Fonctionnement du temps

**Validé**
- Le jeu fonctionne en temps réel accéléré.
- Le joueur peut mettre le jeu en pause et choisir plusieurs vitesses d'écoulement du temps.

**Principe validé — paramètres à définir**
- Les rythmes de jeu doivent permettre de suivre l'activité industrielle sans donner l'impression que les journées défilent trop vite.
- La durée d'une journée réelle de jeu, les vitesses proposées et l'éventuelle différence de rythme entre campagne et intercampagne restent à définir.
- Les vitesses x1, x2 et x4 ont été évoquées comme piste, sans validation définitive.

### 3.2 Campagnes betteravières

**Décision validée — fonctionnement continu pendant la campagne**
- Pendant la campagne betteravière, l'usine est prévue pour fonctionner en continu, **24 heures sur 24 et 7 jours sur 7**.
- La continuité de l'exploitation est assurée par des équipes qui se relaient en postes successifs. Le nombre d'équipes, la durée des postes et l'organisation précise des rotations restent à définir.
- Les pannes, incidents, opérations de maintenance et contraintes d'approvisionnement peuvent entraîner des arrêts ou des réductions de cadence. Ils seront pris en compte dans la disponibilité réelle de l'usine.

**Décision validée — durée de la campagne initiale**
- La durée de référence d'une campagne betteravière est fixée à **120 jours calendaires**.
- Cette durée constitue le paramètre de départ de la V1 pour le calendrier d'exploitation de la sucrerie.
- Les 120 jours représentent une durée de campagne, et non 120 jours de fonctionnement garanti à pleine capacité : les arrêts, pannes, opérations de maintenance, indisponibilités et contraintes d'approvisionnement pourront réduire le tonnage réellement traité.
- La durée des campagnes pourra évoluer selon les scénarios ou les choix de gestion ultérieurs, si cette possibilité est intégrée au gameplay.

**Validé**
- L'activité sucrière est organisée en campagnes saisonnières.
- Une période d'intercampagne suit la campagne.
- L'intercampagne sert notamment à effectuer la maintenance, les travaux, les améliorations et les investissements.
- Le personnel permanent reste employé et rémunéré toute l'année, y compris pendant l'intercampagne.

**Ouvert**
- Durée d'une campagne et d'une intercampagne.
- Calendrier exact et correspondance entre temps de jeu et durée simulée.
- Éventuelles variations de cadence ou de règles entre campagne et intercampagne.

---

## 4. Site industriel et progression

### 4.1 Démarrage

**Validé**
- Le joueur commence sur un terrain vierge.
- Le budget initial doit permettre de construire les installations minimales nécessaires au lancement d'une première production.
- La progression passe par la construction, l'amélioration et le déblocage de nouvelles installations.

### 4.2 Ateliers et bâtiments

**Validé**
- Les ateliers de production sont des bâtiments distincts.
- Les ateliers peuvent disposer de niveaux d'amélioration.
- Le joueur peut construire des ateliers supplémentaires lorsque la progression et les besoins de production le justifient.
- Les niveaux, coûts et effets des améliorations restent à définir.

**Principe validé — paramètres à définir**
- Les bâtiments et ateliers possèdent des capacités propres.
- Les capacités des infrastructures annexes peuvent limiter les ateliers de production.
- Les capacités supplémentaires doivent avoir un coût de construction et des coûts d'exploitation cohérents.

---

## 5. Procédé de production du sucre

### 5.1 Chaîne principale de départ

**Principe validé — organisation retenue**

La chaîne de base comprend neuf ateliers de production distincts :

1. **Réception des betteraves** : réception, déchargement et alimentation de la chaîne.
2. **Lavage et déterrage** : retrait de la terre présente sur les betteraves. Pour la simulation V1, la terre constitue la seule catégorie d'impuretés prise en compte.
3. **Découpage** : transformation des betteraves en cossettes.
4. **Diffusion** : extraction du sucre contenu dans les cossettes. Cette étape génère également des pulpes humides.
5. **Épuration** : traitement du jus, notamment par chaulage, carbonatation et filtration.
6. **Évaporation** : concentration du jus par retrait d'une partie de l'eau.
7. **Cristallisation** : formation des cristaux de sucre.
8. **Centrifugation** : séparation des cristaux et du sirop restant.
9. **Séchage et refroidissement** : préparation du sucre cristallisé destiné au stockage en vrac.

Chaque atelier est représenté par un bâtiment distinct.

**Précision de périmètre**
- Le produit de base est le sucre cristallisé en vrac.
- Le sucre vrac peut être stocké et vendu directement, sans devoir passer par une fabrication de sucre en morceaux.
- Le conditionnement en sacs ou en petits emballages n'est pas retenu comme une étape obligatoire de la chaîne de base à ce stade.

### 5.2 Capacités et flux

**Décision validée — capacité nominale initiale de la sucrerie**
- La capacité nominale initiale de traitement est fixée à **7 500 tonnes de betteraves propres par jour**, c'est-à-dire après lavage et retrait de la terre.
- Cette valeur constitue le débit théorique nominal de référence de l'usine, avant prise en compte des arrêts, de la maintenance, des indisponibilités, des éventuels goulets d'étranglement ou des contraintes d'approvisionnement.
- Le tonnage de betteraves brutes réceptionnées sera nécessairement supérieur au tonnage de betteraves propres traitées. Il dépendra du taux de terre par camion, qui reste à définir.
- Cette capacité journalière ne fixe pas à elle seule le nombre d'heures de fonctionnement par jour ni le taux de disponibilité de l'usine ; ces paramètres restent ouverts.

**Décision validée — cristallisation et récupération du saccharose**
- Pour le modèle simplifié de la V1, l'atelier de cristallisation représente plusieurs cycles successifs de cristallisation et de recyclage des sirops intermédiaires, sans simuler séparément chaque appareil ou chaque cycle.
- La centrifugation constitue l'étape distincte de séparation finale des cristaux de sucre et de la mélasse.
- Le rendement global de récupération du saccharose au cours de la cristallisation est fixé à 88 % du saccharose présent dans le jus épuré entrant dans cette étape.
- Sur la base actuelle de 171,5 kg de saccharose, cela représente environ 150,9 kg de saccharose cristallisé et 20,6 kg de saccharose restant dans la mélasse finale.
- Cette valeur est un paramètre de référence simplifié, choisi dans les ordres de grandeur industriels documentés ; elle ne représente pas une moyenne universelle.
- La masse finale de sucre commercialisable sera déterminée ultérieurement en tenant compte de la pureté des cristaux, du séchage et du refroidissement.

**Décision validée — centrifugation et séparation finale**
- La centrifugation constitue une étape distincte qui sépare les cristaux de sucre de la liqueur mère issue de la cristallisation.
- Le lavage des cristaux est intégré à cette étape ; les sirops récupérés sont recyclés vers le système de cristallisation.
- Le rendement global de récupération du saccharose de 88 % validé pour la cristallisation couvre l'ensemble du système de cristallisation et de séparation. Aucune perte supplémentaire de saccharose n'est appliquée arbitrairement à la centrifugation.
- L'humidité de référence du sucre en sortie de centrifugeuse est fixée à 1,23 %. Le sucre est ensuite dirigé vers l'atelier de séchage et de refroidissement.
- Pour le bilan simplifié, les cristaux sont considérés comme du saccharose pur avant prise en compte de l'humidité : 150,9 kg de saccharose correspondent ainsi à environ 152,8 kg de sucre humide à 1,23 % d'humidité.
- La mélasse finale contient les 20,6 kg de saccharose non récupérés sous forme de cristaux. En retenant une composition de référence de 77,6 % de matière sèche et 60,9 % de saccharose dans cette matière sèche, sa masse estimée est d'environ 43,6 kg.
- Ces quantités sont rapportées à la base commune de 1 000 kg de betteraves propres traitées, et non à une tonne de betteraves brutes livrées ni à une tonne de jus.
- La masse de mélasse est une estimation de bilan matière fondée sur la composition retenue ; elle constitue un paramètre simplifié de gameplay, et non une valeur universelle pour toutes les sucreries.

**Décision validée — séchage et refroidissement**
- Le sucre humide sortant de centrifugation entre dans l'atelier de séchage et de refroidissement avant son transfert vers les silos à sucre vrac.
- L'humidité de référence à l'entrée de cet atelier est de 1,23 %.
- L'humidité résiduelle cible du sucre fini est fixée à 0,04 %.
- La température de référence du sucre en sortie de refroidissement est fixée à 30 °C.
- Pour le bilan simplifié, les 150,9 kg de saccharose sont conservés pendant le séchage et le refroidissement ; seule l'eau est retirée.
- Sur la base de 1 000 kg de betteraves propres traitées, l'entrée est d'environ 152,8 kg de sucre humide. La sortie est d'environ 150,96 kg de sucre fini à 0,04 % d'humidité, soit environ 1,82 kg d'eau retirée.
- Ces valeurs sont des paramètres de référence du modèle de jeu et ne représentent pas une garantie de performance applicable à toute installation industrielle.

**Décision validée — évaporation**
- Le sirop en sortie d'évaporation est fixé à 70 % de matière sèche totale.
- Le bilan de référence est établi sur 1 079,5 kg de jus épuré entrant, contenant 184,4 kg de matière sèche totale (17,08 %).
- En supposant l'absence de perte de matière sèche pendant l'évaporation, la sortie est d'environ 263,4 kg de sirop à 70 % de matière sèche.
- La quantité d'eau évaporée correspondante est d'environ 816,1 kg.
- Le coefficient de référence est donc d'environ 0,756 kg d'eau évaporée par kg de jus épuré traité.
- Ces valeurs sont rattachées à la quantité de jus épuré traitée ; elles ne doivent pas être présentées comme des valeurs unitaires directement rapportées à une tonne de betteraves, même si le lot de jus utilisé dans le bilan provient de notre base de calcul de 1 000 kg de betteraves propres.

**Décision validée — épuration du jus**
- Pour le bilan matière simplifié de la V1, l'épuration entraîne une perte de référence de 1 kg de saccharose par tonne de betteraves propres traitées.
- Cette perte est considérée comme entraînée avec les boues d'épuration.
- La production de boues humides est représentée par une valeur de référence arrondie d'environ 90 kg par tonne de betteraves propres.
- Ces valeurs sont des simplifications de gameplay fondées sur des ordres de grandeur documentés ; elles ne prétendent pas représenter une constante universelle des sucreries.

**Décision validée — teneur en sucre de la matière première et jus brut**
- Le modèle conserve une base de 1 000 kg de betteraves propres donnant 1 150 kg de jus brut de diffusion.
- Ce jus brut est simplifié à 15 % de saccharose en masse, soit 172,5 kg de saccharose.
- Cette teneur correspond à une matière première particulièrement riche en sucre, située dans le haut des ordres de grandeur observés. Elle est néanmoins conservée volontairement comme référence de base du jeu.
- Après la perte de référence de 1 kg à l'épuration, le jus épuré contient 171,5 kg de saccharose.

**Décision validée — organisation de la diffusion**
- L'atelier de diffusion comprend également le pressage des pulpes en fin de diffusion.
- Les pulpes qui sortent de l'atelier de diffusion pour être stockées sont donc des pulpes pressées, et non les pulpes fraîches directement à la sortie du diffuseur.
- L'eau extraite lors du pressage est récupérée et réutilisée dans le circuit de diffusion ; le bilan devra distinguer les flux internes recyclés des flux sortants de l'atelier.

**Décision validée — quantité et composition des pulpes pressées**
- Sur la base de 1 000 kg de betteraves propres traitées, la production de référence est fixée à 210 kg de pulpes pressées.
- La matière sèche est fixée à 27 %, soit 56,7 kg de matière sèche et 153,3 kg d'eau.
- Ces pulpes sont celles qui sortent du pressage intégré à l'atelier de diffusion et qui sont envoyées vers les silos dédiés.
- La valeur de 210 kg est un arrondi de gameplay cohérent avec les références industrielles consultées, notamment un bilan BioBIGG/Nordic Sugar indiquant environ 213 kg à 27 % de matière sèche par tonne de betteraves propres.
- La matière sèche représente l'ensemble des constituants secs des pulpes, et non uniquement les fibres ; elle n'est pas décomposée davantage dans le bilan simplifié de la V1.
- L'eau extraite au pressage reste un flux interne récupéré et recyclé dans le circuit de diffusion ; elle ne doit pas être comptabilisée comme une sortie supplémentaire de l'usine.

**Décision validée — déshydratation des pulpes et production de pellets**
- La filière de valorisation des pulpes commence avec les 210 kg de pulpes pressées produits par tonne de betteraves propres traitées, à 27 % de matière sèche.
- La matière sèche est conservée pendant la déshydratation ; l'opération consiste à retirer de l'eau.
- La teneur en matière sèche des pulpes déshydratées est fixée à 90 %, soit 10 % d'humidité résiduelle.
- Sur la base de 1 000 kg de betteraves propres, les 56,7 kg de matière sèche donnent environ 63,0 kg de produit déshydraté à 90 % de matière sèche, contenant 6,3 kg d'eau.
- La quantité d'eau retirée lors de la déshydratation est donc d'environ 147,0 kg par tonne de betteraves propres traitées.
- Le produit déshydraté est ensuite compacté sous forme de pellets. Pour le bilan simplifié de la V1, la granulation n'entraîne ni ajout ni perte de matière : la masse de pellets produite reste fixée à environ 63,0 kg.
- Aucun ajout de mélasse n'est modélisé dans la filière de base de la V1.
- Les pellets sont transférés vers leurs silos dédiés, distincts des silos à pulpes humides.
- Les valeurs de 90 % de matière sèche et de 63,0 kg de pellets sont des paramètres de gameplay cohérents avec les références industrielles consultées ; elles ne constituent pas une garantie de performance applicable à toute installation.
- Les références énergétiques consultées conduisent à un ordre de grandeur indicatif d'environ 0,35 à 0,44 GJ d'énergie thermique par tonne de betteraves propres traitées pour cette quantité de matière sèche et d'eau évaporée. Cette estimation sert de repère documentaire ; la consommation énergétique retenue pour le gameplay reste à définir après étude globale des utilités de l'usine.

**Références industrielles de travail — valeurs à confirmer**
- Un bilan matière publié par BioBIGG à partir de données Nordic Sugar indique environ 1 150 kg de jus de diffusion et 213 kg de pulpes pressées à 27 % de matière sèche par tonne de betteraves propres.
- Une thèse de doctorat de l'University College London (2025) indique une teneur usuelle du jus brut de 10 à 15 % de saccharose en masse et une pureté saccharosique de 85 à 90 % des matières solubles.
- **Décision validée pour le modèle de jeu :** le jus brut de diffusion est simplifié à 15 % de saccharose en masse. Cette valeur désigne bien la masse de saccharose rapportée à la masse totale du jus, et non le Brix ou la teneur totale en matières solubles.
- Sur une base de 1 150 kg de jus brut, cette convention représente 172,5 kg de saccharose.
- Le jeu vise une représentation industrielle crédible et cohérente, sans chercher une simulation physico-chimique hyper précise. Les valeurs de référence seront donc simplifiées lorsque nécessaire, tout en conservant des bilans matière cohérents et des ordres de grandeur réalistes.
- Les valeurs industrielles documentées restent des références de travail ; les paramètres du jeu pourront être arrondis ou simplifiés pour le gameplay, sans être présentés comme des mesures exactes d'une usine réelle.



**Principe validé — paramètres à définir**
- Chaque atelier possède une capacité nominale exprimée dans une unité adaptée à la matière ou à l'opération qu'il traite.
- Il n'est pas nécessaire d'imposer une unité de capacité unique à toute la chaîne.
- La tonne de betteraves constitue une unité pertinente pour l'approvisionnement, la réception, le stockage des betteraves et les premières opérations qui les traitent.
- Les ateliers suivants peuvent utiliser des unités différentes : masse de cossettes, volume de jus, quantité d'eau évaporée, masse de sirop ou de sucre, etc.
- Les flux entre ateliers doivent être reliés par des coefficients de conversion et des bilans matière cohérents.
- La production réelle dépend de la capacité disponible, des matières entrantes, des ressources, du personnel et de la disponibilité des ateliers en amont et en aval.
- Les ateliers n'ont pas nécessairement les mêmes cadences.
- Pour le bilan matière de la V1, le découpage des betteraves propres en cossettes est considéré sans perte de matière : la masse de cossettes produite est égale à la masse de betteraves propres entrante.
- Les différences de capacité doivent créer des arbitrages et des goulets d'étranglement compréhensibles.
- Les stocks intermédiaires absorbent temporairement les différences de cadence.
- Une saturation ou un arrêt peut réduire le débit de toute la chaîne.
- Les investissements doivent être évalués à l'échelle de la chaîne complète.

**Ouvert**
- Capacités nominales et cadences de chacun des neuf ateliers.
- Bilans matière et coefficients de conversion entre chaque étape : notamment betteraves vers cossettes, cossettes vers jus et pulpes humides, jus épuré, sirop, sucre cristallisé et produits finis.
- Quantités de coproduits, teneurs en matière sèche et en sucre, humidité, taux d'extraction et pertes à chaque étape.
- Volumes et règles de gestion des stocks intermédiaires.
- Consommations de vapeur, d'électricité, d'eau et de consommables.
- Valeurs industrielles de référence et adaptations nécessaires au gameplay.

Les valeurs chiffrées déjà validées sont celles explicitement indiquées dans les décisions ci-dessus. Les autres capacités, rendements, coefficients de conversion et consommations restent à définir.

---

## 6. Coproduits et extensions industrielles

### 6.1 Pulpes humides et pellets

**Validé — principe de filière**

- La diffusion produit des pulpes humides.
- Les pulpes humides sont stockées dans des silos dédiés avant leur traitement ou leur évacuation.
- Une durée maximale de conservation est appliquée afin d'empêcher un stockage indéfini.
- Les pulpes sont conservées par ensilage dans des silos fermés et étanches.
- Avant le déblocage de la déshydratation, le joueur doit supporter un coût pour faire évacuer les pulpes.
- Au cours de la progression, le joueur pourra investir dans un atelier de déshydratation, également appelé bâtiment de déshydratation.
- Cet atelier transforme les pulpes humides en pellets.
- Les pellets sont un véritable produit commercialisable, générateur de revenus.
- Les pellets finis disposent de silos de stockage distincts des silos à pulpes humides.
- La capacité de stockage des pulpes doit être cohérente avec le débit de production et la capacité de déshydratation.

**Décision validée — dimensionnement et organisation des silos à pulpes humides**
- La capacité nominale totale des silos à pulpes humides est dimensionnée sur 33 jours de production de pulpes pressées.
- Cette capacité comprend 30 jours de production correspondant à la phase de fermentation nécessaire avant utilisation, auxquels s'ajoutent 3 jours de réserve opérationnelle pour absorber les décalages entre production et déshydratation.
- Le coefficient de production de pulpes pressées étant fixé à 0,21 tonne par tonne de betteraves propres traitées, la capacité nominale est calculée selon la formule : capacité (t de pulpes) = débit journalier de betteraves propres (t/j) × 0,21 × 33.
- La capacité exacte en tonnes sera déterminée lorsque le débit nominal de betteraves de l'usine de départ sera validé.
- Le stockage est organisé en plusieurs cellules indépendantes afin de permettre le remplissage, la fermeture, la fermentation et le soutirage de lots distincts.
- Les lots sont gérés selon le principe FIFO (premier entré, premier sorti), en tenant compte de leur date de mise en silo et de leur durée de conservation.
- La capacité de 33 jours constitue une règle de dimensionnement du gameplay V1 ; elle ne doit pas être interprétée comme une norme universelle de conception industrielle.

**Décision validée — conservation des pulpes humides par ensilage**
- Les pulpes pressées sont stockées dans des silos fermés et étanches, selon un principe d'ensilage.
- Une phase de fermentation de référence de 30 jours est nécessaire avant que les pulpes puissent être utilisées pour la déshydratation.
- La durée maximale de conservation est fixée à 180 jours à compter de la mise en silo. Cette durée inclut donc la phase initiale de fermentation.
- En fonctionnement normal, lorsque l'ensilage est correctement réalisé et que le silo reste étanche, aucune perte de matière sèche n'est modélisée dans le bilan matière simplifié de la V1.
- Au-delà de 180 jours, les pulpes subissent une dégradation progressive de leur qualité et de leur utilisabilité. Elles finissent par devoir être évacuées ; le seuil et les modalités précises de cette dégradation restent à définir.
- La durée de 180 jours est un paramètre de gameplay retenu pour la V1, et non une limite universelle de conservation applicable à toutes les installations industrielles.
- Le joueur doit donc organiser les capacités de stockage et le débit de déshydratation afin d'éviter le dépassement de la durée de conservation.

**Principe validé — paramètres à définir**
- Les silos à pulpes humides sont des bâtiments indépendants et constructibles séparément.
- Plusieurs capacités de stockage pourront être proposées.
- En cas de dépassement de la durée maximale de conservation, la qualité et l'utilisabilité des pulpes se dégradent progressivement ; les modalités chiffrées de cette dégradation restent à définir.
- La saturation des silos doit contraindre la production ou imposer une solution d'évacuation.
- Le principe de déshydratation à 90 % de matière sèche, la masse de référence de 63,0 kg de pellets et le retrait d'environ 147,0 kg d'eau par tonne de betteraves propres sont validés. Les capacités de l'atelier, sa consommation énergétique de gameplay et les coûts de traitement restent à définir.

### 6.2 Sucre en morceaux

**Validé — principe de filière**
- Le sucre en morceaux n'est pas disponible au démarrage.
- Le joueur pourra investir ultérieurement dans un atelier dédié à la fabrication de sucre en morceaux.
- Le sucre cristallisé de base reste vendable directement en vrac.
- Le sucre en morceaux dispose d'un stockage dédié, distinct des silos à sucre vrac.

**Ouvert**
- Procédé simplifié de fabrication.
- Capacité, coût, besoins en personnel et ressources.
- Conditions de déblocage et intérêt commercial.
- Modalités de stockage détaillées.

### 6.3 Autres coproduits

**Ouvert**
- La mélasse et les écumes sont identifiées comme coproduits possibles du procédé.
- Leur stockage, leur évacuation ou leur valorisation économique ne sont pas encore décidés.
- Ne pas leur attribuer de filière ou de revenu avant décision explicite.

---

## 7. Approvisionnement et réception des betteraves

### 7.1 Fournisseurs et contrats

**Validé**
- Au démarrage, les betteraves sont achetées auprès d'agriculteurs externes.
- Le joueur peut conclure des contrats d'approvisionnement sur plusieurs campagnes.
- Les livraisons contractuelles sont planifiées et automatiques.
- Le joueur peut également commander ponctuellement des camions supplémentaires en fonction de ses besoins.
- Les achats ponctuels peuvent être plus coûteux que les volumes contractuels : cette différence est un principe retenu, mais son niveau reste à définir.

**Progression ultérieure validée**
- Le joueur pourra acquérir des terres et produire une partie de ses propres betteraves.
- Il devra alors arbitrer entre production interne et achats externes.

### 7.2 Camions et réception

**Validé**
- Tous les camions sont considérés comme ayant une capacité de chargement identique.
- Le jeu n'a pas besoin de simuler le pesage individuel des camions.
- Le pont-bascule et la pesée à réception ne sont donc pas nécessaires au gameplay retenu.
- Les camions déchargent les betteraves dans les installations de réception.
- La proportion de terre présente dans les betteraves varie d'un camion à l'autre.
- Pour la simulation V1, la terre est la seule impureté prise en compte : les pierres, feuilles, herbes et autres matières étrangères ne sont pas modélisées séparément.
- Cette variabilité n'est pas liée à une simulation explicite de la météo ou des conditions de récolte.
- Une aire extérieure permet de stocker les betteraves avant leur alimentation vers le lavage.

### 7.3 Stockage des betteraves et limites logistiques

**Principe validé — paramètres à définir**
- L'aire de stockage possède une capacité maximale.
- Sa capacité peut être augmentée par investissement.
- Le joueur doit équilibrer le rythme des livraisons, la capacité de stockage et le débit de transformation.
- La saturation de l'aire doit avoir une conséquence sur les livraisons et la production.

**Ouvert**
- Gestion précise des camions lorsque l'aire est pleine : report, refus, attente ou autre mécanisme.
- Éventuelles pénalités contractuelles en cas de livraison impossible.
- Capacité unitaire d'un camion et capacité initiale de l'aire.
- Règles de conservation des betteraves et éventuelle dégradation de leur qualité.

---

## 8. Infrastructures annexes et utilités

Les infrastructures annexes ne sont pas des ateliers de transformation directe des betteraves. Elles fournissent les ressources ou services nécessaires au fonctionnement de l'usine. Elles possèdent leurs propres capacités et peuvent devenir des goulets d'étranglement.

### 8.1 Chaufferie et vapeur

**Validé**
- La chaufferie produit la vapeur nécessaire aux procédés industriels.
- L'installation initiale est une chaudière au gaz, dimensionnée pour permettre le fonctionnement de l'usine de base.
- La capacité de la chaudière initiale peut être augmentée jusqu'à une limite.
- Au-delà de cette limite, le joueur doit investir dans une seconde chaudière.
- Une évolution ultérieure vers une chaufferie biomasse est prévue.

**Filière biomasse — validée dans son principe**
- Achat de combustible biomasse.
- Stockage du combustible sur le site.
- Approvisionnement de la chaudière.
- Investissement initial plus important que la solution de départ.
- Coût de combustible et coût d'exploitation potentiellement plus avantageux.

**Ouvert**
- Type précis de combustible biomasse.
- Capacités, rendements, coûts, besoins de stockage et modalités de cohabitation entre chaudières.
- Possibilité et intérêt de conserver des chaudières gaz en complément de la biomasse.

### 8.2 Station électrique

**Validé**
- L'usine possède une production électrique sur son propre site.
- L'alimentation électrique n'est pas simplement un achat d'électricité au réseau public.
- La première solution envisagée est une production au gaz.
- Des évolutions avancées pourront prendre la forme d'une centrale nucléaire ou d'une centrale hydroélectrique.
- La solution hydroélectrique suppose la présence d'un cours d'eau à proximité du site et des aménagements adaptés.

**Ouvert**
- Statut exact des solutions nucléaire et hydroélectrique : alternatives de progression, choix de scénario ou possibilités cumulables.
- Capacités, coûts, rendements, contraintes et conditions de déblocage.
- Possibilité d'augmenter la capacité de la première installation au gaz et limites de cette évolution.
- Éventuelle connexion au réseau électrique comme secours ou complément.

### 8.3 Approvisionnement en eau

**Validé**
- L'usine est alimentée par le réseau d'eau de ville.
- La consommation d'eau donne lieu à une facture.
- Aucun forage ou captage autonome n'est prévu dans le principe actuel.

**Ouvert**
- Tarif, règles de facturation, volumes consommés et éventuelles limites de débit.

### 8.4 Station d'épuration (STEP)

**Validé**
- Une station d'épuration traite les eaux usées issues de l'activité de l'usine.
- La capacité de traitement est limitée et peut être augmentée par investissement.
- Une capacité de traitement insuffisante doit constituer une contrainte pour l'exploitation.

**Ouvert**
- Capacité initiale, coûts, consommations et modalités précises des conséquences d'une saturation.
- Niveau de détail du traitement et éventuelle réutilisation de l'eau traitée.

### 8.5 Laboratoire

**Validé**
- Le laboratoire assure le contrôle de la qualité des betteraves, des produits intermédiaires et du sucre fini.
- Son fonctionnement doit rester simple et évolutif.
- Il peut influencer la qualité détectée et le suivi de la production.
- La qualité commerciale du sucre peut avoir un effet sur les contrats et les prix de vente.

**Ouvert**
- Capacité d'analyse, fréquence des contrôles, améliorations et conséquences exactes d'un contrôle insuffisant.
- Niveau de détail des analyses et indicateurs présentés au joueur.

### 8.6 Maintenance

**Validé**
- La maintenance est assurée par une équipe centralisée de techniciens.
- Un effectif plus important améliore la capacité d'intervention et peut réduire les délais de réparation.
- Le système V1 ne repose pas sur des compétences détaillées ou une affectation individuelle des techniciens à chaque atelier.
- La maintenance préventive et la vétusté influencent le risque de panne.
- Une part limitée d'aléatoire demeure : une panne reste possible sur un équipement récent et bien entretenu.

**Ouvert**
- Présentation et fonctionnement détaillé du bâtiment de maintenance.
- Coûts, effectifs, calendrier de maintenance préventive et niveaux d'amélioration.

---

## 9. Stockages et expédition

### 9.1 Stockages retenus

**Validé**

Les stockages suivants sont distincts :

1. **Aire extérieure à betteraves** : réserve de matière première avant transformation.
2. **Silos à pulpes humides** : stockage des pulpes issues de la diffusion avant déshydratation ou évacuation.
3. **Silos à sucre vrac** : stockage du sucre cristallisé après séchage et refroidissement. Le sucre vrac peut être vendu directement.
4. **Stockage du sucre en morceaux** : installation dédiée, disponible après investissement dans l'atelier de fabrication correspondant.
5. **Silos à pellets** : stockage du produit fini issu de la déshydratation, disponible après déblocage de cette filière.

### 9.2 Règles de stockage

**Principe validé — paramètres à définir**
- Chaque stockage possède une capacité maximale.
- Des capacités supplémentaires peuvent être construites ou ajoutées par investissement.
- La saturation d'un stockage peut bloquer ou ralentir l'installation située en amont.
- Les pulpes humides sont ensilées en silos fermés et étanches ; la fermentation dure 30 jours et la durée maximale de conservation est fixée à 180 jours à compter de la mise en silo. La capacité nominale totale est dimensionnée sur 33 jours de production de pulpes pressées, répartis entre 30 jours de fermentation et 3 jours de réserve opérationnelle. Avec la capacité initiale de 7 500 tonnes de betteraves propres par jour et une production de 0,21 tonne de pulpes pressées par tonne de betteraves propres, cette règle conduit à une capacité nominale totale de **51 975 tonnes de pulpes pressées** (7 500 × 0,21 × 33).
- Les produits finis peuvent être conservés avant leur vente ou leur expédition.

**Ouvert**
- Organisation détaillée des zones de chargement et d'expédition.
- Moyens de transport des produits finis.
- Gestion des expéditions, des délais et de la capacité de chargement.
- Éventuelle durée de conservation des autres produits stockés.

---

## 10. Économie et commercialisation

### 10.1 Produits commercialisés

**Validé**
- Le sucre cristallisé en vrac est le produit commercial principal dès le démarrage.
- Il peut être vendu directement depuis les silos à sucre vrac.
- Le sucre en morceaux devient un produit commercial après investissement dans son atelier dédié.
- Les pellets issus des pulpes sont un véritable produit commercial, avec des recettes de vente.

**Ouvert**
- Valorisation commerciale de la mélasse et des écumes.
- Prix, marges, demande et volumes de vente des différents produits.

### 10.2 Contrats clients

**Validé**
- Les ventes de sucre reposent notamment sur des contrats clients.
- Les contrats peuvent différer par leurs volumes, leurs tarifs et leurs délais.
- Les recettes commerciales contribuent à financer les dépenses et les investissements.
- La gestion du marché reste simplifiée : pas de simulation concurrentielle complexe entre sucreries.

**Ouvert**
- Vente au comptant ou au marché en complément des contrats.
- Règles de livraison, pénalités, qualité contractuelle et renouvellement des contrats.
- Modèle commercial applicable aux pellets et au sucre en morceaux.

### 10.3 Dépenses et trésorerie

**Principe validé — paramètres à définir**

Les postes de dépenses identifiés comprennent :
- achats de betteraves et combustible ;
- eau, énergie, consommables et ressources industrielles ;
- salaires ;
- maintenance et réparations ;
- évacuation des pulpes avant déshydratation ;
- construction, agrandissement et modernisation des installations.

Les recettes, dépenses, marges et investissements doivent être suivis dans une gestion économique lisible.

**Ouvert**
- Modèle de trésorerie détaillé, prix, coûts unitaires, financement, fiscalité éventuelle et règles de faillite.

---

## 11. Personnel, organisation et supervision

### 11.1 Personnel

**Validé**
- Le personnel permanent est présent et rémunéré toute l'année, y compris pendant l'intercampagne.
- Les ateliers de production ont un effectif minimum nécessaire à leur fonctionnement.
- Un sous-effectif peut réduire la capacité ou arrêter un atelier.
- Les responsables d'atelier sont prévus et peuvent améliorer la productivité, l'organisation, la qualité d'exécution ou les temps d'arrêt.
- La gestion individuelle approfondie des salariés n'est pas prévue pour la V1.
- Les techniciens de maintenance forment une équipe centralisée.

**Ouvert**
- Effectifs exacts, rémunérations, coûts, effets chiffrés des responsables et règles d'embauche.

### 11.2 Supervision

**Validé**
Le joueur dispose d'une supervision centralisée avec des onglets secondaires, couvrant notamment :
- la vue générale de l'usine ;
- la production : capacité théorique et réelle, utilisation, goulets, consommations et stocks intermédiaires ;
- la maintenance et les alarmes : pannes, interventions, techniciens disponibles et alertes préventives ;
- la gestion financière et le personnel.

Des indicateurs visuels simples peuvent signaler l'état des installations :
- vert : fonctionnement normal ;
- orange : fonctionnement dégradé ;
- rouge : panne ou arrêt ;
- bleu : travaux.

Un indicateur synthétique de l'état général de l'usine a été envisagé.

**Ouvert**
- Liste définitive des indicateurs, écrans, alertes, filtres et interactions.

---

## 12. Incidents et mini-jeux

### 12.1 Pannes

**Validé**
- Les pannes sont influencées par la vétusté et le manque de maintenance préventive.
- Une part limitée d'aléatoire subsiste.
- La réparation est assurée par l'équipe centralisée de techniciens.
- La taille de cette équipe influence les délais d'intervention.

### 12.2 Mini-jeux prioritaires

**Validé**
Deux mini-jeux sont prioritaires pour la V1 :

1. **Dépannage hydraulique** : intervention sur un schéma simplifié de type P&ID, avec manœuvre de vannes et utilisation éventuelle d'une ligne de secours pour rétablir un flux.
2. **Gestion des flux** : intervention sur les convoyeurs et les circuits de circulation des matières.

Les mini-jeux sont déclenchés par certains incidents pendant la campagne. Une réussite réduit le temps d'arrêt ; un échec fait perdre du temps sans nécessairement aggraver la situation.

**Ouvert**
- Règles détaillées, fréquence, difficulté, durée et interface de chaque mini-jeu.
- Autres mini-jeux possibles à une date ultérieure : diagnostic électrique, réglages ou intervention mécanique.

---

## 13. Orientation technique

**Hypothèses de travail, non validées**
- Moteur envisagé : Godot 4.
- Langage à choisir : GDScript ou C#.
- Développement assisté par Claude Code dans VS Code.
- Génération d'un programme Windows autonome.

Aucune architecture technique définitive n'est arrêtée à ce stade.

---

## 14. Éléments explicitement hors périmètre ou non retenus à ce stade

**Validé pour la V1**
- Pas de multijoueur.
- Pas de version mobile ou console au démarrage.
- Pas de plusieurs industries jouables simultanément.
- Pas de simulation détaillée de chaque machine ou composant.
- Pas de placement totalement libre des bâtiments.
- Pas de gestion individuelle approfondie des salariés.
- Pas de simulation concurrentielle complexe entre sucreries.
- Pas de pesage individuel des camions de betteraves.
- Pas de nécessité de vendre le sucre en morceaux pour commercialiser le sucre de base.

Ces exclusions pourront être réexaminées dans une évolution ultérieure, mais ne doivent pas être réintroduites implicitement dans la conception actuelle.

---

## 15. Points restant à traiter pendant la phase de conception

La liste suivante constitue le suivi des principaux sujets ouverts. Elle ne constitue pas encore un cahier des charges.

### Procédé et dimensionnement
- Définir les capacités et cadences cohérentes des neuf ateliers.
- Établir les bilans matière et les coefficients de conversion entre chaque atelier, depuis la tonne de betteraves réceptionnée jusqu'aux produits finis et coproduits.
- Définir les stocks intermédiaires et les règles de saturation.
- Définir les besoins en vapeur, électricité, eau et consommables.
- Vérifier les cohérences entre ateliers et infrastructures.

### Approvisionnements et stockages
- Définir les volumes unitaires des camions et la capacité initiale de l'aire à betteraves.
- Définir les règles de livraison lorsque le stockage est plein.
- Définir les capacités de stockage et les règles de conservation.
- Définir la durée de conservation des pulpes humides.

### Énergie et utilités
- Dimensionner la chaudière initiale et ses extensions.
- Définir la transition vers la biomasse et ses besoins logistiques.
- Définir les scénarios d'évolution de la production électrique.
- Dimensionner l'eau et la STEP.

### Produits et économie
- Définir les conditions de déblocage du sucre en morceaux et des pellets.
- Définir les capacités et coûts des ateliers de diversification.
- Définir les contrats d'approvisionnement et les contrats clients.
- Définir les coûts, prix, salaires, charges et recettes.

### Organisation et calendrier
- Définir les effectifs nécessaires.
- Définir le calendrier des campagnes et de l'intercampagne.
- Définir l'échelle de temps et les vitesses de jeu.
- Définir les règles de maintenance, d'incident et les mini-jeux.

### Conception technique et visuelle
- Confirmer le moteur et le langage.
- Définir l'architecture technique après stabilisation de la conception fonctionnelle.
- Définir l'interface, la direction artistique et le pipeline de ressources.

---

## 16. Arbitrages et corrections de formulations antérieures

Cette section conserve les évolutions importantes pour éviter qu'une ancienne formulation soit réintroduite par erreur.

| Sujet | Ancienne formulation ou proposition | Décision de référence |
|---|---|---|
| Réception des betteraves | Réception avec pesage et suivi du poids de chaque livraison | Les camions ont une capacité standardisée ; pas de pesage individuel ni de pont-bascule nécessaire au gameplay |
| Atelier final de la chaîne de base | Séchage, refroidissement et conditionnement en sacs | Séchage et refroidissement ; le sucre vrac est stocké en silo et vendu directement |
| Sucre en morceaux | Pouvait être interprété comme une activité disponible dès le départ | Atelier de fabrication à débloquer ultérieurement ; stockage dédié |
| Pulpes | Coproduit dont la valorisation restait à définir | Stockage des pulpes humides, durée de conservation limitée, évacuation payante avant déshydratation, puis possibilité de produire et vendre des pellets |
| Stockage du sucre | Stockage générique ou entrepôt de produits finis | Silos à sucre vrac pour le produit initial ; stockage distinct pour le sucre en morceaux |
| Stockage des pellets | Stockage non défini | Silos à pellets distincts des silos à pulpes humides |
| Approvisionnement en betteraves | Contrats d'approvisionnement uniquement envisagés | Contrats à livraisons automatiques et commandes ponctuelles supplémentaires |
| Eau | Approvisionnement et traitement regroupés de manière générique | Eau de ville facturée ; STEP distincte et évolutive |
| Production d'énergie | Achat au réseau électrique envisagé comme possibilité | Production électrique autonome sur site, initialement au gaz, avec évolutions avancées à définir |

---

## 17. Règle de clôture de la phase de conception

La phase actuelle ne sera considérée comme terminée que lorsque :
- les éléments fonctionnels nécessaires auront été recensés ;
- les relations entre ateliers, ressources, stocks, personnel et économie auront été examinées ;
- les décisions incompatibles auront été identifiées et arbitrées ;
- les paramètres encore ouverts auront été clairement distingués des décisions validées ;
- aucune proposition non acceptée ne sera présentée comme une règle acquise.

À l'issue de cette phase seulement, le contenu stabilisé de ce référentiel servira de base à la rédaction du cahier des charges détaillé.
