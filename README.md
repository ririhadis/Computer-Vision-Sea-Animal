# Computer Vision for Sea Animal Classification

This project implements an image classification model for sea animal recognition using a Transfer Learning approach with EfficientNetB0. The dataset consists of underwater images belonging to 23 sea animal classes.

Offline data augmentation was performed manually by generating augmented images and storing them in a separate folder. The original dataset was divided into training, validation, and testing sets. The augmented images were added only to the training dataset to improve the model's generalization capability.

## 📂 Dataset

- **Number of Classes:** 23
- **Training Images:** 34,527
- **Validation Images:** 1,371
- **Test Images:** 1,372

## 🛠️ Installation

```bash
pip install -r requirements.txt
```

## 🧠 Model Architecture

The model uses **Transfer Learning** with **EfficientNetB0** as the feature extractor, followed by a custom CNN classification head. Fine-tuning was performed by unfreezing the last 30 layers of EfficientNetB0 and retraining the model using a learning rate of **1e-5**.

Architecture:

- EfficientNetB0 (ImageNet pretrained)
- Conv2D (64 filters, 3×3, ReLU)
- BatchNormalization
- GlobalAveragePooling2D
- Dense (256 units, ReLU)
- BatchNormalization
- Dropout (0.4)
- Dense (23 classes, Softmax)

## 📊 Model Performance

| Metric | Result |
|--------|-------:|
| Train Accuracy | **87.09%** |
| Validation Accuracy | **86.36%** |
| Test Accuracy | **85.50%** |

The final fine-tuned model achieved more than **85% accuracy** on the training, validation, and test datasets, demonstrating good generalization performance.

## 📁 Output Files

- **efficientnet_finetune.keras** — Final trained Keras model.
- **saved_model/** — TensorFlow SavedModel format for deployment and serving.
- **tfjs_model/** — TensorFlow.js model for web-based applications.
- **model_eff.tflite** — TensorFlow Lite model for deployment.
- **labels.txt** — Class labels generated automatically from the training dataset.
- **README.md** — Project documentation.

## 👨‍💻 Author

**Srie Wahyudhanis Hadis**  
Machine Learning Engineer
