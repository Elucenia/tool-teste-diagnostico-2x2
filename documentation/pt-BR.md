<!-- ELUCENIA technical documentation · teste-diagnostico-2x2 · pt-BR · no clinical/professional/rights approval -->

# Teste diagnóstico (tabela 2×2)

[condições, fontes e permissões](https://elucenia.org/pt-br/ferramentas/teste-diagnostico-2x2)

## Como usar

Use a ferramenta no portal ou abra index.html em um servidor HTTP local. Selecione o idioma, preencha os campos e calcule.

## Entradas e unidades

### Verdadeiros positivos (VP): teste positivo e doente

`vp`

intervalo: 0–1000000

### Falsos positivos (FP): teste positivo e sem a doença

`fp`

intervalo: 0–1000000

### Falsos negativos (FN): teste negativo e doente

`fn`

intervalo: 0–1000000

### Verdadeiros negativos (VN): teste negativo e sem a doença

`vn`

intervalo: 0–1000000

## Edição do método

2×2:Sens/Spec/PPV/NPV; Wilson 95%proporções; Simel 1991 log CILR; sem Waldproporções

## Fórmula documentada

Sensibilidade = VP / (VP + FN) · Especificidade = VN / (VN + FP) · VPP = VP / (VP + FP) · VPN = VN / (VN + FN) · Acurácia = (VP + VN) / total.

RV+ = sensibilidade / (1 − especificidade) · RV− = (1 − sensibilidade) / especificidade.

Intervalos de confiança de 95%: método do escore de Wilson para as proporções; para as razões de verossimilhança, método logarítmico (Simel, 1991), com EP(ln RV+) = √(1/VP − 1/(VP+FN) + 1/FP − 1/(FP+VN)).

## Limites e população

A tabela exige classificação binária do teste e do estado de referência, com contagens coerentes para a mesma população. Valor preditivo positivo e negativo dependem da prevalência; não se transferem automaticamente para outra população. Um denominador zero pode tornar a medida indefinida. Os intervalos de Wilson para proporções e logarítmicos para razões de verossimilhança são métodos diferentes; contagens zero e amostras pequenas exigem interpretação específica. Esta análise não demonstra, sozinha, a qualidade do padrão de referência nem valida o teste.

## Referências

- [Altman DG, Bland JM. Statistics Notes: Diagnostic tests 1: sensitivity and specificity. BMJ, 1994.](https://doi.org/10.1136/bmj.308.6943.1552)

- [Altman DG, Bland JM. Statistics Notes: Diagnostic tests 2: predictive values. BMJ, 1994.](https://doi.org/10.1136/bmj.309.6947.102)

- [Brown LD, Cai TT, DasGupta A. Interval estimation for a binomial proportion. Statistical Science, 2001.](https://doi.org/10.1214/ss/1009213286)

- [Simel DL, Samsa GP, Matchar DB. Likelihood ratios with confidence: sample size estimation for diagnostic test studies. J Clin Epidemiol, 1991.](https://doi.org/10.1016/0895-4356(91)90128-V)

- [Deeks/Altman2004](https://pmc.ncbi.nlm.nih.gov/articles/PMC478236/)

- [Brown/Cai/DasGupta2001](https://repository.upenn.edu/bitstreams/c3690c8b-efaf-485b-a984-39cfc22aae13/download)

## Reproduzir os testes técnicos

Execute node test.cjs na pasta raiz deste repositório para repetir os casos sintéticos registrados. As entradas, expectativas e tolerâncias originais são preservadas. Testes técnicos não constituem validação clínica.

```sh
node test.cjs
```

tool.json contém fontes, edição e escopo de revisão. examples.json conserva as entradas e expectativas sintéticas; results.json registra os resultados obtidos.

[Ficha e referências](../tool.json) · [Código JavaScript](../calculator.js) · [Casos de referência](../examples.json) · [results.json](../results.json)

## Revisão e condições de uso

Revisão clínica independente não realizada.

Esta interface é uma tradução autoral, não uma edição oficial ou certificada. Revisão clínica independente, revisão linguística profissional e autorização de direitos de instrumentos não foram realizadas.

Resultado da fórmula ou classificação. Interpretação, conduta e aplicabilidade dependem da avaliação profissional e da fonte selecionada.

## Licença e atribuição

Apache-2.0 aplica-se somente ao código da ELUCENIA. Os instrumentos, publicações, traduções e dados mantêm os direitos dos respectivos titulares. Preserve LICENSE e NOTICE.

ELUCENIA · Felipe Guedes · Copyright © 2026
