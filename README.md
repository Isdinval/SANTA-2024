# Santa 2024 - The Perplexity Permutation Puzzle

## 📜 Description du Projet

Ce projet a été réalisé dans le cadre de la compétition **Santa 2024 - The Perplexity Permutation Puzzle** organisée par Kaggle. L'objectif était de réorganiser des séquences de mots mélangés, liés aux fêtes de fin d'année, afin de minimiser la perplexité des textes. La perplexité est une mesure qui évalue à quel point un modèle de langage est capable de prédire une séquence de mots. Plus la perplexité est faible, plus le texte est cohérent et fluide.

Le projet utilise des techniques avancées de **traitement du langage naturel (NLP)** et d'optimisation pour réarranger les mots de manière à produire des passages de texte qui sont à la fois cohérents et agréables à lire. Le modèle de langage **Gemma 2 9B** a été utilisé pour calculer la perplexité des séquences de mots, et plusieurs stratégies d'optimisation ont été mises en œuvre pour améliorer les résultats.

## 🛠️ Fonctionnalités

### Optimisation multi-phase

Le projet utilise une combinaison de techniques d'optimisation, incluant :

- **Optimisation locale par fenêtres** : Réarrangement des mots dans de petites fenêtres pour trouver des séquences meilleures, avec un arrêt précoce pour éviter des calculs inutiles.
  - **Exemple** : Pour la séquence "reindeer sleep walk the night", l'optimiseur pourrait réarranger la fenêtre "sleep walk the" en "walk sleep the" si cela réduit la perplexité.

- **Sauts globaux** : Déplacement de groupes de mots à différentes positions dans la séquence, explorant des réarrangements à plus grande échelle.
  - **Exemple** : Dans la séquence "reindeer sleep walk the night", l'optimiseur pourrait déplacer le groupe "sleep walk" à la fin, ce qui donnerait "reindeer the night sleep walk".

- **Échanges de blocs** : Échange de blocs de mots pour tester différentes configurations, améliorant ainsi le flux global du texte.
  - **Exemple** : Pour la séquence "reindeer sleep walk the night", l'optimiseur pourrait échanger les blocs "reindeer sleep" et "the night", ce qui donnerait "the night walk reindeer sleep".

- **Mélange global** : Réorganisation aléatoire de la séquence entière pour explorer de nouvelles configurations, avec un arrêt précoce si aucune amélioration n'est trouvée.
  - **Exemple** : La séquence "reindeer sleep walk the night" pourrait être mélangée pour devenir "night the walk sleep reindeer", afin d'explorer une disposition complètement nouvelle.

### Utilisation de modèles de langage

Le modèle **Gemma 2 9B** est utilisé pour calculer la perplexité des séquences de mots, permettant une évaluation précise de la cohérence des textes.

### Réglage dynamique des paramètres

Les paramètres d'optimisation, tels que la taille des fenêtres et les seuils d'arrêt anticipé, sont ajustés dynamiquement en fonction de la longueur et de la complexité des séquences.

### Suivi des performances

Un système de suivi détaillé permet de mesurer les améliorations, les taux de réussite et le temps d'exécution pour chaque phase d'optimisation.


## 📊 Résultats

Le projet a permis de réduire significativement la perplexité des séquences de mots mélangées, produisant des textes plus cohérents et fluides. Les résultats ont été évalués en fonction de la perplexité moyenne des séquences optimisées, avec des scores plus bas indiquant une meilleure performance.

- **Première tentative** : 859
- **Dernière tentative** : 252
- **TOP1 (meilleure performance de la compétition)** : 247

Ces résultats montrent une amélioration notable de la cohérence des textes générés grâce aux différentes techniques d'optimisation mises en œuvre.

## ⚡ Complexité de la Tâche

Un algorithme de **brute force** n'est pas viable pour ce problème en raison de la complexité exponentielle associée à la réorganisation des mots. L'une des phrases comporte 100 mots, et l'ordre de chaque mot est crucial. Cela crée un nombre énorme de combinaisons possibles.

### Calcul des Combinaisons
Pour une phrase de 100 mots, il y a **100!** (factorielle de 100) combinaisons possibles, ce qui est un nombre astronomiquement élevé et bien au-delà de la capacité des algorithmes de brute force pour être résolu efficacement.

### Répartition des phrases et des tokens
En tout, il y a 6 phrases, et chaque phrase a un nombre de mots et de tokens approximatifs comme suit :

- **Phrase 1** : 10 mots / 14 tokens
- **Phrase 2** : 20 mots / 24 tokens
- **Phrase 3** : 20 mots / 25 tokens
- **Phrase 4** : 30 mots / 36 tokens
- **Phrase 5** : 50 mots / 59 tokens
- **Phrase 6** : 100 mots / 117 tokens

Cela montre la taille et la complexité des séquences à traiter, rendant un algorithme de brute force pratiquement impossible à exécuter dans un délai raisonnable. C'est pourquoi des techniques d'optimisation avancées ont été utilisées pour réduire la perplexité sans recourir à une approche de recherche exhaustive.




