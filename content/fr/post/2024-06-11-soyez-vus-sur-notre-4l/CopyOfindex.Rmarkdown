---
title: Soyez vus sur notre 4L !
author: DG
date: '2024-06-11'
slug: soyez-vus-sur-notre-4L
categories: [R, tutoriel]
tags: [blogdown, créer le site]
links:
- icon: door-open
  icon_pack: fas
  name: projet
  url: fr/my-projects/creating-beautiful-content/
- icon: link
  icon_pack: fas
  name: english
  url: blog/soyez-vus-sur-notre-4L/
summary: 'Comment construire un site avec le package R `blogdown`, une introduction rapide.'
featured: no
image:
  caption: '[Photo de Danielle MacInnes sur Unsplash](https://unsplash.com/photos/IuLgi9PWETU)'
  focal_point: ''
  preview_only: no
---

<!--
{{< table_of_contents >}}
-->

{{%toc%}}

Bonjour!

Nous vous proposons une place sur notre 4L pour partager un bout de cette aventure ensemble. L’occasion de vous rendre visibles tout au long de ces 6000 km de trajet, captés par différents médias dont les réseaux sociaux des organisateurs du 4L Trophy.

Voici quelques exemples d’emplacements pour des autocollants aux couleurs de votre entreprise ou organisation. Les prix et emplacements indiqués sont à titre indicatif, et peuvent être négociés selon votre projet et la taille souhaitée.

## Les prix

* 150
* 300
* 500
* 600
* 700
* 1000


## Les étapes, en gros

1. Créer un répertoire (j'utilise le mot *repo* à partir d'ici) public sur GitHub, avec un fichier README.md, mais pas .gitignore;
2. Cloner le repo localement[^1], et créer un nouveau Rproject dans le repo;
3. Utiliser son huile de coude sur `blogdown`;
4. Commit et push (je ne connais pas les termes en français) les changements effectués sur GitHub;
5. Déployer le site sur Netlify.
6. FIN.

Facile, n'est-ce pas? Allons-y. Mettons nos mains dans le cambouis.

## `blogdown`

J'ai choisi le modèle [Academic](https://academic-demo.netlify.app/) comme armature de mon site. Academic est relativement simple à manier et sympa à personnaliser. D'autres thèmes de base sont disponibles sur [Wowchemy](https://wowchemy.com/) et également sur [Hugo](https://gohugo.io/).

Une fois mon projet R prêt, j'ai suivi le tutoriel d'Alison scrupuleusement. Ci-dessous, les lignes de code essentielles pour construire le site de base:

```{r eval=FALSE}
install.packages("blogdown")
blogdown::new_site(theme = "wowchemy/starter-academic")
blogdown::serve_site()
blogdown::new_post(title = "Hi Hugo",
                     ext = '.Rmarkdown',
                     subdir = "post")
```

`blogdown::serve_site()` lance un aperçu simultané du site dans le volet Viewer[^2]. Il n'y a pas besoin de rafraîchir la page à chaque changement, `blogdown` s'en charge quand on sauvegarde et/ou qu'on "tricote" nos documents. `blogdown::new_post` crée un nouvel article.

Après cette commande, j'ai changé plusieurs paramètres par défaut dans le fichier `.Rprofile`: l'auteure (`blogdown.author`), l'extension de fichier (`blogdown.ext`) et le sous-répertoire de base pour les nouveaux articles (`blogdown.subdir`). Après chaque modification de .Rprofile, il ne faut pas oublier de sauvegarder puis de `Ctrl+Shift+F10` redémarrer R!

On peut également modifier `config.yaml` et `config/_default/params.yaml` pour changer le titre, le thème du site, et bien d'autres choses.

On écrit tranquillement un article dans un fichier Rmarkdown si on veut inclure du code R, qu'on `Ctrl+Shift+K` tricote par la suite pour obtenir le fichier Markdown[^3]. C'est le type de fichier que Hugo (ou Netlify, je ne suis pas sûre) utilise pour publier du contenu. Si on veut écrire du texte seul, on peut directement écrire en Markdown, sans avoir à tricoter quoique ce soit.

Une fois satisfaite avec mes modifications, j'ai effectué de dernières vérifications avec les commandes suivantes[^4].

```{r eval=FALSE}
blogdown::check_config()
blogdown::check_gitignore()
blogdown::check_content()
blogdown::check_netlify()
blogdown::check_hugo()
# Il peut y avoir des tâches [TODO]
```

On peut également utiliser la commande tout-en-1 `blogdown::check_site()`. S'il n'y a plus de tâches à faire, on peut enfin publier le site!

## La publication

1. Netlify;
2. Se connecter avec GitHub;
3. Choisir le repo à déployer;
4. Changer le nom de domaine.

<!--- I'd really like to make an alert note out of this sentence. TO LOOK UP --->
{{% callout warning %}}
À chaque fois qu'on change le nom de domaine sur Netlify, **il faut changer le baseurl** dans le fichier `config.yaml`.
{{% /callout %}}

Et hop! Mon site est en ligne! Je pense avoir pris une heure pour en arriver là. Netlify prend soin de la construction et du déploiement à chaque modification qu'on pousse sur GitHub. Attention à bien tricoter les fichiers `.RMarkdown`!

Bon, cool, on a un site, mais il est un petit peu encombré. Et si on le personnalisait? Rendez-vous dans mon prochain article pour répondre à cette question!

## BONUS: quelques commandes et raccourcis clavier

* `file.create()` pour créer un fichier dans le répertoire de travail en cours. Si je veux créer un fichier dans un dossier, je précise le chemin, jusqu'au nom souhaité du fichier et son extension. Le(s) dossier(s) doit déjà exister! Si ce n'est pas le cas:
* `dir.create()` pour créer un dossier. Si je précise le chemin, je peux créer un dossier dans un dossier.
* `rstudioapi::navigateToFile(path.to.file)` pour ouvrir un fichier existant sans cliquer :)
* `Ctrl+W` pour fermer un onglet, `Ctrl+Shift+W` pour fermer tous les onglets, `Ctrl+Shift+Alt+W` pour fermer tous les onglets sauf celui ouvert;

[^1]:J'ai cloné mon repo avec GitHub Desktop après avoir essayé de le cloner directement avec RStudio. Malheureusement je ne pouvais rien commit, un fichier index.lock bloquait tout, jsp pourquoi.
[^2]:Je peux également utiliser mon navigateur principal en cliquant sur 'Show in new window'.
[^3]:J'ai laissé `blogdown.knit.on.save` sur `FALSE` parce que je n'aime pas la sauvegarde automatique. On a tous des défauts.
[^4]:AJA qu'il faut écrire les notes de bas de page séparément avec `blogdown`, contrairement à `bookdown` avec lequel je pouvais écrire mes notes directement dans le texte, notes qui étaient automatiquement numérotées.
