# Rock-Paper-Scissors Hand Sign Detection with Vision AI

This project is a vision-based AI system that detects hand signs (Rock, Paper, Scissors) from images using a YOLOv8 model. The model is trained to classify and recognize hand signs accurately across various backgrounds, leveraging a preprocessed dataset from Roboflow.

## Project Overview

This project includes:
- Training and validation of a YOLOv8 model to recognize Rock, Paper, and Scissors hand signs.
- Model evaluation using metrics such as Precision, Recall, and mAP.
- Confusion matrix analysis for assessing classification accuracy.
- Analyzed speed metrics to understand preprocessing and inference times per image.

## Dataset

The dataset used for this project is a preprocessed dataset from Roboflow. It contains images of hand signs (Rock, Paper, Scissors) with labeled bounding boxes for each sign, as well as background images with no hand signs to improve the model's ability to distinguish between signs and irrelevant scenes.

### Dataset Structure

- **Training Set**: 80% of the dataset.
- **Validation Set**: 20% of the dataset.

## Model Training

The model is trained using the YOLOv8 architecture in PyTorch, optimized for accuracy in detecting hand signs across various backgrounds.

## Validation Results

The model was validated on a set of 576 images, including 238 background images. Below are the key metrics for each class.

| Class       | Images | Instances | Precision | Recall | mAP@50 | mAP@50-95 |
|-------------|--------|-----------|-----------|--------|--------|-----------|
| All         | 576    | 400       | 0.914     | 0.896  | 0.937  | 0.74      |
| Paper       | 132    | 139       | 0.887     | 0.906  | 0.939  | 0.737     |
| Rock        | 121    | 141       | 0.921     | 0.906  | 0.936  | 0.732     |
| Scissors    | 116    | 120       | 0.936     | 0.875  | 0.935  | 0.75      |


## Confusion Matrix Analysis

The confusion matrix provides insights into the model's classification accuracy across different classes. Below is a summary of the results:

| Class       | True Positives | Misclassified as Paper | Misclassified as Rock | Misclassified as Scissors | Misclassified as Background |
|-------------|----------------|------------------------|------------------------|---------------------------|-----------------------------|
| Paper       | 128            | 0                      | 2                      | 6                         | 18                          |
| Rock        | 133            | 6                      | 0                      | 0                         | 10                          |
| Scissors    | 105            | 4                      | 1                      | 0                         | 9                           |
| Background  | 3              | 7                      | 5                      | 0                         | 0                           |

- **Highest Accuracy**: The Rock class, with 133 true positives.
- **Most Misclassified**: Background class, with frequent misclassification as hand signs.

