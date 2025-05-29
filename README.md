Sure! Here's a clear and professional English description for your GitHub project:

---

## 🐚 Abalone Age Classification Using Neural Networks

This project focuses on building a neural network capable of classifying the **age group** of abalones into three categories: **Young**, **MiddleAge**, and **Old**.

### 📊 Problem

The original dataset is **highly imbalanced**:

* \~2,000 samples each for **Young** and **MiddleAge**
* Only \~36 samples for **Old**

This imbalance posed significant challenges in achieving fair and accurate classification across all classes.

---

### 🧠 Initial Model (Imbalanced Dataset)

**Architecture:**

* Input layer
* Hidden layer 1: 16 neurons, ReLU, Dropout 0.1
* Hidden layer 2: 32 neurons, ReLU, Dropout 0.1
* Output layer: Softmax
* **Batch Normalization** after each layer

**Configuration:**

* Optimizer: Adam
* Loss: Categorical Cross-Entropy
* Learning Rate: Decaying schedule
* Epochs: 450 (Early stopping at 271)
* Batch size: 32

Despite fine-tuning, this setup struggled due to the class imbalance.

---

### 🔁 Balanced Dataset: `ShuffledDataset.csv`

To address the imbalance, I created a **modified and shuffled version** of the dataset.

**Updated Architecture:**

* Input layer
* Hidden layer 1: 64 neurons, ReLU, Dropout 0.3
* Hidden layer 2: 32 neurons, ReLU, Dropout 0.2
* Output layer: Softmax
* **Batch Normalization** included

**Configuration:**

* Optimizer: Adam
* Loss: Categorical Cross-Entropy
* Learning Rate: Decaying schedule
* Epochs: 100 (with Early Stopping)
* Batch size: 32

---

### ✅ Final Results

With the balanced dataset and improved architecture, the model achieved:

* **Precision**: 0.86
* **Recall**: 0.80
* **F1-Score**: 0.82
* **Loss**: 0.04

---

### 📁 Files

* `imbalanced_model.ipynb`: First model on original dataset
* `balanced_model.ipynb`: Improved model using `ShuffledDataset.csv`
* `ShuffledDataset.csv`: Modified dataset with better class balance

---

