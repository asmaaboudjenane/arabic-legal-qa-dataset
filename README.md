# Arabic Legal QA Dataset

A dataset for Arabic legal question answering comprising Algerian Supreme Court rulings and legal QA pairs.

## Overview

This dataset was created to support research in Arabic legal NLP and retrieval-augmented generation (RAG) systems. It contains authentic court rulings from the Algerian Supreme Court and synthetic question-answer pairs for training and evaluation.

## Dataset Files

The repository contains two Excel files:

- **legal_corpus.xlsx** — Algerian Supreme Court rulings
- **qa_dataset.xlsx** — Question-answer pairs

## Dataset Statistics

| Metric | Value |
|--------|-------|
| Total court rulings | 1,248 |
| Total QA pairs | 3,742 |
| Total tokens | 463,631 |
| Vocabulary size | 36,080 |
| Average document length | 371.5 tokens |
| Median document length | 336 tokens |
| Maximum document length | 1,781 tokens |
| Average question length | 9.99 tokens |
| Average answer length | 84.82 tokens |
| Average retrieved context length | 355.91 tokens |
| Duplicate documents | 0 |
| Duplicate QA pairs | 0 |
| Missing values | 0 |

## Data Format

### Legal Corpus (`legal_corpus.xlsx`)

| Column | Description |
|--------|-------------|
| case_id | Unique identifier for the ruling |
| title | Case title |
| keywords | Legal keywords associated with the case |
| full_text | Complete ruling text in Arabic |

### QA Dataset (`qa_dataset.xlsx`)

| Column | Description |
|--------|-------------|
| question_id | Unique identifier for the QA pair |
| question | Legal question in Arabic |
| answer | Reference answer in Arabic |
| question_type | Case-specific, verdict, legal reasoning, or statutory interpretation |
| relevant_case_ids | Related court ruling IDs |

## Dataset Construction

**Court Rulings:** 1,248 rulings were collected from publicly accessible Algerian Supreme Court archives via automated web scraping, followed by HTML parsing, metadata normalization, Arabic text normalization, diacritics removal, and manual quality verification.

**QA Pairs:** 3,742 synthetic Arabic legal QA pairs were generated using a hybrid pipeline. Legal rulings were segmented into coherent chunks, then question templates were applied to produce diverse query types (factual, verdict, legal reasoning, statutory interpretation). Answers were generated via rule-based extraction for explicit facts and AraGPT2 for open-ended questions. All pairs underwent manual filtering to remove hallucinated, inconsistent, or low-quality samples.

## Usage

```python
import pandas as pd

# Load legal corpus
legal_corpus = pd.read_excel('legal_corpus.xlsx')
print(f"Loaded {len(legal_corpus)} court rulings")

# Load QA dataset
qa_dataset = pd.read_excel('qa_dataset.xlsx')
print(f"Loaded {len(qa_dataset)} QA pairs")
```

## Citation

If you use this dataset in your research, please cite:

```bibtex
@dataset{arabic_legal_qa_2026,
  title     = {Arabic Legal QA Dataset: Algerian Supreme Court Rulings and QA Pairs},
  author    = {Boudjenane, Zoubida Asmaa and Salem, Mohammed},
  year      = {2026},
  publisher = {GitHub},
  url       = {https://github.com/AsmaaBoudjenane/arabic-legal-qa-dataset}
}
```

## Related Work

This dataset was created as part of research on agentic RAG systems for Arabic legal question answering:

*ALARQA: An Agentic Retrieval-Augmented Generation System for Arabic Legal Question Answering*, 2026.

## License

Released under the [Creative Commons Attribution 4.0 International License (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/).

- Cite the dataset using the BibTeX entry above
- Acknowledge the Algerian Supreme Court as the source of court rulings
- Indicate if any modifications were made to the original data

## Ethical Considerations

- **Privacy:** All court rulings are publicly available documents
- **Bias:** The dataset reflects the Algerian legal system and may contain jurisdictional biases
- **Usage:** Intended for research purposes only; not for legal advice or decision-making

## Contact

For questions or issues, open a GitHub issue or contact: zoubida.boudjenane@univ-mascara.dz

## Changelog

**Version 2.0.0 (2026)**
- Expanded to 1,248 court rulings and 3,742 synthetic QA pairs
- Improved preprocessing pipeline with full Arabic text normalization
- Added comprehensive corpus statistics

**Version 1.0.0 (2026)**
- Initial release: 103 court rulings, 512 synthetic QA pairs
