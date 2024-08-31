# Face-Mask-and-Social-Distancing-Detection
Introduction
This project demonstrates a deep learning-based approach to detect whether individuals are wearing masks and to identify violations of social distancing norms in images. It combines face detection, mask detection, and social distancing evaluation to provide actionable insights. The solution is built using Haar Cascade for face detection and a VGG19-based Convolutional Neural Network (CNN) for mask classification.

Prerequisites
To run this project, you'll need:

Python: Version 3.6 or higher
pip: Python package installer
Libraries: Ensure the following libraries are installed:
numpy
pandas
opencv-python-headless
scipy
keras
matplotlib
You can install these libraries using:

bash
Copy code
pip install numpy pandas opencv-python-headless scipy keras matplotlib
Setup / Installation
Clone the Repository:

bash
Copy code
git clone https://github.com/your-username/face-mask-social-distancing-detection.git
cd face-mask-social-distancing-detection
Download Pre-trained Models and Datasets:

The project uses Haar Cascade XML files and a VGG19-based model. Follow these instructions to download and set them up:
bash
Copy code
# Install kaggle and configure it
pip install kaggle
mkdir ~/.kaggle
cp kaggle.json ~/.kaggle/
chmod 600 ~/.kaggle/kaggle.json

# Download Haar Cascade and Face Mask datasets
kaggle datasets download -d lalitharajesh/haarcascades
unzip haarcascades.zip

kaggle datasets download -d andrewmvd/face-mask-detection
unzip face-mask-detection.zip
Usage
Prepare Your Environment: Ensure all necessary files are in place and paths are correctly set in the script.

Run the Detection Script: Execute the script to perform face detection, mask detection, and social distancing checks:

bash
Copy code
python detect.py
View Results: The script will output images with annotations showing detected faces, mask status, and social distancing violations.

Code Explanation
Face Detection: Uses OpenCV's Haar Cascade to locate faces in images.
Social Distancing: Measures distances between faces and highlights any violations.
Mask Detection: Applies a VGG19-based model to cropped face images to determine mask usage.
Integration: Combines all detections into annotated images.
Model Training
Data Preparation:

Ensure your datasets are structured in directories: Train, Validation, and Test.
Training:

The model is trained using a VGG19-based architecture with transfer learning. Adjust hyperparameters and data augmentation as necessary.
Saving and Loading Models:

The trained model is saved as masknet.h5 and used for inference.
Example Output
Green Rectangles: Faces wearing masks and maintaining social distancing.
Red Rectangles: Faces not wearing masks or violating social distancing norms.
Labels: Indicate mask status above each face.
Troubleshooting
No Faces Detected: Check image quality and adjust Haar Cascade parameters.
Low Model Accuracy: Retrain with more data or adjust model parameters.
