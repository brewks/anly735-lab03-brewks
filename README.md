# ANLY 735 — Replication Laboratory #3

## Study
Partial replication of Koh et al. (2021),
"WILDS: A Benchmark of in-the-Wild Distribution Shifts."

## Objective
Investigate whether a tumor-classification model trained
on pathology images from certain hospitals maintains
its performance on images from unseen hospitals.

## Dataset
Camelyon17-WILDS: 3,500 balanced image patches.

- Training: 2,000 patches (hospitals 0, 3, 4)
- ID validation: 500 patches (hospitals 0, 3, 4)
- OOD validation: 500 patches (hospital 1)
- OOD test: 500 patches (hospital 2)

## Model
- ImageNet-pretrained ResNet18
- Frozen feature extractor and trainable classification head
- Adam optimizer, learning rate 0.001
- Five training epochs
- Random seed: 735

## Results

| Metric | ID validation | OOD validation | OOD test |
|---|---:|---:|---:|
| Accuracy | 89.6% | 78.6% | 86.8% |
| Sensitivity | 86.8% | 64.8% | 86.4% |
| Specificity | 92.4% | 92.4% | 87.2% |
| False negatives | 33 | 88 | 34 |

## Reproduction
1. Open the corrected `.ipynb` notebook in Google Colab.
2. Use a GPU runtime if available.
3. Run the notebook cells sequentially.
4. The notebook documents dataset loading, preprocessing,
   model training, and evaluation.
5. Review the Quarto source and Word report for the analysis.

Note: Reproducing the experiment requires executing the
notebook and may produce slightly different results.

## Limitations
- Reduced sample rather than the full WILDS benchmark.
- Thirty unique slide identifiers overlap between
  training and ID validation.
- Results are not directly comparable with the original
  benchmark due to methodological differences.

## Replication Verdict
Partially Reproduced.

## Files
- Corrected `.ipynb`: executable experiment
- `replication-lab.qmd`: report source
- `.docx`: final report
- `.bib`: references
- `.png`: experimental figures

## Reference
Koh et al. (2021). WILDS: A Benchmark of
in-the-Wild Distribution Shifts.
https://proceedings.mlr.press/v139/koh21a.html
