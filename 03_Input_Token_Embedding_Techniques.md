# 3. Input Token Embedding Techniques

## **3.1 Positional Embeddings**

### **What is it?**
Transformers process tokens in parallel, so they do not inherently know the order of words.  
Positional embeddings add information about the **position** of each token in a sequence.

### **Use**
- Enables the model to understand **word order**, **sentence structure**, and **positional dependencies**.

### **How to do it**
**A. Learned Positional Embeddings**
- The model maintains a trainable matrix mapping `position → vector`.
- Used in models like BERT.

**B. Sinusoidal Positional Embeddings**
- Uses fixed sine/cosine patterns.

$$
PE[pos, 2i] = sin(pos / (10000^(2i/dim)))  
$$
$$
PE[pos, 2i+1] = cos(pos / (10000^(2i/dim)))
$$

- Used in the original Transformer.

---

## **3.2 Subword Embeddings**

### **What is it?**
Words are broken into **subword units** (e.g., "play", "##ing").  
Each subword gets its own embedding vector.

### **Use**
- Handles rare and unseen words.
- Reduces vocabulary size.
- Captures word morphology (run → running → runner).

### **How to do it**
1. Choose a tokenizer:  
   - **BPE** (GPT)  
   - **WordPiece** (BERT)  
   - **SentencePiece** (T5, LLaMA)

2. Train tokenizer on text to learn frequent subwords.

3. Convert text to subword tokens.

4. Map tokens → embeddings using:


---

## **3.3 Embedding with Time Signal (RoPE)**

### **What is it?**
A technique that encodes position using **rotations** in embedding space.  
Instead of adding positional vectors, the model **rotates** query/key vectors based on token position.

Used in LLaMA, Mistral, GPT-J.

### **Use**
- Better long-range attention.
- Allows longer context extrapolation.
- More stable for large LLMs.

### **How to do it**
RoPE applies rotations:

$$
Rotate(q_t) = q_t * [cos(θ_t), sin(θ_t)]
$$
$$
Rotate(k_t) = k_t * [cos(θ_t), sin(θ_t)]
$$
$$
θ_t = base^( -2i/dim ) * t
$$


This implicitly encodes the position directly inside attention.

---

# **Summary Table**

| Technique | What it is | Why used | How done |
|----------|------------|----------|----------|
| **Positional Embeddings** | Add position info to tokens | Understand word order | Learned vectors or sinusoidal formulas |
| **Subword Embeddings** | Break words into subword units | Handle rare words, reduce vocabulary | Tokenizer + embedding matrix |
| **Time Signal Embeddings (RoPE)** | Position via rotation in embedding space | Long context & stable attention | Apply rotation to Q/K vectors |

