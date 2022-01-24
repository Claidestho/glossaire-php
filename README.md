# Glossaire PHP

## Déclaration de variables

Les variables en PHP sont déclarés de la manière suivante :
`$var1 = valeur`. En PHP pas besoin de déclarer de type.

## Les commandes de base

* **echo** : Echo permet d'afficher des élements à l'écran, de manière similaire à un print en Java ou autre. Il est
  possible grâce à cette balise de rajouter des balises HTML qui seront lu par le navigateur.
    * Exemple : `echo "<p>Ceci est un nouveau paragraphe</p>";`

* **include** : Cette commande permet d'intégrer au code PHP courant une autre page PHP. Cela peut notamment être très
  pratique afin d'inclure footer/header à chaque page sans devoir les réécrire à chaque fois.
    * Exemple : `ìnclude 'footer.php';`

* **array()** : Créer une liste ordonnée d'éléments.

* **count()** : Permet de compter le nombre d'éléments d'une array.
* **implode($glue, $pieces)** : Convertit une array en string pour en afficher les éléments.
* **print_r()** : Affiche les éléments d'une array ainsi que leurs index.
* **array_pop()** : Permet de retirer un élément en partant de la fin d'une array et le retourner pour qu'il puisse être
  assigné à une nouvelle variable si on le souhaite.
* **array_push()** : Ajoute un ou plusieurs éléments à la fin d'une array. Retourne le nombre total d'éléments après
  ajout.
* **array_shift()** : Pop le premier élément d'une array, retourne sa valeur.
* **array_unshift() : Add un ou plusieurs éléments au début d'une array, retourne le nombre total d'éléments après
  ajout.

### Ajouter un élément à une array

* **$string_array[] = "third element";** -> Ajouter la valeur à la fin de l'array existante.
* **$string_array[x] = "third element";** -> Change la valeur à l'index X de l'array existante.