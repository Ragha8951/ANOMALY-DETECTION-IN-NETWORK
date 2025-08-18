# ANOMALY-DETECTION-IN-NETWORK
# Autoencoder & RBM Intrusion Detection System

[**Live Demo**](https://colab.research.google.com/drive/10SO9TvWEi2EAbMzzN68_iRjjLm--g-38)

This Python project implements **two machine learning approaches** — an **Autoencoder** and **RBM (Restricted Boltzmann Machine) with Logistic Regression** — to detect network intrusions using the **UNSW-NB15 dataset**.

CLICK ON OPEN WITH COLLAB  

## Features

- Loads and preprocesses the **UNSW-NB15 training and testing datasets**.
- Encodes categorical features into numeric values.
- Normalizes feature values using **MinMaxScaler**.
- Splits data into **Training**, **Validation**, and **Testing** sets.
- Implements a **deep learning Autoencoder** for anomaly detection.
- Tracks **Loss**, **ROC-AUC**, and **Accuracy** over training epochs.
- Implements **RBM + Logistic Regression** pipeline for classification.
- Compares performance between Autoencoder and RBM approaches.
- Visualizes training curves and confusion matrices.

## Prerequisites

- Python 3.x
- Jupyter Notebook or Google Colab
- Basic knowledge of **machine learning** and **deep learning**.

## How It Works

1. **Data Loading & Preprocessing**  
   - Combines training and testing data for uniform preprocessing.  
   - Drops unnecessary columns (`id`, `attack_cat`).  
   - Encodes categorical values using `LabelEncoder`.  
   - Normalizes features with `MinMaxScaler`.

2. **Data Splitting**  
   - Divides data into training, validation, and test sets with stratified sampling.

3. **Autoencoder Training**  
   - Builds a feed-forward **Autoencoder** with dropout regularization.  
   - Trains only on **normal traffic** to learn reconstruction patterns.  
   - Uses reconstruction error to classify anomalies.  
   - Tracks **Loss**, **ROC-AUC**, and **Accuracy** each epoch.

4. **RBM + Logistic Regression Training**  
   - Creates a pipeline with **BernoulliRBM** feature extraction and Logistic Regression.  
   - Fits the model on training data for binary classification.

5. **Evaluation & Visualization**  
   - Calculates **Accuracy**, **Precision**, **Recall**, and **ROC-AUC** for both models.  
   - Displays confusion matrices.  
   - Compares Autoencoder and RBM results.

## How to Use

1. Open the [Google Colab link](https://colab.research.google.com/drive/10SO9TvWEi2EAbMzzN68_iRjjLm--g-38).
2. Upload the following datasets into the runtime:
   - `UNSW_NB15_training-set.csv`
   - `UNSW_NB15_testing-set.csv`
3. Run all cells in the notebook.
4. View:
   - Training/Validation loss curves.
   - ROC-AUC & Accuracy trends.
   - Confusion matrices.
   - Model performance comparison.

## Example Output

```
Epoch 1/20 - Train Loss: 0.0112 - Val Loss: 0.0120 - Val ROC-AUC: 0.8453 - Val Accuracy: 0.7812
...
Autoencoder Evaluation:
Accuracy: 0.7841
Precision: 0.7652
Recall: 0.8013
ROC-AUC: 0.8524

RBM Evaluation:
Accuracy: 0.7687
Precision: 0.7489
Recall: 0.7856
ROC-AUC: 0.8345
```

## Notes

- Autoencoder is **unsupervised anomaly detection** (trained on normal samples only).  
- RBM + Logistic Regression is **supervised classification**.  
- Threshold for anomaly detection is set using the **54th percentile of reconstruction errors**.

## Future Enhancements

- Implement advanced **deep autoencoders** or **variational autoencoders**.  
- Experiment with **different thresholds** for anomaly detection.  
- Use **feature selection** to reduce dimensionality before training.  
- Integrate real-time detection pipeline.

## Contribution

Contributions are welcome!  
If you find issues or have suggestions for improvements, please create a pull request or open an issue.

## Author

GitHub: [@Ragha8951](https://github.com/Ragha8951)  
Email: [ragha8951@gmail.com](mailto:ragha8951@gmail.com)

Thank you for visiting ❤️

