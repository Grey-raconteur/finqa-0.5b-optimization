# FinQA Stress-Testing: Evaluating Qwen-0.5B on Multi-Step Financial Reasoning

This repository contains a comprehensive evaluation and optimization of the **Qwen 2.5 0.5B Instruct** model on the **FinQA** dataset. The project explores the limitations of Small Language Models (SLMs) in structured data retrieval and introduces a novel "Row-Header Injection" strategy to improve accuracy.

## 📊 Project Overview
FinQA is a challenging benchmark requiring multi-step numerical reasoning over heterogeneous data (tables + text). This project was divided into three distinct layers of analysis:

- **Layer 1 & 2 (Baseline & Forensic):** Diagnosed a 9% baseline accuracy. Identified that **73.6% of errors** were due to "Retrieval Drift," where the model failed to map questions to the correct 2D table coordinates.
- **Layer 3 (Innovation):** Implemented **Row Header Injection** (repeating metric labels in every row) to anchor the model's attention.
- **Results:** Successfully increased execution accuracy from **9.0% to 26.0%** without fine-tuning or increasing model size.

## 📂 File Directory
- `FinQA_new.ipynb`: The main research notebook containing evaluation loops and the Layer 3 implementation.
- `Lqyer3_summary.txt`: Detailed write-up of the "Row-Header Injection" process and final findings.
- `Layer2_summary.txt`: Forensic analysis of baseline failures and error taxonomy.
- `finqa_layer3_final_results.csv`: Final predictions and correctness logs (26% Accuracy).
- `finqa_results_all.csv`: Full evaluation results of the baseline model.
- `finqa_ablation_detailed_results.csv`: Data from the ablation study (Full vs. Table-Only vs. Text-Only).

## 🔗 Attribution
This project uses data from the **FinQA Paper**:
* **Original Paper:** [FinQA: A Dataset of Numerical Reasoning over Financial Data](https://arxiv.org/abs/2109.00122)
* **Original Repository:** [https://github.com/czyssrs/FinQA](https://github.com/czyssrs/FinQA)

---