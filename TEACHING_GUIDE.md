# Teaching guide: predict, reveal, explain, challenge

The investigations extend the original Parts 1–5. Students use forms, sliders, and buttons; no code editing is required. You can omit the AI finale without losing the core learning sequence.

## Facilitation

Ask students to work in page order, rather than choosing Run all on their first visit. Have them record a reason before each reveal. Predictions can be revised in the controls, but keep the original six forecasts for the final comparison. The new investigations have no saved answers in the distributed notebook. Baseline analysis figures remain saved examples.

The six-image activity records predictions of the **participant average**, not personal emotional reactions. Different personal reactions are not errors. This distinction also makes student and AI forecasts comparable. Forecasts are not automatically collected; students can download JSON backups or comparison files if you want a submission.

## 1 · Predict before you peek

Students forecast seven average human ratings for six labelled PG-compatible pictures. They must deliberately confirm their seven choices before saving. Initial slider positions are not treated as submitted answers. Forecasts allow decimals because their target is an average.

After all six are saved, reveal the participant means. The six profile charts and per-picture absolute differences make unexpected patterns visible. Ask students to nominate their hardest question and explain one surprise.

**Learning goal:** operational definitions, scale anchors, forecasting, and interpreting agreement with a group mean. These examples are illustrative, not a representative test sample.

Download and restore functions preserve forecasts between runtime sessions. Loading a different dataset resets them, so download before rerunning setup.

## 2 · The average hides the argument

The selected pair is neutral3 (Picture A) and extreme53 (Picture B). In PG, average valence is approximately 5.129 and 5.133. Standard deviations are approximately 0.922 and 2.224 respectively. Both images are present in Full too.

First show the pictures and means. Ask students to predict or sketch the distributions. Then reveal the histograms. A shared vertical scale supports comparison; each panel reports the response count and sample standard deviation.

**Learning goal:** distinguish central tendency from dispersion. A middling mean can conceal disagreement. A broad histogram alone does not identify the cause or establish distinct psychological subgroups.

## 3 · Name a component and challenge the name

This activity sits after the weights and before the full maps. Students inspect two sets of weights, enter their proposed axis names, and predict a displayed example's direction relative to zero. Three examples support repeated predictions. Both axis names are required before a position is revealed.

Students should cite weights and an example that supports their interpretation, then discuss a counterexample. Pictures are unseen in the activity, not held-out observations used for independent statistical validation.

**Learning goal:** distinguish an interpretation from a proven construct and seek evidence that could challenge it. The zero point is a coordinate origin, not a diagnostic threshold. Component signs are arbitrary.

## 4 · Change the stimulus sample

Start with Pleasant and Neutral, then add categories. Disgust and Erotic are only available in Full; unavailable choices produce an explanatory message. Both maps draw the same selected pictures. Their axes use common limits and equal scale. One map retains the original PCA; the other refits PCA to the subset. Each fit centers its own sample, so a difference in position can include a change of origin as well as different weights.

A maximum-similarity assignment matches all seven weight vectors to their original counterparts and aligns signs. The table reports each match's original variance, new variance rank, new variance percentage, and absolute loading similarity. The paired bars show which question weights changed. A similarity below 0.8 triggers a caution to inspect the weights; this is a display heuristic, not a validated significance threshold.

**Learning goal:** analysis depends on the stimulus sample. Students should distinguish drawing fewer points from changing the fitted model, and should not interpret a sign flip or changed component rank as a new construct.

## 5 · Optional AI comparison

The notebook prepares a labelled contact sheet, individually named image files, and an identical prompt for everyone. It exports only image stimuli, without student or participant ratings. Students choose whether to attach them in their own ChatGPT conversation. The instructions follow [official OpenAI image-input guidance](https://learn.chatgpt.com/docs/image-inputs).

The prompt asks for average human ratings, specifies all seven scale anchors, and requests six labelled arrays of numeric values. It asks the model to state limitations instead of fabricating ratings. Students enter the displayed model name and date, paste the response, and compare it with their saved forecasts and participant averages.

Validation rejects missing/duplicate/extra labels, wrong lengths, nonnumeric values, nonfinite values, and ratings outside 1–9. A model refusal or incomplete answer is a limitation to discuss, not a reason to manufacture data. Students can skip the finale.

Plots show rating profiles for each picture. Tables report average absolute differences by question and picture. The comparison can be downloaded with model/date, prompt, picture identities, forecasts, and participant means. It contains the last successful comparison snapshot, rather than silently recomputing it after later edits.

**Learning goal:** evaluate predictions against a reference, inspect specific errors, and limit conclusions. These 42 ratings are nested within six selected images and seven related questions; they are not 42 independent trials. Participant means are not universal emotional truths. Close AI predictions do not demonstrate emotional experience. Published stimuli may have appeared in model training; the prompt cannot guarantee their novelty.

For a consistency extension, students may repeat the same prompt in a fresh chat. Retain the first answer and compare the repeats rather than selecting the best result.

## Remaining classroom check

The new default paths and button callbacks are tested in local Jupyter kernels. The core notebook previously ran successfully in Colab according to the course author. Please check the new slider/button interaction in a fresh Colab session; browser-only execution of the new widgets is not yet verified in this environment.
