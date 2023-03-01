---
theme: default
size: 16:9
---

<style>
ul {
	font-size: 0.8em;
}
</style>

![bg contain](https://wac-cdn.atlassian.com/dam/jcr:f6948a92-f446-466f-8783-1dd1cbcc661a/hero.svg?cdnVersion=816)

---

# Sommaire

### C'est quoi le versioning de code ? 
### Comment ça fonctionne git ?
### Comment je travaille avec mon équipe ?
### Vers l'infini et au delà !

---

# C'est quoi le versioning de code ?

![w:900](https://cdn.hashnode.com/res/hashnode/image/upload/v1632494998500/GHmHux9o3.png)
https://blog.tarynmcmillan.com/a-history-of-version-control

---

# C'est quoi le versioning de code ?

- travailler à plusieurs personne sur le même code
- avoir un historique des modifications
- revenir en arrière si nécessaire
- figer des versions

---

![bg contain](https://i.ytimg.com/vi/mJ-qvsxPHpY/maxresdefault.jpg)

---

# Comment ça fonctionne git ?

## GIT !== github !== gitlab

---

# Comment ça fonctionne git ?

![](https://rtask.thinkr.fr/wp-content/uploads/transform_as_git_header.png)

---

# Comment ça fonctionne git ?

![](https://stateofther.github.io/finistR2019/img/d-schema_git.png)

---

# Comment ça fonctionne git ?

### exo 1 : mon premier commit

```
mkdir prout
cd prout
git init // On initialise le dossier en tant que repo git
git // On liste les commandes

git status // On vérifie l'état du repo
vim README.md (+ écrire du texte dedans)
git status
git diff // On vérifie les modifications en cours

git add README.md // On ajoute notre fichier dans git
git status // On vérifie qu'il est bien ajouté

git commit -m "my message" // On commit nos modifications (on indique à git qu'on veut les versionner)
git status
git log // On vérifie que notre commit est bien compris par git
```
---

# Comment ça fonctionne git ?

### exo 1 : ma première branche

```
git branch -a // On liste les branches
git checkout -b mabranche // On créée une nouvelle branche à partir de "main"
git status
git log

touch caca
git add caca
git commit -m "caca"
git log

git checkout main // On change de branche pour retourner sur "main"
git log
git status
git merge mabranche // On demande à git de fusionner notre branche "mabranche" dans "main"
git log
```
---

# Comment je travaille avec mon équipe ?

### Merge Request / Pull Request

- same shit !
- **MR** = **gitlab**
- **PR** = **github**
- demande de fusion de code
- code review
- fusion dans la branche principale
- exemple : https://github.com/eleven-labs/black-hole/pull/4

---

# Comment je travaille avec mon équipe ?

### Fetch / Pull

- not same shit !
- récupération des dernières modifs sur le serveur
- **fetch** = je veux les nouvelles modifications du serveur **sans mettre à jour mon local**
- **pull** = je veux les nouvelles modifications du serveur **en mettant à jour mon local**

---

# Comment je travaille avec mon équipe ?

### Rebase VS Merge

- not same shit !
- mise à jour de votre branche par rapport aux modifs des autres (sur une autre branche)
- **rebase** = je veux les dernières modifs de l'autre branche **en gardant mes modifs au dessus dans l'historique**
- **merge** = je veux les dernières modifs de l'autre branche **dans l'ordre chronologique**

---

# Comment je travaille avec mon équipe ?

### Rebase VS Merge

![w:800](https://miro.medium.com/max/1400/1*pFWenykuQ0rwXkbAx5nD_A.png)

---

# Comment je travaille avec mon équipe ?

### Blame

![](https://preview.redd.it/5z3kspwmpkbz.jpg?auto=webp&s=a5439187ed8e352c5563dc86f599dd3efe43e239)

---

# Comment je travaille avec mon équipe ?

### exo 2 : je clone mon premier projet

```
// Je récupère le projet git qui est sur github
git clone https://github.com/snroki/workshop-git.git && cd workshop-git
```

J'ouvre le fichier https://github.com/snroki/workshop-git/blob/main/README.md

---

![bg contain](https://www.thebookedition.com/1458465/conflits-de-canard-format-a5.jpg)

---

# Comment je travaille avec mon équipe ?

### Conflits

![](https://miro.medium.com/max/1400/1*OCBtatJXz9BLErJZpFX07g.png)

---

# Comment je travaille avec mon équipe ?

### Mon workflow

```
// Je créée ma branche et je push mes modifications (je créée ma MR)
git checkout -b ma-branche
git add .
git commit -m "ma feature"
git push

// Si j'ai des retours de review ou des fix à faire
git add .
git commit --fixup HEAD // On indique que notre commit est un fix du commit précédent
git push

// Et ainsi de suite tant qu'on a des modifications à apporter

git rebase -i --autosquash origin/master // On rebase par rapport à master + on squash nos commits afin d'en avoir un seul
git push -f // On force push à cause du rebase
```

---

# Vers l'infini et au delà ?

### git config

```
git config --global user.name "John Doe"
git config --global user.email johndoe@example.com
```

---

# Vers l'infini et au delà ?

### git reset

```
git reset --hard origin/ma-branche
git reset {commit_number}
```

---

# Vers l'infini et au delà ?

### git cherry-pick

```
git cherry-pick {commit_number}
```

---

# Vers l'infini et au delà ?

### git reflog

```
git reflog // Permet de lister les commandes ayant été lancer et de revenir en arrière
```

---

# Vers l'infini et au delà ?

### git bisect

```
git bisect start // Commencer le bisect
git bisect bad // Indique qu'un commit possède le bug
git bisect good // Indique qu'un commit ne possède pas le bug
git bisect skip // Indique qu'on se fout du commit
git bisect reset // Termine le bisect
```

---

# Liens

<style scoped>
ul {
	font-size: 0.4em;
}
</style>

- https://git-scm.com/docs
- https://blog.microlinux.fr/formation-git/

