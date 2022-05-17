# Projet d'Aministartion des systèmes et réseaux

Le projet consiste à créer de A à Z un réseau d'entreprise comprenant différent services.


# Cahier des charges

## Description de l’entreprise
Le client est l’entreprise WoodyToys (WT), qui fabrique de manière artisanale des jouets en bois. Elle travaille en B2B, c’est-à-dire qu’elle ne s’occupe pas de la vente directe de ses produits, mais les fournit à des revendeurs (magasins de jouets).

L’entreprise possède une infrastructure informatique pour le support de la production et des services comptables et commerciaux. Cette infrastructure fournit actuellement principalement un service Web, et utilise un service extérieur pour le service Mail. Elle utilise une téléphonie classique.

L’entreprise souhaite remplacer ses serveurs utilisant des technologies dépassées, et fait appel à vous pour la phase de conception et de validation d’une nouvelle infrastructure d’hébergement des services informatiques.

### Structure de l’entreprise
L’usine comporte un atelier où sont fabriqués les jouets, un hangar de stockage d’où partent les produits vers les revendeurs, le bureau du directeur et les bureaux où travaillent les employés. Parmi ceux-ci, il y a des comptables, des commerciaux et une secrétaire. L’usine dispose d’une connexion à Internet.

L’atelier, le hangar et le bureau sont reliés via une infrastructure IP. Un réseau Wifi permet aux employés d’utiliser des appareils portables (laptops et smartphones). Le plan ci-dessous représente schématiquement l’organisation des bureaux de l’entreprise.

![image](https://user-images.githubusercontent.com/71312671/168784865-d247f541-ef7e-4b34-8c1c-98b2a8d9e297.png)


## Objectif du client
Avant d’investir dans de nouveaux serveurs, l’entreprise souhaite évaluer la faisabilité de ce projet en faisant développer un prototype des configurations des services dont elle a besoin.

## Intervenants
L’entreprise WoodyToys sera représentée par Mr Cooper, qui est l’informaticien en charge de l’infrastructure informatique. Le prestataire est le département TI de la haute école EPHEC, représentée par Mme Van den Schrieck. Il est convenu que la tâche de prototypage sera confiée aux étudiants de 2ème bachelier dans le cadre d’un de leur projet.

## Public cible et utilisateurs
Le prototype simulera une infrastructure qui sera exploitée par plusieurs types d’utilisateurs :

Les employés de l’entreprise, utilisateurs des services internes
Les clients de l’entreprise, via le site web public
Les revendeurs des produits de l’entreprise (clients B2B)
En ce qui concerne le prototype, il est destiné à deux personnes en particulier :

Mr Delfosse, CEO de l’entreprise, qui doit valider l’adéquation des services sur base du prototype du point de vue fonctionnel
Mr Cooper, présenté plus haut, qui, en cas de validation d’un prototype, sera chargé de la mise en oeuvre des configurations produites sur base de la documentation produite par les prestataires de l’Ephec.

## Planification et organisation
Les intervenants se sont accordés sur la date du 30 juin pour la présentation des prototypes les plus convainquants à l’entreprise. Cette présentation sera réalisée par Mme Van den Schrieck, qui aura au préalable évalué l’ensemble des prototypes produits par les étudiants et aura sélectionné ceux qui répondent au cahier des charges.

## Demandes fonctionnelles
### Services internes
Les postes des employés doivent pouvoir accéder à Internet et également aux services internes et externes, via un adressage IP adéquat. L’entreprise souhaite ne pas dépendre de fournisseurs de services extérieurs pour la résolution de noms. Un contrôle du trafic web généré par les employés pourrait s’avérer intéressant.

Au niveau du prototype, Mr Cooper souhaite que vous modélisiez quelques postes clients reprenant une configuration classique, afin de valider les fonctionnalités que vous aurez configurées.

### Web
La vente des produits s’effectue uniquement en B2B (revendeurs). L’entreprise dispose d’un portail Web public présentant ses produits (www.woodytoys.be), et d’un site de vente en ligne réservé aux revendeurs (b2b.woodytoys.be). Le code source de ces trois sites est pré-existant, il s’agit d’un site statique en HTML/CSS pour le site vitrine, et d’un site dynamique en PHP/MySQL pour le site de vente en ligne. Pour le prototype, le client déclare pouvoir se contenter d’un proof of concept composé de pages web très simples utilisant les technologies sus-mentionnées.

### Mail
L’entreprise souhaite fournir une adresse mail à chacun de ses employés, au format nom.prenom@woodytoys.be. Elle dispose également d’adresse smail génériques, dont actuellement :

* contact@woodytoys.be, redirigée chez la secrétaire
* b2b@woodytoys.be, redirigée sur les commerciaux
Les employés doivent pouvoir consulter leur courrier électronique et en envoyer à l’aide d’un client mail classique (lourd) (pas de webmail) depuis les postes de l’entreprise. Ils doivent également être en mesure d’utiliser leur mail en déplacement ou à domicile.

### Gestion des fichiers
L’entreprise souhaite réorganiser son système de fichiers d’entreprise, et vous demande d’explorer les technologies et de proposer une solutions qui permet une mise à disposition aisée de répertoires de travail personnels pour les employés, ainsi que des répertoires partagés pour les différents départements et un répertoire commun à toute l’entreprise. Ces fichiers ne doivent être accessibles qu’au sein de l’entreprise, et une attention particulière doit être portée à la sécurisation des données.

Une attention particulière devra être portée à la facilité d’accès aux fichiers pour les utilisateurs. L’accès souhaité est via le navigateur natif des postes clients.

### Téléphonie IP
Au niveau du service téléphonique, il vous faudra concevoir un nouveau plan d’adressage en téléphonie IP reprenant les besoins suivant :

1. L’entreprise doit être accessible en VoIP depuis Internet, afin que des clients puissent la contacter. L’adresse de contact est contact@woodytoys.be. Les appels doivent aboutir sur le poste de la secrétaire.

2. Les employés de l’entreprise doivent pouvoir communiquer entre eux, à l’intérieur de l’entreprise, mais également depuis l’extérieur dans le cas des commerciaux qui sont souvent en déplacement. Les communications identifiées sont les suivantes :

    * Les ouvriers : Ils disposent d’un poste de téléphonie IP dans leur atelier et dans le hangar pour joindre les autres départements internes.
    * La secrétaire : Elle dispose d’un PC sur lequel se trouve un softphone, lui permettant de contacter n’importe qui.
    * Le service comptable : Réparti dans deux bureaux, il dispose d’un numéro unique permettant de joindre le premier comptable disponible, ainsi que d’un numéro spécifique par bureau. Les comptables peuvent joindre l’extérieur et tout le monde en interne à l’exception du directeur.
    * Les commerciaux : Réunis dans un même bureau, ils peuvent joindre l’extérieur et tout le monde en interne à l’exception du directeur. Ils disposent de smartphones avec lesquels ils peuvent téléphoner en déplacement.
    * La direction : Un numéro qui peut joindre tous les autres postes internes ainsi que l’extérieur. Ce numéro ne peut pas être joint directement, les appels devant transiter préalablement par la secrétaire.
3. Les employés doivent pouvoir disposer d’une boîte vocale. L’entreprise est en outre engagée dans le rachat d’une entreprise concurrente. Il vous est donc demandé d’étudier dès maintenant la fusion des deux réseaux téléphoniques. Cela signifie que :
    * Les deux plans d’adressage doivent être fusionnés en minimisant les changements nécessaires
    * Les deux serveurs de téléphonie doivent être configurés pour que les deux sites puissent se contacter en utilisant le nouveau plan d’adressage interne.
Enfin, de manière secondaire, il vous est demandé d’explorer des fonctionnalités supplémentaires, comme par exemple la visio-conférence ou l’utilisation de téléphones ou de passerelles SIP vers la téléphonie classique.

### Fonctionnalités supplémentaires
Si le temps disponible le permet, le client souhaite également explorer différentes possibilités, et si possible les implémenter dans le prototype :

un système d’annuaire type LDAP
un système de gestion des adresses IP (IPAM)
un système centralisé de monitoring de l’infrastructure
..
## Contraintes
L’entreprise souhaite ne pas devoir dépendre de fournisseurs de services extérieurs (hors accès internet) pour l’ensemble de ses services réseaux.
