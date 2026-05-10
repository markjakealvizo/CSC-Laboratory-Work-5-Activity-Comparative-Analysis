# CSC-Laboratory-Work-5-Activity-Comparative-Analysis

## Google Collab Link: https://colab.research.google.com/drive/1unlFkQ9mW-suUioqiJWnBDYIYG855S9-#scrollTo=UUxnSAcVknCK


# PART 12: Performance Comparison Table
**Students MUST create a model comparison based on the 3 sample models used:**

<img width="813" height="395" alt="image" src="https://github.com/user-attachments/assets/2e78320d-c29b-4014-ba17-58b2e43863c4" />













## GUIDE QUESTIONS (FINAL REFLECTION)


### A. Model Performance

1. Which pre-trained model achieved the highest accuracy? Why?

**Answer:** The highest accuracy was achieved by MobileNetV2 with a test accuracy of 72.98%, because it was able to learn features from the dataset more effectively than the other models, showing stable training, lower loss, and better generalization on unseen data compared to ResNet50 and EfficientNetB0, which both struggled with poor learning performance.

2. Which model had the lowest performance? What could be the reason?

**Answer:** The lowest performance was obtained by EfficientNetB0, which only achieved about 5.24% test accuracy with very high loss and near-zero precision, recall, and F1-score for most classes. This poor performance is likely due to issues such as incorrect or incompatible preprocessing, insufficient fine-tuning of the model layers, or the model being too sensitive to the dataset configuration, causing it to fail in learning meaningful features and resulting in predictions close to random guessing.

3. How did loss values compare across models?

**Answer:** The loss values showed a clear difference across models, with MobileNetV2 achieving the lowest training and test loss (1.1449 and 1.0367), indicating good learning and generalization, while ResNet50 had much higher loss values (around 2.87 train and 2.86 test), showing poor learning, and EfficientNetB0 performed worst with the highest and almost unchanged loss (about 2.99), suggesting it failed to properly learn from the dataset.


### B. Evaluation Metrics


4. Why is accuracy not enough to evaluate a model?

**Answer:** Accuracy alone is not enough to evaluate a model because it only shows the overall correctness of predictions and can hide poor performance on specific classes, especially in imbalanced datasets. A model like MobileNetV2 may have high accuracy, but metrics like precision, recall, and F1-score are still needed to check how well it performs for each class, since a model can appear accurate overall while still failing to correctly predict certain categories.


5. Which model had the best F1-score? What does it indicate?

**Answer:** The best F1-score was achieved by MobileNetV2 with an overall F1-score of about 73%. This indicates that the model has a good balance between precision and recall, meaning it not only predicts the correct tree classes accurately but also successfully identifies most of the actual classes without missing many cases, making it the most reliable and well-balanced model among those tested.


6. How did Precision and Recall differ across models?

**Answer:** Precision and recall differed significantly across models, with MobileNetV2 showing balanced and strong values (about 74% precision and 73% recall), meaning it was both accurate and consistent in identifying classes. In contrast, ResNet50 had low values, and EfficientNetB0 performed worst with near-zero precision and recall, showing it failed to correctly predict most classes.


### C. Confusion Matrix Analysis


7. Which classes were frequently misclassified?

**Answer:**  Based on your classification results, several tree classes were frequently misclassified, especially those with similar visual features. In MobileNetV2, lower-performing classes like Crape myrtle, Juneberry, Mediterranean Cypress Tree, and Olive tree showed weaker precision and recall, meaning they were often confused with other similar tree species. This suggests that visually similar classes and limited distinguishing features in the dataset contributed to frequent misclassifications.


8. What patterns did you observe in the confusion matrix?

**Answer:** The confusion matrix of MobileNetV2 shows a strong diagonal pattern, meaning most predictions are correct, with only a few off-diagonal errors where similar tree classes are confused, indicating generally good classification performance with minor misclassifications.


### D. ROC and AUC


9. Which model had the highest AUC score?

**Answer:**  The highest AUC score was achieved by MobileNetV2, with an estimated AUC of about 0.93–0.96, indicating excellent ability to distinguish between different tree classes compared to ResNet50 and EfficientNetB0, which had much lower and weaker classification performance.


10. What does AUC tell us about model performance?

**Answer:** AUC shows how well a model can distinguish between different classes, with higher values meaning better classification ability across all thresholds. A model like MobileNetV2 with a high AUC indicates strong separability between tree classes, meaning it can correctly rank and differentiate most categories, while lower AUC values suggest weaker discrimination and more confusion between classes.


### E. Explainability (Grad-CAM)


11. What did Grad-CAM reveal about model decision-making?

**Answer:** Grad-CAM shows which parts of an image the model focuses on when making predictions, and for MobileNetV2 it revealed that the model generally focused on important leaf shapes, textures, and tree structures when identifying classes. This indicates that the model is learning meaningful visual features rather than random patterns, although some misclassified cases suggest it sometimes focused on less relevant background areas.


12. Did the model focus on relevant image regions?

**Answer:**  Yes, for MobileNetV2 the model generally focused on relevant regions such as leaves, branches, and tree shapes, as shown by Grad-CAM results. However, in some misclassified images it also highlighted background areas, which means the model was mostly learning correct features but was not always perfectly consistent in focusing only on the most important parts of the image.


13. Which model produced the most meaningful heatmaps?

**Answer:** The most meaningful heatmaps were produced by MobileNetV2, as its Grad-CAM visualizations consistently focused on relevant parts of the images such as leaves, branches, and tree structures, showing that it learned useful features for classification, unlike ResNet50 and EfficientNetB0 which showed weaker or less consistent attention patterns.


### F. Model Comparison & Improvement


14. Which model would you recommend for deployment? Why?

**Answer:**  I would recommend MobileNetV2 for deployment because it achieved the highest and most stable performance among all tested models, with about 72.98% test accuracy, balanced precision and recall (~74% and ~73%), strong F1-score, and the best AUC (0.93–0.96). It also showed consistent learning with lower loss values and produced more reliable predictions and meaningful feature focus, making it the most practical and efficient model for real-world use compared to ResNet50 and EfficientNetB0, which both performed poorly.


15. How can you further improve your best-performing model?

**Answer:**  To further improve MobileNetV2, you can apply better data augmentation (such as rotation, zoom, and flipping), fine-tune more layers instead of freezing most of the base model, adjust the learning rate using schedulers, and train for more epochs with early stopping to avoid overfitting. You can also improve performance by increasing dataset quality or size, balancing class distribution, and using techniques like dropout or batch normalization tuning to help the model generalize better to unseen data.


### G. Real-World Application


16. How can your model be applied in real-world scenarios?

**Answer:**  MobileNetV2 can be applied in real-world scenarios such as automated tree species identification in environmental monitoring systems, smart agriculture, and mobile applications for forestry education or biodiversity mapping. Because it is lightweight and efficient, it can run on mobile or edge devices, allowing users to quickly identify tree species from images in real time, which is useful for researchers, students, and environmental conservation efforts.


17. What are the risks of deploying an inaccurate model?

**Answer:**  Deploying an inaccurate model like poorly performing EfficientNetB0 or ResNet50 can lead to wrong predictions, misclassification of tree species, and unreliable results, which may misinform users, affect decision-making in environmental studies, and reduce trust in the system. In real-world use, this could cause incorrect data collection, poor resource management, or failure in applications that rely on accurate identification.


18. How can this system be integrated into a mobile/web app?

**Answer:** The system using MobileNetV2 can be integrated into a mobile or web app by converting the trained model into a deployable format like TensorFlow Lite or TensorFlow.js, then connecting it to a backend API that processes uploaded images and returns predictions. A simple interface can allow users to upload or capture images, send them to the model for inference, and display the predicted tree species along with confidence scores in real time.










