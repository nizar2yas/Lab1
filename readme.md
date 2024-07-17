# Introduction
Ce laboratoire représente la première étape essentielle de notre formation, visant à établir des bases solides dans l'utilisation de Dataform. Les objectifs principaux de ce lab sont multiples et couvrent plusieurs aspects clés :

1. **Création d'un repository Dataform**: Nous commencerons par créer un repository dans Dataform, fournissant ainsi un espace centralisé pour gérer et développer nos projets de transformation de données. Ce repository servira de point d'ancrage pour tous nos artefacts de données et les processus associés.

2. **Configuration du projet**: Nous configurerons le projet Dataform en définissant les paramètres globaux, les environnements de déploiement et d'autres configurations spécifiques nécessaires au bon fonctionnement de nos pipelines de données.

3. **Familiarisation avec l'interface graphique de Dataform**: Nous explorerons l'interface utilisateur intuitive de Dataform, qui offre des outils visuels pour la gestion des transformations, la planification des tâches et la surveillance des opérations. Cela nous permettra de naviguer efficacement à travers les différentes étapes de développement et de déploiement de nos projets.

4. **Lancement et visualisation des actions Dataform**: Nous apprendrons à lancer et à visualiser les actions dans Dataform, y compris l'exécution des transformations, la vérification des résultats et la gestion des erreurs potentielles. Cela garantit que nos processus de traitement des données sont efficaces et produisent des résultats attendus.

5. **Création d'un repository Git**: En parallèle avec Dataform, nous créerons également un repository Git pour versionner notre code, faciliter la collaboration et assurer la traçabilité des modifications apportées à nos transformations de données.

6. **Connexion de Dataform à Git**: Nous établirons une connexion entre Dataform et notre repository Git, permettant ainsi la synchronisation automatique du code développé dans Dataform avec notre système de contrôle de version. Cela assure une gestion cohérente et sécurisée du code à travers les différentes phases de développement.

7. **Pousser le code vers Git**: Enfin, nous apprendrons à pousser notre code développé dans Dataform vers Git, assurant ainsi sa sauvegarde régulière, sa gestion des versions et sa disponibilité pour d'autres membres de l'équipe. Cette intégration entre Dataform et Git facilite également le déploiement continu et la gestion des changements dans nos projets de transformation de données.

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