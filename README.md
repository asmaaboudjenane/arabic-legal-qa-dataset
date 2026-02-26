# Arabic Legal QA Dataset

A dataset for Arabic legal question answering comprising Algerian Supreme Court rulings and  legal QA pairs.

## Overview

This dataset was created to support research in Arabic legal NLP and retrieval-augmented generation (RAG) systems. It contains authentic court rulings from the Algerian Supreme Court and  question-answer pairs for training and evaluation.

## Dataset Files

The repository contains two Excel files:

1. **`legal_corpus.xlsx`** - Algerian Supreme Court rulings
   - 103 authentic court rulings
   - Average: 632 tokens per ruling
   - Range: 228-1568 tokens
   - Fields: case_id, title, keywords, full_text

2. **`qa_dataset.xlsx`** - Question-answer pairs
   - 512 synthetic QA pairs
   - Fields: question_id, question, answer, question_type, relevant_case_ids

## Dataset Statistics

| Metric | Value |
|--------|-------|
| Total court rulings | 103 |
| Average tokens/ruling | 632 |
| Token range | 228–1568 |
| Total QA pairs | 512 |
| Question types | General, case-specific |

## Data Format

### Legal Corpus (legal_corpus.xlsx)

| Column | Description |
|--------|-------------|
| case_id | Unique identifier for the ruling |
| title | Case title |
| keywords | Legal keywords associated with the case |
| full_text | Complete ruling text in Arabic |


### QA Dataset (qa_dataset.xlsx)

| Column | Description |
|--------|-------------|
| question_id | Unique identifier for the QA pair |
| question | Legal question in Arabic |
| answer | Reference answer in Arabic |
| question_type | "general" or "case_specific" |
| relevant_case_ids | Related court ruling IDs |

## Usage

### Loading with Python (pandas)

```python
import pandas as pd

# Load legal corpus
legal_corpus = pd.read_excel('legal_corpus.xlsx')
print(f"Loaded {len(legal_corpus)} court rulings")

# Load QA dataset
qa_dataset = pd.read_excel('qa_dataset.xlsx')
print(f"Loaded {len(qa_dataset)} QA pairs")

# Example: View first ruling
print(legal_corpus.iloc[0])

```

### Loading with Excel

Simply open the `.xlsx` files in Microsoft Excel, LibreOffice Calc, or Google Sheets.

## Citation

If you use this dataset in your research, please cite:

```bibtex
@dataset{arabic_legal_qa_2024,
  title={Arabic Legal QA Dataset: Algerian Supreme Court Rulings and  QA Pairs},
  author={[Zoubida Asmaa Boudjenane , Mohammed Salem]},
  year={2026},
  publisher={GitHub},
  url={https://github.com/AsmaaBoudjenane/arabic-legal-qa-dataset}
}
```

## Related Work

This dataset was created as part of research on agentic RAG systems for Arabic legal question answering. See the accompanying paper:

> [ALARQA: An Agentic Retrieval-Augmented Generation System for Arabic Legal Question Answering], 2026.

## License

This dataset is released under the [Creative Commons Attribution 4.0 International License (CC BY 4.0)](LICENSE).

### Attribution Requirements
- Cite the dataset using the BibTeX entry above
- Acknowledge the Algerian Supreme Court as the source of court rulings
- Indicate if any modifications were made to the original data

## Ethical Considerations

- **Privacy**: All court rulings are publicly available documents
- **Bias**: The dataset reflects the legal system of Algeria and may contain jurisdictional biases
- **Usage**: Intended for research purposes; not for legal advice or decision-making

## Dataset Creation

The corpus was assembled through web scraping of publicly available Algerian Supreme Court decisions, followed by manual cleaning. The 512 QA pairs were generated using a hybrid approach combining rule-based extraction and AraGPT2 generation, with manual review and quality filtering.

For detailed methodology, see the accompanying research paper.

## Contact

For questions or issues, please open an issue on GitHub or contact: zoubida.boudjenane@univ-mascara.dz.

## Changelog

### Version 1.0.0 (2026)
- Initial release
- 103 court rulings
- 512 synthetic QA pairs
- 20 human-evaluated questions
