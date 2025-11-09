# ✨ **LoRA (Low-Rank Adaptation)**
LoRA fine-tunes large models by **freezing the base model weights** and injecting **low-rank trainable weight** matrices.
- **Uses low-rank updates instead of updating full weights**

---

# ⚙️ **How It Works**

## ✅ **Step-1: Track all weight changes**
Normally weight updates look like:

$$
W = W_0 + \Delta W
$$

LoRA freezes **$W_0$** and replaces the full update with a compact representation:

$$
\Delta W \text{ is represented as a low-rank matrix}
$$

---

## ✅ **Step-2: Matrix decomposition part (Low-Rank Trick 📐)**
LoRA forces the update to be low-rank:

$$
\Delta W = B A
$$

Where:

- $A \in \mathbb{R}^{r \times k}$
- $B \in \mathbb{R}^{d \times r}$
- **$r \ll \min(d, k)$** (tiny rank)

This reduces parameters from:

$$
d \times k \quad \text{to} \quad r(d + k)
$$

which is **much smaller** ✅

---

## ✅ **Step-3: Add Base Model Weights + LoRA Weights**
During the forward pass the effective weight becomes:

$$
W_{\text{eff}} = W_0 + B A
$$

- **\(W_0\)** stays frozen  
- Only **A** and **B** are trained  
- Output is equivalent to a full fine-tune but far cheaper 🚀

---

### 🧩 Summary
- **LoRA = Lightweight fine-tuning**

- **Much faster, cheaper, and memory-efficient**

