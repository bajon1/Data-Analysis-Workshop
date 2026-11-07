# Data Analysis Workshop

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/bajon1/Data-Analysis-Workshop/blob/3aa4257ba3242bb951c4cf3437a60e5180eabf05/notebooks/workshop.ipynb)

Click **Open in Colab**, read the introduction, and run the first code cell. It downloads all repository files into your Colab environment, including helper modules. Everyone works independently; no manual file copying is needed.

A data analysis workshop for people working in psychology, prepared for [Brainhack Kraków 2026](https://brainhackkrakow.org). Basic statistical reasoning is assumed. No previous programming experience is required.

The course uses Google Colab and the public [OSMI Mental Health in Tech Survey](https://www.kaggle.com/datasets/osmi/mental-health-in-tech-survey). The notebook downloads `survey.csv` from Kaggle during the workshop; the repository does not include the dataset. The authors describe it as a 2014 survey and publish it under CC BY-SA 4.0.

Exercises cover six workplace questions: `remote_work`, `self_employed`, `benefits`, `care_options`, `wellness_program`, and `seek_help`. Gender, demographics, family history, treatment history, and free-text comments are excluded from the exercise table. The full dictionary describes all source columns.

The course starts with **Part 0: Setup**. **Part 1** explains short commands, selecting columns by name or position, and filtering rows. **Part 2** covers missing values and response counts. **Part 3** covers bar charts, percentages, group comparisons, and a short gallery of charts to modify. **Part 4** demonstrates masking fictional text using regex and recognizing people and places from context. **Part 5** compares the meanings of words, then compares fictional comments with one positive and one negative example, without manually listing keywords.

There are **8 exercises**, numbered 1 to 8. Each has instructions, a hint, an example, and a code cell. Tasks after Part 1 and at the end of Part 2 combine the operations introduced earlier. Expand the full column dictionary when needed. The participant notebook leaves tasks for you to complete; a separate notebook provides answers and helps you catch up if you miss a section.

## Requirements

- A laptop;
- a stable internet connection;
- a Google account;
- a modern web browser.

You do not need to install Python on your computer.

## Materials

- [Participant notebook — exercises to complete](notebooks/workshop.ipynb)
- [Answer notebook — complete solutions](notebooks/workshop_solutions.ipynb) · [open answers in Colab](https://colab.research.google.com/github/bajon1/Data-Analysis-Workshop/blob/3aa4257ba3242bb951c4cf3437a60e5180eabf05/notebooks/workshop_solutions.ipynb)

Both versions are maintained together: changes to the course, descriptions, or exercises also go into the answer notebook.

Materials can also be shared through the [workshop materials folder](https://drive.google.com/drive/folders/1ijaY-LXx4DGp8ZrUz9KOmUY6Drk4mSBJ?usp=sharing).

## Running in Google Colab

1. Click **Open in Colab** at the top of this README.
2. Sign in to your own Google account if needed.
3. Read the introduction and run the first code cell to download the repository. Then run cells in order using the button next to each cell or `Shift+Enter`.

The setup cell downloads the files needed for the workshop. This also lets us use helper code, such as `nbutils.py`, through `import nbutils`. Files come from the `main` branch on GitHub. Running the cell again preserves files already present in the session.

To keep your changes after the session, select **File → Save a copy in Drive**. Opening a notebook from GitHub does not automatically save a copy to your Drive.

A separate cell in Part 0 installs `kagglehub`, downloads `survey.csv` from Kaggle, and reads it into a pandas table. The source column dictionary appears directly below it. The next code cell selects only the six exercise columns before displaying any rows. Restarting or disconnecting the runtime removes temporary files, so rerun module setup and data download after reconnecting.

The person and place recognition example in Part 4 downloads an English spaCy model. If installation or downloading is unavailable, the instructor can discuss the example sentence and replacement procedure without running the demonstration.

Part 5 installs `sentence-transformers` and downloads a multilingual model. The first run may take longer. Greater similarity to an example is neither a confidence percentage nor a guarantee of a correct comment assessment. The demonstration uses only fictional statements; there are still 8 exercises.

## Checks before the workshop

Before the event, start a fresh Colab runtime and check that:

1. The Kaggle download finishes without requesting credentials or unexpected additional consent.
2. `survey.csv` loads and contains the six exercise columns.
3. Parts 0–3 work: selection, missing values, counts, percentages, and group charts.
4. The spaCy model in Part 4 installs and recognizes a person and city in the fictional sentence.
5. The two consecutive cells in Part 5 show word similarity and comparisons of fictional comments with two reference examples.
6. The answer notebook runs from the beginning, and the participant version contains examples and space for your own solutions.

## Data protection and limits of interpretation

The Kaggle data serves only as public workshop material. Respondents volunteered to take part: charts describe their answers and do not establish population prevalence, diagnoses, or causal effects. The source dictionary's `treatment` column indicates reported treatment seeking, not a diagnosis; it is not used in the exercises.

Working with real research data requires separate decisions about consent, institutional rules, approved infrastructure, access permissions, retention, and disclosure risk. Neither pseudonymization nor automatic detection of identifying information automatically makes a dataset safe to send to an external LLM. Text examples are fictional and never use respondents' comments.
