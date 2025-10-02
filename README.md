# End-to-End-ML-Pipleline-for-Real-Time-Material-Classification-Scrap-Simulation-Challenge-
Performance Report: Scrap Material Classification
1. Project Overview

This project implements an end-to-end deep learning pipeline for classifying recyclable scrap materials into five categories:

Cardboard

Glass

Metal

Paper

Plastic

The solution is based on Transfer Learning with ResNet18, trained on the TrashNet dataset
.
The final model was exported to ONNX format for real-time inference and deployment.

2. Dataset Details

Source: TrashNet dataset

Total Images: ~2,500

Train/Test Split: 80% / 20%

Classes Used: 5 (cardboard, glass, metal, paper, plastic)

Class	Train Images	Test Images
Cardboard	322	81
Glass	400	101
Metal	328	82
Paper	475	119
Plastic	385	97
3. Model Details

Base Model: ResNet18 (pretrained on ImageNet)

Fine-Tuning: Last fully connected layer

Optimizer: Adam (lr=0.001)

Loss Function: CrossEntropyLoss

Epochs: 5

Batch Size: 32

Image Size: 224×224

4. Training Performance
Epoch	Loss	Accuracy
1	1.25	50.2%
2	0.79	74.0%
3	0.67	78.0%
4	0.62	78.1%
5	0.54	81.9%

✅ Final Training Accuracy: ~82%

5. Evaluation on Test Set

Overall Test Accuracy: 77.9%

Macro F1-Score: 0.78

Classes Confusion Matrix:
(see results/confusion_matrix.png)

Class	Precision	Recall	F1-Score
Cardboard	0.96	0.79	0.86
Glass	0.85	0.62	0.72
Metal	0.61	0.93	0.74
Paper	0.87	0.77	0.82
Plastic	0.72	0.80	0.76
6. Key Visualizations

Confusion Matrix: Saved at results/confusion_matrix.png

Accuracy Plot: Saved at results/accuracy_plot.png

Classification Report: Saved at results/classification_report.txt

7. Deployment

Model exported to ONNX: models/resnet18_scrap.onnx

Inference tested using ONNX Runtime (onnxruntime)

Real-time simulation on sample frames stored in data/simulation_frames/

Output results logged to: results/output.csv

8. Key Takeaways

ResNet18 with transfer learning provides ~78% test accuracy.

Metal is harder to classify (confused with glass/paper).

Adding more training samples and data augmentation can improve accuracy further.

ONNX export ensures the model is ready for deployment in lightweight environments.

⚡ Next Steps:

Try deeper models (ResNet34/50).

Use real-time camera feed for inference.

Explore quantization for edge deployment.
