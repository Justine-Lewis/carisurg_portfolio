# Week 7 Interim Draft Benchmark

This table compares the Week 6 logistic regression baseline with the Week 7 Random Forest complex model using the same train/test split.

| Model                          |   Accuracy |   Precision (macro) |   Recall (macro) |   F1 (macro) |   Recall ESI 1 |   Training Time (s) |   Inference Time (ms/prediction) | Interpretability   |
|:-------------------------------|-----------:|--------------------:|-----------------:|-------------:|---------------:|--------------------:|---------------------------------:|:-------------------|
| Logistic Regression (baseline) |      0.562 |               0.412 |            0.614 |        0.41  |          0.625 |             17.9126 |                         0.003732 | High               |
| Random Forest                  |      0.651 |               0.472 |            0.384 |        0.406 |          0     |             60.8122 |                         0.129206 | Medium             |
