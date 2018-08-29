---
title: "Introduction à Unity"
date: 2018-08-25T16:13:52+02:00
draft: true
---

## Sommaire

- Unity en bref
- L'éditeur Unity
- Concepts-clés

---

## Unity en bref

---

![Logo Unity](images/Unity_Technologies_Logo.svg.png)

- Moteur de jeu développé par [Unity Technologies](https://en.wikipedia.org/wiki/Unity_Technologies) depuis 2004.
- Multiplateformes (PC, Mac, consoles, smartphones, web).
- [Licence personnelle](https://store.unity.com/fr/products/unity-personal) gratuite.

---

{{< youtube id="ctNF6QlLBWo" class="youtube-player" >}}

---

## L'éditeur Unity

---

![Unity editor 1](images/Editor-Breakdown.jpg)

---

![Unity editor 2](images/unity-editor.png)

---

## Concepts-clés

---

## Project

- Peut être de type 2D ou 3D.
- Correspond physiquement à un répertoire stocké localement ou dans le *cloud*.

![Fenêtre Project](images/AssetWorkflowFolderAndProjectWindow.png)

---

{{% section %}}

## Asset

- Ressource utilisable dans Unity.
- Nombreux types possibles : image, modèle 3D, fichier audio, etc.

![Import d'un asset](images/AssetWorkflowImportingFiles.png)

---

## Packages

- Plusieurs assets peuvent être regroupés dans un **package**.
- Unity est livré avec une collections d'**assets standards** : formes de base, gestion de la caméra, des entrées utilisateur, etc.

---

## Asset Store

- Magasin en ligne proposant de nombreux assets gratuits ou payants.
- Permet d'importer des packages dans un projet.

![Asset Store](images/AssetStore-download.png)

{{% /section %}}

---

## Scene

- Correspond à un niveau du jeu.
- Sauvegardées parmi les assets.

![Nouvelle scène](images/NewEmptyScene.png)

---

{{% section %}}

## GameObject

- Objet qui représente un élément d'une scène Unity.
- Constitué d'un ensemble de **composants**.

![Exemples de GameObjects](images/GameObjectsExamples.png)

---

### Hiérarchie des GameObjects

- Il est possible de regrouper des objets pour former des hiérarchies parent/enfants à plusieurs niveaux.
- Permet de définir des propriétés communes ou de refléter des relations de composition entre objets.

![Hiérarchie des GO](images/HierarchyParenting1.png)

{{% /section %}}

---

{{% section %}}

## Composant

Ajoute un comportement à un GameObject.

![Exemples de composants](images/RigidBodyGO.png)

---

## Le composant Transform

Définit la position, l'orientation et l'échelle d'un GameObject.

![Transform 1](images/TransformExample2.png)

---

## Transform et hiérarchie

- Position, orientation et échelle d'un GameObject sont relatives à son parent dans la hiérarchie.
- Les valeurs de Transform sont relatives à celles du GameObject parent (**coordonnées locales**) ou absolues en l'absence de parent (**coordonnées globales**).

{{% /section %}}

---

## Mesh

TODO

---

## Collider

TODO

---

## Script

TODO
