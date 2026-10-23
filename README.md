# 🔍 Object Detection Streamlit App

> **A modern, user-friendly web application for real-time object detection powered by YOLOv8 and Streamlit**

Repository: https://github.com/0xyz-exe/object-detection-streamlit-app

## Screenshots

### Streamlit Web Dashboard & Model Selector
![Streamlit dashboard](docs/screenshots/01_streamlit_dashboard.png)

### Static Image Object Detection & Bounding Boxes
![Image detection](docs/screenshots/02_image_detection.png)

### Video Processing & Detection Analytics
![Video analytics](docs/screenshots/03_video_analytics.png)

### Model Confidence & NMS Threshold Settings
![Threshold settings](docs/screenshots/04_settings.png)

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://python.org)
[![Streamlit](https://img.shields.io/badge/Streamlit-1.28%2B-red.svg)](https://streamlit.io)
[![YOLOv8](https://img.shields.io/badge/YOLOv8-Ultralytics-green.svg)](https://github.com/ultralytics/ultralytics)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

## 🌟 Overview

This application provides an intuitive web interface for object detection using state-of-the-art YOLOv8 models. Built with Streamlit, it offers multiple input methods including file uploads, URL-based detection, video processing, and real-time webcam detection.

### 🎯 Key Features

| Feature | Description | Status |
|---------|-------------|--------|
| 📷 **Image Detection** | Upload and detect objects in static images | ✅ Ready |
| 🔗 **URL Detection** | Detect objects directly from image URLs | ✅ Ready |
| 🎥 **Video Processing** | Frame-by-frame object detection in videos | ✅ Ready |
| 📹 **Webcam Detection** | Real-time object detection from webcam | 🚧 In Development |
| 🎯 **Multi-Model Support** | YOLOv8n/s/m and custom model support | ✅ Ready |
| ⚙️ **Configurable Settings** | Adjustable confidence and NMS thresholds | ✅ Ready |
| 📊 **Detection Analytics** | Comprehensive detection statistics | ✅ Ready |
| 💾 **Export Results** | Download annotated images and videos | ✅ Ready |

## 🚀 Quick Start

### Prerequisites
- Python 3.8 or higher
- pip package manager
- Git (optional)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/0xyz-exe/object-detection-streamlit-app.git
   cd object-detection-streamlit-app
   ```

2. **Create virtual environment**
   ```bash
   python -m venv venv
   
   # Activate on Windows
   venv\Scripts\activate
   
   # Activate on macOS/Linux
   source venv/bin/activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Run the application**
   ```bash
   streamlit run app.py
   ```

5. **Open in browser**
   - Navigate to `http://localhost:8501`
   - Start detecting objects!

## 📋 Usage Guide

### � Image Detection
- **Supported formats**: JPG, JPEG, PNG, BMP
- **Max file size**: Configurable (default: 200MB)
- **Features**: Upload → Detect → View results → Download

### 🔗 URL Detection  
- **Input**: Direct image URLs from the web
- **Validation**: Real-time URL format checking
- **Features**: Paste URL → Auto-download → Detect → Export results

### 🎥 Video Processing
- **Supported formats**: MP4, AVI, MOV, MKV
- **Processing**: Frame-by-frame detection with progress tracking
- **Output**: Annotated video with detection overlays

### ⚙️ Configuration Options
- **Model Selection**: Choose between YOLOv8n (fast), YOLOv8s (balanced), YOLOv8m (accurate)
- **Confidence Threshold**: 0.1 - 1.0 (default: 0.5)
- **NMS Threshold**: 0.1 - 1.0 (default: 0.4)
- **Custom Models**: Support for user-trained models

## 🏗️ Project Structure

```
object-detection-streamlit-app/
├── 📄 app.py                    # Main Streamlit application
├── 📄 requirements.txt          # Python dependencies
├── 📄 README.md                 # Project documentation
├── 📁 config/
│   └── config.yaml              # Application configuration
├── 📁 utils/                    # Core utilities
│   ├── detection.py             # YOLOv8 detection engine
│   ├── visualization.py         # Result visualization
│   ├── file_handler.py          # File I/O and URL handling
│   └── __init__.py
├── 📁 models/                   # Model storage
│   └── README.md
├── 📁 assets/                   # Sample files and demos
│   ├── demo_videos/
│   └── sample_images/
├── 📁 tests/                    # Unit tests
│   ├── test_detection.py
│   └── test_url_detection.py
└── 📁 docs/                     # Documentation
    ├── installation.md
    ├── usage.md
    ├── api_reference.md
    └── url_detection_guide.md
```

## 🛠️ Technical Stack

### Core Technologies
- **Frontend**: [Streamlit](https://streamlit.io) - Modern web app framework
- **Backend**: [Python 3.8+](https://python.org) - Primary programming language
- **ML Framework**: [Ultralytics YOLOv8](https://github.com/ultralytics/ultralytics) - State-of-the-art object detection
- **Computer Vision**: [OpenCV](https://opencv.org) - Image and video processing
- **HTTP Requests**: [Requests](https://requests.readthedocs.io) - URL-based image fetching

### Key Dependencies
```python
streamlit>=1.28.0        # Web application framework
ultralytics>=8.0.0       # YOLOv8 object detection
opencv-python>=4.8.0     # Computer vision operations
pillow>=10.0.0          # Image processing
numpy>=1.24.0           # Numerical computations
pyyaml>=6.0             # Configuration management
torch>=2.0.0            # Deep learning framework
torchvision>=0.15.0     # Computer vision models
requests>=2.28.0        # HTTP library for URL processing
```

## 🔧 Configuration

### Application Settings (`config/config.yaml`)
```yaml
model:
  default_model: 'YOLOv8n'
  confidence_threshold: 0.5
  nms_threshold: 0.4

ui:
  theme: 'light'
  sidebar_expanded: true

processing:
  max_image_size: 1920
  max_video_size_mb: 100
```

## 🎯 Supported Object Classes

The application can detect 80+ object classes including:

**Vehicles**: car, truck, bus, motorcycle, bicycle, airplane, boat  
**People & Animals**: person, cat, dog, horse, sheep, cow, elephant, bear, zebra  
**Objects**: bottle, cup, fork, knife, spoon, bowl, banana, apple, sandwich  
**Sports**: tennis racket, baseball bat, skateboard, surfboard, soccer ball  
**Electronics**: laptop, mouse, remote, keyboard, cell phone, microwave, toaster

*Full class list available in YOLOv8 documentation*

## 📊 Performance Metrics

| Model | Speed (ms) | mAP@0.5 | Parameters | Model Size |
|-------|------------|---------|------------|------------|
| YOLOv8n | ~45 | 37.3% | 3.2M | 6.2MB |
| YOLOv8s | ~65 | 44.9% | 11.2M | 21.5MB |
| YOLOv8m | ~95 | 50.2% | 25.9M | 49.7MB |

*Benchmarks on standard hardware (CPU: Intel i5, GPU: RTX 3060)*

## 🚀 Deployment Options

### Local Development
```bash
streamlit run app.py
```

### Docker Deployment
```dockerfile
FROM python:3.9-slim
WORKDIR /app
COPY . .
RUN pip install -r requirements.txt
EXPOSE 8501
CMD ["streamlit", "run", "app.py"]
```

### Cloud Platforms
- **Streamlit Cloud**: One-click deployment from GitHub
- **Heroku**: Container-based deployment
- **AWS/GCP/Azure**: Custom server deployment

## 🧪 Testing

### Run Unit Tests
```bash
# Test detection functionality
python -m pytest tests/test_detection.py

# Test URL handling
python tests/test_url_detection.py

# Run all tests
python -m pytest tests/
```

## 🛡️ Security Considerations

- **Input Validation**: All file uploads and URLs are validated
- **File Size Limits**: Configurable limits prevent resource exhaustion  
- **Timeout Protection**: Network requests have timeout limits
- **Safe Processing**: Images are processed in isolated environments
- **No Data Storage**: Uploaded files are automatically cleaned up

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. **Fork the repository**
2. **Create a feature branch**
   ```bash
   git checkout -b feature/amazing-feature
   ```
3. **Make your changes**
4. **Add tests** for new functionality
5. **Commit your changes**
   ```bash
   git commit -m 'Add amazing feature'
   ```
6. **Push to the branch**
   ```bash
   git push origin feature/amazing-feature
   ```
7. **Open a Pull Request**

### Development Guidelines
- Follow PEP 8 style guidelines
- Add docstrings to all functions
- Include unit tests for new features
- Update documentation as needed

### Development Guidelines
- Follow PEP 8 style guidelines
- Add docstrings to all functions
- Include unit tests for new features
- Update documentation as needed

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **[Ultralytics](https://github.com/ultralytics/ultralytics)** - YOLOv8 implementation
- **[Streamlit](https://streamlit.io)** - Web application framework  
- **[OpenCV](https://opencv.org)** - Computer vision library
- **Community Contributors** - Bug reports and feature suggestions

## 📞 Support & Contact

- **Issues**: [GitHub Issues](https://github.com/wondrv/object-detection-streamlit-app/issues)
- **Discussions**: [GitHub Discussions](https://github.com/wondrv/object-detection-streamlit-app/discussions)
- **Email**: niiellpz@gmail.com

---

<div align="center">

**⭐ Star this repo if you find it helpful!**

Made with ❤️ by [wondrv](https://github.com/wondrv)

</div>
