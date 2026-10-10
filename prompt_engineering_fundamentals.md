# Module 3: Prompt Engineering & In-Context Learning

## 1. Prompt Engineering Kya Hai?

**Prompt Engineering** ek aisi technique aur practice hai jisme hum LLM (Large Language Model) ko structured aur clear instructions dete hain, taaki model se sabse accurate, relevant aur high-quality output mil sake.

LLMs deterministic software nahi hain; wo probability-based hote hain. Isliye aap sawal kaise puchte hain, is baat par jawab ki quality direct depend karti hai.

---

## 2. Ek Perfect Prompt ke Key Components

Ek well-structured prompt mein aamtaur par 4 cheezein hoti hain:

1. **Role (Persona):** Model ko ek role assign karein.
   * *Example:* "Act as a Senior Python Developer..."
2. **Context (Background):** Task ke peeche ka context batayein.
   * *Example:* "I am building a web app for beginners with low latency requirements..."
3. **Task (Instruction):** Saf-saf batayein ki model ko kya karna hai.
   * *Example:* "Write a function to validate email addresses."
4. **Constraints & Output Format:** Output kaisa dikhna chahiye aur kya nahi karna hai.
   * *Example:* "Return only Python code with comments, no extra conversational text."

---

## 3. Core Prompting Techniques

### A. Zero-Shot Prompting
Isme aap bina koi example diye model se seedha answer mangte hain.
```text
Prompt: Translate the following English sentence to Hindi:
"Consistency is the key to success."

Output: "निरंतरता ही सफलता की कुंजी है।"
```

---

### B. Few-Shot Prompting (In-Context Learning)
Isme aap model ko 1 ya 2 examples dete hain taaki wo pattern aur desired format samajh sake.
```text
Prompt:
Input: The movie was exciting and full of twists!
Sentiment: Positive

Input: The food took two hours to arrive and was cold.
Sentiment: Negative

Input: The design is okay, but battery life could be better.
Sentiment:
```
*Output: Neutral / Mixed*

---

### C. Chain-of-Thought (CoT) Prompting
Complex reasoning aur math problems ke liye model ko "step-by-step" sochne ke liye kehna.

* **Without CoT:** Model jaldbazi mein direct galat number predict kar sakta hai.
* **With CoT Prompt:**
  ```text
  Prompt: A shopkeeper buys 5 pens for $10 each and sells 3 of them for $15 each. 
  What is his current profit or loss? 
  Let's think step by step.
  ```
Yeh technique logic errors ko drastically kam kar deti hai.

---

### D. System Prompt vs User Prompt

| Prompt Type | Description | Example |
| :--- | :--- | :--- |
| **System Prompt** | Model ka permanent behavior, tone aur boundary set karta hai | "You are a concise tutor. Always explain concepts using bullet points and Hindi-English mix." |
| **User Prompt** | User ka actual query ya task | "What is an API?" |

---

## 4. LLM Hyperparameters (Control Knobs)

Prompts ke alawa API call karte waqt kuch parameters output ko control karte hain:

* **Temperature (0.0 to 1.0):**
  * **Low (0.0 - 0.2):** Focused, deterministic, factual tasks (Math, Coding).
  * **High (0.7 - 1.0):** Creative, diverse responses (Storytelling, Brainstorming).
* **Top-P (Nucleus Sampling):** Cumulative probability cutoff for word selection.
* **Max Tokens:** Output response ki length limit.

---

## 5. Common Pitfalls & Best Practices

| Best Practices (Karein) | Common Mistakes (Na Karein) |
| :--- | :--- |
| Vague instructions ki jagah specific constraints dein. | "Write an article on tech" (Bahut vague). |
| Delimiters (`"""`, `###`, `<xml>`) use karein input data separate karne ke liye. | Instructions aur input text ko mix kar dena. |
| Negative constraints ("Don't do X") ke bajaye Positive guidance dein ("Do Y instead"). | Model se blind assumption lene dena. |

---

## Next Roadmap Topics:
1. **RAG (Retrieval-Augmented Generation)** — Model ko custom documents/data se jodne ke liye.
2. **Fine-Tuning vs RAG vs Prompting** — Kaun sa method kab choose karein.