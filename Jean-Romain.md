# Organisation du travail
## Interface utilisateur
L’interface utilisateur est une partie extrêmement importante d’un logiciel, dans la mesure où c’est le seul moyen de communication avec l’utilisateur. Il faut permettre à ce dernier d’utiliser toutes les fonctionnalités d’un logiciel, en conservant une interface intuitive.
> Par exemple, le compteur de vitesse d’une voiture est une bonne illustration d’une interface simple, intuitive et qui accomplit parfaitement son rôle.

Dans la création de l’interface, mon rôle a été de mettre en relation l’arbre contenant les Abonnements et les listes de lecture de l’utilisateur avec la liste de vidéos (voir Annexe 1), ainsi que créer l’interface permettant de visionner les vidéos.

## Modules
Afin de structurer LibreCast, j’ai découpé notre code en plusieurs fichiers, et ensuite créé des modules. Un module est un ensemble de code, qui peut-être utilisé depuis un autre fichier. Cela permet d’utiliser plusieurs fois les mêmes fonctionnalités, sans dupliquer du code, mais également de structurer le projet et rendre son fonctionnement plus clair.

Pour LibreCast, j’ai créé 2 modules regroupant du code des mes partenaires et moi-même :
* Le manageur de requêtes, qui s’occupe de récupérer des informations d’internet
* Le manageur de l’interface, qui contient le code pour chaque fenêtre, ainsi que les images utilisées.

## Stocker des informations
Dans la répartition du travail, Jean Thomas s’est occupé de la création d’une base de donnée, qui sauvegarde et organise toutes les informations spécifiques à un utilisateur. Mon rôle a été de lier les différentes parties de l’interface (créées par Marion Ser ou moi-même) avec cette base de donnée, et ainsi permettre d’afficher, par exemple, les listes de lectures ajoutées par l’utilisateur.

## GitHub
Le travail a donc été découpé en plusieurs parties, chacun avec un rôle spécifique. Néanmoins, tous nos rôles sont étroitement liés, et il nous a donc fallu travailler en collaboration.
> En effet, imaginons la situation suivante :
> Marion créée une fenêtre affichant les listes de lectures de l’utilisateur. De mon côté, je souhaite lier la base de donnée créée par Jean avec cette nouvelle interface. Il me faut alors accès aux fichiers de Marion et de Jean en même temps.

Nous avons donc utilisé GitHub, un site internet très répandu permettant à des équipes de stocker leurs fichiers, et à chaque membre de cette équipe de modifier les fichiers à l’aide d’un système de « commits » : chaque fois que quelqu’un fait une modification, il entre un message court expliquant ce qui a été fait. GitHub applique alors ces modifications, sans modifier les fichiers qui n’ont pas été édités dans ce commit. De plus, il conserve un historique des modifications, permettant de vérifier les changements accomplis et, si nécessaire, de retourner à une version précédente du logiciel.

# Analyse de l'interface de LibreCast
## Glisser-déposer (aka Drag and Drop)
Pour permettre à l’utilisateur d’ajouter une vidéo dans une liste de lecture (ses favoris par exemple), le glisser-déposer s’impose comme une solution clair et intuitive. En effet, lorsque vous souhaitez ajouter un fichier dans un dossier, vous pouvez vous contenter d’un glisser-déposer. De là à faire de même avec une vidéo, il n’y a qu’un pas (voir Annexe 2).

## Lecteur de vidéo
Mais l’interface de LibreCast ne serait pas complète sans un moyen de visionner des vidéos. Encore une fois, nous avons pensé à la solution la plus simple : double-cliquer sur une vidéo permet la regarder en lançant le lecteur.
Lancer la vidéo a demandé une réflexion technique, évoqué plus tard, mais également sur l’aspect de l’interface. Si un lecteur de vidéo peut sembler banal, il a tout de même fallu penser aux fonctionnalités nécessaires : réglage du son, de la taille de la fenêtre…

Pour cela, je me suis notamment inspiré de l’apparence de VLC (quant aux fonctionnalités nécessaires), et ai opté pour une interface relativement sombre, souvent préférable lors du visionnage de vidéos (voir Annexe 3).
On retrouve donc des boutons « play » et « pause », une fonctionnalité « plein écran », le temps écoulé et le temps restant de vidéo, mais également une barre montrant l’avancement de manière graphique, et permettant de se déplacer dans la vidéo. Enfin, une dernière barre (située derrière la précédente) montre l’avancement du téléchargement de la vidéo.

## Lier interface et données
LibreCast permet la création de listes de lectures (Playlists) et de gérer des abonnements. Il faut donc une base de données contenant ces informations, comme expliqué précédemment. J’ai donc utilisé des fonctions créées par Jean, et l’interface de Marion pour créer une application vraiment propre à l’utilisateur. Ainsi, ses playlists et abonnements sont sauvegardées et affichés à l’écran, de même pour les vidéos.

Cette expérience m’a permis de regrouper deux technologies différentes, ce que je n’avais pas eu l’occasion de faire précédemment. De plus, j’ai pu comprendre les difficultés techniques qui peuvent exister, comme notamment utiliser une base de donnée correspondant aux demandes spécifiques de l’interface.

# Gestion de la vidéo

## Back-end
Pour lire les vidéos, il a fallu créer une interface comme je l’ai expliqué précédemment. Mais pour lire la vidéo elle-même, il existe un système de « back-end ».
En effet, dans les logiciels, il existe plusieurs « couches » :
* Ce qui est visible par l’utilisateur, nommé le « front-end ». Pour simplifier, c’est toute l’interface utilisateur.
* Ce que l’utilisateur ne voit pas, mais qui créé toutes les fonctionnalités.

Pour la vidéo, il y a donc un back-end qui s’occupe de récupérer le fichier, et de « traduire » toutes les données afin de les afficher à l’écran. Il existe un bac-end différent pour chaque plateforme : par exemple, sur Windows, LibreCast ferait appel à Windows media player.

## Codec vidéo
Un des problèmes qui existe avec les vidéos est la variété de formats existants. Un « codec » est le raccourcit de « Coder, decoder », c’est à dire un logiciel qui permet d’encoder les vidéos dans un certain format (par exemple .mp4), ou de décoder ce format pour l’afficher à l’écran. Dans notre cas, c’est le bac-end qui s’en occupe.

Chaque format de vidéo a des avantages et des inconvénients. Le format mp4, évoqué ci-dessus, est souvent utilisé car il est universel : un fichier encodé dans le format mp4 pourra être visionné sur n’importe quel plateforme. D’autres formats comme avi, qui possède une grande qualité d’image, ou WMW, qui dépend moins des codecs que le format avi.

## Multi-threading
Un dernier « défi technique » que nous avons rencontré est de permettre à l’utilisateur de charger une vidéo et de la visionner, tout en faisant autre chose dans le logiciel (comme télécharger une nouvelle vidéo par exemple). Mais, par défaut, l’ordinateur « lit » les lignes une par une, et les accomplies en attendant qu’elles aient fini avant de passer à la suivante. Ainsi, si l’utilisateur regarde une vidéo, il ne peut pas déplacer la fenêtre !

Pour cela, nous avons utilisé le « mutli-threading ». Pour l’expliquer, je vais l’illuster avec un exemple :
> Imaginons un pont, avec trois voitures voulant traverser, mais le pont ne supporte que le poids d’une voiture à la fois. Ce serait l’exemple précédent : chaque voiture doit attendre que la précédente ait traversé.
> Avec le multi-threading, c’est comme si l’on créé un deuxième pont, avec les même restrictions. Les voitures sur le premier pont peuvent circuler sans que celles sur le deuxième ne les en empêchent.

Ainsi, la lecture de la vidéo se fait sur une « thread » séparée, afin que celle principale (qui gère l’interface utilisateur) ne soit pas bloquée.

# Penser au-delà de LibreCast

## Intégration d’autres plateformes
Un inconvénient avec la méthode de diffusion de LibreCast pour les créateurs de contenu est le transfert de leurs vidéos depuis une autre plateforme (comme YouTube). Pour cela, il serait possible de créer un outil de migration, qui gèrerait le transfert du contenu vers la nouvelle « chaîne » de l’utilisateur.

Il serait également imaginable de permettre aux utilisateurs d’utiliser YouTube comme serveur pour leurs vidéos, et simplement donner un lien YouTube dans LibreCast. Il faudrait alors « convertir » le lien YouTube en un lien directement vers le contenu. En effet, lorsqu’on visionne une vidéo sur YouTube, le lien utilisé n’est pas celui du fichier vidéo (en .mp4 par exemple), il est donc nécessaire de récupérer la véritable adresse du fichier.

## Modification du back-end
L’utilisation du back-end « par défaut » pose certains problèmes :
• Ce dernier dépend de la plateforme, il n’y a donc pas unicité des formats de vidéo compatibles
• Ils peuvent avoir des problème, comme sur Mac OS où la taille de la vidéo n’est pas conservée lorsque la fenêtre est redimensionnée. Ainsi, une vidéo avec un format de 1280 pixels par 720 pixels peut-être redimensionner, et mesure 780 pixels par 720 pixels, étirant ainsi le contenu.

Ainsi, il serait possible de chercher à créer un back-end personnalisé, ou d’utiliser celui de VLC, compatible avec de nombreux fichiers et qui accepte l’affichage de sous-titres.

## Cryptographie
Une amélioration possible est la possibilité pour les utilisateurs de partager du contenu seulement avec leurs amis, ou les personnes autorisées. De plus, il serait utile de pouvoir « signer » une vidéo, c’est-à-dire prouver sa paternité (qui l’a mise en ligne). Pour cela, l’utilisation de cryptographie serait nécessaire, un partenariat avec le groupe de Colin Davalot, Alexis Daley (et qui d’autre ?) pourrait donc s’avérer utile.

## Nouvelles plateformes
Si LibreCast est disponible sur la grande majorité des ordinateurs, un autre marché existant est celui du mobile. Nous pourrions envisager de créer une version pour Android et iOS par exemple, afin de pouvoir visionner et télécharger des vidéos depuis n’importe où.

# Annexes

**Photos**

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
