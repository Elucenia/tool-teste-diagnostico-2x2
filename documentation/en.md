<!-- ELUCENIA technical documentation · teste-diagnostico-2x2 · en · no clinical/professional/rights approval -->

# Diagnostic test (2×2 table)

[conditions, sources and permissions](https://elucenia.org/en/tools/teste-diagnostico-2x2)

## How to use

Use the tool in the portal or open index.html through a local HTTP server. Select the language, complete the fields and calculate.

## Inputs and units

### True positives (TP): positive test and disease present

`vp`

range: 0–1000000

### False positives (FP): positive test and no disease

`fp`

range: 0–1000000

### False negatives (FN): negative test and disease present

`fn`

range: 0–1000000

### True negatives (TN): negative test and no disease

`vn`

range: 0–1000000

## Method edition

2×2:sensitivity/specificity/PPV/NPV; Wilson 95% proportions; Simel 1991 logarithmic LR intervals; not Wald proportions

## Documented formula

Sensitivity = TP / (TP + FN) · Specificity = TN / (TN + FP) · PPV = TP / (TP + FP) · NPV = TN / (TN + FN) · Accuracy = (TP + TN) / total.

LR+ = Sensitivity / (1 − Specificity) · LR− = (1 − Sensitivity) / Specificity.

95% confidence intervals: Wilson score for proportions; logarithmic method for likelihood ratios (Simel 1991), SE(ln LR+) = √(1/TP − 1/(TP+FN) + 1/FP − 1/(FP+TN)).

## Limits and population

The table requires binary classification of the test and reference status, with consistent counts for the same population. Positive and negative predictive values depend on prevalence and do not transfer automatically to another population. A zero denominator may make a measure undefined. Wilson intervals for proportions and logarithmic intervals for likelihood ratios are different methods; zero counts and small samples require specific interpretation. This analysis alone does not establish the quality of the reference standard or validate the test.

## References

- [Altman DG, Bland JM. Statistics Notes: Diagnostic tests 1: sensitivity and specificity. BMJ, 1994.](https://doi.org/10.1136/bmj.308.6943.1552)

- [Altman DG, Bland JM. Statistics Notes: Diagnostic tests 2: predictive values. BMJ, 1994.](https://doi.org/10.1136/bmj.309.6947.102)

- [Brown LD, Cai TT, DasGupta A. Interval estimation for a binomial proportion. Statistical Science, 2001.](https://doi.org/10.1214/ss/1009213286)

- [Simel DL, Samsa GP, Matchar DB. Likelihood ratios with confidence: sample size estimation for diagnostic test studies. J Clin Epidemiol, 1991.](https://doi.org/10.1016/0895-4356(91)90128-V)

- [Deeks/Altman2004](https://pmc.ncbi.nlm.nih.gov/articles/PMC478236/)

- [Brown/Cai/DasGupta2001](https://repository.upenn.edu/bitstreams/c3690c8b-efaf-485b-a984-39cfc22aae13/download)

## Reproduce the technical tests

Run node test.cjs in the root directory of this repository to repeat the recorded synthetic cases. Original inputs, expectations and tolerances are preserved. Technical tests do not constitute clinical validation.

```sh
node test.cjs
```

tool.json contains sources, edition and review scope. examples.json retains synthetic inputs and expectations; results.json records the obtained results.

[Record and references](../tool.json) · [JavaScript code](../calculator.js) · [Reference cases](../examples.json) · [results.json](../results.json)

## Review and conditions of use

Independent clinical review has not been performed.

This interface is an authorial translation, not an official or certified edition. Independent clinical review, professional language review and instrument rights clearance have not been performed.

Formula or classification result. Interpretation, care and applicability depend on professional assessment and the selected source.

## License and attribution

Apache-2.0 applies only to ELUCENIA code. Rights to instruments, publications, translations and data remain with their respective holders. Preserve LICENSE and NOTICE.

ELUCENIA · Felipe Guedes · Copyright © 2026

## Documented results

The information below preserves the method outputs for synthetic examples. It does not constitute independent clinical validation.

### 1

Sensitivity 89.5% and specificity 62.8%. Moderate likelihood ratios (LR+ between 5 and 10 or LR− between 0.1 and 0.2).

| Result details | |
| --- | --- |
| Specificity | 62.8% (95% CI: 52.2% to 72.3%) |
| Positive predictive value | 87.8% (95% CI: 83.3% to 91.2%) |
| Negative predictive value | 66.7% (95% CI: 55.9% to 76.0%) |
| Positive likelihood ratio (LR+) | 2.41 (95% CI: 1.82 to 3.18) |
| Negative likelihood ratio (LR−) | 0.17 (95% CI: 0.11 to 0.25) |
| Accuracy | 82.8% |
| Prevalence in the sample | 75.0% |

The predictive values are only valid for a prevalence equal to that of this sample (75.0%). For another prevalence, use the post-test probability with the LR.


### 2

Sensitivity 80.0% and specificity 90.0%. Moderate likelihood ratios (LR+ between 5 and 10 or LR− between 0.1 and 0.2).

| Result details | |
| --- | --- |
| Specificity | 90.0% (95% CI: 59.6% to 98.2%) |
| Positive predictive value | 88.9% (95% CI: 56.5% to 98.0%) |
| Negative predictive value | 81.8% (95% CI: 52.3% to 94.9%) |
| Positive likelihood ratio (LR+) | 8.00 (95% CI: 1.21 to 52.69) |
| Negative likelihood ratio (LR−) | 0.22 (95% CI: 0.06 to 0.78) |
| Accuracy | 85.0% |
| Prevalence in the sample | 50.0% |

The predictive values are only valid for a prevalence equal to that of this sample (50.0%). For another prevalence, use the post-test probability with the LR.

