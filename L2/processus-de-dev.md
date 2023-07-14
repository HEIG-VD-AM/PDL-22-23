# Processus de développement

Nous sommes partis sur un processus de développement agile. En effet, nous aurons besoin de faire beaucoup de prototypage et avons donc besoin de cycles itératifs pour converger vers une solution pérenne et stable.

Arguments :

- Q/A : Besoin de prototyper et de tester
- Moins de problèmes durant l'intégration (surtout qu'on est sur un projet embarqué)
- Taille du projet raisonnable, peu de risque que le projet devienne de plus en plus difficile et coûteux.
- Le client peut tester et valider les prototypes en cours de projet.
- Le cahier est assez pauvre, on doit pouvoir être évolutif 
- En cascade avec du système embarqué c'est compliqué (choix du hardware très tôt dans le projet et pas flexible)

## Kanban

Pour notre kanban, nous avons utilisé 5 colonnes : 
- Backlog : toutes les tâches du projet (product backlog)
- To do : Les tâches à réaliser de l'itération en cours pas encore (sprint backlog)
- In progress : Les tâches qui sont en train d'être réalisés
- Testing : Les tâches terminées mais qui doivent être testées
- Done : Les tâches qui sont terminées telles qu'elles seront en production

### Passage Backlog -> To Do

Les tâches sont choisies au début du cycle de l'itération en fonction de ce qui a déjà été fait et leur priorité.

### Passage To Do -> In Progress

Un ingénieur choisit une tâche par rapport à sa priorité, la priorité la plus haute passe en premier.

### Passage In Progress -> Testing

Une fois la tâche terminée, celle-ci passe dans la phase de test, selon la nature de la tâche divers types de tests seront réalisés

Des tests concernant uniquement la fonctionnalité implémentée par la tâche seront réalisées et dans une seconde partie des tests après avoir intégré la fonctionnalité seront réalisés.

Précisément on adoptera usuellement le processus de tests suivants :

1. Tests unitaires
2. Tests d'intégration

### Passage Testing -> To Do

Si un ou plusieurs tests échouent, que cela soit avant ou après l'intégration, ils repassent directement en To Do.

### Passage Testing -> Done

Si tous les tests sont passés et que l'intégration s'est faite avec succès alors le la tâche est considérée comme terminées

## Pratiques 

### Intégration continue

Pouvoir intégrer rapidement permettra d'éviter les conflits et les potentiels soucis.

On doit garantir une certaine qualité sur le produit final. A la fois pour le matériel et à la fois pour le logiciel, chaque modifications même mineure doit pouvoir être testée et ne doit pas produire de régression, l'intégration continue permet de réduire les risques.

Également, on facilite le travail si on teste nos modifications plus souvent et surtout de manière automatique, on évite les conflits et les soucis sont beaucoup plus facilement détectables et résolvables.

### Pair programming

L'avantage du pair programming est d'avoir un double-contrôle sur le travail et garantit une plus-value plus grande sur le travail. Certes plus lente mais cela permet d'arriver à un produit contrôlé et sécurisé, ce qui est indispensable pour un système embarqué en production sur la route.

### Cycle hebdomadaire

Afin de compléter l'intégration continue et d'éviter les problèmes conséquents à la fin du projet, on peut implémenter la pratique du cycle hebdomadaire.

Le retour par équipe chaque semaine peut permettre de déceler les problèmes très vite afin d'éviter que ces derniers se gangrènent et affectent le projet de manière trop importante.

D'autant plus que le projet est un système IoT qui va impliquer plusieurs corps d'ingénierie qui peut revenir à des coûts chers de prototypage si les équipes ne travaillent pas ensemble et ne mettent pas souvent leurs avancées en commun. Exemple, un problème hardware avec le matériel, il peut être changé rapidement, évitez de perdre du temps et surtout de l'argent.

Cela évitera également par la suite également des mises à jour trop souvent, ce qui impliquerait de se déplacer sur place pour mettre à jour les systèmes un par un.

## Personas

### Conducteur de camion/engin agricole
Jean-Marie est un professionnel de la conduite de camion/engin agricole âgé de 40 ans. Il a passé une grande partie de sa vie sur les routes et est conscient des risques liés aux dépassements de véhicules sur les routes à double sens. En raison de la taille de son camion ou engin, il est difficile pour lui d'avoir une bonne visibilité lors des dépassements, ce qui peut augmenter le risque d'accident. Jean-Marie est intéressé par un dispositif qui peut l'aider à éviter les accidents lors des dépassements en lui fournissant des informations sur les véhicules qui se trouvent dans son angle mort.

### Conducteur de voiture
Brigitte est une automobiliste âgée de 28 ans qui partage la route avec les camions et les engins agricoles. Elle est consciente des risques liés aux dépassements de véhicules qui ne permettent pas d'avoir une bonne visibilité, ce qui peut augmenter le risque d'accident. Brigitte est intéressée par un système qui peut l'alerter en cas de danger lors d'un dépassement en lui fournissant des informations sur les véhicules qui se trouvent dans son angle mort.

### Responsable des statistiques
Sarah est une analyste de données âgée de 32 ans qui travaille pour une entreprise de transport. Elle a une expérience de 5 ans dans le domaine et est responsable de la gestion des statistiques. Sarah est intéressée par un système qui peut fournir des données précises et fiables sur les accidents de la route impliquant des camions et des engins agricoles. Elle souhaite utiliser ces données pour identifier les tendances et les problèmes récurrents afin de mettre en place des mesures préventives pour réduire le risque d'accidents.

### Technicien d'installation d'appareils IoT
David, 35 ans, est un technicien spécialisé dans l'installation de dispositifs IoT pour améliorer la sécurité routière. Il est passionné par la technologie et dévoué à son travail pour rendre les routes plus sûres pour tout le monde. Son objectif est d'installer des dispositifs qui permettent d'éviter les dépassements dangereux des voitures sur les camions et engins agricoles. Il est capable de résoudre rapidement les problèmes liés à l'installation et est un bon communicateur pour expliquer l'utilisation des dispositifs aux clients.

_NB : Un personas responsable de la sécurité routière est hors cadre par rapport à ce projet. C'est une personne qui demande simplement accès aux statistiques à l'entreprise mandataire._

## Fake Personas

Les fake personas sont des personas internes à l'équipe de développement qui représentent les besoins "invisibles" aux personas classiques.

### Product Owner
Sophie, 32 ans, est Product Owner dans une entreprise de développement de logiciels. Elle est chargée de représenter le produit auprès de l'équipe de développement et de défendre les intérêts des clients. Elle est constamment à l'écoute des clients pour comprendre leurs besoins et leurs attentes, tout en prenant en compte les contraintes des ingénieurs. Sophie a une grande capacité à communiquer et à négocier avec les parties prenantes pour s'assurer que les objectifs du produit sont atteints dans les délais impartis. Elle est également une personne organisée et méthodique qui est capable de hiérarchiser les tâches en fonction de leur importance pour atteindre les objectifs du produit. Cependant, Sophie peut rencontrer des difficultés lorsqu'elle doit arbitrer entre les demandes des clients et les contraintes techniques de ses équipes d'ingénieurs.

### Développeur de l'équipe
Jeanne, 28 ans, est une développeuse expérimentée dans le domaine de l'IoT. Elle est passionnée par les nouvelles technologies et les défis techniques. Elle a déjà travaillé sur des projets similaires et a une expérience en programmation embarquée et en communication sans fil. Elle est capable de comprendre les spécifications techniques et les exigences de sécurité du projet et peut concevoir des systèmes fiables et efficaces. Elle a une bonne compréhension des normes et des réglementations en matière de sécurité routière et est en mesure d'adapter le développement du dispositif IoT en fonction de celles-ci. Elle travaille bien en équipe et est capable de communiquer efficacement avec les autres membres de l'équipe, tels que les ingénieurs mécaniques et électroniques, pour assurer l'intégration réussie du dispositif IoT dans les camions et engins agricoles.


## User stories

### Technicien d'installation d'appareils IoT

**En tant que** technicien d'installation

**Je veux** avoir un manuel d'installation

**Afin d'** installer rapidement le dispositif et éviter les erreurs

Tâches :
- Document d'installation simple et illustré (p = 20h, a = 15h, o = 10h) E = 15 et SD = 5/3

**Je veux** avoir un manuel de dépannage complet

**Afin de** résoudre les pannes rapidement et garantir le bon fonctionnement du dispositif.

Tâches : 
- Document de dépannage complet (p = 48h, a = 36h, o = 24h) E = 36 et SD = 4

**Je veux** pouvoir installer le dispositif en moins de 10 minutes

**Afin d'** optimiser mon temps de travail 

Tâches :
- Vérifier que le dispositif est installable dans le temps imparti (p = 3h, a = 2h, o = 1h) E = 2 et SD = 1/3

### Conducteur de camion/engin agricole

**En tant que** conducteur de camion/engin agricole

**Je veux** pouvoir conduire sans distraction

**Afin de** protéger ma sécurité et celle des autres usagers de la route

Tâches :
- Vérifier que le conducteur peut accéder confortablement à son siège avec le dispositif (p = 3h, a = 2h, o = 1h) E = 2 et SD = 1/3
- Vérifier que le conducteur peut conduire de manière visible avec le dispositif (p = 3h, a = 2h, o = 1h) E = 2 et SD = 1/3

### Conducteur de voiture

**En tant que** conducteur de voiture

**Je veux** apercevoir un message d'alerte simple ne provoquant pas de distraction

**Afin de** protéger ma sécurité et celle des autres usagers de la route

Tâches :
- Vérifier que le panneau n'est pas une source de distraction (p = 3h, a = 2h, o = 1h) E = 2 et SD = 1/3
- Vérifier que le panneau est compréhensible par les usagers de la route (p = 3h, a = 2h, o = 1h) E = 2 et SD = 1/3

### Responsable des statistiques

**En tant que** responsable des statistiques

**Je veux** pouvoir créer un compte sur le site web

**Afin de** pouvoir accéder aux statistiques

Tâches :
- Page de création de compte (p = 8h, a = 5h, o = 2h) E = 5 et SD = 1

**Je veux** me connecter au site web 

**Afin de** afin de visualiser les données et de les exporter

Tâches :
- Page de connexion au site web (p = 3h, a = 2h, o = 1h) E = 2 et SD = 1/3

**Je veux** pouvoir visualiser de manière simple et rapide (max. 30 secs de chargement) les données sur le site web

**Afin de** analyser les données

Tâches :
- Page web de visualisation des données (p = 72h, a = 48h, o = 24h) E = 48 et SD = 8
- Pouvoir sélectionner une plage temporelle, une zone géographique et un véhicule en particulier (p = 9h, a = 6h, o = 3h) E = 6 et SD = 1
- Vérifier que les graphiques se fassent et s'affichent en moins de 30 secondes (p = 3h, a = 2h, o = 1h) E = 2 et SD = 1/3

**Je veux** récupérer les données brutes en format CSV sur le site web

**Afin de** pouvoir les analyser et établir des conclusions

Tâches :
- Fonctionnalité d'export vers CSV sur le site web (p = 3h, a = 2h, o = 1h) E = 2 et SD = 1/3

**Je veux** rapatrier les données des dispositifs en moins de 1 minute

**Afin d'** avoir les données les plus à jour

Tâches : 
- Créer une base de données centralisée capables d'accueilir les données (date/heure, durée, numero du dispositif et coordonnées GPS) des unités de contrôle (p = 8h, a = 5h, o = 2h) E = 5 et SD = 1
- Fonctionnalité sur le site permettant de rapatrier les données manuellement (p = 3h, a = 2h, o = 1h) E = 2 et SD = 1/3
- Vérifier que le rapatriement des données soit fait dans la minute (p = 3h, a = 2h, o = 1h) E = 2 et SD = 1/3

_NB: on entends par "données" les nombres de dépassements leurs dates et heures, leurs coordonnées GPS et finalement leurs durées tels que présentés dans le cahier des charges_

### Product Owner

**En tant** que Product Owner

**Je veux** pouvoir mettre les dispositifs à jour à distance

**Afin de** s'assurer d'avoir un dispositif toujours à jour et de diminuer les risques

Tâches :
- Installer et configurer un serveur FTP sur l'unité de contrôle (p = 3h, a = 2h, o = 1h) E = 2 et SD = 1/3
- Installer et configurer le SSH sur un dispositif (p = 3h, a = 2h, o = 1h) E = 2 et SD = 1/3
- Installer et configurer une antenne connectée au réseau sur l'unité de contrôle (p = 6h, a = 4h, o = 2h) E = 4 et SD = 2/3

**Je veux** pouvoir activer le panneau d'affichage en fonction d'un capteur de distance

**Afin de** prévenir les dépassements dangereux

Tâches :
- Configurer un capteur de distance qui détecte des véhicules (p = 36h, a = 24h, o = 12h) E = 24 et SD = 4
- Transmettre les données du capteur de distance à l'unité de contrôle en temps réel (p = 9h, a = 6h, o = 3h) E = 6 et SD = 1
- Transmission des données au panneau depuis le dispositif (p = 3h, a = 2h, o = 1h) E = 2 et SD = 1/3
- Déterminer le seuil indiquant un dépassement dangereux (distance camion-voiture) (p = 36h, a = 24h, o = 12h) E = 24 et SD = 4
- Sélection du matériel conformément au cahier des charges (p = 12h, a = 9h, o = 6h) E = 9 et SD = 1
- Configurer un accéléromètre pour détecter la vitesse du camion (p = 3h, a = 2h, o = 1h) E = 2 et SD = 1/3
- Déterminer la taille du panneau d'affichage à l'arrière du camion (p = 3h, a = 2h, o = 1h) E = 2 et SD = 1/3
- Mise en place de l'affichage sur le panneau selon le cahier des charges (p = 6h, a = 4h, o = 2h) E = 4 et SD = 2/3

**Je veux** pouvoir sauvegarder les données sur l'unité  de contrôle

**Afin de** pouvoir les récupérer plus tard

Tâches :
- Sauvegarder la date/heure, la durée et les coordonnées GPS des dépassements sur le serveur FTP interne à l'unité de contrôle (p = 8h, a = 6h, o = 4h) E = 6 et SD = 2/3

**Je veux** que les données soient rapatriées automatiquement tous les jours à minuit.

**Afin de** pouvoir avoir des données à jour 

Tâches :
- Création d'un script de rapatriement des données (p = 3h, a = 2h, o = 1h) E = 2 et SD = 1/3
- Activation du script de rapatriement des données locales (p = 3h, a = 2h, o = 1h) E = 2 et SD = 1/3

### Développeur de l'équipe

**En tant** que développeur de l'équipe

**Je veux** avoir un dispositif prêt à l'utilisation

**Afin de** pouvoir commencer le développement sur celui-ci 

Tâches :
- Configuration de base du dispositif (login, etc...) (p = 3h, a = 2h, o = 1h) E = 2 et SD = 1/3
- Création d'un fichier de configuration stockant les paramètres du dispositif (p = 8h, a = 4h, o = 2h) E = 13/3 et SD = 1
- Implémentation de l'algorithme de détection de dépassements (p = 12h, a = 8h, o = 5h) E = 49/6 et SD = 7/6

_Durée :_
- _p = pessimistic_
- _a = average_
- _o = optimistic_

## PERT

Estimation de la valeur attendue (E) du projet = 240.5
 
Calcul de l'erreur (SD) = 11.19

Intervalles de confiance :

- 68.26% = [229.31, 251.69]  
- 95.44% = [218.12, 262.88]
- 99.72% = [206.93, 274.07]

_NB: Les valeurs ci-dessus sont en heures._

## Réalisation de la première itération
Pour la première itération nous avons choisi de nous axer sur 2 tâches principales.
La première étant de directement déterminer les contraintes du matériel afin de pouvoir commencer à soigneusement choisir les différentes pièces.

Mais nous avons décidé de commencer par les pages du site, car celle-ci ne sont pas dépendantes des données des capteurs et/ou du matériel directement.



