# Hierarchical Multimodality Graph Reasoning for Remote Sensing Visual Question Answering[![Paper](https://img.shields.io/badge/Paper-IEEE-green)](https://ieeexplore.ieee.org/abstract/document/10771709)
## Introduction
This is the code repository for the paper -- Hierarchical Multimodality Graph Reasoning for Remote Sensing Visual Question Answering (TGRS). In this repository, we will provide the core code of our designed model, including data processing, data augmentation, data loading, key module and training script. If this code repository has inspired your study, research or work, please contribute your valuable STAR and cite the original paper.

![Overview of HMGR.](./images/fig1.png )
**Figure 1:** Overview of HMGR.

## Citation
```bibtex
@article{zhang2024hierarchical,
  title={Hierarchical Multi-Modality Graph Reasoning for Remote Sensing Visual Question Answering},
  author={Zhang, Han and Wang, Keming and Zhang, Laixian and Wang, Bingshu and Li, Xuelong},
  journal={IEEE Transactions on Geoscience and Remote Sensing},
  year={2024},
  publisher={IEEE}
}
```

## Install
If you are not using Linux, do not proceed. It is recommended to use four RTX3090 GPUs or higher-computing GPUs to train the model and store the training and test data on at least 50GB SSD. Note that the CUDA version in our runtime environment is 11.8. If it does not match your system environment, please refer to the [Pytorch documentation](https://pytorch.org/get-started/previous-versions/) and select the appropriate version.

1. Clone this repository and navigate to TGRS folder.
```bash
git clone https://github.com/Komi-Wang/TGRS.git
cd TGRS
```

2. Install Package
```bash
conda create -n rsvqa python=3.10
conda activate rsvqa
conda env create -f environment.yml
```

## Data preparation
In this paper, we use three mainstream datasets in the field of remote sensing visual question answering (RSVQA). They are, respectively, the [high-resolution](https://zenodo.org/records/6344367) dataset and the [low-resolution](https://zenodo.org/records/6344334) dataset. Among them, the high resolution dataset can be divided into two versions -- v1 and v2. Before the training starts, you need to download the required data to the specified directory and extract the zip files.

## Training

## Evaluation
Since the evaluation code is similar to the training code, only the gradient computation and propagation parts of the code need to be commented out. We do not provide the evaluation code and checkpoint files additionally. It is worth noting that we recommend evaluating the models while training, which helps to filter out the best performing models and prevent overfitting.

### Quantitative Experiment
We obtained SOTA results by evaluating performance on three data, RSVQA-LR/HR1/HR2, and comparing them with competitive models from the last three years.

![Comparison Experiment on RSVQA-LR.](./images/fig2.png )
**Table 1:** Comparison Experiment on RSVQA-LR.

![Comparison Experiment on RSVQA-HR1.](./images/fig3.png )
**Table 2:** Comparison Experiment on RSVQA-HR1.

![Comparison Experiment on RSVQA-HR2.](./images/fig4.png )
**Table 2:** Comparison Experiment on RSVQA-HR2.

### Qualitative Experiment
We visualize qualitative samples on the three datasets (LR, HR1, and HR2 datasets) by rows, respectively. The first column consists of images, questions (Q), GT, and predicted answers (A). The second to fourth columns represent attention distributions at different SHs. Note that the visual attention scores increase sequentially from purple to red and the attention scores rise in sequence from gray to black.

![Visualization of results.](./images/fig5.png )
**Figure 2:** Visualization of results.


