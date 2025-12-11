## 🔹 What Are Positional Embeddings?
Transformers don’t read text in order automatically.  
So **positional embeddings** tell the model *where each token is located* in the sequence.

## 🔹 Why Do We Need Them?
Without position info, the model can’t understand:
- word order  
- sequence meaning  
- relationships like “A → B → C”

Example:  
“Dog bites man” vs “Man bites dog”  
Same words, **different position → different meaning**.

## 🔹 How They Work (Simple)
For every token, the model adds a **position vector**:

token_embedding + position_embedding = final_embedding

This helps the model know:
- token 1  
- token 2  
- token 3  
… etc.

## 🔹 Types of Positional Embeddings
1. **Learned positional embeddings**  
   - Model learns position weights during training  
   - Used in BERT

2. **Sinusoidal positional embeddings**  
   - Fixed pattern using sine/cosine functions  
   - Used in original Transformers  
   - Helps extrapolate to longer sequences

## 🔹 One-Line Summary
**Positional embeddings give tokens a sense of order so the Transformer can understand sequences correctly.**
