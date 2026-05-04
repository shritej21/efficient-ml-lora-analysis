# Efficient ML Systems Project  
## Parameter-Efficient Fine-Tuning using LoRA

### 📌 Overview
This project evaluates different fine-tuning strategies for large language models on the Amazon Polarity dataset. The goal is to compare performance and efficiency across:

- Head-only training  
- LoRA (Low-Rank Adaptation) with ranks r = 4, 8, 16  
- Full fine-tuning  

We analyze these methods across multiple dataset sizes:
- 1%
- 5%
- 10%
- 100%

---

### ⚙️ Methods Compared

| Method        | Description |
|--------------|------------|
| Head-only    | Only classifier head is trained |
| LoRA         | Parameter-efficient fine-tuning |
| Full FT      | Entire model is fine-tuned |

---

### 📊 Metrics Evaluated

- Accuracy  
- F1 Score (Macro)  
- Training Time  
- Trainable Parameters  
- GPU Memory Usage  

---

### 📁 Project Structure
```
├── organized_1pct_5pct_10pct.ipynb
├── organized_amazon_polarity_100pct_head_only.ipynb
├── organized_amazon_polarity_100pct_lora.ipynb
├── organized_amazon_polarity_100pct_full_finetune.ipynb
├── results_analysis.ipynb
├── summaries.json
├── final_results.csv
├── README.md
└── requirements.txt
```

---

### 🚀 How to Run

1. Install dependencies:
```bash
pip install -r requirements.txt
```
2. Run experiments notebooks:
Open and execute notebooks for each training method.
3. Generate results:
   Run results_analysis.ipynb to:
      Convert results to DataFrame
      Generate graphs
      Save outputs
---

### 📈 Key Findings
Full fine-tuning achieves the highest accuracy but is computationally expensive.
LoRA achieves comparable performance with significantly fewer parameters.
Head-only training is fastest but underperforms in accuracy.

---

### 👉 Conclusion:
LoRA provides the best trade-off between efficiency and performance.

---

### 🧠 Insights
LoRA reduces trainable parameters by ~98% compared to full fine-tuning.
Training time is significantly reduced with minimal accuracy loss.
Increasing LoRA rank slightly improves performance but increases cost.

---

###🖥️ Environment
Python 3.8+
Google Colab (recommended)
GPU (T4 / A100 preferred)

---

###📌 Notes
All results are reproducible using provided notebooks.
Ensure GPU is enabled for faster execution.

---

###👨‍💻 Author
Shritej Vasal
Harsh Patel
