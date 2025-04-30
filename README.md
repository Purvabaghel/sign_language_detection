# Sign Language Detection System

![ASL Detection Demo](demo.gif)

## 📌 Overview  
Real-time American Sign Language (ASL) alphabet detection using YOLOv5 with webcam/image input and accuracy feedback.

## 🛠️ Requirements  
### Hardware  
- Webcam (for real-time detection)  
- GPU recommended (NVIDIA CUDA compatible)  

### Software Dependencies  
```python
# requirements.txt
torch>=1.7.0
torchvision>=0.8.0
opencv-python>=4.5.1
streamlit>=1.0.0
numpy>=1.19.5
pyngrok>=5.0.0
Pillow>=8.3.1
matplotlib>=3.4.2
seaborn>=0.11.1
tqdm>=4.41.0
```
git clone https://github.com/Purvabaghel/sign_language_detection.git
cd sign_language_detection
pip install -r requirements.txt
wget -O models/best.pt "YOUR_MODEL_DOWNLOAD_LINK"

sign_language_detection/
├── app/                  # Streamlit web interface
│   ├── main.py           # Core application
│   └── utils.py          # Helper functions
├── models/               # Model files
│   └── best.pt           # Pretrained weights
├── data/                 # Dataset
│   ├── images/           # Test images
│   └── data.yaml         # YOLO config
├── notebooks/            # Training notebooks
├── detect.py             # CLI detection script
├── train.py              # Training script
├── requirements.txt      # Dependencies
└── README.md

streamlit run app/main.py

# Webcam detection
python detect.py --weights models/best.pt --source 0

# Image detection
python detect.py --weights models/best.pt --source data/images/test.jpg

# Training (optional)
python train.py --img 416 --batch 16 --epochs 50 --data data/data.yaml --cfg models/yolov5s.yaml

## 📊 Supported Arguments

| Argument       | Default     | Description                          |
|----------------|-------------|--------------------------------------|
| `--weights`    | best.pt     | Model weights path                   |
| `--source`     | 0           | Webcam (0) or image path             |
| `--img-size`   | 416         | Inference size (pixels)              |
| `--conf-thres` | 0.5         | Confidence threshold (0-1)           |
| `--view-img`   | False       | Display output                       |

## 🎯 Features

- Real-time ASL alphabet recognition
- Accuracy feedback system
- Detection history tracking
- Adjustable confidence threshold
- Cross-platform support

## 📚 Dataset

ASL alphabet dataset containing:
- 2,500+ annotated images
- 26 classes (A-Z)
- 80-10-10 train-val-test split

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/fooBar`)
3. Commit your changes (`git commit -am 'Add some fooBar'`)
4. Push to the branch (`git push origin feature/fooBar`)
5. Create a new Pull Request

## 📜 License

MIT License - see [LICENSE](LICENSE) for details

---

### Key Features:

1. **Single Block Format**: All information contained in one copy-pasteable block
2. **Complete Dependency List**: Ready-to-use requirements.txt content
3. **Structured Layout**: Clear sections with emoji visual cues
4. **Multiple Usage Methods**: Both web interface and CLI options
5. **Contributing Guidelines**: Ready for open-source collaboration

Simply copy this entire block into your project's README.md file and:

1. Replace `YOUR_MODEL_DOWNLOAD_LINK` with your actual model URL
2. Add a demo.gif if available
3. Update license if different from MIT
