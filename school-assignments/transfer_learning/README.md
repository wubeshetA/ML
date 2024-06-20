# Vegetable Classification

## Description

The goal of this project is to classify different types of vegetables using transfer learning with pretrained models. The dataset used for this task contains images of various vegetables, divided into training and testing sets. The pretrained models utilized in this project include InceptionV3, MobileNetV3Small, and MobileNet.

## Dataset

The dataset comprises images of vegetables categorized into different classes. The images are preprocessed and augmented to improve the robustness of the models. Data augmentation techniques such as rescaling, horizontal and vertical flipping, and rotation are applied.

## Evaluation Metrics

To assess the performance of the fine-tuned models, the following evaluation metrics are used:
- **Accuracy**: The proportion of correctly classified instances among the total instances.
- **Loss**: The categorical cross-entropy loss.

## Findings

### Strengths
- **Transfer Learning**: Leveraging pretrained models significantly reduces training time and computational resources while maintaining high accuracy.
- **Data Augmentation**: Applying data augmentation techniques improves model generalization by preventing overfitting.

### Limitations
- **Fixed Feature Extraction**: Freezing layers of pretrained models might not capture specific features relevant to the new dataset.
- **Limited Dataset**: The performance might be constrained by the size and diversity of the dataset.

## Experiment Results

The table below summarizes the evaluation metrics for the fine-tuned models:

| Model           | Accuracy | Loss  | 
|-----------------|----------|-------|
| InceptionV3     |    99%   | 0.06  |       
| MobileNetV3Small|    53%   | 1.32  |      
| MobileNet       |    99%   | 0.03  | 

