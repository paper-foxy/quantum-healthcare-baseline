# Quantum Machine Learning for Healthcare

## Predicting breast-cancer diagnosis with a classical and quantum-kernel baseline

This submission studies a binary healthcare classification problem: predicting whether a breast tumour is **malignant** or **benign** from the Wisconsin Diagnostic Breast Cancer dataset bundled with scikit-learn.

The project compares two deliberately similar pipelines:

1. **Classical baseline:** standardized features reduced to four principal components, followed by an RBF-kernel SVM.
2. **Quantum approach:** the same four standardized PCA features are angle-encoded into a four-qubit state. A fidelity quantum kernel is computed from the overlap of the encoded states, then used by an SVM.

The quantum integration has a clear purpose: it replaces the classical RBF similarity with a physically motivated feature-space similarity while keeping preprocessing, train/test split, and evaluation identical. The simulator is implemented directly with NumPy, so no quantum hardware or proprietary SDK is required.

> Important: this is a reproducible research prototype, not a clinical diagnostic tool. Quantum machine learning is not assumed to outperform the classical baseline; the experiment reports the measured trade-off honestly.

## Run

```bash
pip install -r requirements.txt
python run_experiment.py
```

Outputs are written to `results/`: metrics, a confusion-matrix plot, and a short comparison report.

## Evaluation

Both models use the same stratified 80/20 split (`random_state=42`) and are compared using accuracy, balanced accuracy, precision, recall, F1, ROC-AUC, fit time, and kernel evaluations. The quantum kernel is computed without test-label access and without data leakage.

## Limitations and next steps

- The statevector simulator scales exponentially with the number of qubits; PCA to four dimensions is therefore intentional.
- The dataset is small and public, and the result should not be interpreted as clinical evidence.
- A stronger follow-up would use repeated cross-validation, noise-aware hardware execution, calibration, and external clinical validation.

## Repository contents

- `run_experiment.py` — complete experiment and quantum-kernel implementation
- `requirements.txt` — minimal dependencies
- `results/` — generated after running the experiment

