# 🧠 PEFT

- **PEFT** - **Parameter-Efficient Fine-Tuning**   
- PEFT allow you to **adapt large pre-trained models** (like GPT, BERT, or LLaMA) **without updating all of their parameters**.
- Instead of retraining **billions of weights**, PEFT methods train **a very small subset of parameters** (or add small new ones), which makes fine-tuning **faster, cheaper, and more memory-efficient** 💡

---

## ⚙️ **Motivation**

Large language models (LLMs) have **billions of parameters** — fine-tuning all of them:
- 🧮 Needs massive GPU memory  
- 🕒 Takes long training time  
- 💸 Is very expensive
  
But often, we just need the model to learn **small domain-specific adjustments**, not to forget everything it already knows.  
That’s where **PEFT** helps.

---

## 🧩 **How PEFT Works**

### 🔹 Instead of:
Fine-tuning the full model (updating all weights \( W \))

### 🔹 PEFT does:
Freeze the original weights \( W \) and only:
- Train a **small number of new parameters**, or  
- Add small **adapter layers**, or  
- Use clever math (like **low-rank matrices**) to approximate updates  

---

## 🧰 **Popular PEFT Methods**

| Method | Concept | Description |
|---------|----------|--------------|
| **LoRA (Low-Rank Adaptation)** | Adds small trainable matrices inside transformer layers | Learns only low-rank updates to weights |
| **Prefix Tuning** | Adds learnable “prefix” tokens to attention layers | Model learns task-specific context without modifying base weights |
| **Prompt Tuning** | Adds trainable prompt embeddings | Only the prompts are trained; model remains frozen |
| **Adapters** | Inserts small bottleneck layers between model layers | Only adapter weights are trained |
| **BitFit** | Trains only the bias terms | Simplest, most lightweight approach |

---

## 🧮 **Example**

Imagine a 7B-parameter LLM:
- Full fine-tuning → update all 7B parameters  
- LoRA fine-tuning (a PEFT method) → train only ~30M parameters  
That’s **over 200× smaller**, yet it can achieve **nearly the same accuracy** for many tasks.

---
