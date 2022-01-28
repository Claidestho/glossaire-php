# Glossaire PHP

## Déclaration de variables

Les variables en PHP sont déclarés de la manière suivante :
`$var1 = valeur`. En PHP pas besoin de déclarer de type.
---
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
* **print_r()** : Affiche les éléments d'une array ainsi que leurs index. ⇉ wrapper avec \<pre> pour une meilleure lisibilité
* **array_pop()** : Permet de retirer un élément en partant de la fin d'une array et le retourner pour qu'il puisse être
  assigné à une nouvelle variable si on le souhaite.
* **array_push()** : Ajoute un ou plusieurs éléments à la fin d'une array. Retourne le nombre total d'éléments après
  ajout.
* **array_shift()** : Pop le premier élément d'une array, retourne sa valeur.
* **array_unshift()** : Add un ou plusieurs éléments au début d'une array, retourne le nombre total d'éléments après
  ajout.
* **unset()** : Permet de retirer entièrement une paire clé / valeur d'un tableau associatif.
* **rand()** : Permet de retourner un nombre aléatoire.
* **var_dump($)** : Affiche des informations concernant les variables choisies. Cette commande donne la valeur de la variable mais peut également donner le type de celle ci (float, int...).
---
### Ajouter un élément à une array

* **$string_array[] = "third element";** → Ajouter la valeur à la fin de l'array existante.
* **$string_array[x] = "third element";** ⇾ Change la valeur à l'index X de l'array existante.
---
### Créer une map / Array associative

* $my_array = ["panda" => "very cute", "lizard" => "cute", "cockroach" => "not very cute"];
* $about_me = array(
  "fullname" => "Aisle Nevertell",
  "social" => 123456789
  );
* $php_array = array(
  "language" => "PHP",
  "creator" => "Rasmus Lerdorf",
  "year_created" => 1995,
  "filename_extensions" =>  [".php", ".phtml", ".php3", ".php4", ".php5", ".php7", ".phps", ".php-s", ".pht", ".phar"]
  );
## Les boucles 

* **while()** : <br />``$count = 1;``<br />``
  while ($count < 11)
  {``<br />``
  echo "The count is: " . $count . "\n";``<br />``
  $count += 1;
  }``
* **do{}...while()** : Semblable à une boucle while, seulement l'instruction sera toujours executée une fois avant même de vérifier la condition de répétition. Si la condition est fausse, elle sera donc executée qu'une seule fois quoi qu'il arrive. PENSER AU POINT VIRGULE A LA FIN DU WHILE.
  <br />``$count = 1;``<br />``
  do {``<br />``
  echo "The count is: " . $count . "\n";``<br />``
  $count += 1;``<br />``
  } while ($count < 11);``<br />

* **for() :** <br />``for (#expression 1; #expression 2; #expression 3)``<br />``
  {``<br />``
  // code block``<br />``
}``
* **foreach()** : Cette boucle permet de faire des itérations parmi tous les éléments d'un tableau, en associant une variable temporaire qui prendre le rôle de réceptacle aux différentes valeurs des éléments de l'array :<br />`$counting_array = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];`<br />`
  foreach ($counting_array as $count) {`<br />`
  echo "The count is: " . $count . "\n";`<br />`
  }`<br />
Les boucles **foreach** peuvent également être utilisées avec des tableaux associatifs, afin de stocker clés et valeurs même temps.
* **break** : La commande break permet d'interrompre une boucle avant que la condition ne soit remplie.
* **continue** : Cette commande permet d'indiquer qu'il faut stopper l'itération en cours et reprendre à la suivante suivant une condition.

# Fonctions 

* Pour déclarer une fonction on utilise la commande "function" : ```function bonjour()```
* Les fonctions comme en java peuvent retourner des valeurs, qui peuvent être associées à une variable par exemple grâce à ``return``
* Le retour peut être affiché directement sans avoir à l'attribuer à une variable : ``echo bonjour()``. On peut donc faire directement des opérations grâce aux valeurs retournées par la fonction.
* Les fonctions qui n'ont pas pour but de retourner de valeurs retournent tout de même quoi qu'il arrive la valeur ```NULL```
* Pour le passage de paramètres, il suffit d'indiquer des variables porte-noms entre les parenthèses d'initialisation de la fonction :
`function sayCustomHello($name, $age)`
* Il est possible d'indiquer une valeur de paramètre par défaut, pour éviter de provoquer des erreurs si aucun paramètre n'est renseigné lors de l'appel de la fonction : <br />``function sayCustomHello($name  = "old chum")``<br />``
  {``<br />``
  echo "Hello, $name!";``<br />``
  };``<br />
* Il est possible de faire en sorte que les variables passées en paramètres d'une fonction soit modifiées de manière permanente par les instructions de la fonction :
  <br />``function addXPermanently (&$param)``<br />``
  {``<br />``
  $param = $param . "X";``<br />``
  echo $param;``<br />``
  };``<br />``
* Tous les paramètres définis dans une fonction ne peuvent pas être accédés en dehors de la fonction, à cause du scope local de ceux ci.
* Pour pouvoir utiliser une variable définie précédement à l'intérieur d'une fonction il faut utiliser le mot-clé **global**.

## Conditions

* **Opérateur ?:** : Permet de vérifier si une condition est vraie ou fausse, et de retourner une valeur en fonction. Exemple :<br />
``$isClicked = FALSE;``<br />``
  $link_color = $isClicked ? "purple" : "blue";`` -> Retourne "purple" ou "blue"<br /><br />
`function ternaryCheckout($items){`<br />`
  return $items <= 12 ? "express lane" : "regular lane";`<br />`
  }`<br />

## Valeurs / Expressions retournant FALSE
* Strings vides
* null
* Variables non définies ou non déclarées
* Array vide
* Le chiffre 0
* La string "0"

## Opérateurs conditionels

* **||** : OR
* **&&** : AND
* **!value** : NOT

# Formulaires / Back-end spécificités / PHP&HTML
## Les variables super globales
* Les variables superglobales sont des variables qui peuvent être utilisées dans tous les scopes possibles. Elles sont générées automatiquement et sont reliées aux requêtes HTTP.
  * **Liste des superglobals :**
    * **$GLOBALS**
    * **$_SERVER**
    * **$_GET** = Contient un tableau associatif des variables passées dans l'URL via des paramètres.
    * **$_POST** -> Contient un tableau associatif des variables passées via l'envoi d'un formulaire avec méthode POST.
    * **$_FILES**
    * **$_COOKIE**
    * **$_SESSION**
    * **$_REQUEST** = Contient tous les éléments des variables $_COOKIE, $_GET et $_POST.
    * **$_ENV**

# Back-end validation

* Validation = Vérifier que les informations transmises par le biais d'un formulaire par l'utilisateur soient conformes au type de valeur attendu. On
* La validation au niveau du back-end est impérative car la validation coté client reste peu sécurisée et le risque d'attaque entre le client et le back est important. Il est donc important de validesr une seconde fois les informations envoyées.
* La validation coté back-end permet également de comparer l'info envoyée avec celles présentes en BDD (username/MDP par exemple).
* Dernière défense, permet également de reformater toutes les données envoyées pour être sûr que la BDD soit uniforme.