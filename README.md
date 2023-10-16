# git-goup-1
Travailler en groupe

## 1. Créer un dépôt sur GitHub

Le chef de projet crée un dépôt sur GitHub et ajoute les collaborateurs.

Dans notre cas le dépôt s'appelle `git-goup-1`, créé par `mikhawa`, c'est moi: 

https://github.com/WebDevCF2m2023/git-goup-1

## 2. Création d'un fork

Chaque collaborateur crée un fork du dépôt du chef de projet en cliquant sur le bouton `Fork` en haut à droite de la page du dépôt :

![Fork](https://github.com/mikhawa/git-goup-1/blob/main/datas/screenshot-github.com-2023.10.16-10_14_23.png?raw=true)

Le `Owner` du fork est le collaborateur qui l'a créé. Décochez la case `Copy the main branch only` pour copier toutes les branches du dépôt :

![Fork2](https://github.com/mikhawa/git-goup-1/blob/main/datas/screenshot-github.com-2023.10.16-10_19_27.png?raw=true)

## 3. Cloner le fork

Chaque collaborateur clone son fork sur son ordinateur :

```bash
git clone git@github.com:VotrePseudoGithub/git-goup-1.git

cd git-goup-1

git remote -v

# Affiche :
origin  git@github.com:VotrePseudoGithub/git-goup-1.git (fetch)
origin  git@github.com:VotrePseudoGithub/git-goup-1.git (push)
```

Vous êtes prêt à travailler sur le projet grace à votre fork qui est une copie du dépôt original. Vous êtes le **propriétaire** de votre fork !

Vous pourrez le modifier à votre guise sans affecter le dépôt original.

## 4. Créer un lien avec le dépôt original

Pour pouvoir récupérer les modifications apportées au dépôt original par les autres collaborateurs, il faut créer un lien entre votre fork et le dépôt original.

```bash
git remote add upstream git@github.com:WebDevCF2m2023/git-goup-1.git
```

Vous devez voir apparaître le dépôt original dans la liste des dépôts distants :

```bash
git remote

origin
upstream
```

C'est également grâce à ce lien que vous pourrez proposer vos modifications au dépôt original.

## 5. Créer une branche

Pour travailler sur une fonctionnalité, il faut toujours créer une branche :

```bash
git checkout -b mabranche1
```

C'est un raccourci de la commande :

```bash
# Créer la branche
git branch mabranche1

# Se positionner sur la branche
git switch mabranche1
```

C'est sur cette branche que vous allez travailler. Vous pouvez la nommer comme vous voulez. Il est d'usage de nommer la branche en fonction de la fonctionnalité que vous allez développer.