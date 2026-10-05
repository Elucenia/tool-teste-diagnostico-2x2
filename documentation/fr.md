<!-- ELUCENIA technical documentation · teste-diagnostico-2x2 · fr · no clinical/professional/rights approval -->

# Test diagnostique (tableau 2×2)

[conditions, sources et autorisations](https://elucenia.org/fr/outils/teste-diagnostico-2x2)

## Mode d’emploi

Utilisez l’outil sur le portail ou ouvrez index.html via un serveur HTTP local. Sélectionnez la langue, remplissez les champs et lancez le calcul.

## Données d’entrée et unités

### Vrais positifs (VP) : test positif et maladie présente

`vp`

intervalle: 0–1000000

### Faux positifs (FP) : test positif et maladie absente

`fp`

intervalle: 0–1000000

### Faux négatifs (FN) : test négatif et maladie présente

`fn`

intervalle: 0–1000000

### Vrais négatifs (VN) : test négatif et maladie absente

`vn`

intervalle: 0–1000000

## Édition de la méthode

2×2:sensibilité/spécificité/VPP/VPN ; Wilson 95% proportions ; Simel 1991 IC logRV ; pas Wald

## Formule documentée

Sensibilité = VP / (VP + FN) · Spécificité = VN / (VN + FP) · VPP = VP / (VP + FP) · VPN = VN / (VN + FN) · Exactitude = (VP + VN) / total.

RV+ = Sensibilité / (1 − Spécificité) · RV− = (1 − Sensibilité) / Spécificité.

IC 95 % : score Wilson pour proportions ; méthode logarithmique pour rapports (Simel 1991), ET(ln RV+) = √(1/VP − 1/(VP+FN) + 1/FP − 1/(FP+VN)).

## Limites et population

Le tableau exige une classification binaire du test et de l’état de référence, avec des effectifs cohérents pour la même population. Les valeurs prédictives positive et négative dépendent de la prévalence et ne se transposent pas automatiquement à une autre population. Un dénominateur nul peut rendre une mesure indéfinie. Les intervalles de Wilson pour les proportions et les intervalles logarithmiques pour les rapports de vraisemblance sont des méthodes différentes ; les effectifs nuls et les petits échantillons exigent une interprétation spécifique. Cette analyse ne démontre pas à elle seule la qualité du standard de référence et ne valide pas le test.

## Références

- [Altman DG, Bland JM. Statistics Notes: Diagnostic tests 1: sensitivity and specificity. BMJ, 1994.](https://doi.org/10.1136/bmj.308.6943.1552)

- [Altman DG, Bland JM. Statistics Notes: Diagnostic tests 2: predictive values. BMJ, 1994.](https://doi.org/10.1136/bmj.309.6947.102)

- [Brown LD, Cai TT, DasGupta A. Interval estimation for a binomial proportion. Statistical Science, 2001.](https://doi.org/10.1214/ss/1009213286)

- [Simel DL, Samsa GP, Matchar DB. Likelihood ratios with confidence: sample size estimation for diagnostic test studies. J Clin Epidemiol, 1991.](https://doi.org/10.1016/0895-4356(91)90128-V)

- [Deeks/Altman2004](https://pmc.ncbi.nlm.nih.gov/articles/PMC478236/)

- [Brown/Cai/DasGupta2001](https://repository.upenn.edu/bitstreams/c3690c8b-efaf-485b-a984-39cfc22aae13/download)

## Reproduire les tests techniques

Exécutez node test.cjs dans le répertoire racine de ce dépôt pour reproduire les cas synthétiques enregistrés. Les données d’entrée, les résultats attendus et les tolérances d’origine sont conservés. Les tests techniques ne constituent pas une validation clinique.

```sh
node test.cjs
```

tool.json contient les sources, l’édition et le périmètre de la revue. examples.json conserve les données d’entrée et les résultats attendus des cas synthétiques ; results.json consigne les résultats obtenus.

[Fiche et références](../tool.json) · [Code JavaScript](../calculator.js) · [Cas de référence](../examples.json) · [results.json](../results.json)

## Revue et conditions d’utilisation

Aucune révision clinique indépendante n’a été effectuée.

Cette interface est une traduction réalisée par nos soins, et non une édition officielle ou certifiée. La revue clinique indépendante, la révision linguistique professionnelle et l’autorisation des droits sur les instruments n’ont pas été réalisées.

Résultat de la formule ou de la classification. L’interprétation, la conduite et l’applicabilité dépendent de l’évaluation professionnelle et de la source sélectionnée.

## Licence et attribution

Apache-2.0 s’applique uniquement au code d’ELUCENIA. Les droits sur les instruments, publications, traductions et données restent ceux de leurs titulaires respectifs. Conservez LICENSE et NOTICE.

ELUCENIA · Felipe Guedes · Copyright © 2026
