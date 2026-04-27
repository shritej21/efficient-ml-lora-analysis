# CS-595 Final Project  
## LoRA vs Full Fine-Tuning vs Head-Only  
### A Practical Efficiency Analysis for Transformer Adaptation

---

## 📌 Project Type
**Engineering / Measurement Study**

---

## 📊 Overview

This project presents a systematic evaluation of three fine-tuning strategies for transformer models:

- **Full Fine-Tuning (Full FT)**
- **LoRA (Low-Rank Adaptation)**
- **Head-Only Tuning**

The goal is to analyze the **trade-offs between model performance and system efficiency**, focusing on:

- Accuracy and Macro-F1
- Training time
- GPU memory usage
- Number of trainable parameters

All experiments are conducted using **DistilBERT** on the **Amazon Polarity dataset** across multiple data scales (1%, 5%, 10%, and 100%).

---

## 📂 Repository Structure
```
efficient-ml-lora-analysis/
│
├── README.md
├── requirements.txt
│
├── notebooks/
│ ├── 1pct-5pct-10pct.ipynb
│ ├── amazon_polarity_100pct_full_finetune.ipynb
│ ├── amazon_polarity_100pct_head_only.ipynb
│ └── amazon_polarity_100pct_lora.ipynb
│
├── data_outputs/
│ └── summaries.json
│
├── results/
│ ├── main_compare_f1.png
│ ├── main_compare_train_time.png
│ ├── memory_vs_split.png
│ ├── f1_vs_time_scatter.png
│ └── final_100pct_three_panel.png
│
├── report/
│ └── final_report.pdf

```
---

## ⚙️ Setup Instructions

1. Clone the repository:

```bash
git clone https://github.com/your-username/efficient-ml-lora-analysis.git
cd efficient-ml-lora-analysis
```
2. Install dependencies:
```
pip install -r requirements.txt
```
## ▶️ Running Experiments

All experiments are implemented as Jupyter notebooks.

### Steps:

1. Navigate to the `notebooks/` folder  
2. Run the notebooks sequentially:

- `1pct-5pct-10pct.ipynb` → Small-scale experiments  
- `amazon_polarity_100pct_head_only.ipynb`  
- `amazon_polarity_100pct_lora.ipynb`  
- `amazon_polarity_100pct_full_finetune.ipynb`  

Each notebook corresponds to a specific method and dataset size.

---

## 📊 Results and Outputs

All experimental results are aggregated in:
```
data_outputs/summaries.json
```
This file contains:

- Training time (seconds)
- Peak GPU memory usage (MB)
- Accuracy
- Macro-F1 score
- Number of trainable parameters

Generated plots are stored in:
```
results/
```
---

## 📈 Evaluation Metrics

We evaluate both performance and efficiency.

### Performance Metrics:
- Accuracy  
- Macro-F1 Score  

### System Metrics:
- Training Time  
- GPU Memory Usage  
- Trainable Parameters  

---

## 🔁 Reproducibility

This project ensures reproducibility through:

- Fixed dataset splits: **1%, 5%, 10%, 100%**  
- Consistent training configuration (**2 epochs**)  
- Same model across all experiments (**DistilBERT**)  
- Unified evaluation metrics (**Macro-F1, Accuracy**)  
- Centralized result storage (`summaries.json`)  

### To reproduce results:

1. Run the notebooks  
2. Compare outputs with values in `summaries.json`  

---

## 🧠 Key Findings

- **LoRA achieves near Full Fine-Tuning performance**  
  - Within ~0.002–0.004 Macro-F1 difference  

- **Significant efficiency gains**  
  - ~1% trainable parameters vs 100% in Full FT  
  - Up to ~6× faster training at full dataset scale  

- **Head-only tuning**  
  - Most efficient  
  - But significantly lower performance  

- **Best trade-off**  
  - LoRA provides the optimal balance between performance and efficiency  

---

## ⚠️ Notes

- Experiments on **1%, 5%, and 10%** were conducted on a **T4 GPU**  
- **100% dataset experiments** were conducted on an **H100 GPU**  
- Hardware differences may influence memory and runtime comparisons  

---

## 📄 Report

The complete project report is available at:
```
report/final_report.pdf
```

---

## 👥 Team

- Shritej Vijay Vasal (A20586589)  
- Harsh Patel (A20593019)  

---

## 📌 Acknowledgements

- HuggingFace Transformers  
- PEFT (LoRA implementation)  
- Amazon Polarity Dataset  
