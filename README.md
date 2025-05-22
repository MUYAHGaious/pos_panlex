
````markdown
# 🌍 Multilingual POS-Aligned Dataset Generator

This project builds a multilingual dataset with words aligned by **Part of Speech (POS)** across English, French, Bambara, and Wolof. It leverages:
- **NLTK's WordNet and Treebank** for curated English words by POS
- **Meta's NLLB (No Language Left Behind)** model for translation
- **Transformers (🤗 Hugging Face)** for running the translation pipeline
- Outputs: A structured CSV with English words translated into multiple languages, grouped by POS (e.g., NOUN, VERB, etc.)

---

## 📦 Output Example

| ENG_NOUN       | FRA_NOUN   | BAM_NOUN | WOL_NOUN | ENG_VERB | FRA_VERB | BAM_VERB | WOL_VERB |
|----------------|------------|----------|----------|-----------|-----------|-----------|-----------|
| abduction      | abduction  | NA       | NA       | accept    | accepter | NA        | NA        |
| accident       | accident   | NA       | NA       | add       | ajouter  | NA        | NA        |

---

## 📁 Project Structure

```bash
.
├── english_words_by_pos.json      # Extracted English words by POS
├── multilingual_translations.csv  # Final structured CSV output
├── extract_english_words.py       # Collects words from WordNet & Treebank
├── translate_with_nllb.py         # Translates words using Meta's NLLB
└── README.md                      # This file
````

---

## 🚀 How It Works

### Step 1: Extract English Words by POS

Using:

* **WordNet** (for NOUN, VERB, ADJ, ADV)
* **Treebank corpus** (for DET, PRON, ADP, CONJ, NUM, INTJ)

The output is saved to a JSON file:

```bash
english_words_by_pos.json
```

### Step 2: Translate with NLLB

The script loads the English POS dictionary and uses the NLLB model to translate each word into:

* **French (`fra_Latn`)**
* **Bambara (`bam_Latn`)**
* **Wolof (`wol_Latn`)**

Progress is saved to:

```bash
multilingual_translations.csv
```

---

## 🛠 Installation

Make sure you're using **Google Colab** or a compatible GPU machine.

```python
# Inside a notebook cell:
!pip install transformers sentencepiece
```

---

## 📌 Usage Instructions

1. **Extract English Words**

```bash
python extract_english_words.py
```

2. **Run Translation**

```bash
python translate_with_nllb.py
```

---

## 🧠 Notes

* Words are randomly sampled (up to 500 per POS).
* If a translation fails, it returns `NA`.
* The NLLB model used: `facebook/nllb-200-distilled-600M`.

---

## 🔮 Future Improvements

* Add fallback translation strategies (e.g., synonyms, PanLex API)
* Include more languages or dialects
* Clean and filter translations using confidence scoring

---

## 👤 Author

**Your Name**
Feel free to reach out or contribute via GitHub.

```