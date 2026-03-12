# Forest Cover Type Classification using Neural Networks

## Project Overview
This project focuses on predicting the **forest cover type** of different land areas using machine learning. The dataset contains various cartographic variables such as elevation, slope, soil type, and wilderness area information.

A **Neural Network model built with TensorFlow/Keras** was used to classify forest cover into one of **seven different cover types**.

The goal of this project is to demonstrate a complete **machine learning workflow**, including data preprocessing, model training, evaluation, and performance visualization.

---

## Dataset
The dataset used is the **Forest Cover Type Dataset** originally from the U.S. Forest Service.

Features include:

- Elevation
- Aspect
- Slope
- Horizontal distance to hydrology
- Vertical distance to hydrology
- Horizontal distance to roadways
- Hillshade measurements
- Wilderness area indicators
- Soil type indicators

Target Variable:
- **Cover_Type** (7 forest cover classes)

---

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- TensorFlow / Keras
- Jupyter Notebook

---

## Project Workflow

### 1. Data Exploration
- Loaded dataset using Pandas
- Checked dataset shape and column information
- Verified missing values
- Analyzed class distribution

### 2. Data Preprocessing
- Split data into **training, validation, and test sets**
- Standardized numerical features using **StandardScaler**

### 3. Model Development
A **Neural Network model** was implemented using TensorFlow/Keras with the following structure:

- Input Layer
- Dense layers with **ReLU activation**
- **Dropout layers** to prevent overfitting
- Output layer with **Softmax activation**

Loss Function: **Sparse Categorical Crossentropy**

Optimizer: **Adam**

### 4. Model Training

The neural network model was trained using the following configuration:

- **Epochs:** 40  
- **Batch Size:** 128  
- **Callback Used:** EarlyStopping  

EarlyStopping was used to monitor the validation loss during training.  
If the validation loss stopped improving for several epochs, training was stopped early and the best model weights were restored.  

This helps prevent **overfitting** and improves the model's ability to generalize to unseen data.

### 5. Model Evaluation

After training the model, its performance was evaluated using a separate **test dataset** that was not used during training.

The following evaluation methods were used:

- Test Accuracy
- Classification Report
- Confusion Matrix
- Accuracy vs Validation Accuracy Plot
- Loss vs Validation Loss Plot

These evaluation metrics help measure how well the model performs on unseen data.

### Model Performance

The final trained neural network achieved approximately:

**Test Accuracy: ~90%**

The classification report shows strong precision and recall for most forest cover classes.  
Some classes have slightly lower recall due to **class imbalance in the dataset**, where certain cover types have significantly fewer samples.

### Performance Visualization

Two key plots were generated to understand the model's learning behavior:

**Accuracy Plot**

Shows how training accuracy and validation accuracy change across epochs.

**Loss Plot**

Shows how training loss and validation loss change during training.

These plots help determine whether the model is:

- Overfitting
- Underfitting
- Learning effectively

### Confusion Matrix

A confusion matrix was generated to visualize how well the model predicts each forest cover type and to identify where misclassifications occur.

### Model Saving

The trained neural network model was saved for future use:

model.save("forest_cover_model.keras")

The saved model can later be loaded using:

from tensorflow.keras.models import load_model
model = load_model("forest_cover_model.keras")

---

## Project Structure

Forest_Cover_Type_Classification/
│
├── Forest_cover_Type-classification.ipynb  
├── forest_cover_model.keras  
├── README.md  

---

## Author

**Krishna**  
Machine Learning & Data Science Enthusiast