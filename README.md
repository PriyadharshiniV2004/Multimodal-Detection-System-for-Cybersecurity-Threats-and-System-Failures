# Multimodal Detection System for Cybersecurity Threats and System Failures

This project presents a unified deep learning-based system that detects DDoS attacks, malware infections, and system failures using heterogeneous cybersecurity datasets. It integrates CNN and LSTM models for multi-source threat detection with high accuracy and real-world applicability.

## Features

- Multi-input architecture handling three distinct data sources
- CNN-LSTM fusion for sequence learning and feature extraction
- Classification of cyber threats and system anomalies with high accuracy
- Trained on simulated datasets with approximately 99.93% training and 91.78% validation accuracy

## Model Architecture

- Three parallel branches for DDoS, Malware, and System logs  
- Each branch: Conv1D → LSTM → Dense  
- Merged via concatenation  
- Final Dense (softmax) output layer for classification

## Datasets Used

- DDoS: DrDoS_UDP (flow-based network data)  
- Malware: EMBER dataset (histograms, entropy, string features)  
- System Failures: Windows logs (event ID, CPU, RAM usage)

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

- `IT_HACKATHON.h5` – Trained Keras model (HDF5 format)

## Future Enhancements

- Replace mock data with real-world cybersecurity datasets
- Extend detection to include zero-day threats and anomalies
- Explore GRU or Transformer-based variants for further improvement

## Author

Priyadharshini V
