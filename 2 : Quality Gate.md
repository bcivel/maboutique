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


### Configurer 
1. 
<img width="420" alt="Capture d’écran 2022-06-12 à 20 33 53" src="https://user-images.githubusercontent.com/5376184/173249512-a13c54ec-588f-46a7-b948-0c1baa12da97.png">

2. Désactiver le scan automatique
<img width="1307" alt="Capture d’écran 2022-06-12 à 20 56 18" src="https://user-images.githubusercontent.com/5376184/173249539-3f3c5e5d-236e-4817-9d64-3c40b5c860e8.png">

3. Cliquer sur la configuration via github actions
<img width="1310" alt="Capture d’écran 2022-06-12 à 20 57 40" src="https://user-images.githubusercontent.com/5376184/173249555-f52d0501-2cb9-4a4d-8f79-e5500b9cddec.png">

4. Copier le Token SONAR_TOKEN
<img width="1066" alt="Capture d’écran 2022-06-12 à 20 58 26" src="https://user-images.githubusercontent.com/5376184/173249610-40b888cf-093d-440c-9e1c-f5612807d738.png">

5. Choisir Other, et copier la configuration
<img width="1032" alt="Capture d’écran 2022-06-12 à 21 02 13" src="https://user-images.githubusercontent.com/5376184/173249665-6bd5d406-ecaf-46f1-89c4-cbc91c3341dd.png">

```
sonarcloud:
    needs: build
    name: SonarCloud
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
        with:
          fetch-depth: 0  # Shallow clones should be disabled for a better relevancy of analysis
      - name: SonarCloud Scan
        uses: SonarSource/sonarcloud-github-action@master
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}  # Needed to get PR information, if any
          SONAR_TOKEN: ${{ secrets.SONAR_TOKEN }}
```

6. Copier les propriétés 
```
sonar.projectKey
sonar.organization
```
<img width="1036" alt="Capture d’écran 2022-06-12 à 21 19 45" src="https://user-images.githubusercontent.com/5376184/173249760-924a6856-3aa3-4567-81bf-d95765d23a24.png">

## Configurer votre projet Github

1. Dand Github, aller dans Settings > Secrets > Actions

2. Cliquer sur New repository secret
<img width="789" alt="Capture d’écran 2022-06-12 à 21 32 35" src="https://user-images.githubusercontent.com/5376184/173250157-ce5b9e25-3cf9-4acb-85e6-a6641128c7e0.png">

Name : SONAR_TOKEN
Value : Le token sauvegardé

3. Changer les propiétés du fichier de propriété sonar-project.properties par les propiétés récupérées dans Sonar
<img width="1250" alt="Capture d’écran 2022-06-12 à 21 36 25" src="https://user-images.githubusercontent.com/5376184/173250293-33885f7f-83a8-4fbc-8bb5-3293e99294f7.png">


4. Modifier le fichier /.github/workflows/full_CI_to_complete.yml
<img width="1264" alt="Capture d’écran 2022-06-12 à 21 41 40" src="https://user-images.githubusercontent.com/5376184/173250448-b4b8028d-3292-476c-ad46-e4f4db247aad.png">

Cliquer sur edit
<img width="147" alt="Capture d’écran 2022-06-12 à 21 42 50" src="https://user-images.githubusercontent.com/5376184/173250466-0aada6d8-cdb8-4309-a488-76b5c1c9b22c.png">

Coller la configuration ci dessous :
```
  sonarcloud:
    needs: build
    name: SonarCloud
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
        with:
          fetch-depth: 0  # Shallow clones should be disabled for a better relevancy of analysis
      - name: SonarCloud Scan
        uses: SonarSource/sonarcloud-github-action@master
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}  # Needed to get PR information, if any
          SONAR_TOKEN: ${{ secrets.SONAR_TOKEN }}
```

Vous obtenez ce résultat
<img width="1127" alt="Capture d’écran 2022-06-12 à 21 43 47" src="https://user-images.githubusercontent.com/5376184/173250504-31a29274-a4af-4982-b5b7-cc7c9ee37046.png">

Cliquer sur Start Commit
<img width="618" alt="Capture d’écran 2022-06-12 à 21 44 52" src="https://user-images.githubusercontent.com/5376184/173250546-9ee1a17f-a84d-4f8b-96da-d2cd6858e982.png">

Depuis la page Actions, vérifier la bonne execution de la CI
<img width="1403" alt="Capture d’écran 2022-06-12 à 21 52 59" src="https://user-images.githubusercontent.com/5376184/173250763-bbd6148d-5e3b-4558-83da-c0d141a55fb4.png">

Dans Sonar, vérifier le résultat :
<img width="1049" alt="Capture d’écran 2022-06-12 à 11 17 34" src="https://user-images.githubusercontent.com/5376184/173226381-1dc7a317-62ab-41de-bcd7-bc04606307fe.png">

## Lancer un changement pour tester la Quality Gate

Créer un nouveau fichier 
<img width="914" alt="Capture d’écran 2022-06-12 à 21 53 23" src="https://user-images.githubusercontent.com/5376184/173250771-a4b19e57-b648-4b79-bff4-0b309f094ddc.png">

Nommez le Newfile.js et renseigner le contenu suivant
```
var names = ["Mike","Matt","Nancy","Adam","Jenny","Nancy","Carl"];
var uniqueNames = [];
$.each(names, function(i, el){
    if($.inArray(el, uniqueNames) === -1) uniqueNames.push(el);
});
```

<img width="1217" alt="Capture d’écran 2022-06-12 à 21 55 49" src="https://user-images.githubusercontent.com/5376184/173251082-5f57b582-2f0f-456f-aaa1-d3cc5ace40cf.png">

Commit New File
<img width="1229" alt="Capture d’écran 2022-06-12 à 21 56 05" src="https://user-images.githubusercontent.com/5376184/173251088-a3031c28-b36b-4a76-9d8c-b9b86799e3a1.png">

Depuis la page Actions, vérifier l'execution de la CI. Vous devriez avoir un KO sur la scan Sonarcloud
<img width="1408" alt="Capture d’écran 2022-06-12 à 21 58 30" src="https://user-images.githubusercontent.com/5376184/173251149-24afcf18-5b41-40b9-ae0c-08adb15f9a33.png">

Dans Sonarcloud, vérifier la status
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


