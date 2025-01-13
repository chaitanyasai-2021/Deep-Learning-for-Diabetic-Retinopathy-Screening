# Deep-Learning-for-Diabetic-Retinopathy-Screening

## 📖 Overview  

Diabetic Retinopathy (DR) is a serious complication of diabetes that damages the retina, potentially leading to blindness if not detected early. This project leverages TensorFlow to build neural networks capable of identifying DR from retinal images. By addressing the challenges in the dataset and applying deep learning techniques, this solution aims to assist in early detection.  

---

## 📊 Dataset  

The dataset used in this project comes from the [2015 Kaggle competition](https://www.kaggle.com/c/diabetic-retinopathy-detection). It contains approximately **35,000 retinal images** captured under varying conditions and sizes.  

However, the dataset is:  
- **Imbalanced**: Most images are labeled as "No DR."  
- **Noisy**: Contains inconsistencies in quality, requiring thorough preprocessing.  

### Example: Original Dataset  
<p align="center">  
<img src="images/original_dataset.png" alt="Original Dataset" width="70%">  
</p>  

---

## 🛠️ Preprocessing Pipeline  

To make the dataset suitable for training, a preprocessing pipeline was implemented:  
1. **Crop & Resize Images**: All images were resized to **256x256 pixels**. Black or invalid images were removed.  
2. **Augmentation**: Images were rotated, mirrored, and resized to balance the dataset.  
3. **Label Updates**: A new CSV file was created to map augmented images to DR levels.  

### Augmentation Examples  
<p align="center">  
<img src="images/augmented_dataset.png" alt="Augmented Dataset" width="70%">  
</p>  

### Class Balance Before and After Augmentation  
<p align="center">  
<img src="images/augmentation_example.png" alt="Augmentation Example" width="70%">  
</p>  

> **Note:** Preprocessing scripts were adapted from [Grew Chase's EyeNet](https://github.com/gregwchase/eyenet).  

---

## 🧠 Neural Network Architectures  

Two types of neural networks were trained:  
1. **Standard CNN**: A basic architecture using convolution and pooling layers.  
2. **InceptionV3**: A pre-trained model by Google, fine-tuned on the augmented dataset using **transfer learning**.  

Architectures for both models can be found in the [neural_nets folder](https://github.com/ramanakshay/Diabetic-Retinopathy-Detection/tree/main/neural_nets).  

---

## 🚀 Training  

- **Data Split**:  
  - 80% of the dataset for training.  
  - 20% for validation.  
- **Google Colab Usage**:  
  - Import the `.pynb` file for the neural network architecture.  
  - Use this command to unzip the dataset:  
    ```bash  
    !unzip '/content/drive/MyDrive/filepath/filename.zip'  
    ```  

The dataset was directly accessed from the directory, saving significant space (~20GB).  

---

## 📈 Results  

| Model                | Accuracy (Training) | Accuracy (Validation) |  
|----------------------|---------------------|-----------------------|  
| **Standard CNN**     | 82.2%              | 82.2%                |  
| **InceptionV3**      | 86.0%              | 85.8%                |  

---

## 📷 Visual Examples  

### Training on Google Colab  
<p align="center">  
<img src="images/colab_upload.png" alt="Colab Upload Example" width="70%">  
</p>  

---

By combining advanced neural networks and thorough preprocessing, this project aims to provide a reliable tool for **early detection of Diabetic Retinopathy**. 👁️✨
