# ⭐ LLM Compression Techniques (Complete Overview)

LLM compression aims to reduce:
- Model size (RAM / VRAM)
- Latency
- Inference cost
- Deployability (edge/mobile)

Below are all major categories of compression techniques used in LLMs.

---

# 1️⃣ Quantization
Reduces numerical precision of weights/activations.

### Types:
- Post-Training Quantization (PTQ)  
- Quantization-Aware Training (QAT)
- Dynamic Quantization
- Static Quantization
- Weight-Only Quantization (GPTQ)
- Groupwise Quantization
- 4-bit Quantization (QLoRA)
- 3-bit/2-bit Quantization (experimental)

**Benefits:** 4×–8× smaller models, faster inference  
**Tools:** GPTQ, AWQ, GGUF, BitsAndBytes

---

# 2️⃣ Pruning
Removes unnecessary weights or components.

### Types:
- Weight pruning  
  - Unstructured pruning  
  - Structured pruning  
- Filter pruning  
- Attention head pruning  
- Block pruning  
- Activation pruning  

**Benefit:** Smaller + faster model without changing architecture.

---

# 3️⃣ Knowledge Distillation
Train a smaller **student** model to mimic a larger **teacher**.

### Approaches:
- Logit distillation  
- Feature distillation  
- Layer distillation  
- Task distillation (teacher generates synthetic data)

**Benefit:** Smaller model retains ~90% performance of teacher.

---

# 4️⃣ Low-Rank Factorization (LoRA-based Compression)
Decompose large weight matrices into low-rank matrices.

### Includes:
- LoRA  
- QLoRA  
- ReLoRA  
- DoRA (Weight Decomposition)
- SVD-based Compression
- Tensor decomposition (CP, Tucker)

**Benefit:** Dramatically reduces trainable parameters.

---

# 5️⃣ Sparsity
Introduce zeros in weights/activations to reduce computation.

### Types:
- Static sparsity  
- Dynamic sparsity  
- Mixture-of-Experts (MoE) sparsity  

**Benefit:** Works well with sparse-matrix hardware.

---

# 6️⃣ Parameter Sharing
Reuse parameters across layers.

### Techniques:
- ALBERT-style layer sharing  
- Attention head sharing  
- Shared FFN blocks  

**Benefit:** Reduces total model size significantly.

---

# 🔥 Most Common in LLM Interviews
- Quantization (INT8/INT4/QLoRA/GPTQ/AWQ)  
- Pruning  
- Distillation  
- LoRA / QLoRA  
- Sparsity / MoE  
- SVD decomposition  

Mastering these is enough for most interviews.

---
