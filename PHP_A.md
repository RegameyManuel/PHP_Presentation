PHP, ou "PHP: Hypertext Preprocessor", est un langage de script côté serveur largement utilisé pour le développement web. Il permet de créer des pages web dynamiques qui peuvent interagir avec des bases de données et des fichiers sur le serveur. PHP est particulièrement célèbre pour sa facilité d'intégration avec le HTML et son vaste écosystème de frameworks et bibliothèques.

### Exemples de Code en PHP

1. **Hello World en PHP**:
   ```php
   <?php
   echo "Hello, World!";
   ?>
   ```
   Ce simple script affiche le texte "Hello, World!" sur la page web.

2. **Connexion à une base de données MySQL**:
   ```php
   <?php
   $servername = "localhost";
   $username = "username";
   $password = "password";
   $dbname = "myDB";

   // Création de la connexion
   $conn = new mysqli($servername, $username, $password, $dbname);

   // Vérification de la connexion
   if ($conn->connect_error) {
       die("Connection failed: " . $conn->connect_error);
   }
   echo "Connected successfully";
   ?>
   ```
   Ce script PHP crée une connexion à une base de données MySQL et vérifie si la connexion est réussie.

3. **Traitement d'un formulaire**:
   ```php
   <form method="post" action="<?php echo $_SERVER['PHP_SELF'];?>">
     Nom: <input type="text" name="fname">
     <input type="submit">
   </form>

   <?php
   if ($_SERVER["REQUEST_METHOD"] == "POST") {
       // collect value of input field
       $name = htmlspecialchars($_REQUEST['fname']);
       if (empty($name)) {
           echo "Name is empty";
       } else {
           echo "Name is: " . $name;
       }
   }
   ?>
   ```
   Ce formulaire HTML envoie des données à la même page PHP, qui traite ensuite les données et affiche le nom saisi par l'utilisateur.

4. **Utilisation des sessions pour sauvegarder des données**:
   ```php
   <?php
   session_start();
   // Stockage de la donnée de session
   $_SESSION["favcolor"] = "green";
   echo "Session variable set.";
   ?>
   ```
   Ce code initialise une session et stocke une information au sein de cette session, qui peut être utilisée sur différentes pages du même site.

### Points Clés de PHP Adaptés au Développement Web Côté Serveur

1. **Intégration facile avec HTML**: PHP peut être intégré directement dans le code HTML. Cela simplifie la création de contenus web dynamiques.

2. **Large base de bibliothèques et de frameworks**: PHP bénéficie de nombreux frameworks (Laravel, Symfony, etc.) qui accélèrent le développement et facilitent la maintenance.

3. **Gestion de base de données**: PHP supporte une multitude de systèmes de gestion de base de données comme MySQL, PostgreSQL et SQLite, rendant la gestion de données facile et flexible.

4. **Hébergement répandu**: La majorité des fournisseurs d'hébergement web supportent PHP, souvent sans frais supplémentaires.

5. **Grande communauté**: PHP dispose d'une large communauté de développeurs, ce qui assure une grande quantité de ressources, de tutoriels et de forums pour aider les nouveaux développeurs.

6. **Traitement côté serveur**: Comme PHP s'exécute sur le serveur, cela permet un contrôle complet du comportement de l'application avant d'envoyer le contenu au client, optimisant ainsi la sécurité et l'accès aux ressources du serveur.

7. **Flexible et dynamique**: PHP est adapté pour créer des applications web petites à grandes échelles, et peut gérer des sites statiques aussi bien que des applications web complexes.

8. **Support pour les API**: PHP peut facilement travailler avec des API et des services web, facilitant l'intégration avec d'autres applications et plateformes.

Ce panorama de PHP illustre bien pourquoi ce langage reste un pilier du développement web, notamment pour les applications nécessitant une interaction intense avec des bases de données et un traitement dynamique côté serveur.