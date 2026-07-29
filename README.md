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
git clone https://github.com/arasparsa/MNE-Python-Crash-Course
cd MNE-Python-Crash-Course

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
cd MNE-Python-Crash-Course
```

Launch JupyterLab to start coding:
```bash
jupyter lab
```

---

## Part 2: Step-by-Step EEG Pipeline

If you want to know how MNE works, check out following 5 steps. I’ll quickly go over everything on notebook `01-Overview.ipynb` to give you a general roadmap, and in the other notebooks, I’ll have a detailed, specialized, and practical article for each of these 5 parts.
### 1. Loading Data & Raw Object
### 2. Filtering and Plotting
### 3. Extracting Events and Segmenting Data (Events & Epochs Object)
### 4. Averaging and Extracting Event-Related Potentials (Evoked Object)
### 5. Source Localization & SourceEstimate

---

## 🛠️ Credits & Disclaimers
* **Educational Workflow:** Methodological structures adapted from the foundational materials of the [MNE](https://mne.tools/stable/index.html).
