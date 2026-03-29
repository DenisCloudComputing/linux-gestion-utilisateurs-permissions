  Aide-Mémoire — Permissions et Utilisateurs Linux

 👤 Gestion des utilisateurs
| Commande | Action |
|----------|--------|
| `sudo useradd -m nom` | Créer un utilisateur avec home |
| `sudo passwd nom` | Définir son mot de passe |
| `sudo usermod -aG groupe nom` | Ajouter à un groupe |
| `sudo userdel -r nom` | Supprimer utilisateur + home |
| `id nom` | Voir uid, gid, groupes |
| `whoami` | Mon nom d'utilisateur |
| `groups nom` | Ses groupes |

 Permissions
| Commande | Action |
|----------|--------|
| `ls -la` | Voir les permissions |
| `chmod 755 fichier` | rwxr-xr-x |
| `chmod 644 fichier` | rw-r--r-- |
| `chmod 600 fichier` | rw------- |
| `chmod +x fichier` | Ajouter exécution |

 Propriétaires
| Commande | Action |
|----------|--------|
| `sudo chown user fichier` | Changer le proprio |
| `sudo chown user:group fichier` | Changer proprio + groupe |
| `sudo chgrp group fichier` | Changer le groupe |
| `sudo chown -R user:group dossier/` | Récursif |

  Mémo notation octale
  r = 4   w = 2   x = 1

7 = rwx (4+2+1) Tout
6 = rw- (4+2) Lire + Écrire
5 = r-x (4+1) Lire + Exécuter
4 = r-- (4) Lire seulement
0 = --- (0) Rien


  Permissions critiques en Cloud
chmod 600 ma-cle.pem ← Clé SSH AWS
chmod 700 ~/.ssh/ ← Dossier SSH
chmod 644 /etc/config ← Config lisible
chmod 755 /opt/script.sh ← Script exécutable


------------------------------------------------------------------------------------
Aide-mémoire mis à jour au fil de ma formation
