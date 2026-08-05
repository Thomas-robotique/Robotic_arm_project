# Suivi du developpement du bras articulé

Ce document présente, dans l’ordre chronologique, les différentes étapes d’évolution du bras robotisé.  
Chaque vidéo illustre une amélioration technique, comme la résolution d’un bug, la correction d’un problème mécanique ou l’ajout d’une nouvelle fonctionnalité.

---

### - 17/08/2025 20:28, Suivi du développement, Bras robotique
1ʳᵉ vidéo du bras : il dispose de deux rotations, mais présente encore du jeu mécanique à corriger.  
[Voir la vidéo](https://youtu.be/0k7IBRY94nI)

---

### - 18/08/2025 9:23, Suivi du développement, Bras robotique
- Correction du code de pilotage des servomoteurs afin de réduire le jeu mécanique ([Voir le code Arduino](../software/arduino/Code_arduino.md))  
- Fixation du bras sur une planche en bois pour limiter les vibrations  
- Ajout d’une nouvelle articulation destinée à soutenir la pince  

2ᵉ vidéo du bras robotique : [2e vidéo](https://youtu.be/2np7a8PfgLk)

#### Points d’amélioration futurs :
- Améliorer encore le jeu mécanique  
- Finaliser la fixation de la pince  

---

### - 19/08/2025 13:20, Suivi du développement, Bras robotique
- Modification de la fixation du servomoteur situé au sommet du bras pour réduire le jeu mécanique et améliorer l’angle de rotation  

3ᵉ vidéo du bras robotique : [3e vidéo](https://youtu.be/AkJcX3Q7wKA)
#### Points d’amélioration futurs :
- Optimiser davantage la mécanique pour stabiliser le bras  
- Finaliser la fixation de la pince  
- Réduire le jeu mécanique  

---

### - 27/08/2025 22:56, Suivi du développement, Bras robotique
- Ajout d’un encodeur rotatif pour contrôler la rotation du premier servomoteur  

4ᵉ vidéo du bras robotique : [4e vidéo](https://youtu.be/zPzh-STQNL8)

#### Points d’amélioration futurs :
- Finaliser la fixation de la pince  
- Ajouter 2 encodeurs supplémentaires  
- Réduire le jeu mécanique  

---

### - 28/08/2025 22:04, Suivi du développement, Bras robotique
- Ajout d’un 2ᵉ encodeur pour le second servomoteur  
- Ajout de 2 pieds métalliques afin de supprimer le jeu mécanique  
- Reprise du câblage sur breadboard pour un montage plus propre  

5ᵉ vidéo du bras robotique : [5e vidéo](https://youtu.be/TMBsFKxXWAc)

#### Points d’amélioration futurs :
- Finaliser la fixation de la pince  
- Ajouter 1 encodeur supplémentaire  
- Réaliser une vidéo de meilleure qualité (meilleure luminosité)  

---

### - 06/09/2025 20:42, Suivi du développement, Bras robotique
- Ajout de deux pieds métalliques supplémentaires (équerres usinées) pour réduire le jeu mécanique  
- Fixation définitive de la pince et vérification de la capacité des servomoteurs à supporter son poids  
- Amélioration de la partie électrique (meilleure tenue des composants, réduction des faux contacts)  

6ᵉ vidéo du bras robotique : [6e vidéo](https://youtu.be/Qs0z032AmsQ)

- Mise en fonctionnement de la pince avec détection de la saisie d’objets (arrêt automatique pour éviter la surchauffe)  
- Intégration d’un capteur INA219 en série avec le servomoteur pour surveiller le courant. Lorsque le capteur détecte un pic prolongé (objet saisi), le code arrête la fermeture de la pince.  
[Voir le code Arduino](../software/arduino/Code_arduino.md)  

Vidéo de la pince : [vidéo de la pince](https://youtu.be/Qs0z032AmsQ)

#### Points d’amélioration futurs :
- Réduire encore le jeu mécanique  
- Regrouper toutes les fonctionnalités du bras (déplacement + saisie d’objet) dans un seul code  

---

### - 19/09/2025 16:04, Suivi du développement, Bras robotique
Le bras robotique est désormais pleinement fonctionnel : il combine les mouvements du bras et la saisie d’objets avec la pince.  
Le montage final de la pince avait déjà été réalisé le 06/09/2025. Un code Arduino complet a ensuite été développé pour piloter l’ensemble du bras et la pince.  

Une séquence de démonstration a été programmée : le bras saisit un objet, le déplace puis le relâche.  

7ᵉ vidéo du bras robotique en fonctionnement : [7e vidéo](https://youtu.be/GEP4Osftczw)

#### Points d’amélioration futurs :
- Améliorer l’esthétique et la sécurité du bras  
- Organiser et sécuriser le câblage afin d’éviter tout faux contacts ou courts-circuits  


### - 06/06/2026 18:51, Suivi du développement, Bras robotique
J’ai entièrement refait le système électrique du bras en concevant un PCB qui supprime les fils de connexion.
L’objectif est de rendre le circuit plus fiable et plus robuste. 
Vous trouverez des photos du PCB [ici](../hardware)
Voici une comparaison avant après :
avant                                            
<img width="1000" alt="Photo_système_électrique_sans_pcb" src="https://github.com/user-attachments/assets/5444e699-9615-4d06-81b3-8bacafab156b" />

après
<img width="1920" height="1080" alt="Photo_système_électrique_avec_pcb" src="https://github.com/user-attachments/assets/bb61eaa4-de88-4d4b-8259-e8cc33c0919f" />


#### Points d’amélioration futurs :
- Finaliser la trilatération afin d’obtenir les coordonnées d’un objet et automatiser sa prise.

### - 10/07/2026 18:21, Suivi du développement, Bras robotique

J’ai finalisé le code permettant de calculer la position d’un objet situé devant le bras robotique à partir des distances mesurées par les trois capteurs à ultrasons.
Ce module réalise la trilatération en utilisant les coordonnées fixes des capteurs et les distances mesurées, puis renvoie la position estimée de l’objet dans le repère du bras. [voir le code](../software/arduino/Code_arduino.md)  
Vous pourrez aussi trouvez la démonstration des formules des coordonnées de l'objet [ici](../hardware/Démonstration_des_formules_de_coordonnées.pdf)

J’ai finalisé le code de cinématique inverse permettant, à partir de la position détectée d’un objet, de calculer automatiquement les angles nécessaires pour chaque servomoteur.
Ce module détermine la configuration du bras afin qu’il puisse atteindre et saisir l’objet, en prenant en compte la géométrie du robot et les contraintes mécaniques des articulations.
Comme pour le code précedent vous pouvez le retrouver [ici](../software/arduino/Code_arduino.md)  

#### Points d’amélioration futurs :
– Tester ensemble les deux derniers modules (trilatération et cinématique inverse) afin de rendre la saisie d’objet la plus fiable possible.

### - 05/08/2026 10:57, Suivi du développement, Bras robotique

La méthode par trilatération telle que je l’avais effectuée ne permettait pas une localisation précise de l’objet.
En effet, chacun des trois capteurs détectait un point différent de l’objet, ce qui empêchait le bon calcul de sa position.

À la place, j’ai décidé d’utiliser un seul capteur placé en face du robot afin que, grâce à son scan, il calcule la position de l’objet. L’explication détaillée de ce fonctionnement se trouve ici.
