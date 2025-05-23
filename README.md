# 🛣️ Apotheosis: Traffic Sign Detection Project

**Apotheosis** is an image processing project designed to detect and classify traffic signs using computer vision techniques. It uses Python, OpenCV, and Jupyter Notebooks to build and demonstrate a modular detection pipeline.

---

## 📁 Project Structure
```
apotheosis/
├── assets/
│ └── traffic_sign.png # Sample image
├── test/ # Test images folder
│ ├── test1.png
│ ├── test2.jpg
│ └── ...
├── output/ # Output images or result files
├── TEAM.txt # Team members information
├── test.ipynb # Notebook for testing code or parameters
├── thresholds.json # Config file with detection/classification thresholds
├── traffic_sign_detection.ipynb # Main notebook for traffic sign detection
├── Traffic_Sign_Detection_Report.pdf # Final report summarizing methodology and results
```


---

## 🚀 Features

- Preprocessing of traffic sign images (color filtering, contour detection, etc.)
- Sign classification using visual characteristics
- Threshold tuning via external JSON configuration
- Clear visualization of results using Jupyter notebooks
- Project documentation and methodology in PDF format

---

## 🛠️ Technologies Used

- Python 3.x
- OpenCV
- Numpy
- Jupyter Notebook

---

## 📦 Installation

Clone this repository:

```bash
git clone https://github.com/ZeyadElshenawy/apotheosis-traffic-sign-detection.git
cd apotheosis-traffic-sign-detection
```

## 🚀 Quick Start

### Basic Usage

```python
# Load and process an image
image_path = 'assets/traffic_sign.png'
image = cv2.imread(image_path)

# Convert to HSV
hsv_image = cv2.cvtColor(image, cv2.COLOR_BGR2HSV)

# Apply preprocessing
preprocessed = preprocess_image(image)

# Detect traffic signs
detected_signs = detect_traffic_signs(preprocessed, thresholds)
```

### Interactive Parameter Tuning

The notebook provides interactive sliders for real-time parameter adjustment:

```python
# HSV threshold sliders
h_min_slider = widgets.IntSlider(min=0, max=180, step=1, value=h_min_default)
s_min_slider = widgets.IntSlider(min=0, max=255, step=1, value=s_min_default)
v_min_slider = widgets.IntSlider(min=0, max=255, step=1, value=v_min_default)

# Interactive processing
interact(process_image, 
         image=fixed(normalized_image),
         h_min=h_min_slider,
         s_min=s_min_slider,
         # ... other parameters
        )
```

## ⚙️ Configuration

### HSV Threshold Ranges

| Parameter | Range | Description |
|-----------|-------|-------------|
| Hue | 0-180 | Color tone (OpenCV uses 0-180 for Hue) |
| Saturation | 0-255 | Color intensity |
| Value | 0-255 | Brightness |

### Color Classification

| Color | BGR Ranges | Common Signs |
|-------|------------|--------------|
| Red | R>200, G<80, B<80 | Stop signs, prohibitory signs |
| Yellow | R>200, G>200, B<80 | Warning signs |
| Blue | B>200, R<100, G<100 | Information signs |
| White | R>200, G>200, B>200 | Regulatory signs |

### Shape Classification

| Shape | Vertices | Sign Types |
|-------|----------|------------|
| Triangle | 3 | Yield, warning signs |
| Rectangle | 4 | Regulatory, guide signs |
| Octagon | 8 | Stop signs |
| Round | >8 | Speed limits, prohibitory signs |

## 📊 Output and Results

The pipeline generates several types of output:

### Detection Summary
- Number of detected signs
- Type classification for each sign
- Shape information (vertices count)
- Position and size data

### Visualization Grid
- Original image
- Binary mask
- Component analysis
- Final detection overlay

### Console Output
- HSV threshold values
- Processing parameters
- Detailed sign information
  
## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 👥 Contributors

Thanks to the following people for their contributions:
- [@contributor1](https://github.com/contributor1) – Image Acquisition, Color Space Transformation, Colorimetric Distribution Analysis
- [@contributor2](https://github.com/contributor2) – Parameter Identification, Segmentation Implementation, Component Isolation 
- [@ZeyadElshenawy](https://github.com/ZeyadElshenawy) – Spatial Relationship Analysis, Composite Mask Generation, Final Region Labeling, Visualization 

## Warning***
**Note**: This implementation is designed for educational and research purposes. For production use in safety-critical applications, additional validation and testing are recommended.
