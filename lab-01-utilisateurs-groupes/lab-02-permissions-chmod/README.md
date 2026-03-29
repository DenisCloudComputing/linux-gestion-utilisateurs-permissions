 Lab 02 — Permissions avec chmod

  Objectif
Comprendre et modifier les permissions des fichiers et répertoires.

  Commandes pratiquées

| Commande | Description | Exemple |
|----------|-------------|---------|
| `ls -la` | Voir les permissions | `ls -la fichier.txt` |
| `chmod` | Modifier les permissions | `chmod 755 script.sh` |
| `chmod +x` | Ajouter l'exécution | `chmod +x script.sh` |
| `chmod -w` | Retirer l'écriture | `chmod -w fichier.txt` |
| `stat` | Voir les détails d'un fichier | `stat fichier.txt` |

  Tableau de référence — Notation octale

| Valeur | Permission | Symbole | Usage typique |
|--------|-----------|---------|---------------|
| `7` | Lecture + Écriture + Exécution | `rwx` | Propriétaire d'un script |
| `6` | Lecture + Écriture | `rw-` | Fichier que tu édites |
| `5` | Lecture + Exécution | `r-x` | Script pour les autres |
| `4` | Lecture seule | `r--` | Fichier public |
| `0` | Aucun droit | `---` | Bloqué |

  Permissions courantes en Cloud

| Permission | Usage |
|-----------|-------|
| `chmod 600 ma-cle.pem` | Clé SSH AWS — OBLIGATOIRE car il faut cacher le fichier sauf au propriétaire |
| `chmod 700 ~/.ssh/` | Dossier SSH privé |
| `chmod 755 script.sh` | Script exécutable car tout le monde a des droits d'exécuter |
| `chmod 644 config.txt` | Fichier de config lisible |

  Captures
À ajouter après le lab
