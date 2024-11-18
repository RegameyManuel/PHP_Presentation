# Introduction au PHP : Histoire, Syntaxe et Exemples de Code

## Qu'est-ce que PHP ?

PHP (Hypertext Preprocessor) est un langage de script open-source côté serveur, principalement utilisé pour le développement web. Il est intégré au code HTML et permet de créer des pages web dynamiques et interactives. Grâce à sa simplicité et sa flexibilité, PHP est l'un des langages les plus populaires pour le développement de sites web.

## Histoire de PHP

- **1994** : Création de PHP par Rasmus Lerdorf pour gérer son site web personnel.
- **1995** : Publication de PHP/FI (Personal Home Page / Forms Interpreter).
- **1997** : Sortie de PHP 3, réécrit par Andi Gutmans et Zeev Suraski, introduisant la syntaxe que nous connaissons aujourd'hui.
- **2000** : Lancement de PHP 4 avec le moteur Zend, améliorant les performances et la gestion des ressources.
- **2004** : Introduction de PHP 5, apportant un meilleur support de la programmation orientée objet.
- **2015** : PHP 7 offre des améliorations significatives en performance et en utilisation de la mémoire.
- **2020** : Sortie de PHP 8 avec de nouvelles fonctionnalités comme le compilateur Just-In-Time (JIT).

## Syntaxe de Base de PHP

### Balises PHP

Le code PHP est inclus entre les balises `<?php` et `?>`.

```php
<?php
// Votre code PHP ici
?>
```

### Afficher du Texte

Pour afficher du texte, utilisez la fonction `echo` ou `print`.

```php
<?php
echo "Bonjour le monde !";
?>
```

### Variables

Les variables en PHP commencent par le signe `$` suivi du nom de la variable.

```php
<?php
$nom = "Alice";
$age = 25;
?>
```

### Types de Données

- **Chaînes de caractères (string)** : `$texte = "Bonjour";`
- **Entiers (integer)** : `$nombre = 10;`
- **Flottants (float)** : `$prix = 19.99;`
- **Booléens (boolean)** : `$estVrai = true;`
- **Tableaux (array)** : `$fruits = array("Pomme", "Banane");`
- **Null** : `$valeur = null;`

### Opérateurs

#### Opérateurs Arithmétiques

- Addition : `$a + $b`
- Soustraction : `$a - $b`
- Multiplication : `$a * $b`
- Division : `$a / $b`
- Modulo : `$a % $b`

#### Opérateurs de Comparaison

- Égal à : `$a == $b`
- Identique à : `$a === $b` (même valeur et même type)
- Différent de : `$a != $b` ou `$a <> $b`
- Non identique à : `$a !== $b`
- Plus grand que : `$a > $b`
- Plus petit que : `$a < $b`

#### Opérateurs Logiques

- ET : `$a && $b` ou `$a and $b`
- OU : `$a || $b` ou `$a or $b`
- NON : `!$a`

## Structures de Contrôle

### Conditions If...Else

```php
<?php
$heure = 20;
if ($heure < 12) {
    echo "Bonjour";
} elseif ($heure < 18) {
    echo "Bon après-midi";
} else {
    echo "Bonsoir";
}
?>
```

### Switch

```php
<?php
$jour = "Lundi";
switch ($jour) {
    case "Lundi":
        echo "Bon début de semaine";
        break;
    case "Vendredi":
        echo "Bon week-end";
        break;
    default:
        echo "Bonne journée";
        break;
}
?>
```

### Boucles

#### Boucle While

```php
<?php
$i = 1;
while ($i <= 5) {
    echo "Nombre : $i<br>";
    $i++;
}
?>
```

#### Boucle For

```php
<?php
for ($i = 1; $i <= 5; $i++) {
    echo "Nombre : $i<br>";
}
?>
```

#### Boucle Foreach

```php
<?php
$fruits = array("Pomme", "Banane", "Orange");
foreach ($fruits as $fruit) {
    echo "Fruit : $fruit<br>";
}
?>
```

## Fonctions

### Définir et Appeler une Fonction

```php
<?php
function saluer($nom) {
    return "Bonjour, $nom!";
}

echo saluer("Alice");
?>
```

## Tableaux

### Tableaux Indexés

```php
<?php
$couleurs = array("Rouge", "Vert", "Bleu");
echo $couleurs[0]; // Affiche "Rouge"
?>
```

### Tableaux Associatifs

```php
<?php
$ages = array("Alice" => 25, "Bob" => 30);
echo $ages["Alice"]; // Affiche 25
?>
```

### Fonctions sur les Tableaux

- **count($tableau)** : Retourne le nombre d'éléments.
- **array_push($tableau, $valeur)** : Ajoute un élément à la fin.
- **array_pop($tableau)** : Supprime le dernier élément.

## Inclusion de Fichiers

- **include "fichier.php";** : Inclut le fichier spécifié.
- **require "fichier.php";** : Même chose que include, mais génère une erreur fatale en cas d'échec.

```php
<?php
include "header.php";
require "config.php";
?>
```

## Gestion des Formulaires

### Formulaire HTML

```html
<form action="traitement.php" method="post">
    Nom: <input type="text" name="nom">
    <input type="submit" value="Envoyer">
</form>
```

### Traitement en PHP

```php
<?php
// traitement.php
if ($_SERVER["REQUEST_METHOD"] == "POST") {
    $nom = $_POST['nom'];
    echo "Bonjour, $nom!";
}
?>
```

## Superglobales

- **$_GET** : Contient les variables passées par l'URL.
- **$_POST** : Contient les variables passées par formulaire en méthode POST.
- **$_REQUEST** : Contient les variables de $_GET, $_POST et $_COOKIE.
- **$_SESSION** : Contient les variables de session.
- **$_COOKIE** : Contient les cookies.

## Sessions et Cookies

### Sessions

#### Démarrer une Session

```php
<?php
session_start();
$_SESSION['utilisateur'] = "Alice";
?>
```

#### Accéder aux Données de Session

```php
<?php
session_start();
echo $_SESSION['utilisateur'];
?>
```

### Cookies

#### Créer un Cookie

```php
<?php
setcookie("utilisateur", "Alice", time() + (86400 * 30), "/"); // 86400 = 1 jour
?>
```

#### Accéder à un Cookie

```php
<?php
if(isset($_COOKIE['utilisateur'])) {
    echo "Utilisateur : " . $_COOKIE['utilisateur'];
} else {
    echo "Cookie non défini.";
}
?>
```

## Gestion des Erreurs

### Try...Catch

```php
<?php
try {
    // Code pouvant générer une exception
    throw new Exception("Une erreur est survenue");
} catch (Exception $e) {
    echo "Message d'erreur : " . $e->getMessage();
}
?>
```

## Bonnes Pratiques

- **Validation des Entrées** : Toujours valider et assainir les données entrantes.
- **Sécurité** : Protégez votre code contre les injections SQL et les failles XSS.
- **Commentaires** : Commentez votre code pour une meilleure compréhension.
- **Indentation** : Indentez correctement votre code pour améliorer la lisibilité.
- **Réutilisation du Code** : Utilisez des fonctions pour éviter la redondance.

