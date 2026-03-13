<!---------------------------------------------->

<a name="readme-top"></a>

<!---------------------------------------------->

<h1 align="center">
  <br>
  easilastik
  <br>
</h1>

<h4 align="center">Easy integration of Ilastik segmentation models in Python.</h4>

<!---------------------------------------------->

<p align="center">
  <a href="https://pypi.org/project/easilastik/">
  <img src="https://img.shields.io/pypi/v/easilastik.svg"
    alt="PyPI Version">
  </a>
  <a href="https://github.com/titouanlegourrierec/easilastik/blob/main/LICENSE">
  <img src="https://img.shields.io/badge/License-MIT-green.svg"
    alt="MIT License">
  </a>
  <a href="https://github.com/titouanlegourrierec/easilastik/actions/workflows/ci.yml">
  <img src="https://github.com/titouanlegourrierec/easilastik/actions/workflows/ci.yml/badge.svg"
    alt="CI status">
  </a>
  <a href="https://github.com/astral-sh/ruff">
  <img src="https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/astral-sh/ruff/main/assets/badge/v2.json"
    alt="Code Style: Ruff">
  </a>
  <a href="https://github.com/astral-sh/ty">
  <img src="https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/astral-sh/ty/main/assets/badge/v0.json"
    alt="Type Checking: Ty">
  </a>
</p>

<!---------------------------------------------->

## 🌄 Overview

<p align="center">
  <img src="https://raw.githubusercontent.com/titouanlegourrierec/EasIlastik/main/assets/img.png" width="100%">
</p>

This package provides seamless integration of pre-trained image segmentation models from Ilastik into Python workflows, empowering users with efficient and intuitive image segmentation capabilities for diverse applications.

<!---------------------------------------------->

## 🚀 Getting Started

### Prerequisites

- **Ilastik software**: To train your own model for image segmentation, please download the Ilastik software tailored to your computer's operating system from: https://www.ilastik.org/download.

### Train a model

- To train your own model on Ilastik and properly adjust the different parameters, please refer to [this documentation](https://github.com/titouanlegourrierec/EasIlastik/wiki/Train-a-model-on-Ilastik).

<!---------------------------------------------->

## 📦 Installation

To install `easilastik`, run the following command:

```bash
pip install easilastik
```

<!---------------------------------------------->

## 🛠️ Usage

For usage examples of this package, please refer to the [Example Notebook](https://github.com/titouanlegourrierec/EasIlastik/blob/1be43ebb76bccec6917e05367fbb7e48b184efdc/Examples/example-notebook.ipynb).

### Process a single image

```python
EasIlastik.run_ilastik(input_path = "path/to/your/image.jpg", # The path of the image to process
                       model_path = "path/to/your/model.ilp",
                       result_base_path = "path/to/your/output/folder",
                       export_source = "Simple Segmentation",
                       output_format = "png")
```

<p align="center">
  <img src="https://raw.githubusercontent.com/titouanlegourrierec/EasIlastik/main/assets/run_ilastik_image.png" alt="run_ilastik_image" width="50%">
</p>

### Process a folder of images

```python
EasIlastik.run_ilastik(input_path = "path/to/input/folder", # The path of the folder to process
                       model_path = "path/to/your/model.ilp",
                       result_base_path = "path/to/your/output/folder",
                       export_source = "Simple Segmentation",
                       output_format = "png")
```

<p align="center">
  <img src="https://raw.githubusercontent.com/titouanlegourrierec/EasIlastik/main/assets/run_ilastik_folder.png" alt="run_ilastik_folder" width="70%">
</p>

### Show probabilities

```python
EasIlastik.run_ilastik(input_path = "path/to/input/image",
                       model_path = "path/to/model.ilp",
                       result_base_path = "path/to/output/folder",
                       export_source="Probabilities", # Probabilities
                       output_format="hdf5") # hdf5 format

output_path = "path/to/output/image.h5"
image = EasIlastik.color_treshold_probabilities(output_path, threshold, below_threshold_color, channel_colors)
```

<p align="center">
  <img src="https://raw.githubusercontent.com/titouanlegourrierec/EasIlastik/main/assets/run_ilastik_show_probabilities.png" alt="run_ilastik_probabilities" width="70%">
</p>

### Run with probabilities

```python
EasIlastik.run_ilastik_probabilities(input_path = "path/to/input/folder",
                                     model_path = "path/to/model.ilp",
                                     result_base_path = "path/to/output/folder",
                                     threshold = 70, # threshold for the probabilities
                                     below_threshold_color = [255, 0, 0], # color for the pixels below the threshold (red)
                                     channel_colors = [[63, 63, 63], [127, 127, 127], ...] # colors for the different channels
                                     )
```

<p align="center">
  <img src="https://raw.githubusercontent.com/titouanlegourrierec/EasIlastik/main/assets/run_ilastik_run_probabilities.png" alt="run_ilastik_probabilities" width="70%">
</p>

<!---------------------------------------------->

## ⚖️ License

Elevatr is licensed under the **GNU General Public License v3.0**. This means that you are free to use, modify, and distribute this software, but any derivative works must also be licensed under the same terms. For more details, please refer to the [LICENSE](LICENSE) file.

<!---------------------------------------------->

<p align="right"><a href="#readme-top">back to top</a></p>
<!---------------------------------------------->

______________________________________________________________________

> GitHub [@titouanlegourrierec](https://github.com/titouanlegourrierec)  ·
> Email [titouanlegourrierec@icloud.com](mailto:titouanlegourrierec@icloud.com)
