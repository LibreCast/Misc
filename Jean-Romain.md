
# Organisation du travail
## Interface utilisateur
L’interface utilisateur est une partie extrêmement importante d’un logiciel, dans la mesure où c’est le seul moyen de communication avec l’utilisateur. Il faut permettre à ce dernier d’utiliser toutes les fonctionnalités d’un logiciel, en conservant une interface intuitive.
> Par exemple, le compteur de vitesse d’une voiture est un bon exemple d’une interface simple, intuitive et qui accomplit parfaitement son rôle.

Dans la création de l’interface, mon rôle a été de mettre en relation l’arbre avec les Abonnements et les listes de lecture de l’utilisateur et la liste de vidéos (voir Annexe 1), ainsi que créer l’interface permettant de visionner des vidéos.

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

Nous avons donc utilisé GitHub, un site internet très répandu permettant à des équipes de stocker leurs fichiers, et à chaque membre de cette équipe de modifier les fichiers à l’aide d’un système de « commits » : chaque fois que quelqu’un fait une modification, il entre un message court expliquant ce qui a été fait. GitHub applique alors ces modifications, sans modifier les fichiers qui n’ont pas été édités dans ce commit.

# Analyse de l'interface de LibreCast
## Glisser-déposer (aka Drag and Drop)
Pour permettre à l’utilisateur d’ajouter une vidéo dans une liste de lecture (ses favoris par exemple), le glisser-déposer s’impose comme une solution clair et intuitive. En effet, lorsque vous souhaitez ajouter un fichier dans un dossier, vous pouvez vous contenter d’un glisser-déposer. De là à faire de même avec une vidéo, il n’y a qu’un pas (voir Annexe 2).

## Lecteur de vidéo
Mais l’interface de LibreCast ne serait pas complète sans un moyen de visionner des vidéos. Encore une fois, nous avons pensé à la solution la plus simple : double-cliquer sur une vidéo permet la regarder en lançant le lecteur.
Lancer la vidéo a demandé une réflexion technique, évoqué plus tard, mais également sur l’aspect de l’interface. Si un lecteur de vidéo peut sembler banal, il a tout de même fallu penser aux fonctionnalités nécessaires : réglage du son, de la taille de la fenêtre…
Pour cela, je me suis notamment inspiré de l’apparence de VLC (quant aux fonctionnalités nécessaires), et ai opté pour une interface relativement sombre, souvent préférable lors du visionnage de vidéos (voir Annexe 3).
On retrouve donc des boutons « play » et « pause », une fonctionnalité « plein écran », le temps écoulé et le temps restant de vidéo, mais également une barre montrant l’avancement de manière graphique, et permettant de se déplacer dans la vidéo. Enfin, une dernière barre (située derrière la précédente) montre l’avancement du téléchargement de la vidéo.


# Plan
* Introduction

* Comprendre LibreCast.

* Organisation du travail
  * UI (vidéo + DnD)
  * Création de modules
  * Liens base de donnée
  * GitHub

* Vidéo
  * Gestion du backend
  * codec vidéos
  * Lecteur vidéo
  * Multi-threading

* Analyse de l'UI de LibreCast
  * Réflexion sur l'UI du player
  * Fenêtre plus complexe
  * Rendre l'UI intelligente (test de nouvelles URL)
  * Liens entre interface et données
  * Gestion des Playlists

* Penser au delà de LibreCast
  * Intégration avec d'autres plate-formes de diffusion de vidéo
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
