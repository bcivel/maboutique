## ETAPE 2 : Ajout de l'étape de testing

1. Aller sur l'onglet Action
\
&nbsp;
<img width="394" alt="Capture d’écran 2022-06-12 à 18 31 54" src="https://user-images.githubusercontent.com/5376184/173243328-08fad5c0-5e81-4652-a1ba-9cfd69c5e097.png">

\
&nbsp;

2. Cliquer sur Full_CI_to_complete.yml
<img width="482" alt="Capture d’écran 2022-06-12 à 22 03 23" src="https://user-images.githubusercontent.com/5376184/173251289-bf5ebbcb-4eb7-46ce-99e2-3842cf5ebad1.png">

\&nbsp;

3. Cliquer sur edit
4. Ajouter la configuration ci dessous
```
  run_Tests_UAT:
    needs: sonarcloud
    name: Run_Tests_UAT
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@master
    - name: cerberus-action
      uses: cerberustesting/cerberus-github-action@v6
      with:
        host: https://jftl.cerberus-testing.fr
        campaign: SanityCheck
        apikey: ${{ secrets.APIKEY }}
        author: ${{ github.event.pusher.name }}
        environment: UAT
        tag: ${TAG}
```

Vous obtenez ce resultat
<img width="1237" alt="Capture d’écran 2022-06-12 à 22 11 05" src="https://user-images.githubusercontent.com/5376184/173251555-e01c730b-c1a4-4d9f-b36e-8a1fca9f5207.png">


Commit ce changement. Et vérifier la bonne execution de la CI
<img width="1403" alt="Capture d’écran 2022-06-12 à 22 16 12" src="https://user-images.githubusercontent.com/5376184/173251753-a3b29fcf-2edf-4ea6-82d8-c256ce9fb47b.png">

