Sur les routes à double sens, un moment particulièrement critique est lorsqu’un véhicule essaie de dépasser un poids lourd (ex. camion, bus, autocar...) ou un engin agricole. Dans cette situation, la visibilité du véhicule est très faible sur l’autre voie (sens inverse). Le conducteur souhaitant dépasser ne peut pas facilement déterminer si le dépassement, en toute sécurité, est possible. Les conditions météorologiques dégradées et la nuit augmentent encore la dangerosité d’un tel dépassement.

L’idée de ce projet est de concevoir un dispositif IoT à installer sur les poids lourds et les engins agricoles, capable de détecter la présence de véhicules dans l’autre sens et d’afficher un message aux véhicules à l’arrière pour alerter en cas d’impossibilité de dépassement. Il doit aussi permettre de collecter des statistiques sur le nombre de situations de dépassement dangereuses, leurs dates, heures, durées et les routes sur lesquelles elles ont eu lieu. Ces statistiques, complètement anonymes, permettent de mieux comprendre le trafic routier et d'adapter ainsi l'aménagement et la signalétique routière.

Infra
=====
- On a besoin de faire quoi avec ces stats ? On en s'en sert pour quoi ? Tous les combien de temps sont elles utilisées ?

Hardware
============
- Configuration nécessaire ? Comment faire ? Plug and play? -> si oui comment?
  Plug and play, 
- Comment séparer les différents composants (centralisation des données), capteur, panneau
- Les conducteurs doivent ils avoir un retour ? -> NON a eviter meme
- Quelles sont les limites en terme physique (taille du panneau à l'arrière ...)
- Quelles sont les contraintes en matière de protection (doit supporter les intempéries, etc.)

+ Proposition : On propose un capteur à l'avant qui regarde la route et un panneau d'affichage à l'arrière

Software
========
- Est-ce que le dispositif modulable ? Longueur du camion, etc ? Types de camions ?

Tracteurs, camions, remorques ou non (mais fixe)

- Besoin d'un soft pour gérer les stats ? Est-ce qu'on doit traiter les stats de notre côté ?

Nbr de dépassements dangereux

Divers
======

- Quel(s) sont le(s) but(s) de ce projet ?

sauver des vies

- Est-ce que le dispositif sera sujet à des évolutions ?
-> non mais moyen de mettre a jour les dispositifs ()
  
- Que faire concernant la maintenance, réparation ou remplacement ?

- Durée de vie ~1 an

Camion, tracteurs, + remorques 
par contre, une fois que c'est choisi ca ne change pas, donc configuration unique.



- Question par rapport aux tâches du product owner surtout le code, est-ce qu'on doit réfléchir à tous les problèmes du capteurs ou juste à coder le logiciel ?
- Est-ce qu'on est concerné par les contraintes hardware ? Ex : Taille panneau, problème de connexion ? Où on part du principe que l'hardware est fait et qu'on fait du soft uniquement ?
- Contraintes dans les user story ?
- Qui a accès aux statistiques ?
- Est-ce qu'on jarte le responsable d'entreprise des personas ?
- Est-ce qu'on garde les données statistiques par véhicule ? (C'est pas demandé de base dans le README je crois)


Les contraintes,on les mets où ?
