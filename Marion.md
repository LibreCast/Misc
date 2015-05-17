_Marion Ser_

Communiquer, s'exprimer, partager simplement et librement, c'est ce à quoi nous, en tant qu'internautes, aspirons de plus en plus. Et si de nombreuses plates-formes proposent de répondre à cette demande, elles présentent pourtant souvent des inconvénients notables. C'est dans l'optique de créer un moyen de partage de vidéos qui corresponde à nos attentes que nous avons créé LibreCast.

# Comprendre LibreCast
_LibreCast_ ? C'est l'association de Libre (c'est un logiciel libre, le projet est open source _compléter !!!!_) et de Cast c'est à dire Diffusion (le principe même du logiciel est le partage).

## Pourquoi LibreCast ?

Des géants comme Youtube, Dailymotion ou encore Viméo sont parvenus à s'imposer dans la sphère audiovisuelle d'Internet, concentrant l'accès à des vidéos et/ou musiques. Cependant chacun d'eux aborde le concept de plate-forme de partage de la même manière : les données sont centralisées et c'est la plate-forme elle-même qui gère les problèmes de droits d'auteurs. Ainsi, il leur est nécessaire :

* de stocker toutes ces données eux même
* d'officialiser une politique de gestion des droits d'auteurs et donc également un moyen de contrôle

Ce sont ces deux points que LibreCast cherche à contourner, tout en paliant aux conséquences que cela engendre. Notamment, ne pas stocker les vidéos nous-même implique la mise en place d'un système de peer to peer (p2p), et donc une manière de partager tout à fait différente, de personne à personne. De plus, cela entraîne une prise en charge des droits d'auteur personnelle, sans responsabilité de la plate-forme. Par exemple, Youtube analyse chaque vidéo grâce à un algorithme (Content ID) afin de détecter une quelconque atteinte à des droits d'auteur. Cette méthode rencontre de nombreux problèmes (pas toujours efficace et vidéos bloquées par erreur). 
L'objectif de LibreCast, c'est de proposer un partage plus simple, garantissant une plus grande liberté d'expression et laissant chacun libre de poser des limites de droits sur son propre contenu.

## Comment ça marche ?

LibreCast est un logiciel de partage de vidéos, et se distingue d'autres plateformes en permettant un choix quant à l'hébergement des vidéos et en utilisant le Peer to peer. En effet, chaque internaute est capable d'envoyer des données et donc de fournir aux autres internautes des morceaux de fichiers qu'il possède déjà. Cela allège le serveur et optimise les téléchargements.

Par exemple, je souhaite optenir une vidéo sur LibreCast que Jean et Jean-Romain possèdent déjà. Mon ordinateur va récupérer des morceaux de la vidéo sur leurs deux ordinateurs en parallèle et donc assurer un téléchargement plus rapide.

# Organisation du travail

## Collaboration et Répartition
Le très connu site GitHub a hébergé notre projet et nous a permis de travailler en collaboration. En effet, toutes nos lignes de code sont mises en commun et disponibles depuis tous les ordinateurs ayant accès à Internet.

Nous avons rapidement décidé de se départager le travail afin d'être plus efficaces. Jean a créé une base de donnée, qui sauvegarde et organise toutes les informations spécifiques à un utilisateur. Jean-Romain a lié les différentes parties de l’interface utilisateur (que Jean-Romain et moi-même avons programmée) avec cette base de donnée.

Par exemple, la création d'une nouvelle playlist requiert tous ces domaines : l'utilisateur demande sa création via l'interface, qui appelle alors la base de données et y ajoute les informations nécessaires.

## Brainstorming et réflexions
Notre projet s'est construit petit à petit, partant d'une idée qui s'est préçisée au fil de nos discussions. Nous avons, avant même de penser à sa programmation, passé beaucoup de temps à réfléchir à l'architecture de LibreCast.

Il a ensuite fallu rendre possible une idée jusqu'ici théorique, pouvoir la concrétiser.

# L'Interface Utilisateur 

## Ergonomie, simplicité et accessibilité

### L'importance d'une UI réfléchie

Une Interface Utilisateur (UI) accessible occasionne des contraintes importantes. En effet, il est essentiel de garantir une interface intuitive et centrée utilisateur. La perception d’une application se fait en fonction de son apparence autant que de sa simplicité d’utilisation. Ce premier lien créé avec l'utilisateur doit le guider avec simplicité. 

Nous avons longuement pensé l'Interface Utilisateur de LibreCast, la voulant à la fois simple et fonctionnelle. Bien plus que la seule esthétique du projet, c'est elle qui relie utilisateur et application. Elle se doit d'être organisée et réfléchie, mais surtout adaptée au projet. La coder nous-même garantit alors une main prise sur sa conception. 

### Réflexions sur l'UI de LibreCast
Avant tout, il a fallu revenir aux bases : prendre un tableau et un marqueur et essayer, effacer, recommencer, réorganiser les éléments importants pour chaque fenêtre. Nous avons fait cela en gardant à l'esprit l'étendue de nos compétences. 

(photo1)

* à gauche : première esquisse de la fenêtre principale de LibreCast côté lecture et recherches
* à droite : fenêtre côté téléchargement

On s'est vite aperçus que le premier dessin surchargeait bien trop la page et rendait la lecture difficile. Il a fallu essayer à nouveau.

(photo2)

* à gauche : deuxième essai de la fenêtre principale, très proche du rendu final
* à droite : fenêtre de téléchargement indépendante

Le deuxième dessin nous a permis de mieux appréhender l'interface et de planifier les étapes de sa construction.

## Réalisation de l'interface

### Utilisation de Wxpython

Jean nous a ensuite proposé l'utilisation d'une librairie python pour la programmer : wxpython. Cet outil informatique m'étais alors inconnu et j'ai dû apprendre à m'en servir. C'est dans ce contexte que j'ai également découvert la programmation orienté objet, alors indispensable.

Cette bibliothèque python est utilisée pour la création d'interfaces graphiques. Elle est simple d'utilisation donc facilement appréhendable tout en permettant des réalisations intéressantes. 

### Découpage en widgets

Avec wxpython, les fenêtres sont découpées en _widgets_, c'est à dire des éléments avec lesquels l'utilisateur peut interagir et qui, assemblés, composent l'interface. Par exemple, une zone de texte (_textBox_) permet de proposer à l'utilisateur de saisir une chaîne de caractères. Celle-ci peut être récupérée à l'aide d'une fonction wxpython et éventuellement réutilisée dans un autre widget.

(photo3)

Par exemple, la fenêtre principale de LibreCast est composée d'un _Frame_ ou cadre, lui même divisé en deux parties : un _TreeCtrl_ ou arbre et une _ListCtrl_ ou liste des vidéos. Puis l'arbre est aussi redécoupé etc... 

Les commentaires sont très importants dans cette partie du code car permettent de ne pas s'y perdre ! (voir Annexe)

## Rendre l'interface intelligente

### Convertisseur

Il était nécessaire de convertir des tailles de fichiers et des durées dans la fenêtre de téléchargement de LibreCast. En effet, il faut que ces données soient directement lisibles par l'utilisateur.

Ainsi, 

### Regular Expressions (Regex)

Une regular expression ou Regex est une chaîne de caractères (motif) qui décrit une syntaxe particulière. Elle est utilisée dans le contrôle de texte.

Par exemple, lorsque l'on souhaite ajouter un flux dans LibreCast, il faut entrer une url. Le rôle de la regex est alors de vérifier que le texte entré correspond bien à la syntaxe d'une URL. (voir Annexe)

La difficulté réside dans le choix de notre regex. Elle ne doit pas être trop rigoureuse au risque de refuser trop d'URLs (par exemple des URLs du type www.raspberrypi.html, qui divergent de la syntaxe classique), mais doit contrôler assez pour empêcher trop d'erreurs.


Le convertisseur et la regex contribuent à rendre l'Interface Utilisateur réactive et donc à la rendre intelligente.

# Conclusion

LibreCast est un projet en perpétuelle évolution, il ne s'arrêtera pas là où nous avons établi un premier objectif. Si nous avons construit sa structure, ce n'est que pour mieux l'enrichir par la suite. On peut penser au-delà du LibreCast d'aujourd'hui...

Ce projet m'a énormément apporté en connaissances et savoir-faire personnels, me faisant porter un nouveau regard sur la programmation. 

# Bibliographie

Le site de collaboration entre programmeurs par excellence, Github:

*https://github.com*

Le tutoriel sur wxPython qui m'a éclairée sur le sujet:

*http://zetcode.com/wxpython*

La page officielle de wxPython, répertoriant les nombreux widgets:

*http://wiki.wxpython.org/Getting%20Started*

Conseillé par Jean-Romain, ce tutoriel m'a permis de comprendre les Regex:

*https://docs.python.org/2/howto/regex.html*


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
