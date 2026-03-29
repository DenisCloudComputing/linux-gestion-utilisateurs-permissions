 linux-gestion-utilisateurs-permissions
Labs sur la gestion des utilisateurs et permissions  Linux (chmod, chown, usermod) — Formation Cloud 

  Linux — Gestion des Utilisateurs et Permissions

> Mes travaux pratiques sur la gestion des utilisateurs, groupes
> et permissions dans Linux, compétences essentielles pour
> l'administration de serveurs cloud.

---

  Description

Ce repository regroupe mes labs sur la gestion des droits d'accès
sous Linux. Comprendre les permissions est CRITIQUE en cloud computing :
un mauvais réglage peut exposer des données sensibles ou bloquer
un service entier.

---

  Objectifs d'apprentissage

- Créer et gérer des utilisateurs et groupes Linux
- Comprendre et appliquer le système de permissions (rwx)
- Maîtriser la notation octale (755, 644, 600...)
- Gérer les propriétaires de fichiers et répertoires
- Appliquer le principe du moindre privilège (sécurité cloud)

---

  Technologies utilisées

| Technologie | Usage |
|-------------|-------|
| Debian 12 | Système d'exploitation |
| Bash | Shell / Interpréteur de commandes |
| Git | Versionnement du code |
| VirtualBox | Environnement de virtualisation |

---

 Structure du repository

```
linux-gestion-utilisateurs-permissions/
│
├── README.md
├── .gitignore
├── LICENSE
│
├── lab-01-utilisateurs-groupes/
│   ├── README.md
│   ├── commandes.sh
│   └── captures/
│
├── lab-02-permissions-chmod/
│   ├── README.md
│   ├── commandes.sh
│   └── captures/
│
├── lab-03-proprietaires-chown/
│   ├── README.md
│   ├── commandes.sh
│   └── captures/
│
└── aide-memoire/
    └── cheatsheet-permissions.md
```

---

 Labs réalisés

| # | Lab | Commandes clés | Statut |
|---|-----|---------------|--------|
| 01 | Utilisateurs et groupes | `useradd`, `usermod`, `id`, `groups` |  Complété |
| 02 | Permissions chmod | `chmod`, notation octale, `ls -la` |  Complété |
| 03 | Propriétaires chown | `chown`, `chgrp` |  Complété |

---

 Concept clé : Les permissions Linux

```
  ls -la mon-fichier.txt
  -rw-r--r-- 1 denis cloud 1024 jan 15 14:30 mon-fichier.txt

  DÉCORTIQUONS :

  -  rw-  r--  r--
  │  │    │    │
  │  │    │    └── Autres (other)  : lecture seule
  │  │    └─────── Groupe (group)  : lecture seule
  │  └──────────── Proprio (user)  : lecture + écriture
  └─────────────── Type : - = fichier, d = dossier

  NOTATION OCTALE :
  r = 4    (lecture)
  w = 2    (écriture)
  x = 1    (exécution)

  Exemples courants :
  755 = rwxr-xr-x  → Scripts, dossiers
  644 = rw-r--r--  → Fichiers normaux
  600 = rw-------  → Fichiers sensibles (clés SSH, .pem)
  700 = rwx------  → Dossiers privés (.ssh/)
```

---

 Lien avec le Cloud Computing

```
POURQUOI C'EST IMPORTANT EN CLOUD ?

  ┌──────────────────────────────────────────────────┐
  │                                                  │
  │  Sur AWS, quand tu te connectes à une EC2 :      │
  │                                                  │
  │  ssh -i ma-cle.pem ec2-user@3.15.20.100         │
  │                                                  │
  │  Si ma-cle.pem n'a PAS les permissions 600 :     │
  │  → SSH REFUSE la connexion                       │
  │  → "WARNING: UNPROTECTED PRIVATE KEY FILE!"      │
  │                                                  │
  │  chmod 600 ma-cle.pem  ← OBLIGATOIRE             │
  │                                                  │
  │  Les permissions Linux = la BASE de la sécurité  │
  │  cloud. Pas de raccourci possible.               │
  │                                                  │
  └──────────────────────────────────────────────────┘
```

---

 Comment utiliser ce repo

```bash
# Cloner le repository
git clone https://github.com/DenisCloudComputing/linux-gestion-utilisateurs-permissions.git

# Accéder au dossier
cd linux-gestion-utilisateurs-permissions

# Voir le contenu d'un lab
cat lab-01-utilisateurs-groupes/commandes.sh
```

---

 Références

- [Linux File Permissions Explained](https://linuxcommand.org/lc3_lts0090.php)
- [Debian Wiki — Permissions](https://wiki.debian.org/Permissions)
- [AWS — Securing your key pair](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-key-pairs.html)

---

 👤 Auteur

**Denis** — Étudiant en Cloud Computing
-  Collège de Bois-de-Boulogne
-  denielound@gmail.com
-  [Mon GitHub](https://github.com/DenisCloudComputing)

---

>  Ce repository fait partie de mon portfolio de formation en Cloud Computing
