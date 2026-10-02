# CIFAR-10 Image Classification Using CNN

## 📌 Project Overview

This project develops a **Convolutional Neural Network (CNN)** to classify images from the **CIFAR-10 dataset**.

The model learns to classify an image into one of 10 categories:

- Airplane
- Automobile
- Bird
- Cat
- Deer
- Dog
- Frog
- Horse
- Ship
- Truck

The project demonstrates an end-to-end deep learning workflow, from exploring and preprocessing image data to training and evaluating a CNN model and deploying it through a simple Streamlit application.

## 📊 Dataset

The project uses the **CIFAR-10 dataset** available through TensorFlow/Keras.

The dataset contains **60,000 colour images** divided into 10 classes.

- Training images: 50,000
- Testing images: 10,000
- Image size: 32 × 32 pixels
- Colour channels: RGB
- Number of classes: 10

## 🔍 Exploratory Data Analysis

The dataset was explored before model training to understand:

- Image dimensions
- Number of training and testing images
- Class distribution
- Image labels
- Pixel-value ranges
- Sample images from each category

Visualizations were also used to inspect images from the different CIFAR-10 classes.

## ⚙️ Data Preprocessing

The image pixel values originally range from **0 to 255**.

They were normalized to a range between **0 and 1** using:

```python
X_train = X_train.astype("float32") / 255.0
X_test = X_test.astype("float32") / 255.0
```

The labels were also flattened before training.

## 🧠 CNN Architecture

The classification model was developed using **TensorFlow/Keras**.

The CNN consists of:

- Convolutional layers for feature extraction
- Max-pooling layers for dimensionality reduction
- A Flatten layer
- A fully connected Dense layer
- Dropout for reducing overfitting
- A Softmax output layer for 10-class classification

The convolutional layers contain **32, 64 and 128 filters** respectively.

The final layer contains 10 neurons representing the 10 CIFAR-10 classes.

## 🚀 Model Training

The model was compiled using:

- **Optimizer:** Adam
- **Loss Function:** Sparse Categorical Crossentropy
- **Evaluation Metric:** Accuracy

The model was trained using the CIFAR-10 training dataset while a portion of the training data was used for validation.

Training and validation accuracy and loss were visualized to evaluate the learning process and identify possible overfitting.

## 📈 Model Evaluation

The trained model was evaluated using the unseen CIFAR-10 test dataset.

Performance was analyzed using:

- Test accuracy
- Test loss
- Precision
- Recall
- F1-score
- Classification report
- Confusion matrix

The confusion matrix was used to identify classes that the model commonly confused.

## 🔮 Making Predictions

The trained CNN predicts probabilities for all 10 CIFAR-10 classes.

The class with the highest probability is selected as the final prediction.

Example:

```text
Prediction: Ship
Confidence: 91.34%
```

## 💾 Saving the Model

The trained model is saved as:

```text
cifar10_model.keras
```

This allows the model to be loaded later without retraining it.

## 🌐 Streamlit Application

A simple Streamlit web application allows users to upload an image and receive a prediction from the trained CNN.

The application:

1. Accepts a JPG, JPEG or PNG image.
2. Converts the image to RGB.
3. Resizes it to 32 × 32 pixels.
4. Normalizes the pixel values.
5. Sends the processed image to the CNN.
6. Displays the predicted class and confidence score.

## 📁 Project Structure

```text
cifar10-image-classification/
│
├── cifar_images.ipynb
├── app.py
├── cifar10_model.keras
├── requirements.txt
├── README.md
└── .gitignore
```

## 🛠️ Technologies Used

- Python
- TensorFlow
- Keras
- NumPy
- Matplotlib
- Scikit-learn
- Streamlit
- Pillow
- Jupyter Notebook

## 💻 Installation

Clone the repository:

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
```

Move into the project directory:

```bash
cd cifar10-image-classification
```

Install the required libraries:

```bash
pip install -r requirements.txt
```

## ▶️ Run the Streamlit Application

Run:

```bash
streamlit run app.py
```

The application will open in your browser.

Upload an image and the trained model will attempt to classify it into one of the 10 CIFAR-10 categories.

## ⚠️ Limitations

CIFAR-10 contains very small **32 × 32 pixel images**. Real-world images uploaded through the Streamlit application can differ significantly from the images used to train the model.

As a result, predictions on arbitrary real-world photographs may not always be accurate.

Future improvements could include data augmentation, transfer learning, additional CNN layers, hyperparameter tuning and training with larger image datasets.

## 👤 Author

**Aaron Pam**

Deep Learning & Computer Vision Project
