
# Dogs vs Cats Image Classifier

This project uses machine learning techniques to classify images of dogs and cats. The model leverages Principal Component Analysis (PCA) for dimensionality reduction and Support Vector Machine (SVM) for classification. The goal is to classify images into two categories: **Dogs** and **Cats**.

## Project Overview

The workflow of the project consists of the following steps:

1. **Image Preprocessing**: 
   - Resize the images to a fixed size.
   - Convert images to grayscale.
   - Flatten the images into vectors.

2. **Feature Scaling**: 
   - Standardize the pixel values of the images using `StandardScaler`.

3. **Dimensionality Reduction**:
   - Apply Principal Component Analysis (PCA) to reduce the number of features, improving model performance and reducing computational cost.

4. **Model Training**:
   - Train an SVM model with an RBF (Radial Basis Function) kernel on the processed images.

5. **Model Evaluation**:
   - Test the model using a separate test dataset and evaluate its accuracy using a confusion matrix.

## How the Code Works

1. **Loading and Preprocessing Images**  
   The images are loaded from the specified directories for both training and testing (cats and dogs). Each image is resized to **128x128** pixels and converted to **grayscale**. The images are then flattened into one-dimensional vectors for further processing.

2. **Feature Scaling**  
   To ensure the features (pixel values) are on the same scale, we use **StandardScaler** to standardize the data. This step improves the convergence of the SVM model.

3. **Dimensionality Reduction with PCA**  
   Since images can have many features (i.e., many pixels), we reduce the number of features using **Principal Component Analysis (PCA)**. PCA transforms the data into a lower-dimensional space while preserving most of the variance. The number of components is set to **150**, but you can adjust this based on your requirements.

4. **Training the SVM Classifier**  
   An **SVM** with an **RBF kernel** is trained using the preprocessed images. The SVM model is suitable for binary classification tasks like this one, where we classify the images into two categories: Dogs and Cats.

5. **Model Evaluation**  
   The model is tested on the test set, and the **accuracy** is calculated. A **confusion matrix** is generated to show how well the model performs in terms of correctly identifying cats and dogs. The matrix displays **true positives**, **true negatives**, **false positives**, and **false negatives**.

6. **Display Results**  
   The script displays some test images along with their true and predicted labels, allowing you to visually inspect the model’s predictions.

### Example Output

After running the script, you should see something like this in your terminal:

```bash
Accuracy on test set: 0.85
```
And a confusion matrix like this will be displayed:

Confusion Matrix:
[[250   5]
 [ 40 220]]
Additionally, sample test images will be shown, with titles indicating the true and predicted labels:

True: Cat, Pred: Cat
True: Dog, Pred: Dog


