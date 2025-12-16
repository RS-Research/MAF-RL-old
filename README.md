# MAF-RL: Multi-Source Actor–Critic Fusion Reinforcement Learning

This repository contains the **official implementation of MAF-RL**, a multi-source Actor–Critic reinforcement learning framework for **sequential recommendation**.
MAF-RL formulates recommendation as a **multi-source Markov Decision Process (MDP)** and learns when to **repeat** or **innovate** by fusing heterogeneous signals into a unified RL state.

---

## 📌 Key Features

* Multi-source state construction (sequential, textual, visual, contextual, relational)
* Actor–Critic reinforcement learning with PPO
* Multi-objective reward balancing accuracy, repetition, and novelty
* Scalable training with candidate generation and re-ranking
* Reproducible experiments on public benchmarks

---

## 📁 Repository Structure

```
MAF-RL/
│
├── data/                   # Dataset preprocessing scripts and instructions
├── configs/                # YAML configuration files (hyper-parameters)
├── models/                 # Actor, Critic, fusion modules
├── trainers/               # PPO training and optimization logic
├── evaluation/             # Metrics: HR, NDCG, RR, Novelty
├── scripts/                # Training and evaluation entry points
├── utils/                  # Helper functions and logging
├── requirements.txt
└── README.md
```

---

## 📊 Supported Datasets

The following public datasets are used in the paper:

* **MovieLens-1M**
* **Amazon-Books**
* **Yelp**

Due to licensing restrictions, raw datasets are **not redistributed**.
Instructions for downloading and preprocessing each dataset are provided in the `data/` directory.

---

## ⚙️ Installation

### 1. Clone the repository

```bash
git clone https://github.com/RS-Research/MAF-RL.git
cd MAF-RL
```

### 2. Create a virtual environment (recommended)

```bash
conda create -n maf-rl python=3.9
conda activate maf-rl
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

---

## 🚀 Running Experiments

### Training MAF-RL

```bash
python scripts/train.py --config configs/maf_rl.yaml
```

### Evaluating a trained model

```bash
python scripts/evaluate.py --config configs/maf_rl.yaml
```

All hyper-parameters used in the paper (learning rates, reward weights, PPO settings, etc.) are specified in the configuration files.

---

## 📈 Evaluation Metrics

The implementation supports the following metrics:

* **HR@K** (Hit Rate)
* **NDCG@K**
* **RR@K** (Repetition Rate)
* **Novelty@K**

Results are reported as **mean ± standard deviation over five random seeds**, following the experimental protocol described in the paper.

---

## 🔁 Reproducibility

To ensure full reproducibility:

* All experiments are run with **five different random seeds**
* Final RL performance is averaged over the last training epochs
* Statistical significance is assessed using **paired two-tailed t-tests**
* Configuration files exactly match those reported in the paper

---

## ⚖️ Fairness and Diversity

MAF-RL includes a novelty-aware reward to mitigate over-repetition.
Additional diversity or fairness constraints (e.g., **MMR re-ranking**) can be applied at inference time without modifying the training procedure.

---

## 📄 Citation

If you use this code in your research, please cite:

```
@article{maf_rl,
  title={MAF-RL: Multi-Source Actor–Critic Fusion Reinforcement Learning for Sequential Recommendation},
  author={Mehdi Hosseinzadeh, Rizwan Naqvi, Amir Masoud Rahmani, Gholamreza Zare, Pegah Malekpour Alamdari, Parisa Khoshvaght, Aso Darwesh, Thantrira Porntaveetus, Sang-Woong Lee},
  journal={...},
  year={2025}
}
```

---

## 📬 Contact

For questions or issues, please open an issue or contact the authors via GitHub.

---

## 📜 License

This project is released for **academic and research use only**.
Please check dataset licenses before use.

