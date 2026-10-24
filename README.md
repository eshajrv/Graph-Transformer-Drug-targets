# Graph Transformers for Drug Target Discovery

Predicting which proteins are likely drug targets from their position in a protein-protein interaction (PPI) network. Done at Scripps Research (Su and Wu Computational Biology Lab).

**Approach**
1. Embed every node of the PPI network with node2vec (128 dimensions).
2. Label known drug targets and sample non-targets.
3. Train a transformer over the embeddings to classify target vs. non-target.

**Result:** ROC AUC **0.94** on the held-out test set (`ContTransformer.ipynb`).

| Notebook | What it does |
|---|---|
| `ContTransformer.ipynb` | Continuous-feature transformer (PyTorch, einops, hyper-connections): data prep, training loop, and evaluation (precision, recall, F1, ROC and PR AUC) |
| `tab_transformer.ipynb` | Baseline with `tab-transformer-pytorch` using the same embeddings |

**Stack:** PyTorch · node2vec · scikit-learn · pandas

Input data (PPI embeddings and bioDBnet ID mappings) is not included in this repo. Update the file paths in the notebooks to point to your own copies.
