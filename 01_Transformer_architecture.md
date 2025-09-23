# ⚡ Transformer Architecture  

A well-structured breakdown of the **Transformer Architecture** and its main components:

## 1️⃣ Transformer Architecture Setup  
- High-level overview of the Transformer model  
- Consists of **Encoder** and **Decoder** blocks  

## 2️⃣ Encoder Setup  
- Multiple identical layers  
- Each layer has:  
  - Self-Attention  
  - Feed Forward Network  
  - Add & Normalize  

## 3️⃣ Self-Attention Mechanism  
- Queries, Keys, and Values  
- Scaled Dot-Product Attention  
- Multi-Head Attention  

## 4️⃣ Add & Normalization  
- Residual connections  
- Layer normalization for stable training  

## 5️⃣ Decoder Setup  
- Stacked decoder layers  
- Masked self-attention for autoregressive behavior  
- Encoder-Decoder attention for context  
- Feed Forward + Add & Normalize  

## 6️⃣ Input Embedding  
### 6.1 Word Embedding 🔤  
- Converts tokens/words into dense vectors  

### 6.2 Positional Embedding 📍 
- Injects positional information  
- Captures sequence order  

### 6.3 Embedding with Time Signal ⏳ 
- Combines embeddings with time-based signals  
- Improves temporal/sequence understanding  
