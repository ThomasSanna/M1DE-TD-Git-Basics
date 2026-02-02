# Commandes Git Basiques

## Configuration

### Configurer l'identité globale
```bash
git config --global user.name "Ton Nom"
git config --global user.email "ton.email@example.com"
```

### Configurer pour un projet spécifique
```bash
git config user.name "Ton Nom"
git config user.email "ton.email@example.com"
```

### Vérifier la configuration
```bash
git config --list
git config user.name
```

## Initialisation et Clonage

### Initialiser un nouveau dépôt
```bash
git init
```

### Cloner un dépôt existant
```bash
git clone <url-du-repo>
git clone <url-du-repo> <nom-dossier>
```

## Vérifier le statut

### Voir le statut du dépôt
```bash
git status
git status -s  # version courte
```

### Voir les modifications
```bash
git diff
git diff --staged  # changements en attente de commit
git diff <branche1> <branche2>
```

## Ajouter et Valider

### Ajouter des fichiers à l'index (staging area)
```bash
git add <fichier>
git add .          # ajouter tous les fichiers
git add *.js       # ajouter les fichiers correspondant au pattern
```

### Retirer des fichiers de l'index
```bash
git reset <fichier>
git reset          # reset tous les fichiers
```

### Valider les modifications (commit)
```bash
git commit -m "Message du commit"
git commit -am "Message"  # ajoute et commite tous les fichiers modifiés
git commit --amend        # modifier le dernier commit
```

## Annuler et Restaurer

### Restaurer un fichier (annuler les modifications locales)
```bash
git restore <fichier>
git restore .      # restaurer tous les fichiers
```

### Restaurer un fichier depuis l'index
```bash
git restore --staged <fichier>
```

### Revenir à une version antérieure
```bash
git checkout <commit-hash>
git checkout <branche>
git revert <commit-hash>  # crée un nouveau commit qui annule les changements
```

### Annuler des commits (attention: modifie l'historique)
```bash
git reset --soft HEAD~1   # garde les changements, enlève le commit
git reset --mixed HEAD~1  # par défaut, enlève du staging
git reset --hard HEAD~1   # enlève complètement le commit et les changements
```

## Affichage et Historique

### Voir l'historique des commits
```bash
git log
git log -n 5              # voir les 5 derniers commits
git log --oneline         # version condensée
git log --graph --oneline --all  # visualiser les branches
git log -p                # avec les détails des changements
git log --author="Nom"    # filtrer par auteur
```

### Voir les modifications d'un commit
```bash
git show <commit-hash>
```

## Branches

### Lister les branches
```bash
git branch            # branches locales
git branch -a         # toutes les branches (locales + distantes)
```

### Créer une branche
```bash
git branch <nom-branche>
git checkout -b <nom-branche>  # créer et basculer
git switch -c <nom-branche>    # alternative moderne
```

### Basculer entre branches
```bash
git checkout <nom-branche>
git switch <nom-branche>       # alternative moderne
```

### Supprimer une branche
```bash
git branch -d <nom-branche>    # suppression sûre
git branch -D <nom-branche>    # forcer la suppression
```

### Fusionner des branches
```bash
git merge <branche-source>
```

## Travailler avec le dépôt distant

### Lister les dépôts distants
```bash
git remote -v
```

### Ajouter un dépôt distant
```bash
git remote add <nom> <url>
git remote add origin <url>
```

### Télécharger les changements
```bash
git fetch                    # télécharge sans fusionner
git pull                     # télécharge et fusionne
git pull --rebase            # télécharge et reboise
```

### Envoyer les changements
```bash
git push
git push <remote> <branche>
git push origin <branche>
git push -u origin <branche> # définir la branche de suivi
```

## Astuces Utiles

### Voir les fichiers modifiés
```bash
git status
git diff --name-only
```

### Stash (mise de côté temporaire)
```bash
git stash                    # mettre de côté les changements
git stash list               # voir les changements en attente
git stash pop                # récupérer les changements
git stash drop               # supprimer
```

### Chercher dans l'historique
```bash
git grep "texte"
git log -S "code"  # chercher des changements spécifiques
```

### Alias utiles (à configurer)
```bash
git config --global alias.st status
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.ci commit
git config --global alias.log1 "log --oneline"
```
