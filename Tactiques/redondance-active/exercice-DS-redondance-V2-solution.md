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

![](exercice-DS-redondance-V2/Vue%20contexte.svg)
La vue de contexte représente les acteurs et les systèmes.  J'ai représenté les composants interne du système mais ce n'est pas nécessaire.  Ici je les ai représenté pour indiquer quel composant est utilisé par un acteur.


## 2. Vous devez démontrer le processus de démarrage à l'aide d'un diagramme de séquence
Je vais faire ce diagramme complètement à la fin du processus d'analyse et de conception. Je ne peux pas le réaliser tant que je n'ai pas tous les éléments impliqué dans le système.

### Voici les constructeur des différents classes de notre système et l'ordre dans laquel il faut les utilisé.


**vm1: Machine virtuelle #1**

- DataWebServer(url:string, port:string)
- SommateurInfo(url:string, port:strin  g) -> nouvelle classe du package SystemeSommation
- Vote(orchestrateur:IOrchestrateurCtrl,[sommateurInfo:ISommateurInfo],dataWebServer:IDataWebServer)
- Orchestrateur([sommateurInfo:ISommateurInfo])

**machine virtuelle sommateur: vmSommateur 1 à 3**

- Sommateur(id:integer,url:string, port:string,shadow:boolean)

**Machine virtuelle des capteurs**

- Capteur(id:integer,frequence:int,  name:string,  voteUrl:string, votePort:string, voteToken:string)


La référence circulaire entre la VM1 et les vmSommateur a été éliminé dans cette solution

## 3. Vous devez démontrer le processus normal d'opération à l'aide d'un diagramme de séquence
### 3.1 Capteur envoie des données
![](exercice-DS-redondance-V2/Opération%20normal.svg)


### 3.2 App client fait la lecture des données
![](exercice-DS-redondance-V2/App%20client%20fait%20la%20lecture%20des%20données.svg)
```json
"res = [
  {
    "id": "1",
    "name": "Chambre1",
    "value": "151"
  },
  {
    "id": "2",
    "name": "Chambre2",
    "value": "152"
  },
  {
    "id": "3",
    "name": "Chambre3",
    "value": "153"
  }
]"
```

 ## 4. Traitement d'un crash
 Vous devez démontrer le processus de traitement d'un crash d'un des composant de la redondance ainsi que le fonctionnement du processus de récupération à l'aide d'un diagramme de séquence.

### 4.1 Détection d'un problème au niveau du composant de vote
Puisque que nous utilisons une redondance active, nous envoyons simultanément notre requête aux multiples sommateur. Aussitôt qu'un sommateur cesse de répondre ou répond différamment des autres sommateurs, nous sommes en mesure de l'isolé et de le redémarrer pour le réinséré dans le processus de calcul.

![](exercice-DS-redondance-V2/Détection%20d'un%20problème%20au%20niveau%20du%20composant%20de%20vote.svg)


## 5. Vue Module
Vous devez faire un diagramme de la vue module (MDD ou diagramme de classe)

![](exercice-DS-redondance-V2/vue%20module.svg)

## 6. Vues C&C
Vous devez faire un diagramme de la vue composant & connecteur. 

### 6.1 Vue composant et connecteur sans aucune tactiques

![](exercice-DS-redondance-V2/Vue%20composant%20et%20connecteur.svg)

### 6.2 Vue composants et connecteurs avec les éléments responsables des tactiques
Ce diagramme inclus les interfaces pour le fonctionnement normal du système ainsi que celles nécessaire au contrôle pour la réalisation des tactiques architecturales.

![](exercice-DS-redondance-V2/C&C%20with%20interface.svg)

### 7 Vous devez faire un diagramme de déploiement

![](exercice-DS-redondance-V2/Allocation%20%20Vue%20de%20déploiement.svg)
