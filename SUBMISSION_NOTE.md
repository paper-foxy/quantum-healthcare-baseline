# Submission summary

**Title:** Quantum Fidelity Kernels for Breast-Cancer Diagnosis Classification

**Problem:** Binary classification of malignant versus benign tumours using the Wisconsin Diagnostic Breast Cancer dataset.

**Classical baseline:** StandardScaler + four-component PCA + RBF SVM.

**Quantum contribution:** The same four PCA features are angle-encoded into four simulated qubits. A fidelity kernel, based on squared state overlap after an entangling phase layer, replaces the RBF similarity inside an SVM.

**Measured results on the fixed stratified 80/20 split:**

- Classical accuracy: 0.9649; ROC-AUC: 0.9931; F1: 0.9726.
- Quantum-kernel accuracy: 0.6579; ROC-AUC: 0.6653; F1: 0.7547.

The experiment demonstrates a working, comparable quantum pipeline and makes the limitation explicit: on this small dataset and feature map, the quantum model does not beat the classical baseline. This is a valid result because the challenge asks for a measurable comparison and a justified quantum integration, not an unsupported claim of advantage.

