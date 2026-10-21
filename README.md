# Skin Cancer Classification: InceptionV3 vs ResNet50

## Overview

This project compares two deep learning models, InceptionV3 and ResNet50, for classifying skin lesion images using a sample of the ISIC 2018 dataset. The models are evaluated based on classification accuracy, training time, and statistical significance.

The experiment uses 5-fold cross-validation, with 10 training epochs per fold, to compare both models under the same experimental settings.

## Objectives

- Compare the classification accuracy of InceptionV3 and ResNet50.
- Measure the training time of each model.
- Visualize training and validation accuracy and loss.
- Compare model performance across five folds.
- Use paired t-tests to evaluate differences in accuracy and training time.

## Dataset

The project uses 2,000 sampled skin lesion images stored in folders according to seven classes:

| Label | Skin Lesion Class |
|---|---|
| MEL | Melanoma |
| NV | Melanocytic Nevus |
| BCC | Basal Cell Carcinoma |
| AKIEC | Actinic Keratosis / Intraepithelial Carcinoma |
| BKL | Benign Keratosis |
| DF | Dermatofibroma |
| VASC | Vascular Lesion |

The notebook expects the dataset to be available in Google Drive at:

`(https://drive.google.com/drive/folders/1sfOJmuAeXb1RcbxlYlQe_VqeKM562MWQ?usp=sharing)`

The images are copied to the local Google Colab environment before processing.

## Models

### InceptionV3
A pretrained convolutional neural network used to extract image features and classify skin lesions into seven classes.

### ResNet50
A pretrained convolutional neural network that uses residual connections for feature extraction and skin lesion classification.

Both models use ImageNet pretrained weights. The base model layers are frozen, and a new classification layer is added for the seven output classes.

## Methodology

1. **Dataset Preparation** — Load the image paths and labels from the dataset folders.
2. **Image Preprocessing** — Resize images to 224 × 224 pixels and normalize pixel values.
3. **Data Augmentation** — Apply rotation, width and height shifts, horizontal flips, and vertical flips to training images.
4. **Model Training** — Train InceptionV3 and ResNet50 for 10 epochs per fold.
5. **Cross-Validation** — Apply 5-fold cross-validation using the same fold configuration for both models.
6. **Model Evaluation** — Record validation accuracy and training time for each fold.
7. **Visualization** — Generate charts to compare accuracy, loss, and computational time.
8. **Statistical Testing** — Apply paired t-tests to compare accuracy and training time between the models.

## Experiment Configuration

| Parameter | Value |
|---|---|
| Image size | 224 × 224 pixels |
| Number of classes | 7 |
| Batch size | 32 |
| Optimizer | Adam |
| Learning rate | 0.0001 |
| Loss function | Categorical cross-entropy |
| Training epochs | 10 per fold |
| Cross-validation | 5-fold |
| Pretrained weights | ImageNet |

## Visualizations and Evaluation

The notebook generates the following outputs:

- Accuracy comparison between InceptionV3 and ResNet50 for each fold.
- Training and validation accuracy curves.
- Training and validation loss curves.
- Comparison of accuracy and computational time.
- Summary table containing accuracy and training time for each fold and their averages.
- Paired t-test results for accuracy and training time.

The statistical tests use a significance level of 0.05. The conclusions depend on the p-values obtained when the notebook is executed.

## Technologies Used

- Python
- TensorFlow and Keras
- NumPy
- Pandas
- Matplotlib
- Pillow (PIL)
- Scikit-learn
- SciPy
- Google Colab

## How to Run

1. Open the notebook in Google Colab.
2. Upload `535240109(1).ipynb` or open it from your GitHub repository.
3. Upload the dataset to Google Drive and organize the images into the seven class folders.
4. Ensure the dataset path matches the path specified in the notebook.
5. Run the Google Drive mounting cell and authorize access.
6. Execute the notebook cells in order.
7. Review the evaluation table, visualizations, and statistical test results.

A GPU runtime is recommended to reduce training time.

## Limitations

- The experiment uses a sample of 2,000 images rather than the complete ISIC 2018 dataset.
- Training is limited to 10 epochs per fold.
- The base layers of both pretrained models are frozen.
- The results depend on the selected dataset, experimental configuration, and runtime environment.
- This experiment is intended for research and educational purposes, not clinical diagnosis.

## Disclaimer

This project is an academic experiment in deep learning for skin lesion classification. It is not a clinically validated diagnostic tool and should not replace professional medical evaluation.
