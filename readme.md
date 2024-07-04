# Introduction
ce lab est le 1er dans notre formation, il a pour objectif:
1. créer un repository dataform
2. configurer le projet
3. se familiariser avec l'interface graphique
4. savoir lancer et visualiser des actions dataform
5. créer un repo git
6. connecter dataform a git
7. pusher son code vers git

# Créer un repository dataform
- Suivre les étapes présenter lors de la présentation pour
- créer un répo dataform
- Créer un workspace (lab1)
- lancer les initier le workspace et installer les dépendances
- modifier le fichier de conf
- exécuter tout les actions
- vérifier qu'ils sont bien créer dans bigquery

# Connexion au système de gestion des versions

Suivez les étapes suivantes pour connecter votre repository à Git.

#### Génération du token GIT

Dans cette étape, nous allons générer un jeton que Dataform utilisera pour se connecter au repository Git. Pour ce faire :

1. Créez un repository Git, par exemple `formation-dataform`.
2. Pour générer un token, allez dans `Settings -> Developer Settings -> Personal Access Token -> Tokens (classic) -> Generate new token`.
3. Pour le scope, sélectionnez `Repo`.
4. Copiez le token généré.

#### Ajouter le token dans Secret Manager

Cette étape consiste à ajouter le token généré dans l'étape précédente dans Secret Manager pour qu'il soit accessible de manière sécurisée.

Dans Secret Manager :
1. activer l'api de secret manager
2. Créez un nouveau secret (par exemple `git_token`).
3. Copiez le token généré dans l'étape précédente dans `Secret value`.
4. Laissez les autres valeurs par défaut.

#### Donner les droits nécessaires au SA dataform
dans cette étapes il faut donner au service account dataform les droits nécessaire pour pouvoir lire le token créer dans le secret manager.
1. récupérer le SA dataform
2. allez dans IAM
3. trouver et éditer le SA dataform
4. lui accorde le droit : Secret manager Secret accessor

#### Connecter Dataform à Git

Dans la console Dataform :

1. Dans votre repository, allez dans `Settings -> Connect with Git`.
2. Choisissez `HTTPS`.
3. Entrez le lien vers votre repository Git dans `Remote Git repository`.
4. Mettez `main` comme `Default branch`.
5. Choisissez le secret créé dans l'étape précédente (`git_token`).

---

Ces étapes vous permettront de connecter votre repository à Git de manière sécurisée en utilisant Dataform. Si vous avez des questions ou des problèmes, n'hésitez pas à consulter la documentation officielle ou à contacter le support technique.

# Terminer le lab
commiter et push les vers le répo git
merger les branch lab1 dans la branch principale.