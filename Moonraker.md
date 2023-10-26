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

Vous pouvez ajouter ces macro aussi dans votre configuration:
   ```
   [gcode_macro SET_ACTIVE_SPOOL]  # Définition d'une macro G-code nommée SET_ACTIVE_SPOOL
gcode:  # Début du code de la macro G-code.
description: Indiquer quelle bobine est prise en compte
  {% if params.ID %}  # Vérifie si le paramètre 'ID' est présent dans la commande G-code
    {% set id = params.ID|int %}  # Convertit le paramètre 'ID' en entier et le stocke dans la variable 'id'
    {action_call_remote_method(  # Appelle une méthode distante (définie ailleurs dans le code) avec l'ID du spool en paramètre
       "spoolman_set_active_spool",  # Nom de la méthode à appeler
       spool_id=id  # Paramètre de la méthode, l'ID du spool à définir comme actif
    )}
  {% else %}  # Si le paramètre 'ID' est absent dans la commande G-code
    {action_respond_info("Parameter 'ID' is required")}  # Renvoie une réponse indiquant que le paramètre 'ID' est requis
  {% endif %}  # Fin de la structure conditionnelle

############################################################################################################################

[gcode_macro CLEAR_ACTIVE_SPOOL]  # Définition d'une autre macro G-code nommée CLEAR_ACTIVE_SPOOL
gcode:  # Début du code de la macro G-code
description: effacer les données de la bobine.
  {action_call_remote_method(  # Appelle une méthode distante pour effacer le spool actif (définie ailleurs dans le code)
    "spoolman_set_active_spool",  # Nom de la méthode à appeler
    spool_id=None  # Paramètre de la méthode, défini comme None pour indiquer qu'aucun spool ne doit être actif
  )}
   ```

Vous pouvez maintenant accéder à l'interface de Spoolman en allant a l'adresse suivante:
      ```
      http://adresse_klipper:7912
      ```

![Filament](https://github.com/Eloura74/SpoolMan.md/blob/main/filament.png)
![Bobine](https://github.com/Eloura74/SpoolMan.md/blob/main/general-.png)


Configurez par la suite vos bobine et filaments avec différentes informations.

Pensez à redémarrer Klipper et Moonraker.

Et voilà!!

Si besoin d'une mise à jours, aller voir [Ici](https://github.com/Eloura74/SpoolMan.md/blob/main/Mise_à_jour.md)
