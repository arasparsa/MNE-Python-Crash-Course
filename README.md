<img width="1408" height="768" alt="mne-python" src="https://github.com/user-attachments/assets/193f7be0-15d9-44e7-85eb-6aa6d0a85886" />


# MNE-Python-Crash-Course [2026]
This repository is a quick, step-by-step tutorial of a complete brain signal processing pipeline, from reading raw data to visualizing cortical activity. It introduces the four main MNE data structures: SourceEstimate, Evoked, Epochs, and Raw, with a practical example (recorded data from a visual-auditory experiment).

This repository acts as a teaching resource and a practical implementation of workflows inspired by [MNE](https://mne.tools/stable/auto_tutorials/index.html) website.

---

## Part 1: Environment Setup & Installation

Follow these steps to set up an isolated, reproducible scientific workspace on your computer.

### Step 1: Install Anaconda 
To manage Python environments and heavy computational libraries safely, we use Anaconda.
* Download and install [Anaconda](https://anaconda.com).
* Follow the default installation prompts for your operating system (Windows, macOS, or Linux). My operating system is Windows.

### Step 2: Create a Dedicated Conda Environment
Never install packages into your base environment. Open your Anaconda Prompt and clone the environment defined in this repository:

```bash
# Clone this repository to your machine
git clone https://github.com/arasparsa/EEG-Analysis-MNE-Python
cd EEG-Analysis-MNE-Python

# Create the environment from the provided configuration file
conda env create -f environment.yml
```

Alternatively, you can create and configure it manually line-by-line:
```bash
conda create -n mne_env python=3.11 -y
conda activate mne_env
conda install -c conda-forge mne jupyterlab matplotlib numpy scipy -y
```

### Step 3: Activate and Verify
Every time you want to work on this project, activate the environment:
```bash
conda activate mne_env
```
```bash
cd project-path
```

Launch JupyterLab to start coding:
```bash
jupyter lab
```

---

## 📊 Part 2: Step-by-Step EEG Pipeline

Our notebooks are built to guide you through processing continuous data using real clinical `.edf` files.

### 1. Data Ingestion & Metadata Exploration
* Loading raw European Data Format (`.edf`) files using `mne.io.read_raw_edf()`.
* Inspecting sampling rates (256 Hz for CHB-MIT), channel names, and hardware limits.

### 2. Signal Artifact Mitigation (Filtering)
* Applying high-pass filters (e.g., 0.5 Hz) to eliminate baseline drift caused by patient movement.
* Applying low-pass filters (e.g., 40 Hz) to eliminate high-frequency muscle noise.
* Implementing Notch Filtering (60 Hz) to clear ambient electrical interference.

### 3. Epoching & Feature Extraction
* Slicing long continuous clinical recordings into fixed-duration intervals (e.g., 4-second blocks).
* Computing Welch's Power Spectral Density (PSD) to quantify shifts in Alpha, Beta, Theta, and Delta band power during seizure windows.

---

## 🛠️ Credits & Disclaimers
* **Clinical Dataset:** Data retrieved from the open-source PhysioNet [CHB-MIT Scalp EEG Database](https://physionet.org).
* **Educational Workflow:** Methodological structures adapted and modernized from the foundational materials of the [Pybrain Workshop](https://github.io).
