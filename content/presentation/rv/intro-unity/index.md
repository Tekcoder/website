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
- Multiplateformes : PC, Mac, consoles, smartphones, web.
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

![Demo time](images/keep-calm-it-is-demo-time.png)

---

## Concepts-clés

---

## Project

- Rassemble tous les éléments constituant le jeu.
- Peut être de type 2D ou 3D.
- Correspond physiquement à un répertoire stocké localement ou dans le *cloud*.

![Fenêtre Project](images/AssetWorkflowFolderAndProjectWindow.png)

---

{{% section %}}

## Asset

- Ressource utilisable dans un projet.
- Nombreux types possibles : image, modèle 3D, texture, fichier audio, script, etc.

![Import d'un Asset](images/AssetWorkflowImportingFiles.png)

---

## Packages

- Plusieurs Assets peuvent être regroupés dans un **package**.
- Unity est livré avec une collections d'**Assets standards** : formes de base, gestion de la caméra, des entrées utilisateur, etc.

---

## Asset Store

- Magasin en ligne proposant de nombreux Assets gratuits ou payants.
- Permet d'importer des packages dans un projet.

![Asset Store](images/AssetStore-download.png)

{{% /section %}}

---

## Scene

- Correspond à une partie du jeu (un niveau).
- Sauvegardées parmi les Assets.

![Nouvelle scène](images/NewEmptyScene.png)

---

{{% section %}}

## GameObject

- Objet qui représente un élément d'une scène.
- Constitué d'un ensemble de **composants**.

![Exemples de GameObjects](images/GameObjectsExamples.png)

---

### Hiérarchie des GameObjects

- Création de hiérarchies parent/enfants à plusieurs niveaux en regroupant des GameObjects.
- Permet de refléter des relations de **dépendance** ou de **composition** entre objets.

![Hiérarchie des GO](images/HierarchyParenting1.png)

{{% /section %}}

---

{{% section %}}

## Composant

Ajoute un comportement à un GameObject.

![Exemples de composants](images/RigidBodyGO.png)

---

## Le composant Transform

Définit la position, la rotation et l'échelle d'un GameObject.

![Transform 1](images/TransformExample2.png)

---

## Transform et hiérarchie

- Position, rotation et échelle d'un GameObject sont relatives à son parent dans la hiérarchie.
- Les valeurs de Transform sont relatives à celles du GameObject parent (**coordonnées locales**) ou absolues en l'absence de parent (**coordonnées globales**).

{{% /section %}}

---

{{% section %}}

## Mesh

Maillage géométrique d'une forme 3D.

![Mesh](images/mesh.png)

---

## Mesh renderer

Composant assurant le rendu d'un Mesh à la position définie par le composant Transform du GameObject.

![Mesh renderer](images/class-MeshRenderer-0.png)

{{% /section %}}

---

## RigidBody

Composant permettant à un GameObject de réagir selon les lois de la physique :

- Gestion de la masse, de la gravité, etc.
- Application de forces.
- Réaction aux collisions.

![RigidBody](images/Inspector-Rigidbody.png)

---

{{% section %}}

## Collider

Composant définissant la forme d'un GameObject pour la gestion des collisions :

- **Primitive Collider** : formes géométriques de base (cube, sphère, cylindre, etc).
- **Mesh Collider** : forme spécifique définie par un Mesh. Plus coûteux en temps de calcul.

Par défaut, des GameObjects possédant un Collider ne peuvent pas se chevaucher.

---

## RigidBody Collider

GameObject possédant un Collider et un RigidBody.

- Soumis aux lois de la physique.
- Déclenche des collisions avec les autres (non-Trigger) Colliders.
- Doit être déplacé en lui appliquand des forces.

---

## Static Collider

GameObject possédant un Collider mais pas de RigidBody.

- Déclenche des collisions avec les RigidBody Colliders, mais ne bouge pas.
- Ne doit pas être déplacé.
- Destiné aux éléments immobiles de la scène (murs, obstacles, etc).

---

## Kinematic RigidBody Collider

GameObject possédant un Collider et un RigidBody défini comme Kinematic.

- N'est pas soumis aux lois de la physique.
- Déclenche des collisions avec les RigidBody Colliders, mais ne bouge pas.
- Peut être déplacé en modifiant son Transform.
- Destiné aux éléments animés du décor (portes, objets à récupérer, etc).

---

## Trigger Collider

GameObject dont le Collider est défini comme Trigger.

![IsTrigger](images/is-trigger-check-box.jpg)

- Autorise le chevauchement sans déclencher de collision.
- Permet de définir une **zone** et de réagir lorsque des RigidBody Colliders y pénètrent.

---
[![Collision Matrix](images/UnityCollisionMatrix.png)](https://docs.unity3d.com/Manual/CollidersOverview.html)

{{% /section %}}

---

## Prefab

- Type d'Asset permettant d'instancier des GameObjects à partir d'un modèle commun.
- Changements d'un Prefab appliqués à toutes ses instances.
- Une instance de Prefab peut aussi être modifiée individuellement.

![Prefab](images/PrefabWithOverride.png)

---

## Light

Type de GameObject permettant d'ajouter une source de lumière à la scène.

![Lights](images/LightMood1.png)

---

## Camera

Type de GameObject qui calcule la vue de la scène affichée au joueur.

![Différentes caméras](images/CameraPerspectiveAndOrtho.jpg)

---

{{% section %}}

## Script

- Type d'Asset permettant de coder le comportement d'un GameObject en langage C# ou UnityScript.
- Doit faire partie des composants du GameObject.
- Peut accéder aux propriétés du GameObject définies par ses autres composants.

---

## Anatomie d'un script

```csharp
// ... (directives using)

// MonoBehaviour : superclasse de tous les scripts Unity
public class MainPlayer : MonoBehaviour {
    // Appelée juste avant le rendu de la première image
    void Start() { ... }

    // Appelée à chaque nouvelle image (frame)
    // L'intervalle de temps entre deux appels peut varier
    void Update() { ... }

    // Appelée à intervalles réguliers (0.02s par défaut)
    void FixedUpdate() { ... }
}
```

{{% /section %}}
