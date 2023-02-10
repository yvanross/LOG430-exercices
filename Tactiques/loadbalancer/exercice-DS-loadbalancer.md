# TP6: Processus d'analyse et de conception
Voici le diagramme de contexte d'une application client/serveur utilisant une base de données.

![](exercice-ds-loadbalancer/Vue%20de%20contexte.svg)

Voici l'architecture du système utilisant la tactique "multiple copie of computation" gérant la performance à l'aide d'un load balancer.  Les interfaces nécessaires au bon fonctionnement de cette architecture sont implicites.

![](exercice-ds-loadbalancer/Vue%20composant%20et%20connecteur.svg)

Voici la version avec les interfaces explicites nécessaires aux bons fonctionnements du système.

![](exercice-ds-loadbalancer/C&C%20with%20interface.svg)

Notez que ces interfaces sont celles qui permettent d'offrir les services aux clients en passant par un load balancer pour maximiser la performance du système.

Pour une raison inconnue, le propriétaire de cette architecture vient d'avoir un problème majeur ou le loadBalancer vient de cracher.  Plus aucun client ne recevait de service durant la réparation du problème qui a pris plus d'une heure aux ingénieurs de la compagnie.  Les clients qui paient pour ce service étaient tous fâchés de ne pouvoir accéder à celui-ci durant leur heure de bureau.

En tant qu'architecte, le propriétaire vous demande donc de trouver une solution à ce problème de disponibilité au niveau du loadBalancer.  Il faudrait donc être en mesure de détecter un crash du loadBalancer et de remplacer celui-ci par l'instance d'un nouveau load balancer.

En même temps, il aimerait pouvoir modifier dynamiquement le nombre de services utilisés par le load balancer.  Celui-ci étant présentement configuré lors du démarrage de l'application.

Vous ne pouvez pas modifier les interfaces existantes alors vous devez créer de nouvelles interfaces servant uniquement au contrôle des composants.  


# Détection et réparation du problème de crash du load balancer
Ajouter les composants et interfaces nécessaires pour le contrôle.  Réaliser un ou plusieurs diagrammes de séquence pour démontrer le fonctionnement de cette nouvelle configuration.



# Changement dynamique du nombre de services

on veut une instance de service pour chaque 10 requêtes en attente de traitement

|nombre de requêtes en attente| nombre de service|
|-|-|
|10 | 1|
|20 | 2|
|30 | 3|
|40 | 4|
|.. | ..|

Le système veut ajouter ou enlever des services selon le nombre de tâches.

Démontrer à l'aide d'un diagramme de séquence comment vous ajusterez le nombre de services utilisés par le load balancer.