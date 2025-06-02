# 🧪 AsthmaSimLab: Simulation of Multi-Modal Asthma Profiles and Drug Response in Latent Space

**AsthmaSimLab** is a generative modeling and simulation framework that integrates transcriptomic and CT-derived embeddings to simulate patient trajectories and predict drug effects in asthma. Built on top of **Geneformer** and **MedicalNet**, this pipeline enables in silico patient modeling, stratified drug prioritization, and embedding-driven data augmentation.

---

## 🎯 Objectives
- Integrate transcriptomic (Geneformer) and CT (MedicalNet) embeddings into a shared latent space
- Simulate transitions between asthma states (e.g., T2-low to T2-high, non-responder to responder)
- Predict drug-induced shifts using L1000 transcriptomic signatures
- Generate synthetic patient embeddings for data augmentation and hypothesis testing

---

## 🧬 Inputs
- CT scans preprocessed and embedded using **AsthmaCT-Net**
- Bulk RNA-seq profiles embedded using fine-tuned **Geneformer**
- Drug transcriptomic signatures (LINCS/CMap)
- Clinical labels (e.g., endotype, response, inflammation markers)

---

## ⚙️ Core Modules

### `fusion/`
- Combine CT and gene embeddings per patient
- Apply PCA or shared latent space projection

### `simulation/`
- Interpolate between patients (e.g., simulate response transitions)
- Apply drug shift vectors in embedding space

### `generation/`
- Variational autoencoder (VAE) to sample synthetic profiles
- Conditional generation based on clinical labels

### `evaluation/`
- UMAP and trajectory plots of real vs. synthetic data
- Cosine similarity shift scores
- Drug ranking and target embedding alignment

---

## 📁 Folder Structure
```
├── data/
│   ├── ct_embeddings.npy
│   ├── gene_embeddings.npy
│   ├── drug_signatures.npy
│   └── metadata.csv
├── fusion/
│   └── fuse_embeddings.py
├── simulation/
│   └── interpolate_and_shift.py
├── generation/
│   └── train_vae.py
├── evaluation/
│   └── visualize_embeddings.ipynb
├── notebooks/
│   └── AsthmaSimLab_Overview.ipynb
├── results/
├── requirements.txt
└── README.md
```

---

## 🛠 Dependencies
```bash
transformers
torch
scikit-learn
numpy
pandas
seaborn
umap-learn
scanpy
```

---

## 📊 Outputs
- Synthetic embeddings aligned with real patient data
- Ranked list of drugs predicted to normalize disease embeddings
- UMAPs and similarity plots

---

## 📜 License
MIT License

---

## 📌 References
- Theodoris et al., Nature (2023) — Geneformer
- Tencent AI Lab — MedicalNet
- LINCS/CMap project
# AsthmaSimLab
