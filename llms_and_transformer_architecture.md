# Module 2: Large Language Models (LLMs) & Transformer Architecture

## 1. Large Language Models (LLMs) Kya Hain?

**LLMs (Large Language Models)** Generative AI ke wo deep learning models hain jo insani bhasha (human language) ko samajhne, summarize karne, aur bilkul natural dhang se generate karne ke liye train kiye jate hain.

### "Large" Ka Matlab Kya Hai?
* **Massive Datasets:** Internet ki billions of web pages, kitabein, articles, aur code par training.
* **Billions of Parameters:** Model ke andar ke adjustable weights (jaise 7B, 70B, ya 175B parameters), jo model ki learning capacity decide karte hain.

---

## 2. The Core Foundation: Transformer Architecture

2017 mein Google ke research paper *"Attention Is All You Need"* ne AI ki duniya ko badal diya. Is paper ne **Transformer** architecture introduce kiya, jo aaj lagbhag sabhi modern LLMs (GPT, Gemini, Claude, LLaMA) ki neev hai.

### Transformers se pehle (RNNs aur LSTMs) ki samasya:
* Purane models words ko sequential (ek ke baad ek) process karte the.
* Lambe sentences mein shuruat ka context aakhir tak aate-aate bhool jate the (Long-term dependency issue).
* Parallel processing mushkil thi, isliye training bahut slow hoti thi.

---

## 3. Transformers Kaise Kaam Karte Hain?

Transformer architecture ke teen sabse mahatvapurna components hain:

### A. Tokenization
Sentence ko chhote-chhote hisson mein toda jata hai jinhe **Tokens** kehte hain.
* Example: `"Generative AI"` $\rightarrow$ `["Gener", "ative", " AI"]`

### B. Positional Encoding
Kyunki Transformer sare tokens ko ek sath (parallel) read karta hai, isliye sentence mein word ka sequence/order yaad rakhne ke liye mathematical position vectors add kiye jate hain.

### C. Self-Attention Mechanism (Sabse Important)
**Self-Attention** model ko yeh tay karne ki kshamta deta hai ki sentence ke kaun se words aapas mein closely related hain.

> **Example Sentence:**
> *"The bank of the river was muddy because of recent rain."*
> 
> Yahan Self-Attention model ko batata hai ki word **"bank"** financial institution nahi, balki **"river"** se juda hua hai.

---

## 4. LLM Training ke 3 Mukhya Charn (Stages)

LLM ko train karne ke teen main steps hote hain:

```
[Pre-training] ──▶ [Supervised Fine-Tuning (SFT)] ──▶ [RLHF / Alignment]
```

1. **Pre-training (Next-Token Prediction):**
   * Model bina kisi label wale massive data se agla word predict karna seekhta hai.
   * Yeh stage sabse mehengi aur compute-intensive hoti hai.

2. **Instruction Fine-Tuning (SFT):**
   * Model ko conversational aur question-answer format mein train kiya jata hai (Prompt $\rightarrow$ Helpful Response).

3. **RLHF (Reinforcement Learning from Human Feedback):**
   * Insani feedback ke zariye model ko safe, helpful aur non-toxic banaya jata hai taaki wo users ko harmful jawab na de.

---

## 5. LLM Architecture ke Types

| Architecture Type | Description | Use Cases | Examples |
| :--- | :--- | :--- | :--- |
| **Encoder-Only** | Text ko deeply samajhta hai | Classification, Search, Sentiment Analysis | BERT, RoBERTa |
| **Decoder-Only** | Next token generate karta hai | Text generation, Chat, Creative Writing | GPT-4, LLaMA, Gemini |
| **Encoder-Decoder** | Input samajh kar naya output banata hai | Translation, Summarization | T5, BART |

---

## 6. Summary & Key Takeaways

* LLMs bhasha ko mathematically predict karte hain using probability distributions.
* **Transformer Architecture** aur **Self-Attention** ki wajah se LLMs lambe context ko samajh paate hain.
* Modern LLMs "Pre-training + Fine-tuning + RLHF" ke process se guzarte hain.

---

## Next Recommended Topic:
* **Prompt Engineering Techniques** (Zero-shot, Few-shot, Chain-of-Thought) ya **RAG (Retrieval-Augmented Generation)**.