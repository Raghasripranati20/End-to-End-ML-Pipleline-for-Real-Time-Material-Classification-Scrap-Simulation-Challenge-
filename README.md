End-to-End ML Pipeline for Real-Time Scrap Material Classification

This repository contains an end-to-end machine learning pipeline for classifying scrap materials (based on the TrashNet dataset) using Transfer Learning with ResNet18. The system supports training, evaluation, ONNX export, and real-time frame simulation for deployment.

📂 Repository Structure
.
├── src/              # All source code (training, evaluation, inference)
│   └── main.py





├── data/               # Dataset (not included; link in instructions)
│   ├── train/
│   └── test/





├── models/             # Trained models (PyTorch & ONNX formats)
│   └── resnet18_scrap.onnx




├── results/            # Evaluation outputs & screenshots
│   └── output.csv





├── README.md           # Project instructions
└── performance_report.md # Visual summary with key results

🚀 Features

Dataset Preprocessing: Automatic train/test split with augmentation

Transfer Learning: ResNet18 pretrained on ImageNet (feature extraction)

Training Pipeline: Simple configurable PyTorch training loop

Evaluation: Generates classification report + confusion matrix

Model Export: PyTorch → ONNX for deployment

Real-Time Simulation: Classifies frames and logs predictions to CSV

⚙️ Setup Instructions
1. Clone the repository
git clone https://github.com/your-username/scrap-classification.git
cd scrap-classification

2. Create a virtual environment & install dependencies
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -r requirements.txt

3. Download the dataset

We used the TrashNet Dataset. Download from:
🔗 TrashNet Dataset on Kaggle

Place it inside the data/ folder:

data/
├── cardboard/





├── glass/





├── metal/





├── paper/



├── plastic/





└── trash/

4. Run training
python src/main.py --mode train


This will:

Split dataset into train/ and test/

Train the model

Save the ONNX model in models/

5. Run evaluation
python src/main.py --mode eval


Generates:

classification_report.txt

confusion_matrix.png

6. Run real-time simulation

Put test images inside:

data/simulation_frames/


Run:

python src/main.py --mode simulate


Outputs predictions in:

results/output.csv

📊 Results

Model: ResNet18 (feature extraction)

Epochs: 5

Accuracy: ~85–90% (depending on split)

Evaluation Artifacts:

Confusion matrix

Output CSV with predictions

ONNX export for deployment

📦 Model Export

The trained model is exported to ONNX:

models/resnet18_scrap.onnx


This can be loaded using ONNX Runtime for fast inference.

📑 Performance Report

See performance_report.md
 for:

Accuracy/precision/recall

Confusion matrix

Sample predictions

Key takeaways

🤝 Acknowledgements

Dataset: TrashNet Dataset

Base model: ResNet18

Inspired by: Karan’s End-to-End ML Pipeline

✨ End-to-End Automated ML for Real-Time Scrap Classification – Ready for research & deployment!
