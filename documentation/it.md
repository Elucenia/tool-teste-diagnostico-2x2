<!-- ELUCENIA technical documentation · teste-diagnostico-2x2 · it · no clinical/professional/rights approval -->

# Test diagnostico (tabella 2×2)

[condizioni, fonti e autorizzazioni](https://elucenia.org/it/strumenti/teste-diagnostico-2x2)

## Come usare

Usi lo strumento nel portale oppure apra index.html tramite un server HTTP locale. Selezioni la lingua, compili i campi ed esegua il calcolo.

## Dati di ingresso e unità

### Veri positivi (VP): test positivo e malattia presente

`vp`

intervallo: 0–1000000

### Falsi positivi (FP): test positivo e malattia assente

`fp`

intervallo: 0–1000000

### Falsi negativi (FN): test negativo e malattia presente

`fn`

intervallo: 0–1000000

### Veri negativi (VN): test negativo e malattia assente

`vn`

intervallo: 0–1000000

## Edizione del metodo

2×2:sensibilità/specificità/VPP/VPN; Wilson 95% proporzioni; Simel 1991 IC logRV; non Wald

## Formula documentata

Sensibilità = VP / (VP + FN) · Specificità = VN / (VN + FP) · VPP = VP / (VP + FP) · VPN = VN / (VN + FN) · Accuratezza = (VP + VN) / totale.

RV+ = Sensibilità / (1 − Specificità) · RV− = (1 − Sensibilità) / Specificità.

IC 95%: score Wilson per proporzioni; metodo logaritmico per rapporti (Simel 1991), ES(ln RV+) = √(1/VP − 1/(VP+FN) + 1/FP − 1/(FP+VN)).

## Limiti e popolazione

La tabella richiede classificazione binaria del test e dello stato di riferimento, con conteggi coerenti per la stessa popolazione. I valori predittivi positivo e negativo dipendono dalla prevalenza e non si trasferiscono automaticamente a un’altra popolazione. Un denominatore zero può rendere una misura indefinita. Gli intervalli di Wilson per proporzioni e quelli logaritmici per rapporti di verosimiglianza sono metodi diversi; conteggi zero e piccoli campioni richiedono interpretazione specifica. Questa analisi non dimostra da sola la qualità dello standard di riferimento né valida il test.

## Riferimenti

- [Altman DG, Bland JM. Statistics Notes: Diagnostic tests 1: sensitivity and specificity. BMJ, 1994.](https://doi.org/10.1136/bmj.308.6943.1552)

- [Altman DG, Bland JM. Statistics Notes: Diagnostic tests 2: predictive values. BMJ, 1994.](https://doi.org/10.1136/bmj.309.6947.102)

- [Brown LD, Cai TT, DasGupta A. Interval estimation for a binomial proportion. Statistical Science, 2001.](https://doi.org/10.1214/ss/1009213286)

- [Simel DL, Samsa GP, Matchar DB. Likelihood ratios with confidence: sample size estimation for diagnostic test studies. J Clin Epidemiol, 1991.](https://doi.org/10.1016/0895-4356(91)90128-V)

- [Deeks/Altman2004](https://pmc.ncbi.nlm.nih.gov/articles/PMC478236/)

- [Brown/Cai/DasGupta2001](https://repository.upenn.edu/bitstreams/c3690c8b-efaf-485b-a984-39cfc22aae13/download)

## Riprodurre i test tecnici

Esegua node test.cjs nella cartella principale di questo repository per ripetere i casi sintetici registrati. Gli input, i risultati attesi e le tolleranze originali sono conservati. I test tecnici non costituiscono validazione clinica.

```sh
node test.cjs
```

tool.json contiene le fonti, l’edizione e l’ambito della revisione. examples.json conserva gli input e i risultati attesi dei casi sintetici; results.json registra i risultati ottenuti.

[Scheda e riferimenti](../tool.json) · [Codice JavaScript](../calculator.js) · [Casi di riferimento](../examples.json) · [results.json](../results.json)

## Revisione e condizioni d’uso

Non è stata effettuata una revisione clinica indipendente.

Questa interfaccia è una traduzione realizzata dagli autori, non un’edizione ufficiale o certificata. Non sono state eseguite la revisione clinica indipendente, la revisione linguistica professionale né la verifica delle autorizzazioni relative ai diritti sugli strumenti.

Risultato della formula o classificazione. Interpretazione, condotta e applicabilità dipendono dalla valutazione professionale e dalla fonte selezionata.

## Licenza e attribuzione

Apache-2.0 si applica solo al codice di ELUCENIA. I diritti su strumenti, pubblicazioni, traduzioni e dati restano ai rispettivi titolari. Conservi LICENSE e NOTICE.

ELUCENIA · Felipe Guedes · Copyright © 2026

## Risultati documentati

Le informazioni seguenti conservano gli output del metodo per esempi sintetici. Non costituiscono una validazione clinica indipendente.

### 1

Sensibilità 89,5% e specificità 62,8%. Rapporti di verosimiglianza moderati (RV+ tra 5 e 10 oppure RV− tra 0,1 e 0,2).

| Dettagli del risultato | |
| --- | --- |
| Specificità | 62,8% (IC 95%: 52,2% a 72,3%) |
| Valore predittivo positivo | 87,8% (IC 95%: 83,3% a 91,2%) |
| Valore predittivo negativo | 66,7% (IC 95%: 55,9% a 76,0%) |
| Rapporto di verosimiglianza positivo (RV+) | 2,41 (IC 95%: 1,82 a 3,18) |
| Rapporto di verosimiglianza negativo (RV−) | 0,17 (IC 95%: 0,11 a 0,25) |
| Accuratezza | 82,8% |
| Prevalenza nel campione | 75,0% |

I valori predittivi valgono solo per una prevalenza uguale a quella di questo campione (75,0%). Per un’altra prevalenza, usare la probabilità post-test con il RV.


### 2

Sensibilità 80,0% e specificità 90,0%. Rapporti di verosimiglianza moderati (RV+ tra 5 e 10 oppure RV− tra 0,1 e 0,2).

| Dettagli del risultato | |
| --- | --- |
| Specificità | 90,0% (IC 95%: 59,6% a 98,2%) |
| Valore predittivo positivo | 88,9% (IC 95%: 56,5% a 98,0%) |
| Valore predittivo negativo | 81,8% (IC 95%: 52,3% a 94,9%) |
| Rapporto di verosimiglianza positivo (RV+) | 8,00 (IC 95%: 1,21 a 52,69) |
| Rapporto di verosimiglianza negativo (RV−) | 0,22 (IC 95%: 0,06 a 0,78) |
| Accuratezza | 85,0% |
| Prevalenza nel campione | 50,0% |

I valori predittivi valgono solo per una prevalenza uguale a quella di questo campione (50,0%). Per un’altra prevalenza, usare la probabilità post-test con il RV.

