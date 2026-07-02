# Face-Deblurring-Conditional-GAN

A Deep Learning project that restores blurred images into sharp, high-quality images using a Conditional Generative Adversarial Network (cGAN) based on the Pix2Pix architecture.

---

## 📌 Project Overview

Image blur is a common problem caused by camera shake, motion, or incorrect focus. This project aims to automatically remove blur from images by learning the relationship between blurred and sharp image pairs.

The model is trained using paired datasets where each blurred image has a corresponding sharp version. During training, the Generator learns to reconstruct sharp images while the Discriminator distinguishes between real and generated images.

---

## 🚀 Features

- Image Deblurring using Deep Learning
- Pix2Pix Conditional GAN Architecture
- Custom PyTorch Dataset & DataLoader
- Paired Blur and Sharp Image Training
- Image Preprocessing using TorchVision
- Generator and Discriminator Networks
- GPU Training Support (CUDA)
- Model Saving and Loading
- Easy to Extend for Custom Datasets

---

## 🛠️ Technologies Used

- Python
- PyTorch
- TorchVision
- OpenCV
- NumPy
- Pandas
- Matplotlib
- PIL (Python Imaging Library)
- Google Colab
- CUDA (GPU Training)

---

## 📂 Project Structure

```
Image-Deblurring/
│
├── dataset/
│   ├── blur/
│   └── sharp/
│
├── models/
│   ├── Generator
│   └── Discriminator
│
├── face_prediction.ipynb
│
├── saved_models/
│
└── README.md
```

---

## 📊 Dataset

The project uses paired datasets consisting of:

- Blurred Images
- Sharp Images

Each blurred image has a corresponding sharp image with the same filename.

Example:

```
blur/
    image001.jpg
    image002.jpg

sharp/
    image001.jpg
    image002.jpg
```

---

## ⚙️ Workflow

```
Blurred Images
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
Generator Network
        │
        ▼
Generated Sharp Image
        │
        ▼
Discriminator
        │
        ▼
Loss Calculation
        │
        ▼
Model Training
```

---

## 🧠 Model Architecture

### Generator

The Generator follows an Encoder-Decoder (U-Net style) architecture.

Encoder:
- Convolution Layers
- Downsampling
- Feature Extraction

Decoder:
- Transposed Convolutions
- Upsampling
- Image Reconstruction

Output:
- Restored Sharp Image

---

### Discriminator

The Discriminator receives:

- Blurred Image
- Real or Generated Sharp Image

It predicts whether the generated image is real or fake.

---

## 🏋️ Training Process

The training process consists of:

1. Load paired blur and sharp images.
2. Preprocess and resize images.
3. Feed blurred images into the Generator.
4. Generate deblurred images.
5. Compare generated images with real sharp images.
6. Train the Discriminator.
7. Update Generator weights.
8. Repeat for multiple epochs.

---

## 📈 Loss Functions

The model uses GAN-based learning with:

- Adversarial Loss
- Reconstruction Loss (L1 Loss)

These losses help generate realistic and accurate sharp images.

---

## 💻 Installation

Clone the repository

```bash
git clone https://github.com/yourusername/Image-Deblurring-GAN.git
```

Move into the project directory

```bash
cd Image-Deblurring-GAN
```

Install dependencies

```bash
pip install torch torchvision opencv-python matplotlib numpy pandas pillow tqdm
```

---

## ▶️ Running the Project

Open the notebook

```
face_prediction.ipynb
```

Run all cells sequentially.

If using Google Colab:

1. Mount Google Drive.
2. Place the dataset inside Drive.
3. Update dataset paths.
4. Train the model.

---

## 📷 Input

Blurred Image

```
Blurred Face
```

↓

## 📷 Output

```
Sharp Restored Face
```

---

## 📊 Future Improvements

- Improve image quality using attention mechanisms
- Train on larger datasets
- Deploy as a web application
- Build a real-time deblurring application
- Support video deblurring
- Experiment with ESRGAN or Diffusion Models

---

## 🎯 Applications

- Mobile Photography
- CCTV Image Enhancement
- Medical Imaging
- Satellite Image Processing
- Face Restoration
- Document Image Enhancement
- Digital Photography

---

## 👨‍💻 Author

**GK**

Artificial Intelligence & Machine Learning Student

GitHub: https://github.com/yourusername

---

## ⭐ If you found this project useful

Please consider giving the repository a ⭐ on GitHub.
