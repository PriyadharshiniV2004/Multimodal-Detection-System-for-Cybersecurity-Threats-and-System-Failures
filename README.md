# Multimodal Detection System for Cybersecurity Threats and System Failures

This project presents a unified deep learning-based system that detects DDoS attacks, malware infections, and system failures using heterogeneous cybersecurity datasets. It integrates CNN and LSTM models for multi-source threat detection with high accuracy and real-world applicability.

## Features

- Multi-input architecture handling three distinct data sources
- CNN-LSTM fusion for sequence learning and feature extraction
- Classification of cyber threats and system anomalies with high accuracy
- Trained on simulated datasets with approximately 99.93% training and 91.78% validation accuracy

---

### 📂 Datasets & Preprocessing
1. **DDoS Dataset (CSV)**  
   - Selected features like packet lengths and flow duration.  
   - Label encoding: `0 = normal`, `1 = DDoS`.  
   - Normalized using `StandardScaler`.

2. **Malware Dataset (JSONL)**  
   - Features: `histogram_0`, `histogram_1`, `entropy`, `string_length_average`.  
   - Label encoding: `0 = benign`, `1 = malware`.  
   - Applied feature extraction from nested JSON fields.

3. **System Failure Dataset (CSV)**  
   - Features: `event_id`, `resource_usage`.  
   - Labels: `0 = normal`, `1 = failure`.  
   - Null values handled using median imputation.

---

## Model Architecture

- Inputs: 3 separate branches (one for each dataset).
- Layers:
  - Conv1D → LSTM → Dense (for each input).
  - Merged and passed through a `Dense(3, activation='softmax')` layer.
- Outputs: Multi-class predictions across DDoS, malware, and system failure events.

---

### ⚙️ Model Fusion & Balancing
- **Oversampling**: Upsampled smaller datasets to match the largest.
- **Padding**: Standardized feature dimensions using `pad_sequences`.
- Combined all datasets into a unified input `X_combined` and label set `y_combined`.

---

### 🧪 Training & Evaluation
- Model: Deep neural network with dropout layers to reduce overfitting.
- Loss: `binary_crossentropy`; Optimizer: `Adam` with `clipnorm`.
- Accuracy: ~99.9% (train), ~91.7% (validation).
- Tested on random samples using a custom prediction method.

## Results

| Metric              | Value     |
|---------------------|-----------|
| Training Accuracy   | 99.93%    |
| Validation Accuracy | 91.78%    |

## How to Run

1. Clone this repository
2. Open the notebook `Multimodal_Cybersecurity_Detection.ipynb`
3. Install required dependencies (`tensorflow`, `numpy`, `scikit-learn`)
4. Run all cells to preprocess data, train the model, and evaluate performance

## Output Files

- Saved as `.h5` and `.pkl` model files for reuse.
- Final shape: `X_combined: (2551041, 5, 1)` and `y_combined: (2551041, 1)`.
- `Multimodal_Cybersecurity_Detection.h5` – Trained Keras model (HDF5 format)
- `Multimodal_Cybersecurity_Detection.pkl` – pickle format

## Future Enhancements

- Replace mock data with real-world cybersecurity datasets
- Extend detection to include zero-day threats and anomalies
- Explore GRU or Transformer-based variants for further improvement
  
## Author

Priyadharshini V

## Collaborators

PraveenKumar_Gunasekaran
