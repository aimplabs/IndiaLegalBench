# IndiaLegalBench

**A Section-Grounded Benchmark and Adaptive Verification Agent for India's New Criminal Laws**

## Overview

On July 1, 2024, India replaced the colonial-era Indian Penal Code, Code of
Criminal Procedure, and Indian Evidence Act with three new enactments: the
**Bharatiya Nyaya Sanhita (BNS)**, the **Bharatiya Nagarik Suraksha Sanhita
(BNSS)**, and the **Bharatiya Sakshya Adhiniyam (BSA)**. Because large
language models are trained predominantly on pre-2024 text, they exhibit
*parametric inertia* — hallucinating repealed section numbers and failing to
recognize newly introduced offences.

**IndiaLegalBench** is a section-grounded, multiple-choice benchmark of
**10,590 questions** (1,059 statutory sections × 10 questions/section) built
directly from the official text of the BNS, BNSS, and BSA. Each question is
linked to its originating section, enabling evaluation under both
**closed-book** and **retrieval-augmented (RAG)** settings. We additionally
introduce an **adaptive verification agent** — a retrieval-control policy
(`ACCEPT` / `RETRIEVE_MORE` / `REWRITE_QUERY`) that assesses evidence
sufficiency at each step and dynamically refines retrieval instead of
accepting a single-pass answer.

| | |
|---|---|
| Benchmark size | 10,590 MCQs (full) · 1,059 MCQs (1-per-section eval set) |
| Acts covered | BNS (3,580 Qs / 358 sections), BNSS (5,310 Qs / 531 sections), BSA (1,700 Qs / 170 sections) |
| Models evaluated | Qwen2-7B-Instruct, Llama-3.1-8B-Instruct |
| Retrieval strategies | BM25 (lexical), dense semantic (Qwen3-Embedding-0.6B), hybrid |
| Best result | 96.7% accuracy (Qwen2-7B, hybrid retrieval + agentic verification) |

## Dataset access

The full 10,590-question benchmark and the 1,059-question evaluation set
used in the paper are both released in this repository under `data/` (see
[Dataset license](#license) below). No separate download or access request
is required.

## License

This repository uses two licenses for two different kinds of content:

| Content | License | File |
|---|---|---|
| Code (`src/`, `configs/`, scripts) | Apache License 2.0 | [`LICENSE`](./LICENSE) |
| Benchmark data (`data/`) | Creative Commons Attribution 4.0 (CC BY 4.0) | [`DATA_LICENSE`](./DATA_LICENSE) |

The underlying statutory text of the BNS, BNSS, and BSA is a work of the
Government of India and is exempted from copyright under Section 52(1)(q)
of the Copyright Act, 1957 (reproduction of Acts of a Legislature). The
CC BY 4.0 license applies to the benchmark as compiled — the generated
questions, options, and section-level groundings — not to the statutory
text itself.

If you use this benchmark or code, please cite the paper (see
[`CITATION.cff`](./CITATION.cff) or the BibTeX below).

## Citation

```bibtex
@inproceedings{REPLACE_bibkey2026,
  title     = {IndiaLegalBench: A Section-Grounded Benchmark and Adaptive Verification Agent for India's New Criminal Laws},
  author    = {Abhishek Acharya, Diptendu Dutta, Agnimitra Biswas, Sujoy Kumar Biswas},
  booktitle = {Proceedings of the UNDER REVIEW},
  year      = {2026},
  publisher = {UNDER REVIEW}
}
```

## Acknowledgments

The authors used Google Gemini, OpenAI's ChatGPT, and Anthropic's Claude to
refine the English grammar, spelling, and phrasing of the manuscript. All
conceptual content, experiment design, data preparation and analysis, and
final text verification were performed entirely by the human authors, who
accept full responsibility for the integrity of the work.

## Contact
[Abhishek Acharya](acharyaabhishek84@gmail.com)
