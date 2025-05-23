
# 🧠 Multilingual POS-Aligned Dataset Builder (Colab Edition)

Easily build a **POS-aligned multilingual dataset** from English to **French (FRA)**, **Bambara (BAM)**, and **Wolof (WOL)** using:

✅ **English WordNet** & **Treebank corpora**  
✅ **POS tagging** (WordNet + Universal Dependencies)  
✅ **Meta AI’s NLLB-200 model** for efficient translation  

---

## 📚 Supported POS Categories

We support two major POS systems:  

- **WordNet POS**: `NOUN`, `VERB`, `ADJ`, `ADV`  
- **Universal Dependencies (UD) POS**: `DET`, `PRON`, `ADP`, `CONJ`, `NUM`, `INTJ`  

🔹 Each category can include up to **500 words** (customizable).  

---

## 🚀 How to Use

### 🧩 1. Open the Notebook

Run the full notebook in **[Google Colab](https://colab.research.google.com/)** or upload it yourself.  

---

### 🛠️ 2. Install Dependencies (Handled Automatically)

```python
!pip install transformers sentencepiece --quiet
```

---

### 📥 3. Extract English Words by POS

```python
import nltk
nltk.download('wordnet')
nltk.download('omw-1.4')
nltk.download('treebank')
nltk.download('universal_tagset')

# Extract up to 500 words per POS category
```

🔹 Uses:
- **WordNet** (`NOUN`, `VERB`, `ADJ`, `ADV`)
- **Treebank Corpus** (`DET`, `PRON`, etc.)

📂 **Output file**:  
```plaintext
english_words_by_pos.json
```

---

### 🌐 4. Translate with NLLB-200

The notebook loads the **`facebook/nllb-200-distilled-600M`** model via HuggingFace to:

✔ Translate words into **French (FRA), Bambara (BAM), and Wolof (WOL)**  
✔ Handle batching and retries automatically  

```python
from transformers import pipeline
# Load NLLB model and perform translations
```

---

### 💾 5. Final Dataset Output  

📂 **Output file**:  
```plaintext
multilingual_translations.csv
```

🗂 **CSV Structure** (organized by POS):  

| ENG_NOUN | FRA_NOUN | BAM_NOUN | WOL_NOUN | ENG_VERB | FRA_VERB | ... |  

---

## 📈 Progress Feedback  

Using `tqdm` for visual updates while processing:  

```python
Translating VERB: 100%|██████████| 100/100
```

---

## 💡 Customization Options

🔹 **Modify word count per POS**  
```python
max_words = 500
```  

🔹 **Adjust target languages**  
Edit the `target_languages` list.  

🔹 **Optimize runtime & memory usage**  
Enable/disable checkpointing and logging.  

---

## 🧼 File Management  

All intermediate and final files (`.json`, `.csv`) are saved in **Colab’s `/content/` directory**. You can download or upload them to Drive as needed.  

---

## ✅ Done!  

Once completed, you’ll have a **high-quality POS-aligned multilingual dataset**, ideal for:  

✨ NLP modeling  
✨ Machine translation research  
✨ Low-resource language studies  

---

### 🔗 References  

🔹 [Meta AI’s NLLB-200](https://huggingface.co/facebook/nllb-200-distilled-600M)  
🔹 [NLTK WordNet](https://www.nltk.org/howto/wordnet.html)  
🔹 [Universal POS Tagset](https://universaldependencies.org/u/pos/)  

---

## 👤 Authors  

- [Muyah Gaious](https://github.com/MUYAHGaious) – Software Developer (AI & Backend Systems).  
- [Nichoh Elmic](https://github.com/Nichoh-Elmic) – Web Technologies & DevOps Enthusiast.  

---

```
