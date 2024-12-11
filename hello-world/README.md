# Hello World (Introductory) TinyML Project

## Purpose
The goal of this project is to get familiar with the workflow associated with developing machine learning models and then deploying them onto edge devices (in this case, an Arduino).

As a toy problem, the project will learn a functional approximation of the sine function. That is, the learnign algorithm will be given a dataset of x values, and y values that are computed as the sines of the x values plus some noise. The learning algorithm will then be deployed on an edge device, which will perform inference with the model on-edge.

## Materials/Toolchain
- Arduino Nano BLE Sense
- Google Colab
- PyTorch
- PyTorch Mobile/ExecuTorch/ONNX Runtime

## Procedure (High-Level)
This section details an overview of the project procedure. Steps that require further explanation are given their own sections.
1. Generate dataset
2. Allocate data appropriately for train/validate/test
3. Choosing a model (admittedly arbitrary) to approximate the sine function
4. Train + evaluate model
5. Write code for on-device inference
6. Build code into binary
7. Deploy code onto microcontroller

## Data Generation + Allocation
The code for these steps can be found in the project repo at datagen.ipynb.

We generate 10,000 x-coordinates for our dataset. We generate our x values uniformly at random on [0, 2pi].

We generate our y values as y_i = sin(x_i) + e_i, where e_i ~ N(0, 0.1^2). This yields us the full dataset.

For allocation, we assume that there is sufficient data to partition into train/validation/test sets (cross-validation, bootstrapping, information criteria are unnecessary). We split our data into 60% train, 20% validation, 20% test.

The partitioned datasets are exported as 3 csv files, found at data/train.csv, data/validation.csv, and data/test.csv.

