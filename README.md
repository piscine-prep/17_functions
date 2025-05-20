# Bibliothèque de formes : Fonctions et boucles pour dessiner des motifs

## Introduction

Cet exercice vous permettra de combiner l'utilisation des fonctions et des boucles en C pour créer une bibliothèque de dessin de formes dans le terminal. Vous développerez plusieurs fonctions qui génèrent différents motifs géométriques, améliorant ainsi votre compréhension de la modularité et de la réutilisabilité du code.

## Exercice

### Partie 1 : Dessin de lignes et rectangles

Créez un programme C qui contient les fonctions suivantes pour dessiner des formes de base :

1. Une fonction `dessiner_ligne` qui :

   - Prend deux paramètres : une longueur `longueur` et un caractère `symbole`
   - Affiche une ligne horizontale de longueur spécifiée avec le symbole donné
   - Exemple : `dessiner_ligne(5, '*')` affiche `*****`

2. Une fonction `dessiner_rectangle` qui :
   - Prend trois paramètres : `largeur`, `hauteur`, et `symbole`
   - Utilise des boucles for pour afficher un rectangle plein composé du symbole spécifié
   - Utilise la fonction `dessiner_ligne` pour éviter la duplication de code

Voici un exemple de structure pour commencer :

```c
#include <stdio.h>

// Prototypes des fonctions
void dessiner_ligne(int longueur, char symbole);
void dessiner_rectangle(int largeur, int hauteur, char symbole);

int main() {
    // Votre code ici pour tester les fonctions
    return 0;
}

// Définitions des fonctions
void dessiner_ligne(int longueur, char symbole) {
    // Code pour dessiner une ligne horizontale
}

void dessiner_rectangle(int largeur, int hauteur, char symbole) {
    // Code pour dessiner un rectangle en utilisant dessiner_ligne
}
```

### Partie 2 : Triangles et carrés vides

Étendez votre programme en ajoutant les fonctions suivantes :

1. Une fonction `dessiner_carre` qui :

   - Prend deux paramètres : `cote` et `symbole`
   - Utilise la fonction `dessiner_rectangle` pour afficher un carré
   - C'est un raccourci pratique pour dessiner_rectangle lorsque largeur = hauteur

2. Une fonction `dessiner_triangle` qui :

   - Prend deux paramètres : `hauteur` et `symbole`
   - Affiche un triangle rectangle avec le symbole spécifié
   - Exemple pour hauteur=4 :
     ```
     *
     **
     ***
     ****
     ```

3. Une fonction `dessiner_rectangle_vide` qui :

   - Prend trois paramètres : `largeur`, `hauteur`, et `symbole`
   - Affiche seulement le contour d'un rectangle (première et dernière ligne pleines, mais les lignes du milieu n'ont des symboles qu'aux extrémités)

4. Dans le `main`, créez un petit menu avec `scanf` permettant à l'utilisateur·ice de choisir quelle forme dessiner et avec quels paramètres

### Partie 3 : Formes avancées et personnalisation

Complétez votre bibliothèque de formes avec les fonctions suivantes :

1. Une fonction `dessiner_triangle_inverse` qui :

   - Prend deux paramètres : `hauteur` et `symbole`
   - Affiche un triangle rectangle inversé
   - Exemple pour hauteur=4 :
     ```
        *
       **
      ***
     ****
     ```

2. Une fonction `dessiner_carre_vide` qui :

   - Utilise la fonction `dessiner_rectangle_vide` pour afficher un carré vide

3. Une fonction `dessiner_forme_personnalisee` qui :

   - Combine plusieurs formes pour créer un motif plus complexe, comme une maison (triangle sur un carré) ou un sapin de Noël

4. Améliorez votre menu pour inclure toutes ces nouvelles options et permettez à l'utilisateur·ice de spécifier les paramètres de chaque forme

## Résultat Attendu

Votre programme doit afficher un menu interactif et produire des résultats similaires à ceux-ci selon les choix de l'utilisateur·ice :

```
=== BIBLIOTHÈQUE DE FORMES GÉOMÉTRIQUES ===
1. Ligne
2. Rectangle plein
3. Carré plein
4. Triangle
5. Rectangle vide
6. Triangle inversé
7. Carré vide
8. Forme personnalisée
0. Quitter
Choisissez une forme (0-8) : 2

--- Dessin de rectangle ---
Entrez la largeur : 6
Entrez la hauteur : 3
Entrez le symbole : #

######
######
######

=== BIBLIOTHÈQUE DE FORMES GÉOMÉTRIQUES ===
1. Ligne
2. Rectangle plein
3. Carré plein
4. Triangle
5. Rectangle vide
6. Triangle inversé
7. Carré vide
8. Forme personnalisée
0. Quitter
Choisissez une forme (0-8) : 5

--- Dessin de rectangle vide ---
Entrez la largeur : 6
Entrez la hauteur : 3
Entrez le symbole : #

######
#    #
######

=== BIBLIOTHÈQUE DE FORMES GÉOMÉTRIQUES ===
1. Ligne
2. Rectangle plein
3. Carré plein
4. Triangle
5. Rectangle vide
6. Triangle inversé
7. Carré vide
8. Forme personnalisée
0. Quitter
Choisissez une forme (0-8) : 8

--- Dessin de forme personnalisée ---
Entrez la largeur : 5
Entrez la hauteur : 4
Entrez le symbole : *

    *****
   *******
  *********
 ***********

=== BIBLIOTHÈQUE DE FORMES GÉOMÉTRIQUES ===
1. Ligne
2. Rectangle plein
3. Carré plein
4. Triangle
5. Rectangle vide
6. Triangle inversé
7. Carré vide
8. Forme personnalisée
0. Quitter
Choisissez une forme (0-8) : 0

Merci d'avoir utilisé la bibliothèque de formes!
```

## Astuces

- Utilisez des boucles for imbriquées pour contrôler les lignes et les colonnes de vos formes
- N'oubliez pas d'ajouter des retours à la ligne avec `printf("\n")` à la fin de chaque ligne de vos formes
- Pour les formes vides, utilisez des conditions à l'intérieur de vos boucles pour déterminer quand afficher le symbole
- Pour le losange, pensez à gérer les espaces avant et après les symboles
- Utilisez une boucle do-while pour le menu afin qu'il s'affiche au moins une fois
- Pratiquez la réutilisation du code : plusieurs fonctions peuvent appeler des fonctions plus simples

## Pour aller plus loin

Si vous souhaitez approfondir ce projet, vous pourriez explorer :

- La création de formes plus complexes comme des cercles (approximés) ou des étoiles
- L'implémentation d'une fonction qui sauvegarde les dessins dans un fichier texte
- Le dessin de formes remplies avec différents symboles pour le contour et l'intérieur
- La création d'une animation simple en effaçant et redesssinant l'écran (avec des délais)

---

_Les fonctions combinées aux boucles offrent un vaste potentiel créatif, même dans un environnement aussi simple que le terminal texte. Ce projet vous aide à comprendre comment décomposer un problème complexe en fonctions plus simples et réutilisables._
