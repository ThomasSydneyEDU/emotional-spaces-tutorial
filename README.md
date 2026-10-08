# Emotional spaces tutorial

An interactive psychology tutorial exploring emotional ratings of IAPS images through correlations, principal component analysis, and representational spaces.

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ThomasSydneyEDU/emotional-spaces-tutorial/blob/main/EmotionalSpaces_Colab.ipynb)

## Start the tutorial

1. Click **Open in Colab** above and sign in to your Google account if prompted.
2. Save a personal copy using **File → Save a copy in Drive** if you want to retain your changes and results.
3. Connect to a runtime. Use the default CPU runtime; a GPU is unnecessary.
4. Leave **PG** selected in the first code cell and run the cells in order with the play buttons.
5. Change an image, question, or component control and rerun that activity to explore another example.

**No programming is required.** Calculations open with code hidden, leaving the play buttons, controls, and figures visible. Questions use named dropdowns, components use bounded dropdowns, and picture size uses a slider. Choose **Show code** if you want to inspect the calculations.

Work through the activities in order. Each section gives a task, an exploration, and discussion prompts. The figures shown before you run an activity are saved PG examples. The final numerical check is optional.

The setup cell automatically downloads the selected dataset. No MATLAB installation or manual file uploads are needed. If you change datasets, run the setup cell and all following cells again. After a runtime reset, rerun setup to restore the data.

## Content choice

PG excludes the disgust and erotic categories and is the default. It still contains fear and sadness imagery. The Full dataset includes potentially disturbing imagery and erotica. Select the dataset that you are comfortable using.

## What you will explore

- Individual image ratings and response distributions.
- Correlations among seven emotion questions.
- Scatterplots of mean ratings per image.
- PCA weights and variance explained.
- Representational spaces with text labels and image thumbnails.

The notebook brings explanations, questions, executable code, and figures together. It preserves the original tutorial's Parts 1–5 and uses image numbers beginning at 1.

## Data

The ratings are from the course author's laboratory. Stimulus images are from the International Affective Picture System (IAPS), as identified by the course author. These descriptions identify provenance; this repository does not add a new license for the stimulus images.

[PG dataset](https://github.com/ThomasSydneyEDU/emotional-spaces-tutorial/releases/download/v1.0.0/emotionalspaces_pg.zip) · [Full dataset](https://github.com/ThomasSydneyEDU/emotional-spaces-tutorial/releases/download/v1.0.0/emotionalspaces_full.zip)

| Dataset | Participant rows | Images | Questions | Download |
|---|---:|---:|---:|---:|
| PG | 399 | 375 | 7 | 44.5 MB |
| Full | 399 | 525 | 7 | 63.3 MB |

Each archive contains ratings, image/question metadata, and lossless PNG images. Missing responses are retained. The setup verifies the archive's SHA-256 checksum. Checksums are recorded in [data_manifest.json](data_manifest.json).

## Methods and validation

Individual-response correlations use pairwise complete observations. PCA uses centered, unstandardized image means. Component signs can flip without changing the solution. See [VALIDATION.md](VALIDATION.md) for numerical checks and remaining verification.

The notebook includes saved PG output so it can be reviewed before execution. Only the notebook and documentation are stored in the Git history; data archives are release assets.

## Troubleshooting

- **Download error:** check your internet connection and rerun setup. If it persists, verify the release download is accessible from your network.
- **Checksum mismatch:** remove the selected dataset ZIP from Colab's Files sidebar and rerun setup.
- **NameError:** run earlier cells first, starting with setup.
- **Image/component out of range:** use the ranges printed by setup; questions and components are numbered 1–7.
- **Disconnected runtime:** reconnect and rerun cells. Save a notebook copy to retain your notes and outputs.

## Credits

Original MATLAB tutorial by the course author. Thanks to Brianna Kennedy, Tijl Grootswagers, and Dr Steven Most for contributions to the original project. This notebook translates that workflow to Python for online teaching.
