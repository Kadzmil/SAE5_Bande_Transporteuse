# SAE5_Bande_Transporteuse

![](https://github.com/Kadzmil/SAE5_Bande_Transporteuse/blob/Main/Images/iut%20logo.png)

### Equipe : Kamil AIMAR / Younes AMZERT / Mehdi BELABAOUB 
### Référents : M. Eric HUEBER / M. Benjamin MOURLLION
## Cahier des charges


1. **Objet**\
Conception, fabrication et intégration d'une bande transporteuse avec une supervision IHM (Interface Homme-Machine) permettant le contrôle et la visualisation de la bande transporteuse.

2. **Spécifications Techniques**
   
2.1. **Bande Transporteuse**

Capacité de charge : 12 Kg\
Vitesse : Réglable mais avec un fonctionnement normal de 12m/minute \
Moteur : 230/400 V.\
Matériaux : Structure en acier inoxydable, tapis en pvc .

2.2. **IHM (Interface Homme-Machine)**

Vue Automatique :\
Visualisation en temps réel de l'état de la bande transporteuse :\
Affichage de la position des pièces sur le tapis de la bande transporteuse.\
Alerte de Maintenance Préventive :\
Notifications automatiques pour la maintenance à réaliser.\
Historique des interventions de maintenance et des alertes pour un suivi précis.\

2.3. **Mode Manuel**

Commandes :\
Boutons situés sur l'armoire de contrôle pour la manipulation manuelle.\
Bouton de marche avant pour avancer la bande transporteuse.\
Bouton de marche arrière pour reculer la bande transporteuse.\
Bouton de mise en marche pour démarrer le moteur.\
Bouton d'arrêt pour arrêter le moteur.

Indicateurs Visuels :\
Voyant de mise en service pour indiquer que l'armoire est alimentée.\
Voyant d'arrêt pour indiquer que la bande est arrêtée.\
Voyant de défaut pour indiquer une anomalie ou un dysfonctionnement.

3. **Exigences Fonctionnelles**
   
3.1. **En Mode Automatique**

La bande transporteuse doit être contrôlable depuis l'IHM.\
La position des pièces sur la bande doit être affichée avec précision en temps réel.

3.2. En Mode Manuel

Les commandes doivent être accessibles et faciles à utiliser depuis l'armoire de contrôle.\
Les fonctions de marche avant et arrière doivent être distinctes et clairement identifiées.\
Les boutons de mise en marche et d'arrêt du moteur doivent être facilement accessibles.\
Les voyants doivent fournir des indications claires et visibles sur l'état du système.

4. **Exigences de Performance**
   
Fiabilité : Fonctionnement continu et sans interruption sur de longues périodes.\
Précision : Détection précise de la position des pièces sur la bande.\
Rapidité : Temps de réponse rapide pour la mise en marche et l'arrêt.

5. **Exigences de Maintenance**
   
Alerte Préventive : Notifications automatiques pour planifier les interventions de maintenance.\
Accessibilité : Composants facilement accessibles pour l'entretien et les réparations.  
7. **Planning** 

Étude et conception : 12 semaines.

  
## Inventaire 
Pour ce projet du matériel Schneider a été majoritairement été utilisé. L’automate est un M221TEC40R qui va être alimenté en 230V AC et l’IHM est un HARMONY alimenté en 24V DC.

![image_2024-06-26_181003562](https://github.com/Kadzmil/SAE5_Bande_Transporteuse/assets/166384885/57004fb4-d781-400c-a31f-79c30b8bdde6)  ![image_2024-06-26_181118490](https://github.com/Kadzmil/SAE5_Bande_Transporteuse/assets/166384885/831012e9-c399-4229-ab2c-e2859a1c2e7c)  

Pour ce qui est des protections on a tout d'abord dans l'ordre un disjoncteur moteur magnétothermique qui va permettre de détecter et d'interrompre le courant électrique en cas de surcharge ou de court-circuit pour le moteur, deux disjoncteurs magnétothermique exerçant les mêmes fonctionnalités pour l'IHM et l'entrée du circuit ainsi qu'un sectionneur porte fusible pouvant à la fois protéger de la même manière que les disjoncteurs mais aussi être utilisé comme dispositifs afin de garantir qu'un circuit est complètement hors tension lorsqu'il doit être entretenu ou réparéutiliser en isoleant une partie de ce dernier. Ceci était pour la ligne du haut.\
Pour celle du bas nous avons un contacteur permettant d'ouvrir ou fermer un circuit sur réception d'un signal électrique, le transformateur qui va nous délivrer du 24V AC pour les boutons puis le variateur de vitesse qui a comme fonction de choisir le sens de marche ainsi que la vitesse.

![image_2024-06-26_190020088](https://github.com/Kadzmil/SAE5_Bande_Transporteuse/assets/166384885/5483d57e-bd89-4138-9a49-2c1c878cee80) 

Deplus, voici le transformateur rajouté à la fin permettant de nous délivrer la tension voulue pour alimenter l'IHM qui est du 24V DC.

![image_2024-06-27_152816101](https://github.com/Kadzmil/SAE5_Bande_Transporteuse/assets/166384885/0ceb58ac-3c7b-4fa4-8c1c-e95fdc8a95ba)

Lors de notre projet nous avons du naviguer à travers différents variateur voici les 3 utilisés dans l'ordre chronologique. Les 2 premiers n'ont pas été retenu car soit quelqu'un d'autre en avait besoin soit il était trop grand, mais une caractéristique les unies, ils fonctionnent en monophasé et non triphasé.

![image_2024-06-26_182547281](https://github.com/Kadzmil/SAE5_Bande_Transporteuse/assets/166384885/545d7291-69f0-470c-86e3-5cb8753d7e31) 
### Schématisation sur See Electrical

Pour ce qui est des schémas au début nous sommes parti pour un système classique à 3 phases et 2 contacteurs. Ce système nous permets de pouvoir avoir les 2 sens de direction grace à l'inversion des phases sur l'un de nos contacteur. Vous pouver l'apercevoir ci dessous sur les deux premières images les anciens schémas de puissance et commande. \
![image_2024-06-26_181813138](https://github.com/Kadzmil/SAE5_Bande_Transporteuse/assets/166384885/3fd3cfca-3802-4a60-8b2d-3dd87447bde3) ![image_2024-06-26_181931456](https://github.com/Kadzmil/SAE5_Bande_Transporteuse/assets/166384885/cad9af3e-df7c-42e1-8cf6-088511da8eaa) **Ancien circuit de puissance**&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Ancien circuit de commande** \
\
Lors de l'anvancée du projet nous avons dû passer de 3 à 1 phase et supprimer un contacteur en raison du variateur de vitesse. De plus, 2 transformateurs ont été rajouté afin de pouvoir alimenter comme dis précédemment l'IHM et les boutons. C'est pourquoi de nouveau schémas ont été réalisé et sont consultable ci-dessous.
![nv circuit puissance (1)](https://github.com/Kadzmil/SAE5_Bande_Transporteuse/assets/166384885/e8e3ff0e-029f-4d7b-bd63-47c852e424e0)  
**Nouveau circuit de puissance**

![nv circuit puissance (2)](https://github.com/Kadzmil/SAE5_Bande_Transporteuse/assets/166384885/eafb81ba-cba2-46e9-827f-9614f0c4c68e) **Nouveau circuit commande**
### Programmation sur EcoStruxure Machine Expert
![gpn](https://github.com/Kadzmil/SAE5_Bande_Transporteuse/assets/166384885/bb61957b-ce6d-4d3b-a46f-ebb377492a8e) exemple grafcet
![rung1](https://github.com/Kadzmil/SAE5_Bande_Transporteuse/assets/166384885/6467ab2e-b94d-42b6-ada0-595c6a4e2d1a) exemple étape

### Structuration de l'armoire
En ce qui concerne l'agencement de l'armoire électrique, il a fallu dans un premier temps découper dans les bonnes dimensions des rails et des goulottes pour les fixer sur la plaque métallique qui soutiendra le tout dans l'armoire afin de justememnt pouvoir mettre nos composants et câbles. 
<img src="https://github.com/Kadzmil/SAE5_Bande_Transporteuse/blob/Main/Images/structure.jpg" alt="Description de l'image" width="600" height="600"/>
Une fois l'intérieur de prêt, il a fallu préparer la porte à l'acceuil de boutons et voyants ainsi que l'IHM. C'est pourquoi pour commencer, nous avons dû essayer d'imaginer différentes combinaison afin de trouver le placement le plus ergonomique et esthétique. 

<img src="https://github.com/Kadzmil/SAE5_Bande_Transporteuse/blob/Main/Images/premi%C3%A8re_id%C3%A9e.jpg" alt="Description de l'image" width="300" height="300"/> <img src="https://github.com/Kadzmil/SAE5_Bande_Transporteuse/blob/Main/Images/deuxi%C3%A8me%20id%C3%A9e.jpg" alt="Description de l'image" width="300" height="300"/> <img src="https://github.com/Kadzmil/SAE5_Bande_Transporteuse/blob/Main/Images/id%C3%A9e%20final.jpg" alt="Description de l'image" width="300" height="300"/>  \
**Premier prototype**&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Deuxième prototype**&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Troisième prototype**

<img src="https://github.com/Kadzmil/SAE5_Bande_Transporteuse/blob/Main/Images/d%C3%A9coupe%20IHM.jpg" alt="Description de l'image" width="600" height="600"/>

nous avons mesurer le diamètre des boutons et la taille del'IHM

![image_2024-06-26_181259342](https://github.com/Kadzmil/SAE5_Bande_Transporteuse/assets/166384885/5a81e285-2322-4311-9d47-31ed9a82efe7)  **Résultat final**
### Câblage
![image_2024-06-27_153113325](https://github.com/Kadzmil/SAE5_Bande_Transporteuse/assets/166384885/c8ba61db-8181-4767-9609-208e03500b76)
### Test
## IHM
### Programmation sur EcoStruxure Operator Terminal Expert
![image_2024-06-26_181403762](https://github.com/Kadzmil/SAE5_Bande_Transporteuse/assets/166384885/e3ea87b3-beb9-4a59-914e-c5d610ef5aba) 1ere vue IHM

![image_2024-06-26_181506123](https://github.com/Kadzmil/SAE5_Bande_Transporteuse/assets/166384885/62968746-13c0-4afb-ab48-19e88a982e6b) vue mode auto

![image_2024-06-26_181547640](https://github.com/Kadzmil/SAE5_Bande_Transporteuse/assets/166384885/9654a637-2be7-47d5-8ed5-33bc86cffd10) vue mode manu
### Test IHM
![image_2024-06-26_182352833](https://github.com/Kadzmil/SAE5_Bande_Transporteuse/assets/166384885/b8ac8ef3-c5f1-4927-afe8-baee6b622a8a) IHM grillé







![](https://github.com/Kadzmil/SAE5_Bande_Transporteuse/blob/Main/Images/d%C3%A9coupe%20rail.jpg)

![](https://github.com/Kadzmil/SAE5_Bande_Transporteuse/blob/Main/Images/IMG_20240416_143353.jpg)






















