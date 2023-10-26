# Mise à jour de Spoolman

La mise à jour de Spoolman est assez simple. Si vous utilisez le type de base de données par défaut, SQLite, il est stocké en dehors du dossier d'installation (dans ~/.local/share/spoolman), donc vous ne perdrez aucune donnée en passant à un nouveau dossier d'installation. Suivez ces étapes pour mettre à jour :

1. Si vous exécutez Spoolman en tant que service systemd, arrêtez-le et désactivez-le en utilisant systemctl :
   
   ```
   bash systemctl --user stop Spoolman && systemctl --user disable Spoolman
   ```
