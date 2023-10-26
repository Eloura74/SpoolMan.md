![Spoolman](https://github.com/Eloura74/SpoolMan.md/blob/main/principale.png)
# Suivi de l'inventaire des bobines de filament 3D avec Spoolman

Spoolman est un service web qui vous aide à suivre vos bobines de filament et leur utilisation.

Il agit comme une base de données, où d'autres logiciels d'impression tels qu'Octoprint et Moonraker peuvent interagir pour avoir un endroit centralisé pour les informations sur les bobines. Par exemple, s'il est utilisé avec Moonraker, le poids de votre bobine sera automatiquement réduit pendant l'impression.

Il expose une API HTTP avec laquelle les services peuvent interagir.

## Client
Spoolman comprend un client web qui vous permet de manipuler directement toutes les données. Il a également quelques fonctionnalités supplémentaires telles que l'impression d'étiquettes.


## État d'intégration
Spoolman est encore relativement nouveau, donc le support n'est pas encore généralisé, mais il est activement intégré à plusieurs projets différents.

- ✔️ Moonraker - Voir la documentation Moonraker
- ✔️ Fluidd
- ✔️ KlipperScreen
- ✔️ Mainsail
- ✖️ Octoprint - Un plugin est en cours de développement : OctoPrint-Spoolman

## Installation
Spoolman peut interagir avec l'une des bases de données suivantes : SQLite, PostgreSQL, MySQL, MariaDB, CockroachDB. Par défaut, SQLite est utilisé, c'est une solution de base de données simple et sans installation qui enregistre dans un seul fichier .db situé dans le répertoire utilisateur du serveur.

Spoolman peut être installé de deux manières, soit directement sur votre machine, soit en utilisant Docker. Ici nous allons l'installer directement sur la machine.

### Installation
Ce guide d'installation suppose que vous utilisez une distribution Linux basée sur Debian telle qu'Ubuntu ou Raspberry Pi OS. Si vous utilisez une autre distribution, veuillez consulter les scripts bash pour voir quelles commandes sont exécutées et les adapter à votre distribution.

1. Téléchargez le dépôt sur votre machine. Il est recommandé de télécharger la dernière version depuis la page des versions. Il s'agit du fichier Source code (zip) que vous voulez. [Lien](https://github.com/Donkie/Spoolman/releases) vers ce dépot.

2. Une fois le fichier Zip mis sur votre machine decompressez le :
   
   ```
   unzip Spoolman-*.zip
    ```
Cela va créer un dossier "Spoolman-version".

3. Accédez au répertoire Spoolman-<version>:

    ```
    cd Spoolman-<version>
    ```
    
4. Exécutez le script d'installation Debian.

     ```
     bash ./scripts/install_debian.sh
     ```

5. Suivez les instructions à l'écran pour installer toutes les dépendances et configurer Spoolman.Il vous sera demandé de taper "y" pour accepter de le lancer à chaque redémarrage.

6. Ensuite nous allons intégrer ceci dans [Moonraker](https://github.com/Eloura74/SpoolMan.md/blob/main/Moonraker.md).

