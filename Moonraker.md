# Configuration de l'intégration Spoolman dans moonraker.conf

Pour intégrer Spoolman avec Moonraker et envoyer automatiquement les mises à jour d'utilisation du filament à la base de données Spoolman, suivez ces étapes :

   Permet l'intégration avec le gestionnaire de filament Spoolman. Moonraker enverra automatiquement les mises à jour d'utilisation du filament à la base de données Spoolman.

 **Fichier `moonraker.conf`**

   ```ini
   [spoolman]
   server: http://<adresse_klipper>:7912
   # URL vers l'instance Spoolman. Ce paramètre doit être fourni.
   sync_rate: 5
   # L'intervalle, en secondes, entre les requêtes de synchronisation avec le
   # serveur Spoolman. Par défaut, c'est 5 secondes.
