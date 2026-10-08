# Conversion validation

Both dataset variants completed all nine code cells in fresh local Jupyter kernels. No cell errors occurred. Seven figures were produced per run. The delivered notebook includes the saved PG outputs; its online download links point to the versioned GitHub release.

| Check | PG | Full |
|---|---:|---:|
| Participant rows | 399 | 399 |
| Images | 375 | 525 |
| Questions | 7 | 7 |
| Valence–happiness correlation | 0.82063603 | 0.83560685 |
| Handout value to four decimals | 0.8206: matches | 0.8356: matches |
| PC1 variance explained | 74.7884% | 76.2509% |
| First three PCs combined | 94.4861% | 92.3521% |

## Passed checks

- Every rating matches its source MAT file exactly, including missing values.
- Every converted image matches the source pixel array exactly. PNG encoding is lossless.
- Image names, question names, and their order are unchanged.
- PG image names contain no disgust or erotic categories.
- The correlation matrix is finite, symmetric, and has a unit diagonal.
- PCA weights are orthonormal; scores reconstruct all centered image means; their covariance is diagonal and matches component variances.
- PCA variance percentages independently agree with eigendecomposition of the covariance matrix.
- Valence–happiness correlations independently agree with SciPy's Pearson calculation and the original handouts.
- A simulated HTTPS download populated a clean folder and loaded the dataset successfully. A login-page response was rejected by checksum validation.
- Invalid image indices were rejected with descriptive errors.
- The notebook file passed notebook-format validation.

The default PG image inspection, correlation heatmap, scatterplot, PCA variance plot, weights, labelled space, and image space were inspected visually. Label and thumbnail overlap occurs in crowded regions, as in the original tutorial; adjustable stride and image zoom allow students to reduce crowding.

## Deliberate changes from MATLAB

- PG, image 1, and component 1 are the starting defaults, consistent with the handouts' initial examples.
- The PCA variance plot displays actual percentages.
- Histograms use a natural vertical range rather than clipping counts at 30.
- Each figure remains inline, rather than closing earlier figures.
- Thumbnail images are displayed in their original orientation and retain their aspect ratio.
- A correlation heatmap complements the original numeric matrix.
- Teaching text distinguishes individual-response correlations from PCA on image means, and explains PCA sign ambiguity and limits of interpretation.
- The unfinished VR export and unused slim-label helper were not included in the student workflow.

The notebook uses centered, unstandardized PCA, matching the main MATLAB helper. Missing responses are ignored per question for image means and pairwise for correlations. Component signs follow a largest-absolute-weight-positive convention; mathematical equivalence should be judged allowing a sign flip.

## Remaining verification

An actual Colab session has not yet been tested. The versioned download links are configured; a fresh-kernel download test follows publication. MATLAB startup was blocked, so this is not a direct comparison with a successful MATLAB run. Source preservation, published handout values, and independent numerical calculations provide the current validation evidence.

The local kernel emitted sandbox-related cleanup warnings after executing cells. These did not cause cell errors or affect returned results.
