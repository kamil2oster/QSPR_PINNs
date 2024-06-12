# Physics Informed Neural Networks – Case Study of Quantitative Structure-Property Relationships

## Overview
This GitHub repository contains Jupyter notebooks and accompanying documentation for a project that explores the application of Physics Informed Neural Networks (PINNs) to Quantitative Structure-Property Relationship (QSPR) modeling. Specifically, the project focuses on predicting the density of ionic liquids (ILs) as a function of temperature and pressure.

## Contents
- **1. Prepare Data and Check Literature Performance.ipynb**: This notebook covers data preparation, initial exploration, and comparison with literature benchmarks.
- **2. Train MLP.ipynb**: This notebook details the training of a Multilayer Perceptron (MLP) model.
- **3. Train PINN.ipynb**: This notebook focuses on training the Physics Informed Neural Network (PINN) model.
- **4. Compare Predictions.ipynb**: This notebook compares the predictions of the MLP and PINN models and evaluates their performance.

## Project Highlights
### Physics Informed Neural Networks (PINNs)
PINNs are neural networks that incorporate physical theories or equations into their training process to guide the model in learning patterns that are consistent with known physical laws. This approach helps improve the model's generalization and interpretability.

### Quantitative Structure-Property Relationship (QSPR)
QSPR models predict the properties of molecules based on their structural descriptors. In this project, we focus on predicting the density of ILs using their molecular descriptors, temperature, and pressure.

### Dataset
The dataset used in this project contains 23,764 data points of ILs, with molecular descriptors, temperature, and pressure as inputs, and density as the output. The data was sourced from a publication by Kamil Paduszynski.

## Notebooks Overview
1. **Prepare Data and Check Literature Performance**: 
   - Data extraction and preprocessing.
   - Initial exploration and comparison with literature data.

2. **Train MLP**: 
   - Building and training a simple MLP model.
   - Evaluating the performance using metrics like Mean Absolute Error (MAE) and Standard Deviation of Errors.

3. **Train PINN**: 
   - Integrating a physics-based Fluctuation Theory Equation of State (FT-EoS) with the neural network.
   - Training the PINN model and evaluating its performance.

4. **Compare Predictions**: 
   - Comparing the performance of MLP and PINN models.
   - Visualizing the predicted vs. actual densities for both models.

## Results
The PINN model significantly outperformed the MLP model in predicting the density of ILs. The integration of physical equations into the neural network training process improved both the training efficiency and the numerical performance.

| Model                         | AARD (%) | MAE     | STD of Errors | Min Error | Max Error  |
|-------------------------------|-----------|---------|---------------|-----------|------------|
| SWMLR + FFANN (Paduszynski)   | 2.305     | 0.028   | 1.038         | -8.270    | 158.902    |
| FFANN + FFANN (Paduszynski)   | 1.600     | 0.020   | 0.127         | -11.724   | 0.798      |
| LSSVM + FFANN (Paduszynski)   | 3.634     | 0.044   | 3.667         | -564.936  | 0.782      |
| **MLP (this work)**           | **0.339** | **0.0042** | **0.0133** | **-0.418** | **0.995**  |
| **PINN (this work)**          | **0.173** | **0.0021** | **0.0126** | **-0.415** | **1.182**  |
