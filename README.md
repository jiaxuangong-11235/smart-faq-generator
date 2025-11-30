# Smart FAQ Generator from Documents

This project implements a **Smart FAQ Generator** that automatically generates high-quality Frequently Asked Questions (FAQ) pairs from PDF documents using Large Language Models (LLMs). It was developed as part of Project 1.2 for USC ISE 547 (Generative AI & Data Engineering).

---

## Project Overview

The system:

1. Reads PDF documents
2. Extracts and cleans the text
3. Splits long text into smaller chunks
4. Sends each chunk to an LLM with a carefully designed prompt
5. Collects and merges generated FAQ question–answer pairs
6. Saves results as both Markdown (`.md`) and HTML (`.html`) files

This is useful for:

- Turning course documents into FAQs
- Summarizing research papers
- Building knowledge-base style documentation
- Creating study guides from long readings

---

## Repository Structure

```text
smart-faq-generator/
│
├── smart_faq.ipynb                 # Main Jupyter Notebook (core pipeline)
│
├── faq_outputs/                    # Generated FAQ outputs (examples)
│   ├── LLM as a judge_faqs.md
│   ├── LLM as a judge_faqs.html
│   ├── Generative AI project ideas_faqs.md
│   ├── Generative AI project ideas_faqs.html
│   ├── Module 7 Homework_faqs.md
│   ├── Module 7 Homework_faqs.html
│   ├── NeurIPS-2023-judging-llm-..._faqs.md
│   └── NeurIPS-2023-judging-llm-..._faqs.html
│
└── README.md                       # Project documentation
