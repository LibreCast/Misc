Communiquer, s'exprimer, partager simplement et librement, c'est ce à quoi nous, en tant qu'internautes, aspirons de plus en plus. Et si de nombreuses plates-formes proposent de répondre à cette demande, elles présentent pourtant souvent des inconvénients notables. C'est dans l'optique de créer un moyen de partage de vidéos qui corresponde à nos attentes que nous avons créé LibreCast.

# Comprendre LibreCast

##Pourquoi LibreCast ?

Des géants comme Youtube, Dailymotion ou encore Viméo sont parvenus à s'imposer dans la sphère audiovisuelle d'Internet, concentrant l'accès à des vidéos et/ou musiques. Cependant chacun d'eux aborde le concept de plate-forme de partage de la même manière : les données sont centralisées et c'est la plate-forme elle-même qui gère les problèmes de droits d'auteurs. Ainsi, il leur est nécessaire :
 * de stocker toutes ces données eux même
 * d'officialiser une politique de gestion des droits d'auteurs et donc également un moyen de contrôle
 
Ce sont ces deux points que LibreCast cherche à contourner, tout en paliant aux conséquences que cela engendre. Notamment, ne pas stocker les vidéos nous-même implique la mise en place d'un système de peer to peer (p2p), et donc une manière de partager tout à fait différente, de personne à personne. De plus, cela entraîne une prise en charge des droits d'auteur personnelle, sans responsabilité de la plate-forme. Par exemple, Youtube analyse chaque vidéo grâce à un algorithme (Content ID) afin de détecter une quelconque atteinte à des droits d'auteur. Cette méthode rencontre de nombreux problèmes (pas toujours efficace et vidéos bloquées par erreur). 

L'objectif de LibreCast, c'est de proposer un partage plus simple, garantissant une plus grande liberté d'expression et laissant chacun libre de poser des limites de droits sur son propre contenu.

## Comment ça marche ?
_à compléter_

# Réalisation de l'Interface Utilisateur

## Ergonomie, simplicité et accessibilité
Une Interface Utilisateur (UI) accessible occasionne des contraintes importantes. En effet, il est important de garantir une interface intuitive et centrée utilisateur. La perception d’une application se fait en fonction de son apparence autant que de sa simplicité d’utilisation. 

> L 'exemple du tactile illustre bien cette importance :
> L'informatique connaît une véritable révolution avec la mise au point des interfaces tactiles. Elles simplifient alors notablement le dialogue avec l'utilisateur. 
> _à compléter_

> On sait également que de nombreux smartphones équipés de fonctions attractives ont été des échecs commerciaux parce que leur interface étaient trop complexes et difficiles à utiliser.

Nous avons longuement pensé l'Interface Utilisateur de LibreCast, la voulant à la fois simple et fonctionnelle. Bien plus que la seule esthétique du projet, c'est elle qui relie utilisateur et application. Elle se doit d'être organisée et réfléchie, mais surtout adaptée au projet. La coder nous-même garantit alors une main prise sur sa conception. 

## Réflexions sur l'UI de LibreCast
Avant tout, il a fallu revenir aux bases : prendre un tableau et un marqueur et essayer, effacer, recommencer, réorganiser les éléments importants pour chaque fenêtre. Nous avons fait cela en gardant à l'esprit l'étendue de nos compétences. 

_(photos avec commentaires)_

Jean nous a ensuite proposé l'utilisation d'une librairie python pour la programmer : wxpython. Cet outil informatique m'étais alors inconnu et j'ai dû apprendre à m'en servir, avec l'aide de mes camarades. C'est dans ce contexte que j'ai également découvert la programmation orienté objet, alors indispensable.

# Utilisation de Wxpython

## Découpage en widgets
Cette bibliothèque python est utilisée pour la création d'interfaces graphiques. Elle est simple d'utilisation donc facilement appréhendable mais permet des réalisations intéressantes. Avec wxpython, les fenêtres sont découpées en _widgets_, c'est à dire des éléments avec lesquels l'utilisateur peut interagir et qui, assemblés, composent l'interface. Par exemple, une zone de texte (_textBox_) permet de proposer à l'utilisateur de saisir une chaîne de caractères. Celle-ci peut être récupérée à l'aide d'une fonction wxpython et éventuellement réutilisée dans un autre widget. C'est le cas lorsque l'on crée une playlist sur LibreCast.



- [ ]  Comprendre LibreCast
Pourquoi la nécessité de LIbreCast ? (ce que ça apporte de plus que les autres plate-formes de partage de vidéos)
Ses principes (droits d'auteurs et liberté etc...)
Comment ça marche concrètement ?

- [ ] Organisation du travail + cahier des charges (ensemble de ce qu'il fallait réaliser // nos compétences)
  * UI + liens entre les modules
  * GitHub = permet une meilleure collaboration, adaptée au partage de code

- [ ] Création de l'UI
  * Réflexion sur l'accessibilité (photos de Jean)
  * Les contraintes d'une UI compréhensible
  => exemple des téléphones avant tactile, puis après

- [ ] WxPython is love, WxPython is life
  * Découpage en widgets
  * Photo de découpages
  
- [ ] Analyse de l'UI de LibreCast
  * Découpage de la fenêtre
  * Pourquoi cette partie est là + utilité
  * Rendre l'UI intelligente (regex)

- [ ] Penser au delà de LibreCast = perspectives
  * Financièrement (serveurs + Google ads)
  * D'autres types de médias : textes, PDF, audio, modèles 3D, etc.

- [ ] Conclusion
  * LibreCast se veut être une tentative pour penser autrement que les autres plateformes.
  * Plus les problèmes de droits d'auteurs
  * Utilisation de technologies à la mode, en ajoutant des fonctionnalités
  * Projet qui peut encore évoluer

- [ ] Annexes
 * Code d'une fenêtre simplifiée
 * Photo de la fenêtre avec explication
 * Même photo mais découpage des widgets et sizers
