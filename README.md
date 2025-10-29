# Face Recognition Attendance System using DeepFace and SVM

## Team Members:
* Sarah Biju (MS23090)
* Tushti Govind (MS23144)
* Eshita Tandon (MS23163)

## Overview 
This project is our attempt at building a face recognition attendance system. We used the Labeled Faces in the Wild (LFW) dataset to train our models and created an interactive system that can recognize faces and mark attendance automatically.
The system uses deep learning to extract facial features, reduces those features using PCA to make processing faster, then uses an SVM classifier to identify people, and record recognised faces . The system works in Google Collab, which made it easy for us to collaborate and test.

## Python Libraries and Tools Used
Language (Python 3.X), Deep Learning (DeepFace, FaceNet), Computer Vision (OpenCV), Machine Learning (Scikit-learn (SVM, PCA)), Data Processing	(pandas, NumPy), Visualization (Matplotlib, seaborn), Database (SOLite3), Environment (Google Collab), Model persistence (Joblib)

## Features:

### Dataset Management
LFW dataset was downloaded and organised. The system automatically selected 20 different identities and saves >= 20 images of each person. Everything gets organised into neat foldes.

### Face Recognition Pipeline
* First, 128-dimensional feature vectors are extracted from each using Facenet.
* Using PCA those 128-dimensions were reduced down to just 10, to make everything run faster.
* Linear SVM classifier was trained to recognise different people.
* When a new face comes in, we checked if confidence is above 30% before making a prediction.

### Interactive Attendance System
A menu-driven interface is built to make it easy to use that includes:
* Webcam Mode: Capture photos directly from your webcam and get instant recognition
* Upload Mode: Upload images from your computer and process them in batches
* View Records: See all attendance records with helpful charts
* Analytics Dashboard: Dive deep into how well the system is performing
* Report Generation: Download everything as CSV and text files

### Advanced Analytics
* Confusion Matrix: Visual representation of correct and incorrect predictions
* Accuracy Metrics: F1-score, Cohen's Kappa, and detailed classification reports
* ROC Curve Analysis: Multi-class ROC curves showing how well we can distinguish between different people
* SVM Details: All the technical details about our classifier

### Smart Attendance Mangement 
The system marks attendance smartly as:
* Does not mark the same person twice within an hour (cooldown period)
* Lets you manually enter the name of person for faces it doesn't recognise
* Each session gets a unique ID for easy tracking
* Automatically records the date and time of every entry
