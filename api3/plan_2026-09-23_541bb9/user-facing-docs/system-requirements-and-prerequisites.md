# System Requirements and Prerequisites

This page helps you prepare your computer before you start using HierSpeech. Work through the checks below to confirm your environment is ready.

## Core Software Requirements

HierSpeech requires a working Python environment and a way to install Python packages. The exact package versions listed below must be available in that environment.

| Package | Required Version |
|---|---|
| AMFM_decompy | 1.0.11 |
| Cython | 3.0.3 |
| einops | 0.7.0 |
| joblib | 1.3.2 |
| matplotlib | 3.8.1 |
| numpy | 1.26.1 |
| pesq | 0.0.4 |
| phonemizer | 3.2.1 |
| scipy | 1.11.3 |
| timm | 0.6.13 |
| torch | 1.13.1 |
| torchaudio | 0.13.1 |
| tqdm | 4.65.0 |
| transformers | 4.34.0 |
| Unidecode | 1.3.7 |

## Python Version

The provided installation information does not specify a single required Python version. To avoid compatibility problems, use a Python version that supports every package listed above. Python 3.8, 3.9, or 3.10 are commonly compatible with these package versions.

## Package Manager

You need a Python package installer that can install packages from the Python Package Index. A current version of `pip` is sufficient. If you use a different installer, make sure it can install the packages at the exact versions shown in the table above.

## Git Version Control

If you plan to obtain the project through Git, install any recent Git client. The installation information does not require a specific Git version. You can also download the project directly without Git.

## Supported Operating Systems

The available installation information does not list supported operating systems. Most packages are cross-platform, but some audio and phonemizer components may need additional setup on Windows. Linux and macOS are typically smoother environments for these types of tools.

## Browser Compatibility

HierSpeech is not a web application, so no browser is required to run it. If you are viewing this documentation in a browser, any modern browser is sufficient.

## Verification Checklist

Use this checklist to confirm your environment is ready:

- [ ] A Python environment is installed and can run commands.
- [ ] A package installer such as `pip` is available and up to date.
- [ ] Every package in the table above is installed at exactly the listed version.
- [ ] If you use Git, a Git client is installed and you can connect to the project repository.
- [ ] You know how to activate the Python environment where these packages are installed.

If any package version differs from the table, update that package before continuing.