# Processus d'analyse et de conception
Réaliser un système qui calcul la somme cumulative des niveaux de température d'une liste de capteur. Le calcul du sommateur de température doit se réaliser dans une architecture utilisant la redondance active avec 3 éléments de redondance. Une application externe se connecte sur ce système pour récupérer la température résultante de chaque capteur.

Vos composants doivent implémenter un interface pour le contrôle et une interface pour la fonctionnalité.

1. Vous devez faire une vue de contexte
2. Vous devez démontrer le processus de démarrage à l'aide d'un diagramme de séquence
3. Vous devez démontrer le processus normal d'opération à l'aide d'un diagramme de séquence
4. Vous devez démontrer le processus de traitement d'un crash d'un des composant de la redondance ainsi que le fonctionnement du processus de récupération à l'aide d'un diagramme de séquence.
5. Vous devez faire un diagramme de la vue module (MDD ou diagramme de classe)
6. Vous devez faire un diagramme de la vue composant & connecteur. Diagramme de composant incluant les interfaces.
7. Vous devez faire un diagramme de déploiement.

## 1. Vous devez faire une vue de contexte

La vue de contexte représente les acteurs et les systèmes.  J'ai représenté les composants interne du système mais ce n'est pas nécessaire.  Ici je les ai représenté pour indiquer quel composant est utilisé par un acteur.


## 2. Vous devez démontrer le processus de démarrage à l'aide d'un diagramme de séquence
Je vais faire ce diagramme complètement à la fin du processus d'analyse et de conception. Je ne peux pas le réaliser tant que je n'ai pas tous les éléments impliqué dans le système.


## 3. Vous devez démontrer le processus normal d'opération à l'aide d'un diagramme de séquence
### 3.1 Capteur envoie des données

### 3.2 App client fait la lecture des données


## 4. Traitement d'un crash
Vous devez démontrer le processus de traitement d'un crash d'un des composant de la redondance ainsi que le fonctionnement du processus de récupération à l'aide d'un diagramme de séquence.

### 4.1 Détection d'un problème au niveau du composant de vote
Puisque que nous utilisons une redondance active, nous envoyons simultanément notre requête aux multiples sommateur. Aussitôt qu'un sommateur cesse de répondre ou répond différamment des autres sommateurs, nous sommes en mesure de l'isolé et de le redémarrer pour le réinséré dans le processus de calcul.


## 5. Vue Module
Vous devez faire un diagramme de la vue module (MDD ou diagramme de classe)


## 6. Vue C&C
Vous devez faire un diagramme de la vue composant & connecteur. 

### 6.1 Vue composant et connecteur sans aucune tactiques


### 6.2 Vue composants et connecteurs avec les éléments responsables des tactiques
Ce diagramme inclus les interfaces pour le fonctionnement normal du système ainsi que celles nécessaire au contrôle pour la réalisation des tactiques architecturales.


### 7 Vous devez faire un diagramme de déploiement

