# Configuration de l'intégration Spoolman dans moonraker.conf

Pour intégrer Spoolman avec Moonraker et envoyer automatiquement les mises à jour d'utilisation du filament à la base de données Spoolman, suivez ces étapes :

   Permet l'intégration avec le gestionnaire de filament Spoolman. Moonraker enverra automatiquement les mises à jour d'utilisation du filament à la base de données Spoolman.

 **Ouvrez le fichier `moonraker.conf`**

   ```ini
   [spoolman]
   server: http://<adresse_klipper>:7912
   # URL vers l'instance Spoolman. Ce paramètre doit être fourni.
   sync_rate: 5
   # L'intervalle, en secondes, entre les requêtes de synchronisation avec le
   # serveur Spoolman. Par défaut, c'est 5 secondes.
   ```

Pensez bien à remplacer l'adresse klipper par l'adresse de votre machine.

Vous pouvez maintenant accéder à l'interface de Spoolman en allant a l'adresse suivante:
      ```
      http://adresse_klipper:7912
      ```

Configurez par la suite vos bobine et filaments avec différentes informations.
