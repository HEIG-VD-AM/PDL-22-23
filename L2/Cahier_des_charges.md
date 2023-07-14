# Cahier des charges

## 1. Informations générales

Titre : Dispositif IoT évitant les accidents liés aux dépassements de gros véhicules

Auteurs :
 - ANNEN Rayane
 - DUCOMMUN Hugo
 - MARTINS Alexis
 - SAEZ Pablo

Réalisation : Jeudi 09.03.2023 à 17h au dimanche 09.04.2023 à 23h

## 2. Descriptif du projet

Le projet vise à concevoir un dispositif IoT qui peut être installé sur les poids lourds et les engins agricoles, afin de détecter la présence de véhicules dans l'autre sens de la route, permettant ainsi d'alerter les conducteurs qui souhaitent dépasser si cela n'est pas sûr. Le dispositif affichera un message pour avertir les conducteurs à l'arrière du véhicule en question. Il sera également capable de collecter des statistiques sur les situations de dépassement dangereuses, telles que les dates, heures, durées et les routes où elles ont eu lieu. Les statistiques collectées seront anonymes et aideront à mieux comprendre le trafic routier, ce qui permettra d'adapter l'aménagement et la signalétique routière pour améliorer la sécurité sur les routes à double sens.

### 2.1. Conception du dispositif IoT

Le dispositif est composé de 3 parties différentes :

1. Capteur de véhicules

Il sera situé à l'avant juste au dessus du pare-brise. Son but est de visualiser la/les route(s) opposée(s) et de détecter si un véhicule se présente. Dans ce cas, l'information est envoyée à l'unité de contrôle.

2. Panneau d'affichage

Lorsque l'unité de contrôle reçoit un nouvel enregistrement de la part du capteur, celle-ci est transmise au panneau d'affichage. Celui-ci se situe à l'arrière du camion et permet d'annoncer au potentiel véhicule derrière le camion/tracteur que s'il envisageait un dépassement, celui-ci pourrait être dangereux.
L'affichage sera éteint sauf lorsqu'un dépassement est dangereux, dans ce cas, un pictogramme universel sera affiché.

3. Unité de contrôle

C'est l'unité centrale de tout le système. Elle joue 2 rôles principaux. Le premier est d'unir les 2 composants précédents pour la transmission d'information. Le second rôle est là pour le stockage de l'information. Chaque enregistrement de dépassement dangereux est enregistré dans le système. Les informations sont automatiquement envoyées tous les soirs (00h) à une base de données sur un serveur centralisant toutes les informations sur les dépassements. Il possède aussi une connexion FTP pour l'accès direct au données si besoin, ainsi que de pouvoir apporter des modifications au logiciel.

L'unité de contrôle est directement alimentée par le camion. Elle possède aussi une carte Wi-Fi afin que la connexion avec les utilisateurs et les serveurs soit possible. Il est important que le dispositif ne dérange absoluement pas la conduite du conducteur du camion.

### 2.2. Conception du logiciel

Le logiciel du dispositif sert à réaliser les calculs afin de déterminer si le dépassement est dangereux. Une notion importante dans ce calcul est de prendre en compte la longueur du véhicule sur lequel le dispositif est installé.  

### 2.3. Gestion distante du dispositif

Il doit être possible d'accéder au dispositif IoT à distance. Le but est de permettre aux développeurs de mettre à jour les logiciels si besoin ou de changer le fichier de configuration pour la longueur de véhicule. Cela permettra aussi aux responsables des statistiques de récupérer les données pour leurs analyses. 

Sur chaque dispositif, on retrouve deux types de connexions. La première étant du FTP afin que les développeurs puissent déposer/modifier les fichiers du logiciels et ceux de configuration. La seconde connexion étant une connexion SSH pour pouvoir gérer le système du dispositif. Les identifiants de connexion à ces deux services seront établis lors de la phase d'implémentation conformément aux normes de l'entreprise mandatée.

### 2.4. Récupération des statistiques

Les données sont stockées au format CSV sur le dispositif. Elles sont mises dans une base de données MySQL commune qui servira qui sur le site web. Les accès à celle-ci seront eux aussi établis selon les mêmes normes que les connexion SSH et FTP.

 Chaque fichier représente une semaine et les lignes dans ce fichier représente une détection. Une détection est composée d'un jour et d'une heure, une position, une durée et un l'identifiant du camion (dispositif).

### 2.5. Accès des statistiques par le client

Les statistiques actuelles sont accessibles par l'entreprise mandataire via une interface web. Elle doit permettre de pouvoir visualiser les données de chaque véhicule, ainsi que les données générales. Elle permet aussi de récupérer directement les données si l'utilisateur souhaite avoir les dernières données disponibles dans les dispositifs.

## 3. Livrables

Afin que le projet soit validé lors de son rendu, le mandant doit remettre les livrables suivant :
- Dispositif IoT
- Code source du dispositif
- Accès aux serveurs FTP des dispositifs, de la base de données et au SSH
- Code source du site d'accès aux données

## 4. Validation

Chef de projet : -

Mandant : Fouad Hannah