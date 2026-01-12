# Lean CNNs for mapping Electron Charge Density fields to material properties

This work introduces a lean CNN (convolutional neural network) framework, with a drastically reduced number of fittable parameters (< 81K) compared to the benchmarks in current literature, to capture the underlying low-computational cost (i.e., surrogate) relationships between the electron charge density (ECD) fields and their associated effective properties. These lean CNNs are made possible by adding a pre-processing step (i.e., a feature engineering step) that involves the computation of the ECD fields' spatial correlations (specifically, 2-point spatial correlations). The viability and benefits of the proposed lean CNN framework are demonstrated by establishing robust structure–property relationships involving the prediction of effective material properties using the feature-engineered ECD fields as the only input. The framework is evaluated on a dataset of crystalline cubic systems consisting of 1410 molecular structures spanning 62 different elemental species and 3 space groups.

The code for Trigonometric Interpolation is at: https://github.com/pranoy-ray/cubicTI

If you use this code, please cite:
(i) LeanCNN: https://doi.org/10.1007/s40192-024-00389-9
(ii) CubicTI: https://doi.org/10.5281/zenodo.15258119

Created by Pranoy Ray
Contact: pranoy@gatech.edu
