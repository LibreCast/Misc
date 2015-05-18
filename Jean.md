# LibreCast

## Une courte introduction à la vidéo en ligne

Avant internet, s'exprimer publiquement n'était pas aussi simple qu'aujourd'hui : on était obligé de passer par des journaux, des chaînes de télévision ou des chaînes de radio. Impossible donc, à l'époque, de s'exprimer publiquement sans passer par un intermédiaire (qui peut refuser de nous publier, ou au mieux, altérer nos propos) pour distribuer à grande échelle nos contenus.

Depuis l'arrivée d'internet, pour exploiter cette avancée technique, un grand nombre de personnes se sont penchées sur des solutions permettant à chacun de partager librement et publiquement ses idées au monde entier, en évitant les contraintes des médias traditionnels.

Parmi ces solutions, les sites de partage de vidéos en streaming comme Vimeo, YouTube ou Dailymotion, attirent chaque année de plus en plus de visiteurs et de créateurs de contenus. Ces sites permettent à n'importe quelle personne disposant d'une connexion internet de publier des vidéos, sans pour autant requérir des compétences avancées en informatique.

Cependant, ces sites ont le même problème : ils concentrent tous en un seul et unique endroit l'intégralité des vidéos publiées du site. C'est ce qu'on appelle une architecture centralisée. Cette architecture centralisée pose plusieurs problèmes :

 * En cas de forte affluence sur un contenu en particulier, tout le site peut rencontrer des difficultés à fonctionner
 * La présence de contenus appartenant à des ayants droits sur YouTube a conduit à la présence d'un algorithme pour déterminer si une vidéo ne respecte pas le droit d'auteur, qui peut se tromper
 * Elle engendre des coûts d'infrastruction augmentant de manière exponentielle avec la popularité du site et le nombre de vidéos qui y sont stockées
 
En ayant conscience de ces problèmes, comment peut-on fournir un moyen de partager de la vidéo en ligne, tout en gardant la liberté d'expression comme objectif principal de la démarche ?

## Présentation de LibreCast

### Le concept

LibreCast est un logiciel utilisable par n'importe qui, lui permettant de s'abonner aux publications vidéos d'un auteur, et de visionner ces vidéos. L'idée derrière LibreCast n'est pas de recréer un énième site de partage de vidéo centralisé, mais bien d'aller dans une toute autre direction, en laissant à l'auteur de la vidéo le soin d'héberger ses contenus (c'est à dire d'assurer la mise en ligne de sa vidéo sur un ordinateur qui lui appartient). La pluralité des sources de vidéos permet au passage de rendre LibreCast invulnérable à une attaque ciblée.

Jusque là, le principe évoqué est identique à la technologie Podcast, une technologie qui est apparue il y a un peu plus de 10 ans, une époque où le partage de vidéo en streaming était réservé à ceux qui disposaient de bonnes connaissances en informatiques et surtout d'une bonne connexion à internet. Mais dans LibreCast nous souhaitons dépasser ce format là, pour apporter des technologies qui se sont démocratisées après le podcast.

Et parmi ces technologies, nous avons choisi le peer-to-peer. Le peer-to-peer est une méthode de téléchargement de contenu où au lieu de télécharger depuis un seul et même serveur, l'utilisateur va télécharger depuis plusieurs personnes, qui sont elles même en train de télécharger le même contenu. L'intêret de cette technologie est qu'elle permet de mettre à disposition un contenu à un nombre très très grand de personnes sans pour autant se ruiner en serveurs.

### Présentation de l'aspect visible

* Présentation de la fenêtre principale
* Fenêtre de téléchargements
* Fenêtre de lecture vidéo

### Fonctionnement interne



## Partir de zéro pour arriver à LibreCast

### Organisation du travail

Notre travail s'est divisé en trois phases.

Nous avons tout d'abord pris du temps pour écouter tous les sujets que nous pouvons traiter (la thématique du partage de vidéos en ligne que j'avais soumis a finalement été choisie), puis nous avons exposé chacun nos idées du sujet pour savoir quels objectifs nous devons nous fixer. Nous en avons aussi profité pour se renseigner sur les technologies que nous allons utiliser pour notre projet, et pour se répartir équitablement la charge de travail.

Nous avons ensuite codé le logiciel, pendant une dizaine de semaines. Je me suis occupé des aspects internes du logiciel (invisible pour l'utilisateur final) : le téléchargement des vidéos, du système d'abonnement, et du stockage des données internes, Marion s'est occupée de l'interface graphique du logiciel, et Jean-Romain s'est occupé de faire le lien entre mon travail et celui de Marion, et s'est aussi occupé de réaliser un lecteur vidéo.

Nous avons finalement consacré 2 semaines à la préparation de nos soutenances écrites et orales tout en procédant à la création de correctifs mineurs du logiciel.

### Techniques de travail

Pour collaborer sur le code source du logiciel, nous avions besoin d'un outil nous permettant de collaborer simultanément sur le code, tout en gardant un historique de l'avancement de notre travail, au cas où nous aurions besoin de revenir en arrière dans notre code. Nous utilisons pour cela un logiciel de "versionning" : GitHub, qui est de plus en plus utilisé en entreprise.

Afin d'avoir un code source lisible et exploitable, nous avons choisi d'établir des bonnes pratiques lors du développment. Jean-Romain s'est chargé de vérifier l'application de la norme PEP8, une norme sur la forme du code (identation, nom des variables, etc.).

Pour certaines parties de LibreCast, j'ai écrit des programmes pour tester mon code : il s'agit de test unitaires. Cela permet de travailler sur une partie de LibreCast tout en étant isolé du reste du code, ce qui rend asynchrone notre collaboration.

## Mon travail au sein de LibreCast

### Un système de téléchargement pratique et fiable

Pour télécharger des vidéos dans LibreCast, nous avons décidé de recourir à un logiciel tiers pour assurer cette tache complexe : aria2. Il nous permet de télécharger les fichiers vidéos à la fois en direct download, mais aussi en peer-to-peer. Nous pouvons aussi l'utiliser pour télécharger un même fichier vidéo depuis plusieurs sources, ce qui nous permet d'assurer une redondance de la disponibilité des contenus, c'est le "failover".

LibreCast communique avec aria2 grâce au protocole "XML-RPC" qui nous permet d'ajouter des téléchargement, les supprimer, et connaître leur progresser.


### Un système d'abonnement

* Pour savoir les vidéos qu'un utilisateur met à disposition, il crée un fichier index. Quand on ajoute un abonnement sur LibreCast, c'est cet index qui est lu pour afficher la liste des vidéos disponible
* Index écrit en XML
* Un langage qu'il faut parser à l'aide d'un parseur : lxml

### Une base de donnée pour stocker des données internes

Dans LibreCast nous avons besoin de stocker de manière des données internes ; par exemple le nom des playlists et leur contenu, ou des préférences de l'utilisateur. Nous avons choisi d'utiliser une base de donnée, un programme qui s'occupe d'organiser des données qu'on lui demande de stocker de manière stucturée, et de les récupérer selon ce que l'on a besoin.

Nous utilisons pour LibreCast la base de donnée SQlite3, qui est très légère et stocke l'entièreté de ses données dans un seul fichier, par opposition à d'autres bases de données qui répartissent toutes leurs données dans une large arborescence de fichier.

Les données sont organisée dans la base de donnée sous forme de tables : chaque information est organisée autour de plusieurs champs. On peut par exemple représenter les données par un tableau (voir annexe X)

Pour communiquer avec notre base de donnée nous utilisons le langage SQL, qui sert à effectuer des requête vers la base de donnée depuis notre programme. Par exemple, pour récupérer la liste des vidéos nous envoyons la commande suivante :

```
SELECT * FROM videos;
``` 

# Conclusion

LibreCast est une tentative de solution au problème de l'expression sur internet, en résolvant le problème de la centralisation sur les solutions existantes de partage de vidéos.

LibreCast n'est cependant pas une finalité, nous pouvons y voir encore quelques idées pour pousser le concept encore plus loin. Nous pourrions en effet penser à implémenter la solution de cryptographie développée par nos confrères en ISN, afin de pouvoir limiter la diffusion d'une vidéo seulement aux personnes qui disposent de la clé de décryptage, ou encore à faire un annuaire de flux, pour créer une dimension sociale autour de LibreCast, permettant à un utilisateur lambda de découvrir des vidéos d'un auteur qu'il ne connait pas. 

# Bibliographie

* [Page officielle Aria2](http://aria2.sourceforge.net)
* [Page officielle lxml]()
* [Page officielle SQlite3]()
* [La page d'Apple au sujet des podcasts](http://www.apple.com/itunes/podcasts/)
* [Page "peer-to-peer" Wikipedia]()
