# Implémenter le Continuous Testing

Ce projet sert de support à l'atelier ***Implémenter le Continuous Testing***
\
&nbsp;

## Préparation de l'atelier
\
&nbsp;

### ETAPE 1 : FORK le projet cerberustesting/cerberus-sample-maboutique
1. Depuis le projet github https://github.com/cerberustesting/cerberus-sample-maboutique, fork l’application sur votre repository perso
\
&nbsp;

<img width="766" alt="Capture d’écran 2022-06-11 à 00 22 09" src="https://user-images.githubusercontent.com/5376184/173158111-dd7de72e-fb0b-40c6-bfdb-c0db1aa3261e.png">

\
&nbsp;

2. Valider la creation du fork

\
&nbsp;

<img width="378" alt="Capture d’écran 2022-06-11 à 00 23 40" src="https://user-images.githubusercontent.com/5376184/173158234-68f72a2d-0130-43be-86c7-8a790113669c.png">

\
&nbsp;

Vous devriez être redirigé sur votre fork (Cf. ci dessous)

\
&nbsp;

<img width="758" alt="Capture d’écran 2022-06-11 à 00 35 05" src="https://user-images.githubusercontent.com/5376184/173159047-5136bc6b-58e5-4fbd-94b3-aba35671f274.png">

\
&nbsp;

## Ajout d'une Github Actions Qualité de code

Aller sur la page https://sonarcloud.io/

Choisir de parser un nouveau projet github
<img width="520" alt="Capture d’écran 2022-06-12 à 09 37 10" src="https://user-images.githubusercontent.com/5376184/173222554-58f36ff0-bf29-41f5-a587-a0840aa8d3e0.png">

Cliquer sur + / Ou ajouter un nouveau reposotory
<img width="416" alt="Capture d’écran 2022-06-12 à 09 39 18" src="https://user-images.githubusercontent.com/5376184/173222632-4be3aa0d-e614-4c57-a107-fd997718d0f5.png">

Choisir une organisation
<img width="657" alt="Capture d’écran 2022-06-12 à 09 40 25" src="https://user-images.githubusercontent.com/5376184/173222660-48a0df75-8dbd-469f-a6f1-87550855550f.png">

Choisir votre organisation perso
<img width="608" alt="Capture d’écran 2022-06-12 à 09 40 57" src="https://user-images.githubusercontent.com/5376184/173222668-3e57b9eb-a8a0-4a40-b184-d9fcc6389011.png">

Cliquer sur only select repository
Choisir le projet ma boutique
<img width="564" alt="Capture d’écran 2022-06-12 à 09 42 08" src="https://user-images.githubusercontent.com/5376184/173222704-d30d3892-ef93-486e-a516-9160415cbb8a.png">

Create an organisation
<img width="1098" alt="Capture d’écran 2022-06-12 à 09 43 25" src="https://user-images.githubusercontent.com/5376184/173222744-d36a1eeb-1b0d-4bc1-9098-90d07b8dd793.png">

Choisir Free plan
<img width="1076" alt="Capture d’écran 2022-06-12 à 09 43 53" src="https://user-images.githubusercontent.com/5376184/173222761-7b8175b2-5f37-477b-9b34-dd1e992356ce.png">

Selectionner et cliquer sur setup
<img width="1097" alt="Capture d’écran 2022-06-12 à 09 44 34" src="https://user-images.githubusercontent.com/5376184/173222775-90676be0-a2d0-4186-94cb-8b8c42ad7761.png">

Dans Sonar, vous arrivez sur cette page
<img width="1070" alt="Capture d’écran 2022-06-12 à 11 05 22" src="https://user-images.githubusercontent.com/5376184/173225836-05ec0cb7-c13e-4695-91c7-a993960c2b8a.png">

Pour lancer une analyse, Faire un changement sur votre projet
<img width="949" alt="Capture d’écran 2022-06-12 à 11 08 34" src="https://user-images.githubusercontent.com/5376184/173225998-9a0efd18-b745-473a-a282-c28e99fab76b.png">

<img width="578" alt="Capture d’écran 2022-06-12 à 11 09 20" src="https://user-images.githubusercontent.com/5376184/173226005-4d8d2f2a-8d43-464a-bb9e-e883cf55a433.png">

<img width="1254" alt="Capture d’écran 2022-06-12 à 11 10 03" src="https://user-images.githubusercontent.com/5376184/173226016-4021ae43-dd92-44eb-b8d4-1cb31196ca5d.png">

Cliquer sur Set New Code Definition
<img width="1078" alt="Capture d’écran 2022-06-12 à 11 15 27" src="https://user-images.githubusercontent.com/5376184/173226264-f2f00e47-acef-40af-8c87-8f4623d6efda.png">

Choisir previous version
<img width="1340" alt="Capture d’écran 2022-06-12 à 11 15 57" src="https://user-images.githubusercontent.com/5376184/173226288-2c95b367-7df2-40ad-965b-0dc74eca2303.png">

Lancer un changement

Voir le resultat
<img width="1049" alt="Capture d’écran 2022-06-12 à 11 17 34" src="https://user-images.githubusercontent.com/5376184/173226381-1dc7a317-62ab-41de-bcd7-bc04606307fe.png">


Lancer un changement avec duplication de code

```
var names = ["Mike","Matt","Nancy","Adam","Jenny","Nancy","Carl"];
var uniqueNames = [];
$.each(names, function(i, el){
    if($.inArray(el, uniqueNames) === -1) uniqueNames.push(el);
});

var names2 = ["Mike","Matt","Nancy","Adam","Jenny","Nancy","Carl"];
var uniqueNames2 = [];
$.each(names2, function(i, el){
    if($.inArray(el, uniqueNames2) === -1) uniqueNames2.push(el);
});

var names3 = ["Mike","Matt","Nancy","Adam","Jenny","Nancy","Carl"];
var uniqueNames3 = [];
$.each(names3, function(i, el){
    if($.inArray(el, uniqueNames3) === -1) uniqueNames3.push(el);
});
```


<img width="1066" alt="Capture d’écran 2022-06-12 à 11 23 12" src="https://user-images.githubusercontent.com/5376184/173226663-faa3345c-37ab-4ca2-8c91-d6ec1bd1a0ae.png">




### Activer les Actions 
1. Aller sur l'onglet Action
2. Cliquer sur Activer les workflows
<img width="341" alt="Capture d’écran 2022-06-11 à 00 23 23" src="https://user-images.githubusercontent.com/5376184/173158211-2988a774-3f33-46c5-bb0c-7180c9cdb1c8.png">
