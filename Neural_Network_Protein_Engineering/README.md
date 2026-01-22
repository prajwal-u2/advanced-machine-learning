# Neural Network Protein Engineering

This notebook implements transformer-based models for predicting protein activity levels from amino acid sequences, focusing on engineering nuclease enzymes (NuCB) for biofilm dispersion.

- **Notebook**: `Neural_Network_Protein_Engineering.ipynb`
- **Goal**: Build a transformer classifier to predict protein activity levels and maximize Precision@100 for identifying high-activity variants.

## What it's about

- **Manual Backpropagation**: Implement backward pass for scaled dot-product attention layer from scratch.
- **Protein Activity Classification**: Multi-class classification task predicting activity levels (non-functional → activity > A73R) from protein sequences.
- **Real-world Dataset**: Uses experimental data from wet-lab protein engineering (NuCB enzyme variants).
- **Transformer Architecture**: Build and train transformer models for sequence classification.

## How to run

1. Open the notebook: `Neural_Network_Protein_Engineering.ipynb`
2. Install dependencies (see below).
3. Download the dataset using the provided Google Drive link in the notebook.
4. Run cells sequentially. The notebook includes:
   - Attention backward pass implementation
   - Data loading and preprocessing
   - Transformer model training
   - Evaluation and Precision@100 calculation

## Dependencies

- Python 3.9+
- PyTorch
- numpy, matplotlib, pandas
- Jupyter

Install:
```bash
pip install torch numpy matplotlib pandas jupyter
```

## What we're trying to achieve

- **Understand Attention Mechanisms**: Manually implement backpropagation through attention to understand gradient flow.
- **Protein Engineering**: Predict which protein variants will have high activity (class 3: activity > A73R) to guide expensive wet-lab experiments.
- **Precision@100 Optimization**: Maximize the fraction of true high-activity proteins in the top 100 ranked candidates, simulating a fixed experimental budget scenario.

## Key Exercises

1. **Exercise 1**: Implement `attention_backward` function for scaled dot-product attention.
2. **Exercise 2-4**: Build transformer classifier, train on protein sequences, and evaluate Precision@100.

## Dataset

- **Input**: Protein sequences (amino acid sequences encoded as integers).
- **Output**: Activity class labels (0: non-functional, 1: activity > 0, 2: activity > WT, 3: activity > A73R).
- **Split**: Chronological split (G1-G3 for train/val, G4 for test).

