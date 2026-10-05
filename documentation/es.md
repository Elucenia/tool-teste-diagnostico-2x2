<!-- ELUCENIA technical documentation · teste-diagnostico-2x2 · es · no clinical/professional/rights approval -->

# Prueba diagnóstica (tabla 2×2)

[condiciones, fuentes y permisos](https://elucenia.org/es/herramientas/teste-diagnostico-2x2)

## Cómo usar

Utilice la herramienta en el portal o abra index.html mediante un servidor HTTP local. Seleccione el idioma, complete los campos y calcule.

## Entradas y unidades

### Verdaderos positivos (VP): prueba positiva y enfermedad presente

`vp`

intervalo: 0–1000000

### Falsos positivos (FP): prueba positiva y ausencia de enfermedad

`fp`

intervalo: 0–1000000

### Falsos negativos (FN): prueba negativa y enfermedad presente

`fn`

intervalo: 0–1000000

### Verdaderos negativos (VN): prueba negativa y ausencia de enfermedad

`vn`

intervalo: 0–1000000

## Edición del método

2×2:sensibilidad/especificidad/VPP/VPN; Wilson 95% proporciones; Simel 1991 IC logRV; no Wald

## Fórmula documentada

Sensibilidad = VP / (VP + FN) · Especificidad = VN / (VN + FP) · VPP = VP / (VP + FP) · VPN = VN / (VN + FN) · Exactitud = (VP + VN) / total.

RV+ = Sensibilidad / (1 − Especificidad) · RV− = (1 − Sensibilidad) / Especificidad.

IC 95%: método de puntuación de Wilson para proporciones; logarítmico para razones (Simel 1991), EE(ln RV+) = √(1/VP − 1/(VP+FN) + 1/FP − 1/(FP+VN)).

## Límites y población

La tabla exige clasificación binaria del test y del estado de referencia, con recuentos coherentes para la misma población. Los valores predictivos positivo y negativo dependen de la prevalencia y no se transfieren automáticamente a otra población. Un denominador cero puede hacer que la medida sea indefinida. Los intervalos de Wilson para proporciones y los logarítmicos para razones de verosimilitud son métodos diferentes; recuentos cero y muestras pequeñas exigen interpretación específica. Este análisis no demuestra por sí solo la calidad del patrón de referencia ni valida el test.

## Referencias

- [Altman DG, Bland JM. Statistics Notes: Diagnostic tests 1: sensitivity and specificity. BMJ, 1994.](https://doi.org/10.1136/bmj.308.6943.1552)

- [Altman DG, Bland JM. Statistics Notes: Diagnostic tests 2: predictive values. BMJ, 1994.](https://doi.org/10.1136/bmj.309.6947.102)

- [Brown LD, Cai TT, DasGupta A. Interval estimation for a binomial proportion. Statistical Science, 2001.](https://doi.org/10.1214/ss/1009213286)

- [Simel DL, Samsa GP, Matchar DB. Likelihood ratios with confidence: sample size estimation for diagnostic test studies. J Clin Epidemiol, 1991.](https://doi.org/10.1016/0895-4356(91)90128-V)

- [Deeks/Altman2004](https://pmc.ncbi.nlm.nih.gov/articles/PMC478236/)

- [Brown/Cai/DasGupta2001](https://repository.upenn.edu/bitstreams/c3690c8b-efaf-485b-a984-39cfc22aae13/download)

## Reproducir las pruebas técnicas

Ejecute node test.cjs en el directorio raíz de este repositorio para repetir los casos sintéticos registrados. Se conservan las entradas, los resultados esperados y las tolerancias originales. Las pruebas técnicas no constituyen validación clínica.

```sh
node test.cjs
```

tool.json contiene las fuentes, la edición y el alcance de la revisión. examples.json conserva las entradas y los resultados esperados de los casos sintéticos; results.json registra los resultados obtenidos.

[Ficha y referencias](../tool.json) · [Código JavaScript](../calculator.js) · [Casos de referencia](../examples.json) · [results.json](../results.json)

## Revisión y condiciones de uso

No se ha realizado una revisión clínica independiente.

Esta interfaz es una traducción de elaboración propia, no una edición oficial o certificada. No se han realizado la revisión clínica independiente, la revisión lingüística profesional ni la autorización de derechos de los instrumentos.

Resultado de la fórmula o clasificación. La interpretación, la conducta y la aplicabilidad dependen de la evaluación profesional y de la fuente seleccionada.

## Licencia y atribución

Apache-2.0 se aplica únicamente al código de ELUCENIA. Los derechos de los instrumentos, publicaciones, traducciones y datos permanecen en manos de sus respectivos titulares. Conserve LICENSE y NOTICE.

ELUCENIA · Felipe Guedes · Copyright © 2026
