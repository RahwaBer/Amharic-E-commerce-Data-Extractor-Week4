## 📄 Amharic E-commerce Data Extractor

### ✅ Step 1: Data Ingestion and Preprocessing

* **Channel Selection**: Reviewed `channels_to_crawl.csv` and identified 5 target Telegram channels for data extraction.
* **Real-Time Scraper Setup**: Implemented a real-time data ingestion system using the `Telethon` library to collect:

  * Amharic messages
  * Media files (images/documents)
  * Metadata (timestamps, channel info)
* **Data Storage**: Structured messages and media paths saved.

---

### ✅ Step 2: Preprocessing

* **Text Cleaning**:

  * Normalized Amharic characters
  * Removed emojis, Latin text, and special symbols
  * Standardized whitespace
* **Tokenization**:

  * Custom whitespace-based tokenization for Ge'ez script
  * Saved as `structured_telegram_data.csv` with fields: `channel`, `date`, `media_path`, `cleaned_text`, `tokens`

---

### ✅ Step 3: CoNLL Formatting for NER

* Generated a baseline CoNLL template file (`labeled_data_template.txt`) where each token is labeled as `O` (outside any entity).
* Defined entity types according to the business objective:

  * `B-Product`, `I-Product`
  * `B-PRICE`, `I-PRICE`
  * `B-LOC`, `I-LOC`
* Built an interactive Python labeling tool using Jupyter widgets to assist with efficient manual annotation.
* Output saved to `labeled_data_final.conll.txt` for fine-tuning NER models.

