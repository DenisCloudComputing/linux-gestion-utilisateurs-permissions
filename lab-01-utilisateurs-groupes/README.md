 Lab 01 — Gestion des Utilisateurs et Groupes

  Objectif
Créer, modifier et supprimer des utilisateurs et groupes sous Linux.

  Commandes pratiquées

 Utilisateurs
| Commande | Description | Exemple |
|----------|-------------|---------|
| `useradd` | Créer un utilisateur | `sudo useradd denis` |
| `useradd -m` | Créer avec répertoire home | `sudo useradd -m denis` |
| `usermod` | Modifier un utilisateur | `sudo usermod -aG sudo denis` |
| `userdel` | Supprimer un utilisateur | `sudo userdel denis` |
| `passwd` | Changer le mot de passe | `sudo passwd denis` |
| `id` | Voir l'identité d'un utilisateur | `id denis` |
| `whoami` | Qui suis-je ? | `whoami` |

 Groupes
| Commande | Description | Exemple |
|----------|-------------|---------|
| `groupadd` | Créer un groupe | `sudo groupadd devops` |
| `groupdel` | Supprimer un groupe | `sudo groupdel devops` |
| `groups` | Voir les groupes d'un utilisateur | `groups denis` |
| `usermod -aG` | Ajouter à un groupe | `sudo usermod -aG devops denis` |

 Notes importantes
- `-m` dans `useradd -m` crée le répertoire `/home/utilisateur`
- `-aG` dans `usermod -aG` = append to Group (AJOUTER sans retirer les autres groupes)
- Sans le `-a`, l'utilisateur est RETIRÉ de tous ses autres groupes !
- `id denis` → affiche uid, gid et tous les groupes

 Captures
À ajouter après le lab
