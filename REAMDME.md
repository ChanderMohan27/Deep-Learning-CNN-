
# Facial Expression and FACS Code Recognition using CNN

## Introduction

This project develops a single CNN neural network capable of automatically recognizing facial expressions and FACS codes from images. The model is designed to process an image and output the corresponding emotion and FACS codes, enhancing the dataset with our custom data loader for preprocessing. 

For more detailed information about this project, please refer to our comprehensive report. You can access it here: [Project Detailed Report](https://drive.google.com/file/d/1zVa3jGvPfJ2JzR1B7_so7mhvTdyEVBAF/view?usp=drive_link)


## Dataset Description

We utilize the CK+ dataset, which includes 560 labeled images from 123 subjects, encompassing grayscale and RGB images. In our dataset the target variables are high level emotion which has three different categories negative, positive and surprise, and also 15 different facs codes label columns that consist with binary values.

## Data Analysis

Analysis of the dataset revealed that the distribution of high-level emotion labels is approximately 58% and the images are labelled as conveying a negative emotion, while the remaining images are distributed between the positive and surprise labels. The majority of facs code columns labelled as 0.

## Data Preprocessing

One of the main challenges in developing an effective emotion detection model is the limited size of the dataset. Normally, creating robust neural network classification models requires millions of images, but this project works with a considerably smaller dataset. To address this limitation, we have implemented several regularization techniques. These include Data Augmentation, L1 and L2 regularization, an Adam learning rate scheduler, and the application of transfer learning strategies. These methods help enhance model performance despite the dataset's constraints.

The dataset was divided into training, validation, and test sets. We processed images to fit the VGG16 model requirements, converting grayscale to 3-channel images, and encoding emotion labels numerically.

## Model Selection and Architecture

VGG16 was chosen for its simplicity and effectiveness on small datasets. Transfer learning was applied by freezing VGG16 layers and attaching custom layers for emotion and FACS code prediction.

## Experiments & Tuning

Initial training without regularization led to overfitting, prompting the introduction of data augmentation, learning rate adjustments, L1 and L2 regularization, early stopping, batch normalization, and dropout layers to improve the model.

## Evaluation Framework

We employed classification reports and confusion matrices for emotion class evaluation and F1 scores for FACS code evaluation because the target labels are imbalance. 

## Ultimate Judgment Analysis & Limitations

The model achieved a 71% accuracy for emotion classification. Performance varied across classes and FACS codes, highlighting limitations due to the small and imbalanced dataset.

## Ethical Issues and Biases

### Developing an automatic The development and application of automated facial expression recognition systems raise several ethical issues.

**Data privacy**: Proper anonymization and privacy protection should be ensured to avoid the misuse of individuals' facial data.

**Cultural Sensitivity**: The emotions expressed in the dataset might not accurately represent the emotions across different cultural backgrounds. Applying models trained on this dataset to diverse populations could lead to misinterpretations.

**Fair Representation**: The CK+ dataset might not have balanced representation across various demographics, such as age, gender, and ethnicity. Using an imbalanced dataset can lead to biased models that don't generalize well to all groups.

**Labelling Bias**: The dataset is imbalanced. 60% of the images are negative labelled images that will lead to Unfair Treatment, Impact on Decision-Making and that will lead to an ethical issue.

**Security Risks**: If facial recognition databases are compromised, it can lead to identity theft, unauthorized access, and other security breaches.
