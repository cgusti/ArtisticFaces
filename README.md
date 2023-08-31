# ArtisticFaces

## Overview

This repo contains code for a machine learning based platform for transfering historical art styles like impressionism and realism into a user's uploaded/captured images in real-time using two different appraaches:

- Training and fine-tuning a Cyclical Generative Adversarial Network (CycleGAN) on ImageNet and Wikiart dataset
- Utilizing layers in VGG - 16 to capture style loss and information for style transference

## Project Structure

- src: contains run.py file to launch gradio interface and interact with our application
- scripts: contains CycleGAN and VGG-16 related code and dependencies
- notebooks: contains .ipnyb notebooks for debugging and demo purposes
- training: training script for CycleGAN
- data: contains compressed files to image data used to train

## Getting Started

To get a local copy up and running, please follow these simple steps.

### Prerequisites

Here is what you need to run ArtisiticFaces.

- Python3
- pip
- Miniconda\* (optional to use GPU on Windows machine)

### Setup Repository

1. git clone this repo

```
git clone https://github.com/nmorgan8/ArtisticFaces.git
```

2. cd into directory

```
cd ArtisticFaces
```

### Setup Python Modules

1. Install project requirements and set module dependencies

```
pip install -r requirements.txt
```

2. Install tensorflow_examples

```
git clone https://github.com/tensorflow/examples.git
```

3. Set module dependencies

```
python3 setup.py install
```

### Extract Model Checkpoints

- Untar PROD.tar.gz to retrieve trained models

```
tar -xvzf checkpoints/PROD.tar.gz -C checkpoints/
```

- Unzip PROD.zip to retrieve trained models

```
unzip checkpoints/PROD.zip
```

- Use softwares (7zip, Archive Utilities, etc.) to extract PROD directory containing the trained models

```
ArtisticFaces/checkpoints/
```

### Launch Gradio

1. Navigate to ArtisticFaces home directory

2. Run src/run.py file to start gradio server

```
python3 src/run.py
```

## Optional Environment Setup

Optional instuctions to setup GPU if on Windows Machine (tensorflow does not allow MAC GPU use) and create a python virtual environment

### Windows GPU Setup

Use the following instructions to setup Windows Machine to run Tensorflow on local GPU

1. Install and update [Nvidia GPU Drivers](https://www.nvidia.com/download/index.aspx?lang=en-us)

2. Install [Miniconda](https://docs.conda.io/en/latest/miniconda.html)

3. Create conda environment

```
conda create --name tf python=3.10
```

    * Activate conda evironment

    ```
    conda activate tf
    ```

    * Deactivate conda environment

    ```
    conda deactivate
    ```

### Create python virtual environment

Use the following instructions to create a python virutal environment to ensure no dependency issues with python modules.

If using virtual environment, must create env **BEFORE** installing python modules

1. Navigate to ArtisticFaces directory

2. Create Virtual Environment

```
python3 -m venv <name_of_virtual_env>
```

## Common Errors

1. ValueError: Trying to load a model of incompatible/unknown type. <file_name>

   - Delete cached model files to allow it to re-download

```
rm -r <file_name>
```

2. Navigate to ArtisticFaces home directory

3. Re-launch gradio server

## Team Members

- Nick Morgan
- Claudia Gusti

## Technologies

- CycleGANs, VGG-Net
- Tensorflow, Keras, matplotlib, Gradio
