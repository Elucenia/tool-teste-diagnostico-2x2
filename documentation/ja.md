<!-- ELUCENIA technical documentation · teste-diagnostico-2x2 · ja · no clinical/professional/rights approval -->

# 診断検査（2×2表）

[条件・出典・許諾](https://elucenia.org/ja/tools/teste-diagnostico-2x2)

## 使い方

ポータルでツールを使用するか、ローカルHTTPサーバー経由でindex.htmlを開いてください。言語を選択し、項目を入力して計算してください。

## 入力項目と単位

### 真陽性（TP）：検査陽性で疾患あり

`vp`

範囲: 0–1000000

### 偽陽性（FP）：検査陽性で疾患なし

`fp`

範囲: 0–1000000

### 偽陰性（FN）：検査陰性で疾患あり

`fn`

範囲: 0–1000000

### 真陰性（TN）：検査陰性で疾患なし

`vn`

範囲: 0–1000000

## 方法の版

2×2：感度/特異度/PPV/NPV、Wilson 95%比率、Simel 1991対数LR区間、Wald比率ではない

## 記載された計算式

感度 = TP / (TP + FN) · 特異度 = TN / (TN + FP) · 陽性適中率 = TP / (TP + FP) · 陰性適中率 = TN / (TN + FN) · 正確度 = (TP + TN) / 総数.

LR+ = 感度 / (1 − 特異度) · LR− = (1 − 感度) / 特異度.

95%信頼区間：比率はWilsonスコア、尤度比は対数法（Simel 1991）, 標準誤差(ln LR+) = √(1/TP − 1/(TP+FN) + 1/FP − 1/(FP+TN)).

## 限界・対象集団

この表は検査結果と参照状態の二値分類、および同じ集団に対する整合した件数を必要とします。陽性・陰性適中率は有病率に依存し、別の集団に自動的に移用できません。分母がゼロだと指標が未定義になることがあります。割合の Wilson 区間と尤度比の対数区間は異なる方法で、ゼロ件数や小標本には個別の解釈が必要です。この分析だけで参照基準の質を証明したり、検査を妥当性確認したりするものではありません。

## 参考文献

- [Altman DG, Bland JM. Statistics Notes: Diagnostic tests 1: sensitivity and specificity. BMJ, 1994.](https://doi.org/10.1136/bmj.308.6943.1552)

- [Altman DG, Bland JM. Statistics Notes: Diagnostic tests 2: predictive values. BMJ, 1994.](https://doi.org/10.1136/bmj.309.6947.102)

- [Brown LD, Cai TT, DasGupta A. Interval estimation for a binomial proportion. Statistical Science, 2001.](https://doi.org/10.1214/ss/1009213286)

- [Simel DL, Samsa GP, Matchar DB. Likelihood ratios with confidence: sample size estimation for diagnostic test studies. J Clin Epidemiol, 1991.](https://doi.org/10.1016/0895-4356(91)90128-V)

- [Deeks/Altman2004](https://pmc.ncbi.nlm.nih.gov/articles/PMC478236/)

- [Brown/Cai/DasGupta2001](https://repository.upenn.edu/bitstreams/c3690c8b-efaf-485b-a984-39cfc22aae13/download)

## 技術テストの再現

このリポジトリのルートディレクトリでnode test.cjsを実行すると、記録された合成ケースを再実行できます。元の入力、期待結果、許容誤差は保持されています。技術テストは臨床的検証を意味しません。

```sh
node test.cjs
```

tool.jsonには出典、版、確認範囲が記録されています。examples.jsonには合成入力と期待結果が保持され、results.jsonには実際に得られた結果が記録されています。

[記録・参考文献](../tool.json) · [JavaScriptコード](../calculator.js) · [参照ケース](../examples.json) · [results.json](../results.json)

## 確認状況と使用条件

独立した臨床レビューは実施されていません。

このインターフェースは独自に作成した翻訳であり、公式版や認証済みの版ではありません。独立した臨床レビュー、専門家による言語レビュー、評価尺度等の権利許諾の確認は実施されていません。

式または分類の結果です。解釈、対応、適用可能性は専門家による評価と選択した出典に依存します。

## ライセンスと帰属表示

Apache-2.0はELUCENIAのコードにのみ適用されます。評価尺度等、出版物、翻訳、データの権利は、それぞれの権利者に帰属します。LICENSEとNOTICEを保持してください。

ELUCENIA · Felipe Guedes · Copyright © 2026

## 記録された結果

以下の情報は、合成例に対する手法の出力を保持したものです。独立した臨床的検証を示すものではありません。

### 1

感度 89.5%、特異度 62.8%。尤度比は中等度（LR+ は 5〜10、または LR− は 0.1〜0.2）。

| 結果の詳細 | |
| --- | --- |
| 特異度 | 62.8%（95% CI: 52.2%～72.3%） |
| 陽性的適中率 | 87.8%（95% CI: 83.3%～91.2%） |
| 陰性的適中率 | 66.7%（95% CI: 55.9%～76.0%） |
| 陽性尤度比 (RV+) | 2.41（95% CI: 1.82～3.18） |
| 陰性尤度比 (RV−) | 0.17（95% CI: 0.11～0.25） |
| 正確度 | 82.8% |
| サンプル内の有病率 | 75.0% |

予測値は、このサンプルと同じ有病率（75.0%）の場合にのみ有効です。別の有病率では、LR を用いた検査後確率を使用してください。


### 2

感度 80.0%、特異度 90.0%。尤度比は中等度（LR+ は 5〜10、または LR− は 0.1〜0.2）。

| 結果の詳細 | |
| --- | --- |
| 特異度 | 90.0%（95% CI: 59.6%～98.2%） |
| 陽性的適中率 | 88.9%（95% CI: 56.5%～98.0%） |
| 陰性的適中率 | 81.8%（95% CI: 52.3%～94.9%） |
| 陽性尤度比 (RV+) | 8.00（95% CI: 1.21～52.69） |
| 陰性尤度比 (RV−) | 0.22（95% CI: 0.06～0.78） |
| 正確度 | 85.0% |
| サンプル内の有病率 | 50.0% |

予測値は、このサンプルと同じ有病率（50.0%）の場合にのみ有効です。別の有病率では、LR を用いた検査後確率を使用してください。

