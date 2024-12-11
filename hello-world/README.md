# Hello World (Introductory) TinyML Project

## Purpose
The goal of this project is to get familiar with the workflow associated with developing machine learning models and then deploying them onto edge devices (in this case, an Arduino).

As a toy problem, the project will learn a functional approximation of the sine function. That is, the learnign algorithm will be given a dataset of x values, and y values that are computed as the sines of the x values plus some noise. The learning algorithm will then be deployed on an edge device, which will perform inference with the model on-edge.

## Materials/Toolchain
- Arduino Nano BLE Sense
- Google Colab
- PyTorch
- PyTorch Mobile/ExecuTorch/ONNX Runtime
