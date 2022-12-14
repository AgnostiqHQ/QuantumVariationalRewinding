# Quantum Variational Rewinding for Time Series Anomaly Detection

<div align="center">

<img src="https://raw.githubusercontent.com/AgnostiqHQ/covalent/master/doc/source/_static/covalent_readme_banner.svg" width=150%>

</div>


Author: Jack S. Baker

Email: <research@agnostiq.ai>

This repository contains an explicit code demonstration for the Quantum Variational Rewinding (QVR) algorithm as proposed in the article <https://arxiv.org/abs/2210.16438>.

In this repository, you will find:

1. A Jupyter notebook (`QVR_example.ipynb`) employing QVR to detect anomalous behaviour in cryptocurrency time series data (i.e, a local simulation of the cryptocurrency case in the article) and to detect anomalous behaviour in the synthetic univariate data from the article (i.e. the didactic toy example from the paper)

2. The pre-processed data sets used in the article in `~/data/`

## Install instructions

### 1: Install the Conda environment

To run the Jupyter Notebook, you will need a new `conda` environment with all of the dependices.

First, clone or download this repository to your local machine.

Next, if you don't already have conda, navigate to <https://conda.io/projects/conda/en/latest/user-guide/install/download.html> and install the correct version for your OS for either Miniconda or Anaconda.

In a terminal window, navigate to root directory of this repo (`~QuantumVariationaRewinding`) and issue

```bash
conda env create -f environment.yml
```

This will install the `QVR` environment. Let's activate it

```bash
conda activate QVR
```

### 2: Starting Covalent

After successfully creating the conda environment, the Covalent server can be started as follows

```bash
covalent start
```

If prompted, migrate the databases

```bash
covalent db migrate
```

If you run into problems starting the Covalent server, please try purging Covalent

```bash
covalent purge -Hy
```

this will purge any old files and directories created by Covalent giving you a fresh start. This, however, should be used sparingly as it also purges the Covalent database. Once purged, try `covalent start` once more.

### 3: Launching the notebook

If you are comfortable using the newly installed environment in your own jupyter notebook extension (VSCode etc.), then you are done and can skip this step. If not, follow the below instructions to launch a standard Jupyter Notebook from the command line. 

We first need to make the kernel visible to Jupyter

```bash
python -m ipykernel install --user --name=QVR
```

then launch the notebook

```bash
jupyter notebook
```

which will open a browser window in the Jupyter explorer. Navigate to the `QVR_example.ipynb` and click it.

From the top drop-down menu, select `kernel > change kernel > QVR`. You are now good to go!
