
# CAM-KD: Class Activation Map-Based Knowledge Distillation

## Project Overview

**CAM-KD** is a method for compressing large neural networks by transferring knowledge from a larger **teacher model** to a smaller **student model** using **Class Activation Maps (CAMs)**. This approach improves both model performance and transparency by showing which regions of the image contribute to the model’s predictions.

### Key Features:
- **Improved Model Accuracy**: Achieved 68.3% accuracy on CIFAR10 using CAM-based distillation, outperforming traditional methods.
- **Explainability**: CAMs provide insights into the decision-making process of both teacher and student models.
- **Efficient Student Model**: The custom **CAM-Net** student model has only 0.096 million parameters, making it highly efficient for deployment on resource-constrained devices.

## How It Works

1. **Knowledge Distillation**: The student model learns from the teacher model by mimicking its predictions. In our approach, CAMs are also used to transfer the structural knowledge.
2. **Class Activation Maps (CAMs)**: CAMs highlight important regions of an image for classification. During training, we compare the CAMs of the teacher and student and minimize the difference between them.
3. **Distillation Process**: We combine the CAM loss with traditional distillation loss to guide the student model to learn both high-level predictions and low-level visual features.

## Experiments and Results

- **Dataset**: We used the **CIFAR10** dataset with 60,000 32x32 images across 10 classes.
- **Teacher Model**: ResNet-50 (27.8M parameters)
- **Student Model**: CAM-Net (0.096M parameters)
- **Best Accuracy**: The student model reached 68.3% accuracy by combining CAM and distillation losses, outperforming the baseline approach (67.2%).

### Result Visualizations

Below is a comparison of the **Class Activation Maps** generated by the teacher and student models after training with CAM-based distillation. The red regions show where the models focus when classifying the images.

![CAM Results](https://github.com/shahriyar-zaman/CAM-KD-A-Class-Activation-Map-Based-Approach-Towards-Knowledge-Distillation/blob/fbd70d592ef073f6665edc46b20ef4f683053771/cam_com_upd.png)




