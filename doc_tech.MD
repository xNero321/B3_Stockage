# Documentation technique (Stockage)

## Création d'un RAID sur un NAS SYNOLOGY

### Création d'un groupe de stockage
1. Ouvrir le gestionnaire de stockage
2. Allez dans groupe de stockage et créer
<img src="./Screen/groupe_stockage_fin_bis.png">

3. Choix du type de groupe de stockage
<img src="./Screen/groupe stockage 1.png">
Nous utilisons la plus grande flexibilité 
4. Choix des propriétés du groupe de stockage
<img src="./Screen/groupe stockage 2.png">
5. Choix des disques suivant 
<img src="./Screen/groupe stockage 3.png">
6. Résultat
<img src="./Screen/groupe stockage fin.png">


### Création d'un volume

1. Ouvrir le gestionnaire de stockage
2. Allez dans volume et créer
<img src="./Screen/volume fin bis.png">

3. Choix du type de groupe de stockage 
<img src="./Screen/volume 1.png">
Nous utilisons la plus grande flexibilité 

4. Sélection du groupe de stockage. Choisissez le groupe de stockage que vous avez créé au préalable puis suivant.
<img src="./Screen/volume 2.png">

5. Choix du systeme de fichiers on garde le systeme recommandé
<img src="./Screen/volume 3.png">

6. Résultat
<img src="./Screen/volume fin.png">

## ISCSI 

### Création target et LUN

1. Ouvrir ISCSI manager
2. Dans l'onglet target cliquez sur créer
3. Lors de la création de la target choisissez le nom et activer CHAP
<img src="./Screen/target2.png">

4. Création du ISCSI LUN
<img src="./Screen/target1.png">

5. Configurer les propriétés d'ISCSI LUN
<img src="./Screen/target3.png">

6. Confirmation
<img src="./Screen/targetfin.png">


## Création d'une AD

1. Ajout du rôle et des fonctionnalités de l'ad 
<img src="./Screen/ad1.png">

2. On choisi l'installation basée sur un rôle ou une foncitonnalité
<img src="./Screen/ad2.png">

3. On choisi notre serveur
<img src="./Screen/ad3.png">

4. On choisi le rôle AD DS et service de fichier ISCSI pour gagner du temps
<img src="./Screen/ad4.png">

5. On applique l'installation

6. On doit promouvoir le serveur
<img src="./Screen/promotion.png">

7. On ajoute un nouvelle forêt et on choisi le nom du domaine
<img src="./Screen/promotion2.png">

8. on Choisi le mot de passe
<img src="./Screen/promotion3.png">

9. Maintenant on clique sur suivant jusqu'à l'installation

## Ajout du NAS à l'AD 

1. Dans le panneau de configuration sur le NAS allez dans domaine/LDAP
<img src="./Screen/nasdomaine.png">

2. Rentrer le nom d'utilisateur de l'administrateur et le mot de passe définie lors de la promotion
<img src="./Screen/nasdomaine2.png">

3. Valider et le NAS sera ajouté à l'AD

## Créer une sauvegarde de Windows Server stockée sur une cible ISCSI sur le NAS

1. Ouvrir l'initiateur ISCSI sur le serveur windows et rentré l'ip de la cible puis cliquez sur connexion rapide
<img src="./Screen/initiscsi.png">

2. Allez dans avancé
<img src="./Screen/initiscsi2.png">

3. On active le CHAP 
<img src="./Screen/initiscsi3.png">

4. On valide pour que la connexion soit éffectué
<img src="./Screen/initiscsi4.png">

5. Allez dans gestion de l'ordinateur

6. Dans gestion de disque on va faire un clique droit sur le disque 1 <, le mettre en ligne puis l'intialiser
7. Ensuite avec un clique droit sur la partie 20,00 Go on va créer un nouveau volume simple
<img src="./Screen/save1.png">

8. Dans les outils de windows serveur allez dans sauvegarde 
9. Une fois dans l'outils de sauvegarde choisissez sauvegarde unique
<img src="./Screen/save2.png">

10. Dans options de sauvegarde choisissez autre options
<img src="./Screen/save3.png">

11. Cliquez sur personnalisé puis suivant
<img src="./Screen/save4.png">

12. Cliquez sur ajouter des éléments
<img src="./Screen/save5.png">

13. Cliquez sur récupération complète et validez
<img src="./Screen/save6.png">

14. Cliquez sur suivant puis choisir le disque sur lequel vous voulez effectuer la sauvegarde puis valider.


