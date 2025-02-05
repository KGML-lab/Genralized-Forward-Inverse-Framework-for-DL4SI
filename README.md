[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT) ![Python Version](https://img.shields.io/badge/python-3.8-blue) ![PyTorch Version](https://img.shields.io/badge/pytorch-2.0.1-blue)  [![arXiv](https://img.shields.io/badge/arXiv-1234.56789-b31b1b.svg)]([https://arxiv.org/abs/2310.09441](https://arxiv.org/abs/2410.11247)) 

# A Unified Framework for Forward and Inverse Problems in Subsurface Imaging using Latent Space Translations | ICLR 2025


In subsurface imaging, learning the mapping from velocity maps to seismic waveforms (forward problem) and waveforms to velocity (inverse problem) is important for several
applications. While traditional techniques for solving forward and inverse problems are computationally prohibitive, there is a growing interest to leverage recent advances in deep learning to learn the mapping between velocity maps and seismic waveform images directly from data. Despite the variety of architectures explored in previous works, several open questions still remain unanswered such as the effect of latent space sizes, the importance of manifold learning, the complexity of translation models, and the value of jointly solving forward and inverse problems. We propose a unified framework to systematically characterize prior research in this area termed the Generalized Forward-Inverse (GFI) framework, building on the assumption of manifolds and latent space translations. We show that GFI encompasses previous works in deep learsning for subsurface imaging, which can be viewed as specific instantiations of GFI. We also propose two new model architectures within the framework of GFI: Latent UNet and Invertible X-Net, leveraging the power of U-Nets for domain translation and the ability of IU-Nets to simultaneously learn forward and inverse translations, respectively. We show that our proposed models achieve state-of-the-art (SOTA) performance for forward and inverse problems on a wide range of synthetic benchmark datasets, and also investigate their zero-shot effectiveness on two real-world datasets.


**Paper Link: [OpenReview](https://openreview.net/forum?id=yIlyHJdYV3)** 

**Paper Arxiv Link: [https://arxiv.org/abs/2310.09441](https://arxiv.org/abs/2410.11247)** (For updated results and information)

## Table of Contents

- [Installation](#installation)
- [Training Instructions](#training-instructions)
- [Evaluation Instructions](#evaluation-instructions)

## Installation

### Prerequisites

Before you begin, ensure you have the following installed:

- [Anaconda](https://www.anaconda.com/products/distribution) or [Miniconda](https://docs.conda.io/en/latest/miniconda.html)
- Git (if cloning the repository)

### Setting Up the Environment

Follow these steps to set up the Python environment using the provided `.yaml` file:

1. **Clone the repository (if you haven't already):**

    ```bash
    git clone https://github.com/your-username/your-repo-name.git
    cd your-repo-name
    ```

2. **Create the Conda environment:**

    Ensure you are in the directory containing the `environment.yaml` file, then run:

    ```bash
    conda env create -f environment.yaml
    ```

    This command will create a new Conda environment with all the necessary dependencies specified in the `environment.yaml` file.

3. **Activate the environment:**

    After the environment is created, activate it with:

    ```bash
    conda activate your-environment-name
    ```

    Replace `your-environment-name` with the actual name specified in the `environment.yaml` file, or simply use the default name provided by Conda.

4. **Verify the environment setup:**

    To ensure everything is installed correctly, you can list all the installed packages:

    ```bash
    conda list
    ```

## Training Instructions
The training scripts for the project are located in the `src` folder. Depending on your task, you can train the model using either the forward or inverse training scripts. Sample training scripts are located in the `scripts` folder

### Train the Forward Model

To train any of the forward models (baselines and Latent U-Nets), run the following command:

```bash
python src/train_forward.py
```

### Train the Inverse Model

To train any of the inverse models (baselines and Latent U-Nets), run the following command:

```bash
python src/train_inverse.py
```
### Train Invertible X-Net

To train Invertible X-Net for both directions, run the following command:

```bash
python src/train_invertible_x_net.py
```

## Evaluation Instructions

The evaluation scripts for the project are located in the `evaluate` folder. Depending on your task, you can evaluate either the forward or inverse model. Sample training scripts are located in the `scripts` folder

### Evaluate the Forward Model

To evaluate any of the forward models (baselines and Latent U-Nets), run the following command:

```bash
python -u evaluate/evaluate_zero_shot_forward_models.py
```
### Evaluate the Inverse Model

To evaluate any of the inverse models (baselines and Latent U-Nets) and also the Invertible X-Net, run the following command:

```bash
python -u evaluate/evaluate_zero_shot_inverse_models.py
```

