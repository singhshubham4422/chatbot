# Neural Chatbot with Intel Extension for Transformers

This repository contains a neural chatbot implementation using Intel's extension for transformers. The setup instructions provided will guide you through creating a Python environment, installing necessary dependencies, and running a sample chatbot.

## Table of Contents
- [Prerequisites](#prerequisites)
- [Environment Setup](#environment-setup)
- [Installation](#installation)
- [Running the Chatbot](#running-the-chatbot)
- [Usage Example](#usage-example)
- [Acknowledgements](#acknowledgements)

## Prerequisites

Before you begin, ensure you have the following installed on your system:
- [Anaconda](https://www.anaconda.com/products/distribution) or [Miniconda](https://docs.conda.io/en/latest/miniconda.html)
- [Git](https://git-scm.com/)

## Environment Setup

1. **Create a Conda Environment:**

    Open a terminal or command prompt and run the following commands to create and activate a new conda environment named `itrex` with Python 3.10:

    ```sh
    conda create -n itrex python=3.10 -y
    conda activate itrex
    ```

    - `conda create -n itrex python=3.10 -y`: This command creates a new conda environment named `itrex` with Python version 3.10. The `-y` flag automatically confirms the creation without prompting the user.
    - `conda activate itrex`: This command activates the newly created `itrex` environment.

2. **Install Dependencies:**

    Install the Intel extension for transformers and other required packages:

    ```sh
    pip install intel-extension-for-transformers
    ```

    - `pip install intel-extension-for-transformers`: This command installs the Intel extension for transformers package, which provides performance enhancements for transformer models on Intel hardware.

3. **Clone the Repository:**

    Clone the Intel extension for transformers repository:

    ```sh
    git clone https://github.com/intel/intel-extension-for-transformers.git
    ```

    - `git clone https://github.com/intel/intel-extension-for-transformers.git`: This command clones the Intel extension for transformers repository from GitHub to your local machine.

4. **Navigate to the Neural Chat Directory:**

    Change to the neural chat directory and install additional dependencies:

    ```sh
    cd ./intel-extension-for-transformers/intel_extension_for_transformers/neural_chat/
    pip install -r requirements_cpu.txt
    pip install -r requirements.txt
    ```

    - `cd ./intel-extension-for-transformers/intel_extension_for_transformers/neural_chat/`: This command navigates to the neural chat directory within the cloned repository.
    - `pip install -r requirements_cpu.txt`: This command installs the CPU-specific dependencies listed in the `requirements_cpu.txt` file.
    - `pip install -r requirements.txt`: This command installs the additional dependencies listed in the `requirements.txt` file.

5. **Hugging Face CLI Login:**

    Log in to Hugging Face CLI to access models:

    ```sh
    huggingface-cli login
    ```

    - `huggingface-cli login`: This command logs you into Hugging Face's command-line interface, allowing access to various models and datasets hosted on Hugging Face's platform.

6. **Install Jupyter and IPython Kernel:**

    Install Jupyter and add the IPython kernel for the neural chat environment:

    ```sh
    pip install jupyter ipykernel
    python3 -m ipykernel install --name neural-chat --user
    ```

    - `pip install jupyter ipykernel`: This command installs Jupyter Notebook and IPython kernel, which are necessary for running notebooks.
    - `python3 -m ipykernel install --name neural-chat --user`: This command adds the `neural-chat` kernel to Jupyter, allowing you to select it as an environment in Jupyter notebooks.

## Installation

To ensure all dependencies are correctly installed, repeat the installation steps as follows:

```sh
pip install intel-extension-for-transformers
git clone https://github.com/intel/intel-extension-for-transformers.git
cd ./intel-extension-for-transformers/intel_extension_for_transformers/neural_chat/
pip install -r requirements_cpu.txt
cd ../../../
```
# Running the Chatbot

## Import Required Libraries:

Start by importing the necessary modules from the Intel extension for transformers:
```python
from intel_extension_for_transformers.neural_chat import build_chatbot, PipelineConfig
from intel_extension_for_transformers.transformers import MixedPrecisionConfig
```
`from intel_extension_for_transformers.neural_chat import build_chatbot, PipelineConfig`: Imports the `build_chatbot` function and `PipelineConfig` class for configuring and building the chatbot.

`from intel_extension_for_transformers.transformers import MixedPrecisionConfig`: Imports the `MixedPrecisionConfig` class for configuring mixed precision optimization.

## Configure and Build the Chatbot:

Create a configuration for the chatbot and build it:
```python
config = PipelineConfig(optimization_config=MixedPrecisionConfig())
chatbot = build_chatbot(config)
```
## Make Predictions:

Use the chatbot to make predictions:
```python
response = chatbot.predict(query="Tell me about Intel Xeon Scalable Processors.")
print(response)
```
## Usage Example:
```python
from intel_extension_for_transformers.neural_chat import build_chatbot, PipelineConfig
from intel_extension_for_transformers.transformers import MixedPrecisionConfig

config = PipelineConfig(optimization_config=MixedPrecisionConfig())
chatbot = build_chatbot(config)
response = chatbot.predict(query="What is intel arc")
print(response)
```


## Acknowledgements
---------------
This project uses the [Intel Extension for Transformers](https://github.com/intel-analytics/Extension-for-Transformers), a library that enhances the performance of transformer models on Intel hardware.

- [Intel Extension for Transformers GitHub](https://github.com/intel-analytics/Extension-for-Transformers)
- [Hugging Face](https://huggingface.co)

