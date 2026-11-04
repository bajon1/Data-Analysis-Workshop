# Data Analysis Workshop

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/bajon1/Data-Analysis-Workshop/blob/main/notebooks/workshop.ipynb)

Click **Open In Colab**, then run the helper-setup cell above the course title. It downloads all files from this repository into your own Colab runtime, including any helper modules. Each participant works independently; no manual copying is needed to get started.

A data-analysis workshop for psychology participants at [Brainhack Kraków 2026](https://brainhackkrakow.org). Participants are expected to understand basic statistical reasoning; prior programming experience is not required.

The workshop uses Google Colab and OSMI's public [Mental Health in Tech Survey](https://www.kaggle.com/datasets/osmi/mental-health-in-tech-survey). The notebook downloads `survey.csv` from Kaggle during the session; no dataset is bundled with this repository. The publisher describes it as the 2014 survey and lists the data under CC BY-SA 4.0.

Exercises focus on six workplace questions: `remote_work`, `self_employed`, `benefits`, `care_options`, `wellness_program`, and `seek_help`. Gender, demographic identifiers, family history, treatment history, and free-text comments are excluded from the exercise table. A complete dictionary documents all original columns.

The course starts with **Part 0: setup**, then introduces functions, methods, attributes, and indexing in **Part 1**, before cleaning in **Part 2** and descriptive plots in **Part 3**. Each practical exercise adapts a worked example, includes a specific hint, and has a folded self-check. Later parts cover possible data leakage when predicting treatment, LLM coding assistance, and synthetic-text masking and NLP examples.

## Requirements

- a laptop;
- a stable internet connection;
- a Google account;
- a modern web browser.

No local Python installation is needed.

## Materials

- [Participant notebook](notebooks/workshop.ipynb)

The same materials can be distributed through the shared [Workshop Materials folder](https://drive.google.com/drive/folders/1ijaY-LXx4DGp8ZrUz9KOmUY6Drk4mSBJ?usp=sharing).

## Start in Google Colab

1. Click **Open In Colab** at the top of this README.
2. Sign in to your own Google account if prompted.
3. Run the helper-setup cell above the course title to download the repository. Then follow the course from the title onward, running cells in order with the button beside a cell or with `Shift+Enter`.

The setup cell makes the repository root the working directory and adds it to Python's import path. Helper code added as `nbutils.py` or a `nbutils/` package at the repository root will be available with `import nbutils`. The repository files are downloaded from the `main` branch on GitHub; rerunning setup keeps the existing files in the current runtime.

To keep your edits after the session, optionally select **File > Save a copy in Drive**. Opening the notebook from GitHub does not automatically save a copy to your Drive.

The separate data-download cell in Part 0 installs `kagglehub`, downloads `survey.csv` from Kaggle, and reads it into a pandas DataFrame. The next cell selects only the six exercise columns before displaying any rows. Restarting or disconnecting the runtime removes its temporary files, so rerun the helper setup and data-download cells after reconnecting.

Presidio and sentence-transformers are optional demonstrations. If downloads or installation are unavailable, the facilitator can discuss the synthetic examples without running these cells.

## Facilitator preflight

Before the event, use a new Colab runtime and verify that:

1. the Kaggle download completes without credentials or an unexpected consent step;
2. `survey.csv` loads and the six exercise columns are present;
3. Parts 0–3 run through selection, missing-answer handling, counts, percentages, and group charts;
4. the optional Presidio and sentence-transformers cells still install.

## Data protection note

The Kaggle data are used only as public workshop material. The survey is self-selected: the charts describe its responses and do not establish population prevalence, diagnoses, or causal effects. `treatment` means reported treatment-seeking, not a diagnosis. Workplace-support answers may be shaped by prior treatment experiences, so a treatment-prediction task requires an explicit information timeline and a leakage audit.

Real research data require a separate decision about consent, institutional policy, approved infrastructure, access control, retention, and disclosure risk. Neither pseudonymisation nor automated PII detection automatically makes a dataset safe to send to an external LLM. The text demonstrations use invented examples and never the survey's comments.
