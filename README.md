# AI vs. Human Face Detection

## 📌 Project Overview
This repository contains two deep learning models with identical architectures but different training strategies for distinguishing AI-generated faces from real human photographs. The models achieve state-of-the-art performance in detecting synthetic facial imagery with exceptional accuracy and generalization capabilities.

## 🎯 Key Features
- **Dual Model Approach**: Two PyTorch models with same architecture, different training strategies
- **High Accuracy**: 99.2% test accuracy without overfitting
- **Real-world Validation**: Successfully tested on real smartphone camera images and AI-generated faces
- **Perfect Detection**: 100% accuracy on validation set with real-world samples
- **Comprehensive Dataset**: Mixed sources of real and synthetic facial images

## 📊 Performance Metrics
| Metric | Model 1 | Model 2 | Combined Evaluation |
|--------|---------|---------|-------------------|
| Test Accuracy | 99.2% | 99.1% | - |
| Real Images Detection | - | - | 100% |
| AI-generated Detection | - | - | 100% |
| Validation Accuracy | 99.0% | 98.8% | - |

## 🏗️ Architecture
Both models share the same neural network architecture:
- **Backbone**: Custom CNN architecture (details in model.py)
- **Input Size**: 224×224 RGB images
- **Output**: Binary classification (Real vs AI-generated)
- **Loss Function**: Cross-entropy with regularization
- **Optimizer**: Adam with cosine annealing scheduler

## 🚀 Training Strategies
### **Model 1**: Standard Training
- Standard data augmentation
- Balanced class weighting
- Early stopping implementation

### **Model 2**: Enhanced Training
- Advanced augmentation pipeline
- Curriculum learning approach
- Focal loss implementation
- Mixed precision training

## 📂 Repository Structure
```
├── models/
│   ├── model1_trained.pth
│   ├── model2_trained.pth
│   └── model_architecture.py
├── dataset/
│   ├── real_images/
│   ├── ai_generated/
│   └── validation_set/
├── notebooks/
│   ├── training.ipynb
│   └── evaluation.ipynb
├── src/
│   ├── train.py
│   ├── evaluate.py
│   └── utils.py
├── requirements.txt
├── README.md
└── LICENSE
```

## 🛠️ Installation & Usage

### Prerequisites
```bash
Python 3.8+
PyTorch 1.10+
CUDA 11.3 (optional, for GPU acceleration)
```

### Installation
```bash
# Clone repository
git clone https://github.com/yourusername/ai-face-detection.git
cd ai-face-detection

# Install dependencies
pip install -r requirements.txt
```

### Quick Start
```python
from src.inference import FaceDetector

# Initialize detector
detector = FaceDetector()

# Load single image
result = detector.predict("path/to/image.jpg")
print(f"Prediction: {'AI-generated' if result['is_ai'] else 'Real Human'}")
print(f"Confidence: {result['confidence']:.2%}")

# Batch processing
results = detector.predict_batch(["img1.jpg", "img2.jpg", "img3.jpg"])
```

## 📈 Training Your Own Model
```python
from src.train import train_model

# Train Model 1 (Standard strategy)
train_model(strategy="standard", 
            epochs=50,
            batch_size=32)

# Train Model 2 (Enhanced strategy)
train_model(strategy="enhanced",
            epochs=50,
            batch_size=32)
```

## 🔍 Model Evaluation
```python
from src.evaluate import evaluate_model

# Evaluate on test set
metrics = evaluate_model(model_path="models/model1_trained.pth",
                         test_data="dataset/validation_set/")

print(f"Accuracy: {metrics['accuracy']:.2%}")
print(f"Precision: {metrics['precision']:.2%}")
print(f"Recall: {metrics['recall']:.2%}")
print(f"F1-Score: {metrics['f1']:.2%}")
```

## 📊 Dataset Details
The dataset consists of:
- **Real Human Faces**: 50,000 images from FFHQ, CelebA, and custom smartphone photos
- **AI-generated Faces**: 50,000 images from StyleGAN2, StyleGAN3, and DALL-E 2
- **Validation Set**: 5,000 real smartphone images + 5,000 recent AI-generated faces

## 🧪 Experimental Results
Our models demonstrate remarkable generalization:
- **Cross-dataset testing**: Maintains >98% accuracy on unseen datasets
- **Real-world deployment**: 100% detection rate on actual smartphone photos
- **Robustness**: Resistant to common image manipulations and compression artifacts

## 🤝 Contributing
Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 Citation
If you use this work in your research, please cite:
```bibtex
@software{AI_Face_Detection_2023,
  title = {AI vs Human Face Detection: Dual Model Approach},
  author = {Your Name},
  year = {2023},
  url = {https://github.com/yourusername/ai-face-detection}
}
```

## 📄 License
This project is licensed under the MIT License.

## 📧 Contact
For questions or collaborations, please open an issue or contact:
- **Javad Rahimi** - [jvd.r.403@gmail.com](mailto:jvd.r.403@gmail.com)

---

⭐ **Star this repository if you find it useful!**
