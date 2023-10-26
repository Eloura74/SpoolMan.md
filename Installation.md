# Suivi de l'inventaire des bobines de filament 3D avec Spoolman

Spoolman est un service web qui vous aide à suivre vos bobines de filament et leur utilisation.

Il agit comme une base de données, où d'autres logiciels d'impression tels qu'Octoprint et Moonraker peuvent interagir pour avoir un endroit centralisé pour les informations sur les bobines. Par exemple, s'il est utilisé avec Moonraker, le poids de votre bobine sera automatiquement réduit pendant l'impression.

Il expose une API HTTP avec laquelle les services peuvent interagir. Voir la description OpenAPI pour plus d'informations.

## Client
Spoolman comprend un client web qui vous permet de manipuler directement toutes les données. Il a également quelques fonctionnalités supplémentaires telles que l'impression d'étiquettes.

![Icône d'une bobine de filament](lien_vers_l_image)

Le client web est traduit par la communauté via Weblate.

## État d'intégration
Spoolman est encore relativement nouveau, donc le support n'est pas encore généralisé, mais il est activement intégré à plusieurs projets différents.

- ✔️ Moonraker - Voir la documentation Moonraker
- ✔️ Fluidd
- ✔️ KlipperScreen
- ✔️ Mainsail
- ✖️ Octoprint - Un plugin est en cours de développement : OctoPrint-Spoolman

## Installation
Spoolman peut interagir avec l'une des bases de données suivantes : SQLite, PostgreSQL, MySQL, MariaDB, CockroachDB. Par défaut, SQLite est utilisé, c'est une solution de base de données simple et sans installation qui enregistre dans un seul fichier .db situé dans le répertoire utilisateur du serveur.

Spoolman peut être installé de deux manières, soit directement sur votre machine, soit en utilisant Docker. Si vous avez déjà Docker installé, il est recommandé d'utiliser cette méthode.

### Autonome
Ce guide d'installation suppose que vous utilisez une distribution Linux basée sur Debian telle qu'Ubuntu ou Raspberry Pi OS. Si vous utilisez une autre distribution, veuillez consulter les scripts bash pour voir quelles commandes sont exécutées et les adapter à votre distribution.

1. Téléchargez ce dépôt sur votre machine. Il est recommandé de télécharger la dernière version depuis la page des versions. Il s'agit du fichier Source code (zip) que vous voulez. Vous pouvez également cloner le dépôt Git si vous voulez être à la pointe de la technologie.
   
   ```bash
   unzip Spoolman-*.zip
    ```
Cela va créer un dossier "Spoolman-<version>.
Accédez au répertoire Spoolman-<version>.
    ```
    cd Spoolman-<version>
    ```
    
Exécutez le script d'installation Debian.

  ```
  bash ./scripts/install_debian.sh
  ```

Suivez les instructions à l'écran pour installer toutes les dépendances et configurer Spoolman.Il vous sera demandé de taper "y" pour accepter de le lancer à chaque redémarrage.

Ensuite nous allons intégrer ceci dans Moonraker.

