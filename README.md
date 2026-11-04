# Data Analysis Workshop

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/bajon1/Data-Analysis-Workshop/blob/main/notebooks/workshop.ipynb)

Click **Open In Colab**, then run the helper-setup cell above the course title. It downloads all files from this repository into your own Colab runtime, including any helper modules. Each participant works independently; no manual copying is needed to get started.

A data-analysis workshop for psychology participants at [Brainhack Kraków 2026](https://brainhackkrakow.org). Participants are expected to understand basic statistical reasoning; prior programming experience is not required.

The workshop uses Google Colab and the public [Big Five Personality Test dataset](https://www.kaggle.com/datasets/tunguz/big-five-personality-test). The notebook downloads the source file during the session, so no dataset is bundled with this repository.

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

The separate data-download cell in the course installs `kagglehub`, downloads `data-final.csv` from Kaggle to the temporary Colab runtime, and reads a bounded workshop subset. Restarting or disconnecting the runtime removes its temporary files, so rerun the helper setup and data-download cells after reconnecting.

Presidio and sentence-transformers are optional demonstrations. If network or installation time is limited, the facilitator can discuss their prepared outputs without running them.

## Facilitator preflight

Before the event, use a new Colab runtime and verify that:

1. the Kaggle download completes without credentials or an unexpected consent step;
2. `data-final.csv` is found and the first 5,000 rows load;
3. the participant notebook runs through the core scoring and analysis sections;
4. the optional Presidio and sentence-transformers cells still install.

## Data protection note

The Kaggle data are used only as public workshop material. Real research data require a separate decision about consent, institutional policy, approved infrastructure, access control, retention, and disclosure risk. Neither pseudonymisation nor automated PII detection automatically makes a dataset safe to send to an external LLM.
