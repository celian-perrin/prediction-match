# prediction-match
Ce projet combine d'une part un générateur automatisé de fiches statistiques de joueurs, et d'autre part un modèle de régression logistique dédié à la prédiction de matchs de tennis. Je me suis appuyé sur la base de données de référence de Jeff Sackmann : https://github.com/JeffSackmann/tennis_atp.

Dans un premier temps, j'ai réalisé une phase de cata engineering. Les données brutes comportaient des valeurs manquantes qu'il a fallu traiter. J'ai aussi dû symétriser l'ensemble du dataset vers un format neutre "Joueur 1 vs Joueur 2" pour éviter tout biais lors de l'entraînement des modèles.

J'ai ensuite développé un générateur de fiches joueurs automatisé. C'est un script qui permet de sortir un rapport PDF complet sur n'importe quel joueur du circuit. On y retrouve visuellement l'évolution de son classement, ses statistiques de service (aces, doubles fautes) et ses performances détaillées par surface, ce qui permet d'avoir une vue d'ensemble rapide avant un match.

Pour la partie prédiction, j'ai enrichi les données en créant de nouvelles features plus pertinentes, comme l'état de forme sur les 10 derniers matchs, le ratio de victoire spécifique au tournoi en cours, et l'historique des confrontations (H2H) calculé chronologiquement avant chaque rencontre.

Enfin, j'ai mis en place une régression logistique pour modéliser les probabilités de victoire. Le modèle a été entraîné sur l'historique des matchs passés, puis testé spécifiquement sur la saison 2024.
