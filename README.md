# AI-Powered-Multilingual-PDF-Translator
Multilingual PDF Processor is a Python tool that extracts text from PDFs, summarizes content, detects the original language, translates it into English, and generates a clean Unicode PDF. Ideal for researchers, students, and professionals saving time translating and understanding multilingual documents.

## Table of Contents 📚

1. [Features](#features-)
2. [Installation](#installation-)
3. [Usage](#usage-)
4. [Folder Structure](#folder-structure-)
5. [Configuration](#configuration-)
6. [Dependencies](#dependencies-)
7. [How It Works](#how-it-works-)
8. [Example](#example-)
9. [Contributing](#contributing-)
10. [License](#license-)

---

## Features ✨

* **Text Extraction:** Extracts text from PDFs using `PyPDF2`. For scanned PDFs, it uses OCR via `pytesseract`.
* **Automatic Summarization:** Summarizes large documents using TextRank (`summa`).
* **Language Detection:** Detects the original language using `langdetect`.
* **Multilingual Translation:** Translates text into English using `googletrans`.
* **Unicode PDF Generation:** Generates a clean PDF with full Unicode support using `fpdf2` and DejaVuSans font.
* **Asynchronous Translation:** Uses `asyncio` to speed up translation for large texts.
* **Keyword Extraction:** Extracts unique words from the document for quick reference.
* **Fallbacks:** Provides fallback summaries if automated summarization fails.

---

## Installation 🛠️

1. **Clone the repository**:

```bash
git clone https://github.com/yourusername/multilingual-pdf-processor.git
cd multilingual-pdf-processor
```

2. **Install dependencies**:

```bash
pip install -r requirements.txt
```

3. **Download the Unicode font**: Place `DejaVuSans.ttf` in the `fonts/` folder (required for Unicode support).

---

## Usage 🚀

1. Place your PDF files in the `sample_pdfs/` folder.
2. Update `main.py` or `config.py` with the correct paths for input PDF and output PDF.
3. Run the main program:

```bash
python main.py
```

4. Output: A translated, summarized PDF will be generated in the specified output folder (`translated_output.pdf`).

---

## Folder Structure 📂

```
multilingual-pdf-processor/
│
├── fonts/                 # Unicode fonts (DejaVuSans.ttf)
├── sample_pdfs/           # Example PDFs to test
├── main.py                # Main program
├── config.py              # Configurable paths
├── requirements.txt       # Python dependencies
├── README.md              # This file
└── .gitignore             # Files to ignore
```

---

## Configuration ⚙️

* `FONT_PATH`: Path to the DejaVuSans font for Unicode support.
* `DEFAULT_INPUT_PDF`: Default input PDF file path.
* `DEFAULT_OUTPUT_PDF`: Output path for the generated translated PDF.

All paths can be modified in `config.py` to suit your environment.

---

## How It Works 

1. **PDF Processing:** Extracts text from each page of the PDF. If no text is found, performs OCR on images.
2. **Text Cleaning:** Converts text to lowercase, removes punctuation, and extracts keywords.
3. **Summarization:** Uses TextRank algorithm to summarize the content.
4. **Language Detection & Translation:** Detects the source language and translates to English using `googletrans`.
5. **PDF Generation:** Generates a clean, Unicode-supported PDF using `fpdf2`. Long strings are automatically wrapped for readability.

---

## Dependencies 

* Python 3.9+
* [PyPDF2](https://pypi.org/project/PyPDF2/) – PDF reading and text extraction
* [pytesseract](https://pypi.org/project/pytesseract/) – OCR for scanned PDFs
* [Pillow](https://pypi.org/project/Pillow/) – Image processing for OCR
* [summa](https://pypi.org/project/summa/) – Text summarization
* [googletrans](https://pypi.org/project/googletrans/) – Translation API (use version 4.0.0-rc1)
* [langdetect](https://pypi.org/project/langdetect/) – Detects the source language
* [fpdf2](https://pypi.org/project/fpdf2/) – PDF generation
* [asyncio](https://docs.python.org/3/library/asyncio.html) – For asynchronous translation

---

## Example 📝

**Input:** PDF in Marathi or any supported language.
**Output:** Summarized English PDF with Unicode support.

**Before:** Large multi-page multilingual PDF
**After:** Clean, readable, translated PDF with keywords and summaries for quick understanding

---

## Contributing 🤝

Contributions are welcome! You can:

* Report bugs or issues
* Suggest improvements or new features
* Submit pull requests

Please follow Python best practices and update `requirements.txt` if new packages are added.

---

## License 📝

This project is licensed under the **MIT License** – see the `LICENSE` file for details.

---

## Acknowledgements 🙏

* [PyPDF2](https://pypi.org/project/PyPDF2/)
* [pytesseract](https://pypi.org/project/pytesseract/)
* [summa](https://pypi.org/project/summa/)
* [fpdf2](https://pypi.org/project/fpdf2/)
* [Google Translate API](https://pypi.org/project/googletrans/)

---

