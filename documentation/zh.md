<!-- ELUCENIA technical documentation · teste-diagnostico-2x2 · zh · no clinical/professional/rights approval -->

# 诊断试验（2×2 表）

[条件、来源与许可](https://elucenia.org/zh/tools/teste-diagnostico-2x2)

## 使用方法

在门户中使用工具，或通过本地 HTTP 服务器打开 index.html。选择语言，填写各字段，然后计算。

## 输入与单位

### 真阳性（TP）：检测阳性且患病

`vp`

范围: 0–1000000

### 假阳性（FP）：检测阳性但无病

`fp`

范围: 0–1000000

### 假阴性（FN）：检测阴性但患病

`fn`

范围: 0–1000000

### 真阴性（TN）：检测阴性且无病

`vn`

范围: 0–1000000

## 方法版本

2×2：敏感度/特异度/PPV/NPV；Wilson 95%比例；Simel 1991对数LR区间；非Wald比例

## 已记录的公式

敏感度 = TP / (TP + FN) · 特异度 = TN / (TN + FP) · 阳性预测值 = TP / (TP + FP) · 阴性预测值 = TN / (TN + FN) · 准确率 = (TP + TN) / 总数.

LR+ = 敏感度 / (1 − 特异度) · LR− = (1 − 敏感度) / 特异度.

95%置信区间：比例用Wilson评分法，似然比用对数法（Simel 1991）, 标准误(ln LR+) = √(1/TP − 1/(TP+FN) + 1/FP − 1/(FP+TN)).

## 限制与适用人群

此表要求检测结果和参考状态均为二分类，并使用同一人群的一致计数。阳性与阴性预测值依赖患病率，不能自动移用于其他人群。分母为零可能使指标无定义。比例的 Wilson 区间和似然比的对数区间是不同方法；零计数和小样本需要专门解释。此分析本身不能证明参考标准的质量，也不能验证检测的有效性。

## 参考文献

- [Altman DG, Bland JM. Statistics Notes: Diagnostic tests 1: sensitivity and specificity. BMJ, 1994.](https://doi.org/10.1136/bmj.308.6943.1552)

- [Altman DG, Bland JM. Statistics Notes: Diagnostic tests 2: predictive values. BMJ, 1994.](https://doi.org/10.1136/bmj.309.6947.102)

- [Brown LD, Cai TT, DasGupta A. Interval estimation for a binomial proportion. Statistical Science, 2001.](https://doi.org/10.1214/ss/1009213286)

- [Simel DL, Samsa GP, Matchar DB. Likelihood ratios with confidence: sample size estimation for diagnostic test studies. J Clin Epidemiol, 1991.](https://doi.org/10.1016/0895-4356(91)90128-V)

- [Deeks/Altman2004](https://pmc.ncbi.nlm.nih.gov/articles/PMC478236/)

- [Brown/Cai/DasGupta2001](https://repository.upenn.edu/bitstreams/c3690c8b-efaf-485b-a984-39cfc22aae13/download)

## 复现技术测试

在此仓库的根目录中运行 node test.cjs，以重复已记录的合成案例。原始输入、预期结果和容差保持不变。技术测试不构成临床验证。

```sh
node test.cjs
```

tool.json 包含来源、版本和审查范围。examples.json 保留合成输入与预期结果；results.json 记录实际得到的结果。

[记录与参考文献](../tool.json) · [JavaScript代码](../calculator.js) · [参考案例](../examples.json) · [results.json](../results.json)

## 审查与使用条件

尚未开展独立临床审查。

此界面为自主编写的翻译，并非官方或认证版本。尚未完成独立临床审查、专业语言审查或工具权利授权。

公式或分类结果。解释、处理及适用性须结合专业评估和所选来源。

## 许可与署名

Apache-2.0 仅适用于 ELUCENIA 代码。工具、出版物、翻译和数据的权利仍归各自权利人所有。请保留 LICENSE 和 NOTICE。

ELUCENIA · Felipe Guedes · Copyright © 2026
