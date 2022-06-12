## Ajout d'une Github Actions Qualité de code

1. Aller sur la page https://sonarcloud.io/

2. Choisir de parser un nouveau projet github
\
&nbsp;

<img width="320" alt="Capture d’écran 2022-06-12 à 09 37 10" src="https://user-images.githubusercontent.com/5376184/173222554-58f36ff0-bf29-41f5-a587-a0840aa8d3e0.png">

\
&nbsp;

3. Cliquer sur + (ajouter un nouveau repository)
\
&nbsp; 
<img width="416" alt="Capture d’écran 2022-06-12 à 09 39 18" src="https://user-images.githubusercontent.com/5376184/173222632-4be3aa0d-e614-4c57-a107-fd997718d0f5.png">
\
&nbsp;

4. Choisir une organisation, choisir votre organisation perso, cliquer sur only select repository, choisir le projet "ma boutique" et cliquer sur install
\
&nbsp;
<img width="457" alt="Capture d’écran 2022-06-12 à 09 40 25" src="https://user-images.githubusercontent.com/5376184/173222660-48a0df75-8dbd-469f-a6f1-87550855550f.png">
<img width="408" alt="Capture d’écran 2022-06-12 à 09 40 57" src="https://user-images.githubusercontent.com/5376184/173222668-3e57b9eb-a8a0-4a40-b184-d9fcc6389011.png">
<img width="364" alt="Capture d’écran 2022-06-12 à 09 42 08" src="https://user-images.githubusercontent.com/5376184/173222704-d30d3892-ef93-486e-a516-9160415cbb8a.png">

\
&nbsp;
5.Créer une organisation
\
&nbsp;
<img width="798" alt="Capture d’écran 2022-06-12 à 09 43 25" src="https://user-images.githubusercontent.com/5376184/173222744-d36a1eeb-1b0d-4bc1-9098-90d07b8dd793.png">
\
&nbsp;
6. Choisir Free plan
\
&nbsp;
<img width="776" alt="Capture d’écran 2022-06-12 à 09 43 53" src="https://user-images.githubusercontent.com/5376184/173222761-7b8175b2-5f37-477b-9b34-dd1e992356ce.png">
\
&nbsp;
7. Selectionner et cliquer sur setup
\
&nbsp;
<img width="797" alt="Capture d’écran 2022-06-12 à 09 44 34" src="https://user-images.githubusercontent.com/5376184/173222775-90676be0-a2d0-4186-94cb-8b8c42ad7761.png">
\
&nbsp;
8. Dans Sonar, vous arrivez sur cette page
\
&nbsp;
<img width="770" alt="Capture d’écran 2022-06-12 à 11 05 22" src="https://user-images.githubusercontent.com/5376184/173225836-05ec0cb7-c13e-4695-91c7-a993960c2b8a.png">
\
&nbsp;

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


Lancer un changement

```
var names = ["Mike","Matt","Nancy","Adam","Jenny","Nancy","Carl"];
var uniqueNames = [];
$.each(names, function(i, el){
    if($.inArray(el, uniqueNames) === -1) uniqueNames.push(el);
});
```


<img width="1066" alt="Capture d’écran 2022-06-12 à 11 23 12" src="https://user-images.githubusercontent.com/5376184/173226663-faa3345c-37ab-4ca2-8c91-d6ec1bd1a0ae.png">


cliquer sur "See full Analysis"
<img width="1060" alt="Capture d’écran 2022-06-12 à 11 36 28" src="https://user-images.githubusercontent.com/5376184/173227111-ab74afba-0bab-4ea9-ab60-b61436f7014d.png">
Cliquer sur A rating required

Analyser les changements à appliquer
<img width="1002" alt="Capture d’écran 2022-06-12 à 11 37 14" src="https://user-images.githubusercontent.com/5376184/173227139-e1c22d3c-0217-4ffe-8394-4b389a7dddf6.png">

Dans github, modifier le fichier 
```
let names = ["Mike","Matt","Nancy","Adam","Jenny","Nancy","Carl"];
let uniqueNames = [];
$.each(names, function(_i, el){
    if($.inArray(el, uniqueNames) === -1) uniqueNames.push(el);
});
```
Commit
<img width="1050" alt="Capture d’écran 2022-06-12 à 11 40 48" src="https://user-images.githubusercontent.com/5376184/173227263-86ee8590-3503-4c9f-89c5-9880361cd532.png">


### Générer un token sonarcloud
Aller sur Account
<img width="254" alt="Capture d’écran 2022-06-12 à 11 50 30" src="https://user-images.githubusercontent.com/5376184/173227573-f40b2de0-9c49-4730-ac19-8f6704f2eaf4.png">

Aller sur Sécurité
<img width="677" alt="Capture d’écran 2022-06-12 à 11 51 18" src="https://user-images.githubusercontent.com/5376184/173227612-4d2faaa9-7871-49b0-971f-f35ec8f3862a.png">

Générer un token, et le copier

Dans github, cliquer sur Settings
<img width="837" alt="Capture d’écran 2022-06-12 à 11 53 06" src="https://user-images.githubusercontent.com/5376184/173227664-502ad354-378e-49d7-97a0-cd9f0b48385b.png">

Dans le menu Secret / Actions
<img width="1132" alt="Capture d’écran 2022-06-12 à 11 53 47" src="https://user-images.githubusercontent.com/5376184/173227702-df0c8cf5-ee78-472e-a321-6c9763239ca3.png">

Ajouter un secret SONAR_TOKEN
<img width="796" alt="Capture d’écran 2022-06-12 à 11 55 07" src="https://user-images.githubusercontent.com/5376184/173227763-bcb49e54-32ce-48b4-b84b-c3eb064dc6e2.png">


