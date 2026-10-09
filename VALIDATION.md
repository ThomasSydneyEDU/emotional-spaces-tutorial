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

The published notebook opened successfully in Colab, with dataset and parameter controls visible. Both real GitHub release downloads were then tested in clean local Jupyter sessions, with no dataset files present initially. All notebook cells passed on both downloaded datasets, including archive checksum validation. This local download test used macOS trusted certificates because the bundled Python certificate store did not recognize the local network issuer; certificate verification stayed enabled.

The course author subsequently tested the first published notebook in Colab and reported that it ran successfully. The revised student-facing edition is checked locally again; its Colab presentation is verified separately. MATLAB startup was blocked, so this is not a direct comparison with a successful MATLAB run. Source preservation, published handout values, and independent numerical calculations provide the current validation evidence.

The local kernel emitted sandbox-related cleanup warnings after executing cells. These did not cause cell errors or affect returned results.

## Student-facing revision

- All calculation cells use Colab form view and open with their code hidden.
- Question controls use emotion names; component controls allow only values 1–7.
- Sampling choices use readable labels and thumbnail size uses a bounded slider.
- Instructions explain play buttons, saved examples, changing choices, and restarting a session.
- Sections give concrete actions and discussion questions. Technical output is reduced while analytical methods stay the same.
- The original uncertainty around PCA interpretation, arbitrary component signs, missing responses, and averaging is retained in accessible wording.

The revised notebook completed all cells on PG and Full in local Jupyter kernels. An additional PG run tested alternate questions (Arousal/Fear), components (2/3), and the every-sixth-picture display. All consistency checks passed.

Colab presentation was verified on the published revision: all nine code cells displayed Show code controls rather than their source, named question dropdowns and bounded component dropdowns were visible, and picture size rendered as a slider.


## Investigation extensions

Default runs completed on PG and Full. A separate interaction run exercised saving forecasts, refusing unconfirmed defaults, switching pictures, restoring backups, histogram reveals, named-axis position reveals, AI input parsing, comparisons, and downloads (with download opening replaced by a local no-op in tests). Only synthetic AI values were used; no model was queried or image sent to an AI service.

Checks covered six stable picture identities in both datasets, the similar-mean contrasting-spread pair, subset PCA orthonormality and reconstruction, exact recovery of the original fit when selecting all pictures, and exact component matching after a known permutation and sign reversal. AI validation accepted valid decimal ratings and JSON fences and rejected missing/duplicate labels, out-of-range ratings, booleans, numeric strings, and nonfinite values. Exported participant means and predictions matched the completed comparison.

Public notebook outputs retain only original PG analysis examples. No synthetic forecasts, AI comparison values, widget-state predictions, histogram-reveal answers, or component-challenge answers are saved in the published artifact.

Browser-only execution of the new interactive widgets remains a classroom check. Core ipywidgets are supported by Colab; local callback tests verify the implemented logic but do not substitute for a new Colab runtime test.

## Single-picture component prediction activity

Locally executed with PG and Full: all three pictures for components 1–3, blank-input guard, and actual reveal-button callbacks. Each reveal contains predicted and actual positions on one axis; the actual position matches the fitted PCA score. Slider bounds cover the dataset's component scores. Published activity outputs remain empty.
