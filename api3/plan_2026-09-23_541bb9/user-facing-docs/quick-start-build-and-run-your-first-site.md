# Quick Start: Build and Run Your First Site

This guide walks you through getting started with the **HierSpeech** repository. HierSpeech is a speech synthesis tool — it uses artificial intelligence to turn written text into spoken audio. It runs entirely in **Python**, not as a website builder, so the setup path described here focuses on preparing your computer to use this tool. If you were expecting a static-site workflow with commands like `npm start` or `npm build`, note that those do not apply to this repository.

## Before You Begin

You will need:

- **Python 3.8 to 3.10** installed on your computer (this version range is required by the machine-learning components this project relies on)
- A **terminal** application (Command Prompt on Windows, Terminal on macOS or Linux)
- About **5 GB of free disk space** for the software packages the project downloads during setup
- A stable **internet connection** for downloading required components

## Step 1: Obtain the Repository

Download or clone the HierSpeech project to a folder on your computer. Once you have the folder, open your terminal and navigate into it:

```
cd HierSpeech
```

## Step 2: Set Up a Virtual Environment

A virtual environment keeps this project's packages isolated from the rest of your system, preventing conflicts with other software. In your terminal, run:

**On macOS/Linux:**

```
python3 -m venv venv
source venv/bin/activate
```

**On Windows:**

```
python -m venv venv
venv\Scripts\activate
```

After this step, your terminal prompt usually shows `(venv)` to indicate the environment is active.

## Step 3: Install the Required Packages

The repository includes a file named `requirements.txt` that lists every package and its exact version. Install all of them with one command:

```
pip install -r requirements.txt
```

This process downloads and installs the following key components:

| Package | Version | What It Provides |
|---|---|---|
| torch | 1.13.1 | Core deep-learning engine |
| torchaudio | 0.13.1 | Audio processing for the deep-learning engine |
| transformers | 4.34.0 | Pre-trained AI model support |
| phonemizer | 3.2.1 | Converts written text into speech sounds |
| numpy | 1.26.1 | Numerical data handling |
| scipy | 1.11.3 | Scientific computing support |
| matplotlib | 3.8.1 | Charts and visual outputs |
| tqdm | 4.65.0 | Progress indicators during long-running tasks |
| pesq | 0.0.4 | Audio quality measurement |

The full list also includes supporting packages such as `einops`, `joblib`, `Cython`, `timm`, `Unidecode`, and `AMFM_decompy`, each pinned to a specific version to ensure compatibility.

This step may take several minutes depending on your internet speed.

## Step 4: Verify the Installation

Once installation finishes, check that the core packages imported successfully:

```
python -c "import torch; import torchaudio; print('All packages loaded successfully')"
```

If you see the success message without errors, your environment is ready.

---

## What Happens Next

The setup steps above prepare your computer to run HierSpeech. The actual task of generating speech from text — loading a pretrained model, feeding it a written sentence, and producing an audio file — requires running the project's Python entry scripts.

**Important limitation:** At the time this document was written, only the dependency list (`requirements.txt`) was available for reference. The specific commands to launch a speech generation run, the exact input format, and the output audio settings are not described in the provided source material. To proceed beyond environment setup, consult the repository's README file or main documentation, which typically contains usage examples and example commands.

## Troubleshooting Common Issues

**"Python not found" during Step 2.**  
Ensure Python is installed and added to your system path. You can check by running `python --version` in your terminal.

**"pip not found" errors.**  
Upgrade pip first with: `python -m pip install --upgrade pip`, then retry the installation command.

**A package fails to build or install.**  
Some packages like `Cython` and `phonemizer` need a C compiler on your system. On Windows, install **Microsoft C++ Build Tools**; on macOS, install **Xcode Command Line Tools** with `xcode-select --install`; on Linux, install `build-essential`.

**Out-of-memory or disk-full warnings.**  
Free up disk space before retrying. The `torch` and `transformers` packages are large.

**A specific pinned version is unavailable.**  
Your Python version may be outside the supported range of 3.8–3.10. Switch to a compatible Python version and create a fresh virtual environment.