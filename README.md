# Parameter-Optimization-of-SVM
# SVM Optimization on Letter Recognition Dataset

This project applies Support Vector Regression (SVR) to a multi-class classification problem using the *Letter Recognition* dataset. The goal is to evaluate the model's performance over 10 randomized 70-30 train-test splits, optimize hyperparameters using GridSearchCV, and visualize the convergence of accuracy over increasing training sizes.

---

## Dataset

The dataset used is the *UCI Letter Recognition Dataset*, which contains 20,000 samples of capital letters (A–Z) represented by 16 numerical features extracted from pixel images.

- *Total Samples:* 20,000
- *Features:* 16
- *Target Classes:* 26 (A to Z)
- *Source:* [UCI Repository - Letter Recognition](https://archive.ics.uci.edu/ml/datasets/letter+recognition)

---

## Methodology

1. *Label Encoding:* The alphabet labels are encoded to numerical values (0–25).
2. *Model:* Support Vector Regression (SVR) is used for prediction.
3. *Hyperparameter Tuning:* GridSearchCV is used with:
   - kernel: ['linear', 'rbf', 'poly']
   - C: [0.1, 1, 10]
   - epsilon: [0.01, 0.1, 0.5]
4. *Evaluation:* The accuracy is computed by rounding and clipping predicted outputs to the nearest class.
5. *Convergence Plot:* For the best-performing model, a graph is plotted to show accuracy as training data increases from 1% to 100%.

---

##  Files

- svm_letter_optimization.py: Main Python script.
- letter-recognition.csv: Dataset (must be in the same folder).
- svm_results.csv: Accuracy and best parameters for each of 10 runs.
- convergence_graph.png: Convergence graph of accuracy for the best sample.

---

## Sample Output (Top 3 Results)

| Sample | Accuracy (%) | Kernel | C   | Epsilon |
|--------|--------------|--------|-----|---------|
| S1     | 86.45        | rbf    | 10  | 0.1     |
| S2     | 85.32        | poly   | 1   | 0.01    |
| S3     | 87.02        | rbf    | 10  | 0.01    |

---

##  How to Run

1. Clone this repo or copy the files.
2. Ensure the dataset file is named letter-recognition.csv and placed in the same directory.
3. Run the script:

```bash
python svm_letter_optimization.py
