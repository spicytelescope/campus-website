---
title: 📝 Guide pour les associations
sidebarDepth: 3
---

# Guide pour les associations

L'objectif de ce guide est de vous montrer et expliquer vous pouvez **ajouter** ou **modifier** du **contenu**, _comme le bureau de votre association par exemple._

## Ce qu'il faut savoir avant de commencer

Tout d'abord, l'ensemble du code source du website est disponible [ici](https://github.com/Campus-INSA-CVL/campus-website). Ainsi, pour les plus connaisseurs de GitHub, vous pouvez simplement soumettre une Pull Request afin de modifier les sources du website. Pour les autres, nous allons voir ensemble comment soumettre vos modifications.

::: warning N'oubliez pas
Pensez à prévenir le respo info ou le respo asso des changements que vous allez réaliser afin de s'assurer que les changements sont bien voulus et qu'ils puissent être accepter.
:::

## Fonctionnement

Afin de simplifier le process de création et de maintien du site, les pages créées ont pour objectif de **récupérer le contenu de fichiers textes** afin de les affichers sur l'écran de l'utilisateur. Ainsi, vous n'aurez qu'à **modifier** de **petits fichiers textes**. Rien de plus simple ! Cela permet aussi de s'affranchir des notions de droits utilisateurs et donc de facilier les passations. Aussi, le président, le secrétaire et plus généralement n'importe qui, sous réserve d'acception des modifications par le respo info ou respo asso, sera en mesure de mettre à jour le contenu du site !

::: tip En savoir plus
Vous pouvez aller lire le [Guide pour les développeur](/guide-dev.html)
:::

## Localisation du contenu

Afin de voir le fichier brut, il vous suffit de vous rendre dans le dossier `content` trouvable sur [GitHub](https://github.com/Campus-INSA-CVL/campus-website/). Ensuite, l'arboresence est assez facile à comprendre puisqu'il s'agit de la même que celle que l'on peut suivre sur le website campus. Les fichiers qui nous interessent le plus sont les fichiers dont l'extension est `md`.

### Arborescence

```
content
|---federation
    |----fichiers et dossiers pour l'ensemblde des fédérations
    index
    |----fichier pour l'acceuil
    olympiade
    |----fichiers pour les olympiades
    outils
    |----fichiers pour présenter les outils
    services
    |----fichiers pour présenter les services
    vie-etudiante
    |----fichiers de présentation de l'INSA et des campus
```

## Modification du contenu

:::tip Création de nouvelles routes
Pour la création d'une nouvelle association, outil ou service (et onglet) ou une modification technique, nous vous invitons à prendre contact avec le BDE
:::

:::tip Expert
Pour les créateurs experts, vous pouvez explorer [cette partie](https://content.nuxtjs.org/writing/) du module utilisé afin de compredre les possibilités offertes par le Markdown. Il notamment possible d'utiliser le front matter afin de stocker des données utilisables par les composants. Il est aussi possible d'utiliser des composants custom ou ceux de [Vuetify](https://vuetifyjs.com).
:::

Il existe un point commun entre toutes ces modifications, elles reposent sur la modification d'un fichier Markdown. Il s'agit de fichier texte qui vont permettre de mettre en place de la sémentique sur votre texte, c'est à dire ce qui est le titre, les paragraphes, un tableau et pleins de choses encore. Vous n'avez pas à vous occuper du design.

Pour en **savoir plus** sur le Markdown: [Getting Started](https://www.markdownguide.org/getting-started/)

Pour **apprendre la synthaxe** (très simple) du Markdown: [Basic Synctax](https://www.markdownguide.org/basic-syntax/)

Pour **écrire du markdown**: [Dillinger](https://dillinger.io/)

### Comment modifier le contenu ?

- Demander au respo info de réaliser les modifications souhaitées

**ou**

- Aller sur [GitHub](https://github.com/Campus-INSA-CVL/campus-website/)
- Parcourir l'arborescence pour trouver le fichier à modifier
- Cliquer sur le crayon, en haut à droite du document
- Modifier
- Envoyer les changements en créant une nouvelle branche afin de générer une nouvelle pull request et en expliquant la motivation des changements dans la description

**ou**

- Effectuer un fork du repo sur votre machine de travail
- Effectuer les modifications en créant une nouvelle branche
- Effectuer une pull request

### Modification de la présentation d'un pôle

- Dans le dossier fédération, se rendre dans le dossier du pôle
- Apporter les modifications au fichier `index.md`

**Exemple**

```md
---
title: pôle culturel <!-- Sera utilisé pour le nom de la card sur la page fédération -->
---

# hello
```

### Modification de l'équipe d'un pôle

- Dans le dossier fédération, se rendre dans le dossier du pôle
- Apporter les modifications au fichier `equipe.md`

**Exemple**

```md
---
title: équipe du pôle culturel <!-- utilsé pour changer le nom de l'onglet -->
color: culturelColor
team: <!-- données utilisées pour la création visuel de la team -->
  bureau:
    - responsability: président
      name: Jules Perrault
      description: responsable de l'association
    - responsability: trésorier
      name: Courtland Vaillancour
      description: Phasellus et laoreet augue. Aliquam tristique nisi sed velit faucibus auctor. Nulla turpis diam, volutpat nec nisl vitae.
      avatar: federation/culturel/tresorier.png
  communication:
    - responsability: responsable communication
      name: Charlotte Beaudoin
      description: gère son équipe de communication afin d'augmenter la visibilité de l'association
---

# L'équipe

<team :team="team" :color="color"></team>
```

### Modification d'une association

- Dans le dossier fédération, se rendre dans le dossier du pôle qui fédère son association
- Chercher ensuite son association dans l'ensemble des dossiers (si elle n'est pas visible, demandez au respo info de la faire)
- Modifier le fichier `index.md`

**Exemple**

```md
---
title: INSAction <!-- utilsé pour changer le nom de l'onglet -->
color: culturelColor
team: <!-- données utilisées pour la création visuel de la team -->
  bureau:
    - responsability: président
      name: Michel Harquin
      description: responsable de l'association
    - responsability: trésorier
      name: Courtland Vaillancour
      description: Phasellus et laoreet augue. Aliquam tristique nisi sed velit faucibus auctor. Nulla turpis diam, volutpat nec nisl vitae.
      avatar: federation/culturel/tresorier.png
  communication:
    - responsability: responsable communication
      name: Charlotte Beaudoin
      description: gère son équipe de communication afin d'augmenter la visibilité de l'association
---

# Bienvenue dans INSAction !

Lorem ipsum dolor sit amet, consectetur adipiscing elit.

# L'équipe

<team :team="team" :color="color"></team>
```

### Modification d'un outil ou d'un service

- Trouver le fichier dans le dossier correspondant
- Procéder aux modifications

**Exemple**

```md
---
title: alumni <!-- utilsé pour changer le nom de la card -->
description: Lorem ipsum dolor sit amet, consectetur adipiscing elit. <!-- utilsé pour changer la description présente sur la card -->
color: alumniColor <!-- utilsé pour changer la couleur présente de la card (en informer le respo info afin qu'il procède aux changements) -->
---

# lorem upsum

Quisque luctus odio et est maximus posuere id nec quam.
```

### Modification d'un onglet, Vie Étudiante / Sports / Représentation

- Trouver le fichier dans le dossier correspondant
- Procéder aux modifications

**Exemple**

```md
---
title: blois <!-- utilsé pour changer le nom de l'onglet -->
order: 2 <!-- utilsé pour ranger les onglets -->
---

# Lorem ipsum dolor sit

Lorem ipsum dolor sit amet, consectetur adipiscing elit.
```

## Les blogs

::: danger Soon
Cette fonction n'est pas encore disponible
:::