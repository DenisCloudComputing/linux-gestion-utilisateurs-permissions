Lab 03 — Propriétaires avec chown et chgrp

  Objectif
Modifier le propriétaire et le groupe d'un fichier ou répertoire.

  Commandes pratiquées

| Commande | Description | Exemple |
|----------|-------------|---------|
| `chown` | Changer le propriétaire | `sudo chown denis fichier.txt` |
| `chown user:group` | Changer proprio ET groupe | `sudo chown denis:devops fichier.txt` |
| `chgrp` | Changer seulement le groupe | `sudo chgrp devops fichier.txt` |
| `chown -R` | Changer récursivement | `sudo chown -R denis:devops dossier/` |

  Notes importantes
- `chown` nécessite `sudo` (seul root peut changer le propriétaire)
- `-R` = récursif (applique à TOUT le contenu d'un dossier)
- En cloud, le propriétaire détermine QUI peut gérer le fichier
- Principe du moindre privilège : donner le MINIMUM de droits nécessaires

 🔗 Lien avec AWS

 Sur une instance EC2 Debian :
Le fichier /var/www/html/index.html doit appartenir
à www-data (le serveur web Apache/Nginx)

sudo chown www-data:www-data /var/www/html/index.html
sudo chmod 644 /var/www/html/index.html

→ Le serveur web peut LIRE le fichier
→ Seul www-data peut le MODIFIER
→ Personne d'autre ne peut le toucher


 📸 Captures
À ajouter après le lab
