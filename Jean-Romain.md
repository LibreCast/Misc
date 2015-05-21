# Introduction
Aujourd’hui, internet s’est imposé comme un lieu d’échanges libres, de contenu diverse, avec le monde entier. Ainsi, partager et visionner des vidéos est devenu courant, et de nombreux sites proposant ces fonctionnalités sont apparus.

En quoi LibreCast propose-t-il une solution différente, et plus « libre » que ces plateformes ?

# Comprendre LibreCast
## D’où vient LibreCast ?
LibreCast est la contraction des mots « Libre », et de « Broadcast ». Ainsi, ce nom résume à la fois les fonctionnalités du logiciel (Broadcast signifie diffuser en anglais), et le buts que nous nous sommes fixé : créer une solution laissant les utilisateurs plus libres que sur d’autres plateformes, tout en gardant leur confidentialité. De plus, le code de notre application est disponible à tous sur internet : l’application est donc réellement « libre ». 

## Une solutions nouvelle et différente
Plusieurs solutions de partage de vidéos, notamment YouTube et Dailymotion, sont déjà accessibles au grand public. Néanmoins, toutes très similaires, elles ont certains problèmes : les données sont centralisées (stockées sur des serveurs appartenant à l’entreprise elle-même), engendrant un grand coût et forçant la plateforme à gérer les problèmes de droit d’auteurs elle-même.
LibreCast essaye de palier à ces problèmes, en laissant les créateurs de contenu héberger leurs propres vidéos. Ainsi, chacun est responsable des droits d’auteur, et doit trouver une solution d’hébergement. Il serait par exemple imaginable d’utiliser des hébergeurs gratuits, ou tout simplement dropbox pour gérer le contenu.

## Aspect plus technique
Un autre aspect novateur de LibreCast est l’intégration directe du « peer-to-peer » en tant que mode de téléchargement. Cette technologie permet à un utilisateur de télécharger des données depuis d’autres utilisateurs, n’importe où dans le monde, plutôt que directement depuis un serveur.
> Par exemple, imaginons que je souhaite télécharger une vidéo, et que Jean et Marion en ont chacun téléchargé une partie. Ils me transmettraient alors le contenu qu’ils ont obtenu, tandis que de mon côté je leur transmettrais du nouveau contenu qu’ils n’ont pas encore pu télécharger.
Ainsi, la pluralité des sources permet un téléchargement plus rapide, et parfois plus anonyme.

# Organisation du travail
## Répartition du travail
Notre travail s’est composé de trois phases (Voir annexe 1) :
* Nous avons d’abord choisit la thématique du partage de vidéos, puis fixé les objectifs à atteindre,
* Nous avons ensuite créé le logiciel lui-même, pendant environs dix semaines,
* Nous avons finalement rédigé ensemble une liste des points à traiter, et ainsi préparé le dossier écrit et la présentation orale.

Pour programmer le logiciel, nous nous sommes également attribué des taches à chaque membre du groupe. Je me suis principalement orienté sur la création de l’interface utilisateur, ainsi que le liens entre l’interface et les données du logiciel. Cette répartition ne s’est pas faite en fonction des acquis, mais plutôt des préférences personnelles de chacun, et des objectifs que nous nous sommes fixés. Ainsi, chaque semaine nous avons élit les points à traiter en priorité, et les axes secondaires sur lesquels nous pourrions réfléchir.

## Interface utilisateur
L’interface utilisateur est une partie extrêmement importante d’un logiciel, dans la mesure où c’est le seul moyen de communication avec l’utilisateur. Il faut permettre à ce dernier de tirer parti toutes les fonctionnalités d’un logiciel, en conservant une interface intuitive.
> Par exemple, le compteur de vitesse d’une voiture est une bonne illustration d’une interface simple, intuitive et qui accomplit parfaitement son rôle.

Dans la création de l’interface, mon rôle a été de mettre en relation l’arbre avec les Abonnements et les listes de lecture de l’utilisateur et la liste de vidéos (voir Annexe 1), ainsi que de créer le lecteur de vidéos.

## Modules
Afin de structurer LibreCast, j’ai découpé notre code en plusieurs fichiers, puis ai créé des modules. Un module est un ensemble de code qui peut être utilisé depuis un autre fichier : il permet d’avoir accès plusieurs fois aux mêmes fonctionnalités, sans dupliquer du code, mais également de structurer le projet et rendre son fonctionnement plus clair.

Pour LibreCast, j’ai créé 2 modules regroupant du code de mes partenaires et moi-même :
* Le manageur de requêtes, qui s’occupe de récupérer des informations d’internet,
* Le manageur de l’interface, qui contient le code pour chaque fenêtre, ainsi que les images utilisées.

## Stocker des informations
Dans la répartition du travail, Jean Thomas s’est occupé de la création d’une base de données, qui sauvegarde et organise toutes les informations spécifiques à un utilisateur. Mon rôle a été de lier les différentes parties de l’interface (créées par Marion Ser ou moi-même) avec cette base de données, et ainsi permettre d’afficher, par exemple, les listes de lecture ajoutées par l’utilisateur.

## GitHub
Le travail a donc été réparti en plusieurs parties, chacun avec un rôle spécifique. Néanmoins, tous nos rôles sont étroitement liés, et il nous a donc fallu travailler en collaboration.
> En effet, imaginons la situation suivante :
> Marion crée une fenêtre affichant les listes de lecture de l’utilisateur. De mon côté, je souhaite lier la base de donnée créée par Jean avec cette nouvelle interface. Il me faut alors accès aux fichiers de Marion et de Jean en même temps.

Nous avons donc utilisé GitHub, un site internet très répandu permettant à des équipes de stocker leurs fichiers, et à chaque membre de cette équipe de modifier les fichiers à l’aide d’un système de « commits » : chaque fois que quelqu’un fait une modification, il entre un message court expliquant ce qui a été fait. GitHub applique alors ces modifications, sans changer les fichiers qui n’ont pas été édités dans ce commit.

# Analyse de l'interface de LibreCast
## Glisser-déposer (aka Drag and Drop)
Pour permettre à l’utilisateur d’ajouter une vidéo dans une liste de lecture (ses favoris par exemple), le glisser-déposer s’impose comme une solution claire et intuitive. En effet, lorsque vous souhaitez ajouter un fichier dans un dossier, vous pouvez vous contenter d’un glisser-déposer. De là à faire de même avec une vidéo, il n’y a qu’un pas (voir Annexe 2).

## Lecteur de vidéo
Mais l’interface de LibreCast ne serait pas complète sans un moyen de visionner des vidéos. Encore une fois, nous avons pensé à la solution la plus simple : double-cliquer sur une vidéo permet de la regarder en lançant le lecteur.
Lancer la vidéo a demandé une réflexion sur la technique, évoquée plus tard, mais également sur l’aspect de l’interface. Si un lecteur de vidéo peut sembler banal, il a tout de même fallu penser aux fonctionnalités nécessaires : réglage du son, de la taille de la fenêtre…
Pour cela, je me suis notamment inspiré de l’apparence de VLC (quant aux fonctionnalités nécessaires), et ai opté pour une interface relativement sombre, souvent préférable lors du visionnage de vidéos (voir Annexe 3).
On retrouve donc des boutons « play » et « pause », une fonctionnalité « plein écran », le temps écoulé et le temps restant de vidéo, mais également une barre montrant l’avancement de manière graphique, et permettant de se déplacer dans la vidéo. Enfin, une dernière barre (située derrière la précédente) montre l’avancement du téléchargement de la vidéo.

## Lier interface et données
LibreCast permet la création de listes de lecture (Playlists) et de gérer des abonnements. Il faut donc une base de données contenant ces informations, comme expliqué précédemment. J’ai donc utilisé des fonctions créées par Jean, et l’interface de Marion pour créer une application vraiment propre à l’utilisateur. Ainsi, ses listes de lecture et abonnements sont sauvegardés et affichés à l’écran, de même pour les vidéos.
Cette expérience m’a permis de regrouper deux technologies différentes, ce que je n’avais pas eu l’occasion de le faire auparavant. De plus, j’ai pu comprendre les difficultés techniques qui peuvent exister, comme notamment utiliser une base de données correspondant aux demandes spécifiques de l’interface.

# Gestion de la vidéo
## Back-end
Pour lire les vidéos, il a fallu créer une interface comme je l’ai expliqué précédemment. Mais pour lire la vidéo elle-même, il existe un système de « back-end ».
En effet, dans les logiciels, il existe plusieurs « couches » :
* Ce qui est visible par l’utilisateur, nommé le « front-end ». Pour simplifier, c’est toute l’interface utilisateur.
* Ce que l’utilisateur ne voit pas, mais qui crée toutes les fonctionnalités.

Pour la vidéo, il y a donc un back-end qui s’occupe de récupérer le fichier, et de « traduire » toutes les données afin de les afficher à l’écran. Il existe un back-end différent pour chaque plateforme : par exemple, sur Windows, LibreCast ferait appel à Windows media player.

## Codec vidéo
Un des problèmes qui existe avec les vidéos est la variété de formats existants. Un « codec » est le raccourci de « Coder, decoder », c’est-à-dire un logiciel qui permet d’encoder les vidéos dans un certain format (par exemple .mp4), ou de décoder ce format pour l’afficher à l’écran. Dans notre cas, c’est le back-end qui s’en occupe.
Chaque format de vidéo a des avantages et des inconvénients. Le format mp4, évoqué ci-dessus, est souvent utilisé car il est universel : un fichier encodé dans le format mp4 pourra être visionné sur n’importe quelle plateforme. D’autres formats comme avi, qui possède une grande qualité d’image, ou WMW, qui dépend moins des codecs que le format avi.

## Multi-threading
Un dernier « défi technique » que nous avons rencontré est de permettre à l’utilisateur de charger une vidéo et de la visionner, tout en faisant autre chose dans le logiciel (comme télécharger une nouvelle vidéo par exemple). Mais, par défaut, l’ordinateur « lit » les lignes une par une, et les accomplit en attendant qu’elles aient fini avant de passer à la suivante. Ainsi, si l’utilisateur regarde une vidéo, il ne peut pas déplacer la fenêtre !

Pour cela, nous avons utilisé le « mutli-threading ». Pour l’expliquer, je vais l’illustrer avec un exemple :
> Imaginons un pont, avec dix voitures voulant traverser, mais le pont ne supporte que le poids d’une voiture à la fois. Ce serait l’exemple précédent : chaque voiture doit attendre que la précédente ait traversé.
> Avec le multi-threading, c’est comme si l’on crée un deuxième pont, avec les mêmes restrictions. Les voitures sur le premier pont peuvent circuler sans que celles sur le deuxième ne les en empêchent.

Ainsi, la lecture de la vidéo se fait sur un « thread » séparée, afin que celui principal (qui gère l’interface utilisateur) ne soit pas bloqué.

# Penser au-delà de LibreCast
## Intégration d’autres plateformes
Un inconvénient avec la méthode de diffusion de LibreCast pour les créateurs de contenu est le transfert de leurs vidéos depuis une autre plateforme (comme YouTube). Pour cela, il serait possible de créer un outil de migration, qui gèrerait le transfert du contenu vers la nouvelle « chaîne » de l’utilisateur.
Il serait également imaginable de permettre aux utilisateurs d’utiliser YouTube comme serveur pour leurs vidéos, et simplement donner un lien YouTube dans LibreCast. Il faudrait alors « convertir » le lien YouTube en un lien directement vers le contenu. En effet, lorsqu’on visionne une vidéo sur YouTube, le lien utilisé n’est pas celui du fichier vidéo (en .mp4 par exemple), il est donc nécessaire de récupérer la véritable adresse du fichier.

## Modification du back-end
L’utilisation du back-end « par défaut » pose certains problèmes :
* Ce dernier dépend de la plateforme, il n’y a donc pas unicité des formats de vidéo compatibles,
* Ils peuvent avoir des dysfonctionnements, comme sur Mac OS où la taille de la vidéo n’est pas conservée lorsque la fenêtre est redimensionnée. Ainsi, une vidéo avec un format de 1280 pixels par 720 pixels peut être redimensionnée, et mesurer 1780 pixels par 720 pixels, étirant alors le contenu.

Ainsi, il serait possible de chercher à créer un back-end personnalisé, ou d’utiliser celui de VLC, compatible avec de nombreux fichiers et qui accepte l’affichage de sous-titres.

## Cryptographie
Une amélioration éventuelle est la possibilité pour les utilisateurs de partager du contenu seulement avec leurs amis, ou les personnes autorisées. De plus, il serait utile de pouvoir « signer » une vidéo, c’est-à-dire prouver sa paternité (qui l’a mise en ligne). Pour cela, l’utilisation de cryptographie serait nécessaire, un partenariat avec le groupe de Colin Davalot, Alexis Daley (et qui d’autre ?) pourrait donc s’avérer utile.

## Nouvelles plateformes
Si LibreCast est disponible sur la grande majorité des ordinateurs, un autre marché existant est celui du mobile. Nous pourrions envisager de créer une version pour Android et iOS par exemple, afin de pouvoir visionner et télécharger des vidéos depuis n’importe où.

# Conclusion
Pour Conclure, LibreCast est une solution qui tente de s’adapter aux besoins des utilisateurs, dans la mesure où elle leur permet d’avoir une grande liberté de diffusion. De plus, LibreCast est une tentative pour penser différemment que les autres plateformes, aussi bien au niveau de la diffusion que du téléchargement. Finalement, il existe plusieurs possibilités d’évolution, qui pourraient voir le jour dans le futur.

# Annexes

**Annexe 1 : Répartition du travail**
**Annexe 2 : Découpage de la fenêtre principale de LibreCast**
**Annexe 3 : Exemple de glisser-déposer**
**Annexe 4 : Lecteur de vidéos**

## Webographie
* Documentation de wxPython  http://wxpython.org/Phoenix/docs/html/main.html
* Le site de GitHub  https://github.com
* Notre projet sur GitHub  https://github.com/LibreCast
* Page sur les back-ends de Wikipédia  http://fr.wikipedia.org/wiki/Backend


# Plan
* Introduction

* Comprendre LibreCast.

* Organisation du travail **(Done)**
  * UI (vidéo + DnD)
  * Création de modules
  * Liens base de donnée
  * GitHub

* Vidéo **(Done)**
  * Gestion du backend
  * codec vidéos
  * Lecteur vidéo
  * Multi-threading

* Analyse de l'UI de LibreCast **(~ Done)**
  * Réflexion sur l'UI du player
  * Fenêtre plus complexe
  * Rendre l'UI intelligente <del>(test de nouvelles URL)</del>
  * Liens entre interface et données
  * Gestion des Playlists

* Penser au delà de LibreCast
  * Intégration avec d'autres plate-formes de diffusion de vidéo
  * Utiliser un back-end perso ou VLC
  * Cryptographie : signer des vidéos pour en prouver sa paternité, pour les partager uniquement avec ceux qui y sont autorisés (rapide)
  * Application iOS

* Conclusion
  * LibreCast tente de s'adapter aux besoins des utilisateurs
  * LibreCast se veut être une tentative pour penser autrement que les autres plateformes.
  * Plusieurs possibilités d'évolution

* Annexes
 * Schéma backend -> wxpython
 * Photo de la fenêtre (avec vidéo qui joue)
 * Webographie : http://wxpython.org/Phoenix/docs/html/main.html (doc wxpython)
