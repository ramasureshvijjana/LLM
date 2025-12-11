## 🔹 What Are Subword Embeddings?
Instead of using full words or single characters, LLMs break words into **small meaningful pieces** called *subwords* (e.g., "playing" → "play" + "ing").

Each subword gets an embedding (vector), and combined they represent the whole word.

---

## 🔹 Why Do We Need Them?
- Handle rare words  
- Handle new/unseen words  
- Reduce vocabulary size  
- Improve model performance

Example:  
“unbelievable” → “un” + “believe” + “able”  
Even if “unbelievable” is unseen, model can understand it.

---

## 🔹 How It Works (Simple)
1. Tokenizer splits text into subwords  
2. Each subword has an embedding  
3. These embeddings represent the full word when processed

Common tokenizers:
- BPE (GPT)
- WordPiece (BERT)
- SentencePiece (T5)

---

## 🔹 One-Line Summary
**Subword embeddings represent words using smaller chunks so models can handle any new or complex word efficiently.**
