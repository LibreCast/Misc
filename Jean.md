# LibreCast

## Une courte introduction à la vidéo en ligne

Si la liberté d'expression était jusque là limitée par les évolutions de la technologie, internet a apporté la base matérielle à des communications bi-directionnelles avec toutes les personnes reliées au réseau.
Internet étant simplement un "tuyau", des sites de partage de vidéos en streaming comme YouTube, Vimeo ou DailyMotion offrent une solution logicielle utilisant ce réseau pour permettre à tout un chacun de publier des vidéos.

Cependant, il faut noter que ces sites web ont une limite : ils sont basés sur une architecture centralisée. C'est à dire que quiconque veut publier une vidéo sur un plate-forme de ce genre devra la confier au site. Cela adment plusieurs inconvénients, faisant obstacle à une liberté d'expression totale :

 * Les sites recueillant des vidéos provenant de nombreux pays, ils doivent adapter leurs actions aux législation de différents pays
 * Le volume de vidéos qu'ils contiennent est parfois si important qu'ils sont contraints par les ayants droit à utiliser des robots pour censurer les vidéos contenant des contenus soumis au droit d'auteur. Ces robots pouvant se tromper
 * La centralisation fait que si les serveur
 
Comment fournir alors un moyen de partager de la vidéo en ligne, tout en gardant la liberté d'expression comme objectif principal de la démarche ?

L'objet de notre démarche par LibreCast est de répondre à cette problématique.

## Présentation de LibreCast

### Le concept

LibreCast est un logiciel utilisable par n'importe qui, lui permettant de s'abonner aux publications vidéos d'un auteur, et de visionner ces vidéos. L'idée derrière LibreCast n'est pas de recréer un énième site de partage de vidéo centralisé, mais bien d'aller dans une toute autre direction, en laissant à l'auteur de la vidéo le soin d'héberger ses contenus (c'est à dire d'assurer la mise en ligne de sa vidéo sur un ordinateur qui lui appartient). La pluralité des sources de vidéos permet au passage de rendre LibreCast invulnérable à une attaque ciblée.

Jusque là, le principe évoqué est identique à la technologie Podcast, une technologie qui est apparue il y a un peu plus de 10 ans, une époque où le partage de vidéo en streaming était réservé à ceux qui disposaient de bonnes connaissances en informatiques et surtout d'une bonne connexion à internet. Mais dans LibreCast nous souhaitons dépasser ce format là, pour apporter des technologies qui se sont démocratisées après le podcast.

Et parmi ces technologies, nous avons choisi le Peer-to-peer. Le peer-to-peer est une méthode de téléchargement de contenu où au lieu de télécharger depuis un seul et même serveur, l'utilisateur va télécharger depuis plusieurs personnes, qui sont elles même en train de télécharger le même contenu. L'intêret de cette technologie est qu'elle permet de mettre à disposition un contenu à un nombre très très grand de personnes sans pour autant se ruiner en serveurs.

### Présentation de l'aspect visible

* Présentation de la fenêtre principale
* Fenêtre de téléchargements
* Fenêtre de lecture vidéo

### Fonctionnement interne



## Partir de zéro pour arriver à LibreCast

### Organisation du travail

* Organisation dans le temps
* Répartition du travail entre les membres de l'équipe

Nous avons organisé une répartition du travail entre chacun des membres de l'équipe : Marion s'est occupée de la création de l'interface, Jean-Romain s'est occupé de relier l'interface à la gestion des données, et je me suis occupé 


### Techniques de travail

Pour collaborer sur le code source du logiciel, nous avons utilisé GitHub. Cet outil nous permet de versionner le code, c'est à dire de pouvoir enregistrer plusieurs versions du code source au fur et à mesure du développement, et si besoin, de pouvoir revenir en arrière. Cet outil est de plus en plus souvent utilisé en entreprise.

Afin d'avoir un code source lisible et exploitable, nous avons choisi d'établir les bonnes pratiques du développement. Jean-Romain s'est chargé de vérifier l'application de PEP8, une norme sur la forme du code (identation, nom des variables, etc.). Nous avons effectué beaucoup de programmation orientée objet, ce qui nous permet de créer une application facilement modifiable et de limiter la redondance du code.

Pour certaines parties de LibreCast, j'ai écrit des programmes pour tester mon code : il s'agit de test unitaires. Cela permet de développer une fonctionnalité de manière indépendante du projet.

## Mes missions au sein de LibreCast

### Un système de téléchargement pratique et fiable

* Basé sur le logiciel aria2
* Communication avec aria2 en XMLRPC

Télécharger plusieurs contenus en simultané et en supportant du P2P est une t


Pour gérer les téléchargements dans LibreCast, j'ai proposé d'utiliser aria2, un logiciel de téléchargement. Pour l'intégrer dans LibreCast, nous utilisons une interface nommée "XML-RPC".

Cette interface nous permet de lancer un téléchargement d'une vidéo


### Un système d'abonnement

* Pour savoir les vidéos qu'un utilisateur met à disposition, il crée un fichier index. Quand on ajoute un abonnement sur LibreCast, c'est cet index qui est lu pour afficher la liste des vidéos disponible
* Index écrit en XML
* Un langage qu'il faut parser à l'aide d'un parseur : lxml

### Une base de donnée pour stocker des données internes

* Besoin de stockage de données internes (préférences, playlists, etc.)
* Base de donnée = logiciel qui gère le stockage de données de manière autonome
* On communique avec une base de donnée à l'aide du langage SQL
* SQLITE3

Dans LibreCast nous avons besoin de stocker de manière des données internes ; par exemple le nom des playlists et leur contenu, ou des préférences de l'utilisateur. Nous avons choisi d'utiliser une base de donnée, un programme qui s'occupe d'organiser des données qu'on lui demande de stocker de manière stucturée, et de les récupérer selon ce que l'on a besoin.

Pour communiquer avec la base de donnée, nous utilisons le langage SQL. Il nous permet

## Conclusion

## Bibliographie

* [Page officielle Aria2](http://aria2.sourceforge.net)
* [La page d'Apple au sujet des podcasts](http://www.apple.com/itunes/podcasts/)
