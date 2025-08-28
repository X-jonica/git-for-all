# **Formation Git – Commandes utiles**

Voici quelques commandes essentielles pour configurer et manipuler un dépôt Git, avec des explications claires.

# MANIPULATION LOCAL

---

## Première configuration de Git (nom et email)

```bash
git config --global user.name "Votre Nom"
git config --global user.email "votre.email@example.com"
```

> --global : applique cette configuration pour tous les dépôts Git sur votre machine.
> On peut redéfinir ces valeurs par projet avec --local.

---

## Modifier la configuration Git avec nano

```bash
nano .gitconfig
```

> Cette commande ouvre le fichier de configuration Git global dans l’éditeur nano.
> Tu peux y voir et modifier des paramètres comme "user.name" et "user.email".

---

## Commande pour modifier les paramètres système de Git

```bash
git config --system
```

> Modifie la configuration à l’échelle du système (tous les utilisateurs de la machine).
> Nécessite souvent des droits administrateur (sudo).

---

## Commande pour initialiser un projet git

```bash
git init
```

> Cette commande crée un dépôt Git local dans le dossier courant.
> Elle génère un dossier caché .git qui contient toute la configuration et l’historique de ton projet.

---

## Commande pour configurer un dépôt Git (local)

> ⚠️ Il faut se placer dans le dossier où Git a été initialisé (`git init` ou cloné).

```bash
git config --local
```

> Modifie uniquement la configuration de ce dépôt spécifique.
> Exemple : définir un user.name/email différent pour ce projet.

---

## Commande pour ajouter un fichier dans l’index de Git

```bash
git add <fichier>
```

> ➜ Ajoute le fichier dans la "zone de préparation" (staging area)
> Cela signifie que Git se prépare à inclure ce fichier

---

## Commande pour désindexer un fichier du dépôt Git

```bash
git rm --cached <fichier>
```

> Supprime un fichier de l’index Git (zone de staging) mais le laisse présent dans ton dossier.
> Pratique si tu as ajouté un fichier par erreur avec "git add".

---

## Commande pour afficher les fichiers non suivis par Git

```bash
git ls-files --others --exclude-standard
```

> Liste tous les fichiers qui ne sont pas suivis par Git (non ajoutés à l’index).
> L’option --exclude-standard permet d’ignorer les fichiers listés dans .gitignore.

---

## Commande pour commit (Créer son premier commit)

> Un commit est un ensemble de modification, qui corresponde très souvent a une fonctionnalité, un commit doit etre coherent (c-à-d on ne doit pas commit au commencement d'un projet)

> Il est important également de noter qu'un message de commit est obigatoire;

```bash
git commit -m "message de commit"

#et

git log
# pour voir la liste des derniers commit.

git log --oneline
# pour afficher l'historique des commit d'un dépôt Git dans un format concis, monoligne.

git log -1
# Pour afficher "le" dernier commit
```

---

## Commande pour valider les modifications (commit)

```bash
git commit -a
```

> Ecrivez votre message de commit -> (saisir) i -> Echap -> (saisir) :wq -> Entrer

```bash
# i     : passer en mode insertion pour écrire
# Échap : sortir du mode insertion
# :wq   : write & quit → enregistrer et quitter l’éditeur
```

---

## Commande pour modifier le dernier commit

```bash
git add <fichier>
# ou
git add .
# Pour ajouter le(s) fichier(s) oublié(s) dans l’index
# (avec "." on ajoute tous les fichiers modifiés)

# puis

git commit --amend
# ou
git commit --amend --no-edit
# Si on veut garder le message tel qu'il est
```

> Cette commande permet de modifier le dernier commit. Elle est utile si vous avez oublié d’ajouter un fichier ou si vous souhaitez corriger le message du commit précédent.

---

> Une commane qui permet de voir ou on en est ?

```bash
git status
# ➜ Permet de voir l’état actuel du dépôt Git :
#    - Fichiers suivis/modifiés
#    - Changements prêts pour le commit
#    - Changements non suivis (untracked files)
```

---
