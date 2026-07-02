# 🖼️ Face Image Deblurring using Pix2Pix Conditional GAN (cGAN)

![Python](https://img.shields.io/badge/Python-3.10-blue?logo=python)
![PyTorch](https://img.shields.io/badge/PyTorch-Deep%20Learning-red?logo=pytorch)
![OpenCV](https://img.shields.io/badge/OpenCV-Computer%20Vision-green?logo=opencv)
![Gradio](https://img.shields.io/badge/Gradio-Web%20Interface-orange)
![Google Colab](https://img.shields.io/badge/Google-Colab-yellow?logo=googlecolab)
![License](https://img.shields.io/badge/License-MIT-green)

## 📌 Project Overview

This project presents a **Deep Learning-based Face Image Deblurring System** using a **Conditional Generative Adversarial Network (Pix2Pix cGAN)** implemented in **PyTorch**.

The model learns the mapping between **blurred face images** and their corresponding **sharp images** using paired datasets. During training, the Generator reconstructs high-quality facial images while the Discriminator learns to distinguish between real and generated images, resulting in progressively better image restoration.

The project also integrates **MTCNN Face Detection**, **OpenCV**, and a **Gradio Web Interface** for interactive testing.

---

# 🎯 Problem Statement

Blurred facial images are common due to:

- Camera shake
- Motion blur
- Incorrect focus
- Low-light conditions
- Fast object movement

These degraded images reduce the performance of facial recognition systems and affect image quality.

This project aims to restore blurred facial images into sharp, visually realistic images using deep learning.

---

# 🚀 Key Features

- Face Image Deblurring using Pix2Pix Conditional GAN
- Generator and Discriminator implemented in PyTorch
- Custom Dataset class for paired images
- Automatic image preprocessing
- GPU (CUDA) support
- Face Detection using MTCNN
- OpenCV integration
- Gradio-based interactive web application
- Model checkpoint saving
- Batch inference support

---

# 🧠 Model Architecture

The project uses the **Pix2Pix Conditional GAN** architecture consisting of two neural networks.

## Generator

The Generator receives a blurred image and generates a sharp version.

Main tasks:

- Feature Extraction
- Downsampling
- Upsampling
- Image Reconstruction

Input:

```
Blurred Face Image
```

Output:

```
Deblurred Face Image
```

---

## Discriminator

The Discriminator receives

- Original Blur Image
- Real Sharp Image OR Generated Sharp Image

Its job is to classify whether the generated image is real or fake.

The Generator improves by trying to fool the Discriminator.

---

# 🏗️ Overall Workflow

```
Blurred Face Images
        │
        ▼
Image Preprocessing
        │
        ▼
Custom Dataset
        │
        ▼
DataLoader
        │
        ▼
Generator (Pix2Pix)
        │
        ▼
Generated Sharp Image
        │
        ▼
Discriminator
        │
        ▼
GAN Loss + L1 Loss
        │
        ▼
Backpropagation
        │
        ▼
Model Training
        │
        ▼
Saved Generator Model
        │
        ▼
Inference
        │
        ▼
Face Detection (MTCNN)
        │
        ▼
Gradio Web Interface
```

---

# 📂 Dataset

The model is trained using **paired images**.

Dataset Structure

```
dataset/

│

├── blur/

│      image001.jpg

│      image002.jpg

│      ...

│

└── sharp/

       image001.jpg

       image002.jpg

       ...
```

Each blurred image has a corresponding sharp image with the same filename.

---

# 📦 Data Preprocessing

Images undergo several preprocessing steps before training.

- Image Loading
- Resize to **256 × 256**
- Tensor Conversion
- Normalization
- Batch Loading using DataLoader

---

# 🛠️ Technologies Used

| Technology | Purpose |
|------------|----------|
| Python | Programming Language |
| PyTorch | Deep Learning Framework |
| TorchVision | Image Processing |
| OpenCV | Computer Vision |
| PIL | Image Handling |
| NumPy | Numerical Operations |
| Matplotlib | Visualization |
| MTCNN | Face Detection |
| Gradio | Web Interface |
| Google Colab | Development Environment |

---

# ⚙️ Hyperparameters

| Parameter | Value |
|-----------|-------|
| Image Size | 256 × 256 |
| Batch Size | 32 |
| Learning Rate | 0.0002 |
| Epochs | 3 |
| Optimizer | Adam |
| GAN Loss | BCEWithLogitsLoss |
| Reconstruction Loss | L1 Loss |
| L1 Weight | 100 |

---

# 📉 Loss Functions

## 1. Adversarial Loss

Used to train the Generator and Discriminator.

```
BCEWithLogitsLoss
```

It helps the Generator produce realistic images.

---

## 2. L1 Loss

Measures the pixel-wise difference between

Generated Image

and

Ground Truth Sharp Image

```
L1 Loss = |Generated − Real|
```

L1 Loss Weight

```
100
```

---

# 🏋️ Training Pipeline

Training follows these steps:

1. Load paired images.
2. Apply preprocessing.
3. Create batches using DataLoader.
4. Feed blurred images to Generator.
5. Generate deblurred images.
6. Train Discriminator.
7. Compute GAN Loss.
8. Compute L1 Loss.
9. Backpropagate.
10. Update Generator.
11. Repeat for all epochs.

---

# 💾 Model Saving

After training, the Generator model is saved.

Example

```
generator_epoch_3.pth
```

The saved model can later be loaded for inference.

---

# 🔍 Inference Pipeline

The inference pipeline follows:

```
Input Image

↓

Preprocessing

↓

Generator

↓

Deblurred Image

↓

Face Detection

↓

Final Output
```

---

# 😊 Face Detection

The project integrates **MTCNN** for detecting facial regions.

Benefits

- Accurate face localization
- Robust detection
- Works with multiple faces

---

# 🌐 Gradio Interface

A Gradio web application is included for testing.

Features

- Upload image
- Automatic prediction
- Display restored image
- User-friendly interface

---

# 📈 Results

The Generator successfully learns to reconstruct clearer facial images from blurred inputs.

The model demonstrates:

- Improved visual quality
- Sharper facial details
- Better edge reconstruction
- Reduced blur artifacts

---

# 📁 Project Structure

```
Face-Deblurring-using-Pix2Pix/

│

├── dataset/

│      ├── blur/

│      └── sharp/

│

├── models/

│

├── saved_models/

│      generator_epoch_3.pth

│

├── face_prediction.ipynb

│

├── requirements.txt

│

└── README.md
```

---

# 📥 Installation

Clone the repository

```bash
git clone https://github.com/yourusername/Face-Deblurring-using-Pix2Pix.git
```

Move to project folder

```bash
cd Face-Deblurring-using-Pix2Pix
```

Install dependencies

```bash
pip install torch torchvision
pip install opencv-python
pip install matplotlib
pip install pillow
pip install numpy
pip install gradio
pip install mtcnn
```

---

# ▶️ Running the Project

Open

```
face_prediction.ipynb
```

Run all notebook cells sequentially.

If using Google Colab

- Mount Google Drive
- Update dataset path
- Train the model
- Save Generator
- Run inference
- Launch Gradio interface

---

# 🎯 Applications

- Face Restoration
- CCTV Enhancement
- Mobile Photography
- Security Systems
- Image Enhancement
- Social Media Photo Restoration
- AI-based Photo Editing
- Medical Image Enhancement

---

# 🔮 Future Improvements

- Train on larger datasets
- Increase training epochs
- Use U-Net based Generator
- Integrate Attention Mechanisms
- Improve image resolution
- Real-time video deblurring
- Deploy using Streamlit
- Deploy on Hugging Face Spaces
- Convert model to ONNX
- Mobile deployment

---

# 📚 Learning Outcomes

Through this project, the following concepts are demonstrated:

- Deep Learning
- GANs
- Conditional GANs
- Pix2Pix Architecture
- Image-to-Image Translation
- Computer Vision
- Face Detection
- PyTorch Model Training
- Model Saving and Loading
- Web Deployment using Gradio

---

# 👨‍💻 Author

**GK**

Artificial Intelligence & Machine Learning Student

Interested in:

- Machine Learning
- Deep Learning
- Computer Vision
- Generative AI
- AI Application Development

---

# ⭐ Support

If you found this project helpful, consider giving the repository a **⭐ Star** on GitHub.

It motivates further development and improvements.

---

## 📜 License

This project is released under the **MIT License**.

Feel free to use, modify, and distribute it for educational and research purposes.
