# Introduction
Ce lab est le premier de notre formation et a pour objectifs :
1. Créer un repository Dataform.
2. Configurer le projet.
3. Se familiariser avec l'interface graphique de Dataform.
4. Savoir lancer et visualiser des actions Dataform.
5. Créer un repository Git.
6. Connecter Dataform à Git.
7. Pousser le code vers Git.

# Créer un repository dataform
Suivez les étapes présentées lors de la présentation pour :

- Créer un repository Dataform.
- Créer un workspace nommé lab1.
- Initialiser le workspace et installer les dépendances.
- Modifier le fichier de configuration.
- Exécuter toutes les actions.
- Vérifier que les actions ont bien été créées dans BigQuery.

# Connexion au système de gestion des versions

#### Génération du Token Git

Dans cette étape, nous allons générer un jeton que Dataform utilisera pour se connecter au repository Git. Pour ce faire :

1. Créez un repository Git, par exemple `formation-dataform`.
2. Pour générer un token, allez dans `Settings -> Developer Settings -> Personal Access Token -> Tokens (classic) -> Generate new token`.
3. Pour le scope, sélectionnez `Repo`.
4. Copiez le token généré.

#### Ajouter le token dans Secret Manager

Cette étape consiste à ajouter le token généré dans l'étape précédente dans Secret Manager pour qu'il soit accessible de manière sécurisée.

Dans Secret Manager :
1. Activez l'API de Secret Manager.
2. Créez un nouveau secret (par exemple `git_token`).
3. Copiez le token généré dans `Secret value`.
4. Laissez les autres valeurs par défaut.

#### Donner les Droits Nécessaires au Service Account Dataform
1. Récupérez le Service Account Dataform.
2. Allez dans IAM.
3. Trouvez et éditez le Service Account Dataform.
4. Accordez-lui le droit : `Secret Manager Secret Accessor`.

#### Connecter Dataform à Git

1. Dans votre repository, allez dans `Settings -> Connect with Git`.
2. Choisissez `HTTPS`.
3. Entrez le lien vers votre repository Git dans `Remote Git repository`.
4. Mettez `main` comme `Default branch`.
5. Choisissez le secret créé dans l'étape précédente (`git_token`).

Ces étapes vous permettront de connecter votre repository à Git de manière sécurisée en utilisant Dataform. Si vous avez des questions ou des problèmes, n'hésitez pas à consulter la documentation officielle ou à contacter le support technique.

# Terminer le lab
commiter et push les vers le répo git
merger les branch lab1 dans la branch principale.