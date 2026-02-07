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
│   ├── model_1.pt
│   ├── model_2.pt
├── dataset/
│   ├── dataset_real_or_fake_face.rar
├── notebook/
│   ├── notebook.ipynb
├── README.md
└── LICENSE
```

## 📊 Dataset Details
The dataset consists of:
- **1290 Face Images**
- **590 Real Face Images**
- **700 AI Generated Face Images**

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
@software{AIGenerated_Or_Real_Image_Detection,
  title = {AI vs Human Face Detection: Dual Model Approach},
  author = {Javad Rahimi},
  year = {2025},
  url = {https://github.com/AloneMaster7/ai-face-detection}
}
```

## 📄 License
This project is licensed under the MIT License.

## 📧 Contact
For questions or collaborations, please open an issue or contact:
- **Javad Rahimi** - [jvd.r.403@gmail.com](mailto:jvd.r.403@gmail.com)
- **Telegram ID** - @AlServiceHub
---

⭐ **Star this repository if you find it useful!**
