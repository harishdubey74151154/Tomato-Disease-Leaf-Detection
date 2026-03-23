# 🍅 Tomato Disease Detection: A Comparative Study of ML & Deep Learning

This project was developed as part of a Final Year Project (FYP) to automate the detection of 10 different tomato leaf diseases using computer vision. It tracks the evolution of the solution from traditional machine learning feature extraction to state-of-the-art Deep Learning ensembles.

---

## 📌 Project Overview
Tomato crops are vital to global food security but are highly susceptible to pathogens. This project provides a diagnostic pipeline that:
* **Solves Class Imbalance:** Balances a highly skewed dataset via targeted data augmentation.
* **Evaluates Feature Extraction:** Compares traditional methods (HOG, LBP) against Raw Pixel values and Deep Learning.
* **Implements Deep Learning:** Utilizes CNNs and Transfer Learning (MobileNet, EfficientNet, etc.).
* **Achieves High Accuracy:** Reaches a final ensemble accuracy of **96.6%**.

---

## 📂 Project Structure

### 1. Data Augmentation (`pre_main_1.ipynb`)
The original Kaggle (PlantVillage) dataset had extreme imbalances (e.g., Mosaic Virus: 373 images vs. Yellow Leaf Curl Virus: 3,208 images).
* **Method:** Used `ImageDataGenerator` from Keras.
* **Transformations:** 15° rotation, 20% width/height shifts, 20% zoom, and horizontal flipping.
* **Result:** Achieved a balanced dataset with ~2,800–3,000 images per class.

### 2. Traditional ML & Feature Extraction (`pre_main_2.ipynb`)
Before moving to Deep Learning, I experimented with traditional classifiers (Random Forest, KNN, Decision Trees, Naive Bayes).
* **HOG & LBP:** These methods yielded poor results (~9%–40% accuracy) as they failed to capture the complex visual symptoms of the diseases.
* **Normalized Raw Pixels:** Found that 32x32 normalized pixel values were the most effective representation for traditional models.
* **Top Performer:** Random Forest achieved **65% accuracy**.

### 3. Deep Learning Implementation (`Final Term Submission.ipynb`)
The core implementation focuses on Convolutional Neural Networks (CNNs) and Transfer Learning.
* **Standardization:** Images resized to 128x128.
* **Model Architecture:** * Developed a custom 7-layer CNN.
  * Integrated **Preprocessing Layers** (Resizing/Rescaling) and **Dropout** for robustness.
* **Transfer Learning:** Evaluated MobileNetV2, EfficientNetB1, DenseNet201, Xception, ResNet50, and VGG19.
* **The Ensemble:** Combined top-performing iterations to reach a final test accuracy of **96.6%**.

---

## 📊 Evaluation Metrics
The project was evaluated based on Accuracy, Precision, Recall, and F1-Score. While traditional ML peaked at 65%, the transition to Deep Learning allowed for:
* Superior spatial feature extraction.
* Better generalization across different lighting and leaf orientations.
* Significantly lower false-negative rates for critical diseases.

---

## 🛠️ Installation & Usage
### Requirements
* Python 3.8+
* TensorFlow / Keras
* OpenCV
* Scikit-learn
* Matplotlib / Seaborn

### Running the Project
1. **Dataset:** Ensure the `PlantVillage` dataset is in the root directory.
2. **Preprocessing:** Run `pre_main_1.ipynb` to generate the augmented images.
3. **ML Baseline:** Run `pre_main_2.ipynb` to view traditional ML performance metrics.
4. **Final Model:** Run `Final Term Submission.ipynb` to execute the full CNN training and evaluation pipeline.

---

## 📄 Documentation
For detailed insights into the hyperparameters, architectural choices, and full literature review, please refer to the following documents in this repository:
* `FYP CM3070 Final Report.pdf`
* `Final Term Submission Draft - Tomato Disease Detection.pdf` (Jupyter Export)

## 👨‍💻 Author
**Harish Dubey**
