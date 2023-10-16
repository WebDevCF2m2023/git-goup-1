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
# Créer la branche et se positionner dessus
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

## 6. Faire des modifications

Vous pouvez maintenant faire des modifications sur le projet. Par exemple, ajouter un fichier `index.html` et le commiter :

```bash
touch index.html

git add index.html

git commit -m "Ajout du fichier index.html"
```

## 7. Pousser les modifications sur votre fork

Une fois que vous avez terminé de travailler sur votre branche, vous pouvez pousser les modifications sur votre fork :

```bash
git push origin mabranche1
```

## 8. Créer une Pull Request

Une fois que vous avez poussé vos modifications sur votre fork, vous pouvez créer une `Pull Request` pour proposer vos modifications au dépôt original :

![PR](https://github.com/mikhawa/git-goup-1/blob/mabranche1/datas/screenshot-github.com-2023.10.16-11_15_02.png?raw=true)

Vous pouvez ajouter un commentaire pour expliquer vos modifications et cliquer sur le bouton `Create pull request` :

![PR2](https://github.com/mikhawa/git-goup-1/blob/mabranche1/datas/screenshot-github.com-2023.10.16-11_18_36.png?raw=true)

## 9. Récupérer les modifications du dépôt original

Une fois que vous avez créé votre `Pull Request`, vous pouvez récupérer les modifications apportées au dépôt original par les autres collaborateurs.

Pour cela, il faut se positionner sur la branche `main` de votre fork et récupérer les modifications du dépôt original :

```bash
git checkout main
# ou git switch main

git pull upstream main
```

Vous pouvez ensuite vous positionner sur votre branche et fusionner la branche `main` avec votre branche :

```bash
git checkout mabranche1
# ou git switch mabranche1

git merge main
```

## 10. Résoudre les conflits

Si vous avez des conflits, vous devez les résoudre en modifiant les fichiers concernés. Vous devez ensuite ajouter les modifications et commiter :

```bash
git add index.html

git commit -m "Résolution des conflits"
```

Vous pouvez ensuite pousser les modifications sur votre fork :

```bash
git push origin mabranche1
```

## 11. Mettre à jour la Pull Request

Une fois que vous avez résolu les conflits, vous pouvez mettre à jour votre `Pull Request` en cliquant sur le bouton `Update branch` :

![PR3](