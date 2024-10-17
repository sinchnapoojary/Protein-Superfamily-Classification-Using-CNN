# Protein Superfamily Classification Using CNN

This project focuses on classifying proteins into their respective superfamilies using a Convolutional Neural Network (CNN). The approach utilizes protein sequence data, and the model is trained to predict the classification based on the input sequences.

## Overview

This project implements a CNN-based architecture for protein superfamily classification. The goal is to classify protein sequences into one of the top 10 most common classes based on their sequence data. The model uses 1D convolutions to extract features from the sequences and then applies fully connected layers to predict the class.

## Dataset

The project merges two datasets:

- **pdb_data_no_dups.csv**: Contains structural data of proteins.
- **pdb_data_seq.csv**: Contains sequence data of proteins.

The datasets are merged on the `structureId` field, and only protein sequences with residue counts below 1200 are considered. The final dataset consists of 10 classes with the highest frequencies.

## Model Architecture

The model is built using Keras and consists of the following layers:

- **Embedding Layer**: Transforms the sequence into an embedding representation.
- **Convolutional Layers**: Multiple 1D convolutions with different filter sizes (3, 5, 9, 15, and 21).
- **Pooling Layers**: MaxPooling to downsample the feature maps.
- **Dropout Layers**: Applied after convolutions and before the fully connected layers to prevent overfitting.
- **Batch Normalization**: Normalizes the activations and helps in faster convergence.
- **Dense Layers**: Fully connected layers for final classification.

## Usage

- **Preprocessing**: The sequences are tokenized at the character level and padded to a maximum length of 350. The labels are one-hot encoded.
- **Training**: Run the script to train the CNN model. The data is split into training and test sets, and an early stopping mechanism is used to prevent overfitting.
- **Evaluation**: After training, the model's accuracy is evaluated on both training and test sets. A confusion matrix and classification report are also generated to assess the model's performance.

## Results

The model achieves a Train Accuracy of approximately 92% and a Test Accuracy of approximately 60%.  
A confusion matrix and classification report are generated to evaluate the predictions.

## Project Associates

- Shreeharsh Joshi
- Shreyas C
- Sinchana Poojary
- Sreevalli R
