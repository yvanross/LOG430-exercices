---
numbersections: true
export_on_save:
  pandoc: true
# the logo is hard-coded in the default.latex template
etstitlelogo: true
# to use http://ctan.forsale.plus/fonts/fontawesome/doc/fontawesome.pdf in LaTeX
usefontawesome: true
title: "LOG430 Architecture logicielle"
subtitle: "RUIS - exercice vue de contexte"
graphics: true
subject: "Exercice"
#keywords: 
author: 
- Yvan Ross
date: \today
papersize: letter
geometry: portrait
lang: fr-CA
csquotes: true
# to make sure quotes are « »
header-includes:
- \usepackage[style=french]{csquotes}
- \usepackage{tcolorbox}
- \newtcolorbox{myquote}{colback=red!5!white, colframe=red!75!black}
- \renewenvironment{quote}{\begin{myquote}}{\end{myquote}}
documentclass: scrbook
fontfamily: libertinus
#fontfamily: cochineal
fontfamilyoptions: 
- osf
- p
- tt=false
fontsize: 11pt
colorlinks: true
linkcolor: blue
pagestyle: headings
tables: true
output:
  pdf_document: 
    template: default.latex
    toc: true
    toc_depth: 4
---

# Réalisation d'une vue de contexte

## Description du problème

**SOGIQUE** se consacre exclusivement à l’informatisation du réseau québécois de la santé et des services sociaux. Elle appuie, conseille et accompagne le réseau dans ses divers axes d’intervention.
(Source : http://www.sogique.qc.ca/sogique-en-bref/mission-mandats.aspx)

##Mission

**SOGIQUE** a pour mission de mettre en valeur et de gérer, à partir des orientations stratégiques et technologiques du ministère de la Santé et des Services sociaux, un portefeuille d’actifs informationnels d’intérêt commun appartenant au réseau de la santé et des services sociaux.

## Relation entre le ministère de la Santé et des Services sociaux et **SOGIQUE**

La gouvernance des technologies de l’information du réseau est assurée par le Ministère et le rôle de **SOGIQUE** est de concrétiser la vision ministérielle en assurant la mise en œuvre de solutions performantes adaptées à ses réalités cliniques, sociales et administratives.

Votre entreprise a été approchée par la **SOGIQUE** dans le cadre du projet « répertoire d’imagerie diagnostique provincial ».

Votre équipe devra développer un répertoire d’imagerie diagnostique (**RID**) d’envergure pour fournir des services centralisés d’archivage d’images. Les Réseaux Universitaires Intégrés de Santé (**RUIS**) sont de nouveaux territoires de référence au ministère de la Santé et des Services sociaux. Ces quatre réseaux sont respectivement rattachés aux universités Laval, McGill, de Montréal et de Sherbrooke. Les **RUIS** ont été créés afin de favoriser la concertation, la complémentarité et l'intégration des missions de soins, d'enseignement et de recherche des établissements de santé ayant une désignation universitaire et des universités auxquelles sont affiliés ces établissements.
 
 
L’entente vise à créer de multiples environnements hétérogènes « **PACS** » (Picture Archive Communication System) partagés afin d’établir des diagnostics mieux informés et plus rapides en permettant aux médecins, même dans les régions éloignées, d’accéder plus facilement aux antécédents d’imagerie d’un patient au moyen d’Internet – peu importe le lieu où s’est déroulé l’examen. Par exemple, un omnipraticien dans le nord du Québec et un spécialiste exerçant à Montréal pourraient visionner ensemble une image diagnostique par voie électronique, et ce, à des centaines de kilomètres de distance, sans que le patient ait besoin de se déplacer vers un grand centre urbain.

Grâce au système, les **radiologues**, les **chirurgiens** et les autres fournisseurs de soins peuvent saisir, récupérer, afficher ou sauvegarder électroniquement des images médicales – y compris des échographies et des tomodensitométries multi coupes – dans de multiples centres. Le système assure un meilleur accès à l’information, réduit les délais de réponse et améliore le bien-être pour le patient.

Le but ultime est d'avoir un ensemble d'applications capables d'échanger des informations de telle sorte que le dossier complet (images, rapports. prescriptions, etc.) d'un **patient** soit disponible de n'importe où dans le réseau (bureau du médecin de famille, CLSC du quartier, hôpital n'importe où au Québec, etc.). Il est important de noter que l'accès (en lecture et en écriture) des diverses parties du dossier d'un patient est permis en fonction du rôle de l'intervenant de santé (infirmière, médecin, etc.). Autrement dit, un intervenant jouant un rôle spécifique ne doit avoir accès qu'aux parties du dossier le concernant.

Votre patron vous a affecté à l'équipe d'architecture responsable de proposer une architecture initiale dans le cadre de ce projet. Votre équipe travaille en étroite collaboration avec le groupe "Analyse d'affaires" de la **SOGIQUE**. Notez que la solution choisie sera déployée incrémentalement sur une période de cinq ans dans les divers sites, et que la durée de vie utile de l'architecture proposée est de 15 ans à partir du moment où le système est complètement déployé et fonctionnel.

## Travail à faire

1. Identifier les différentes parties prenantes ainsi que leur responsabilitées.
1. Faire une Diagramme de cas d'utilisation
1. Quels attribut de qualité devrait avoir ce système.  
    -  Rédiger un scénario de qualité pour chaque attribut important incluant une ébauche de solution pour satisfaire le scénario
        1. Disponibilité
        1. Performance
        1. Modifiabilité
        1. Interopérabilité
        1. Sécurité
        1. Usabilité
        1. Testabilité

1. Choix technologiques

1. Faire une vue de contexte
    1. Texte explicatif
    1. Diagramme
    1. Légende
    1. Tableau des éléments avec leurs responsabilitées
    1. Tableau de relation/API avec ses responsabilitées
    1. Identifier les frontières (RID, RUIS, PACS)

1. Documenter les API selon le gabarit du rapport de laboratoire (DSA 7.3)
    1. Identité de l’interface
    1. Ressources
        1. Syntaxe
        2. Sémantique - Assomption,  Préconditions, Postcondition, Valeur limite des paramètres
        3. Erreurs
    1. type de données et constantes
    1. Gestion des erreurs
        - Liste des exceptions commun à toutes les resources ou des codes d’erreur pouvant être recu suite à l’utilisation des resources.
    1. Variabilité
        - Documenter les paramètres ayant un impact important sur un attribut de qualité ou l'architecture du système
    1. Attribut de qualité géré par cet interface
    1. Décisions et problèmes de conception
    1. Guide d'utilisation
        - Exemple de **CODE** permettant de démonter l’utilisation de l’interface

1. Quel style architecturale retrouve t'on dans cet architecture
    1. Client / serveur
    2. Peer to peer (pair à pair)
    3. Éléments / relations / propriétés
    

1. Autre vues architecturale
  1. Pouvez vous décomposer un ou plusieurs éléments
      1. Expliquez les relations entre les éléments décomposés et les scénarios d'attribut de qualité

  1. Expliquez la mécanique d'authentification
      1. Faire une vue de module (classe, Interface, package, couche)
      1. Faire un diagramme de séquence
           