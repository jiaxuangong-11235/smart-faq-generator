# Smart FAQ Generator from Documents  
*A Lightweight LLM-Based System for Automatic FAQ Extraction*

## Abstract
This project presents a **Smart FAQ Generator**, a lightweight and fully automated system designed to extract high-quality Frequently Asked Questions (FAQ) from PDF documents using state-of-the-art Large Language Models (LLMs). The system addresses the common challenge organizations face in converting dense documents—such as academic papers, technical manuals, and homework materials—into user-friendly FAQ pairs.

The method involves three key steps: (1) parsing and extracting text from PDFs, (2) chunking long documents into manageable segments, and (3) generating question-answer pairs using an OpenAI model. The system outputs both **Markdown** and **HTML** FAQ files, making the results compatible with documentation systems, websites, and chat-based retrieval tools. Experiments were conducted across multiple PDF types, including a NeurIPS research paper, a project-idea document, an academic homework file, and an LLM-evaluation paper. The system achieved consistent performance across domains, generating structured and contextually relevant FAQs with minimal post-processing.

The project concludes that automated FAQ generation is both feasible and highly effective using modern LLMs. It reduces manual workload, improves accessibility, and provides a scalable approach for transforming large text corpora into practical knowledge assets.

---

## Introduction
Organizations and individuals often rely on dense documents—research papers, reports, manuals, homework sheets, and project proposals—to share complex information. However, these documents are rarely optimized for quick reference or user-friendly consumption. As a result, readers often struggle to locate key points or understand the material efficiently.

This project addresses this challenge by developing a **Smart FAQ Generator**, an LLM-based system that automatically transforms PDF documents into high-quality question–answer pairs. The goal is to streamline knowledge extraction by leveraging powerful language models, enabling users to interact with documents more effectively.

**Objectives of the project:**

- Automate the identification and generation of FAQ-style questions.
- Enable scalable processing of long technical documents.
- Provide consistent output formats suitable for documentation pipelines.
- Evaluate system behavior across multiple document types.

---

## Data
The project uses four PDF documents, each representing a different category of text:

| Document                                  | Type                    | Approx. Length | Notes                                    |
|-------------------------------------------|-------------------------|----------------|------------------------------------------|
| *LLM as a Judge*                          | Research introduction   | ~20,000 chars  | High-level conceptual overview           |
| *Generative AI Project Ideas*             | Idea list / proposal    | ~14,000 chars  | Many short ideas and descriptions        |
| *Module 7 Homework*                       | Homework instructions   | ~5,300 chars   | Task-oriented, instructional structure   |
| *NeurIPS 2023 LLM-as-a-Judge Paper*       | Research paper          | ~20,000 chars  | Dense, technical, benchmark-oriented     |

### Preprocessing Steps

- PDFs were parsed using **PyPDF2** (or a similar PDF text extraction library).
- Extracted text was cleaned (removing extra line breaks and irregular spacing).
- Long documents were chunked into segments of roughly 8,000 characters to fit within the LLM context window.
- Each text chunk was processed independently by the LLM to generate FAQs.

---

## Experimental Setup

### System Pipeline

1. **PDF Text Extraction**  
   A loader function reads PDF files and concatenates text from all pages into a single string.

2. **Text Chunking**  
   A `chunk_text` helper function splits long strings into overlapping chunks to preserve context across segment boundaries.

3. **LLM-Based FAQ Generation**  
   A dedicated function sends each chunk to the LLM with a structured prompt instructing the model to:
   - Propose relevant questions a user might ask about the content;  
   - Provide accurate, concise answers grounded in the chunk;  
   - Format the output as a list of Q&A pairs.

4. **FAQ Aggregation and Output Rendering**  
   Generated Q&A pairs from all chunks are:
   - Combined into a single list;  
   - Rendered to **Markdown** (`*_faqs.md`);  
   - Rendered to **HTML** (`*_faqs.html`).

### Tools and Libraries

- **Python 3.10+**
- **Jupyter Notebook** (`smart_faq.ipynb`)
- **PyPDF2 / pypdf** for PDF parsing
- **OpenAI Python SDK** for LLM calls
- **markdown** and standard Python I/O utilities

### Evaluation Criteria

Although the task is qualitative, the system was evaluated along these dimensions:

- **Relevance** – Are questions aligned with key ideas in the document?
- **Answer Accuracy** – Are answers faithful to the text?
- **Coverage** – Do FAQs cover the main concepts instead of trivial details?
- **Readability** – Are generated questions and answers clear and understandable?
- **Consistency** – Is style consistent across chunks and documents?

---

## Results

### Output Summary

For each document, the system generated a small set of focused FAQs:

| Document                           | #FAQs Generated | Outputs                      |
|------------------------------------|-----------------|------------------------------|
| LLM as a Judge                     | 6               | `.md` + `.html`              |
| Generative AI Project Ideas        | 7               | `.md` + `.html`              |
| Module 7 Homework                  | 7               | `.md` + `.html`              |
| NeurIPS 2023 LLM-as-a-Judge Paper  | 7               | `.md` + `.html`              |

### Example (LLM as a Judge)

Q1: What is LLM-as-a-Judge?
A1: LLM-as-a-Judge refers to the use of Large Language Models (LLMs) to evaluate objects, actions, or decisions based on predefined rules, criteria, or preferences.

Q2: What are the main challenges in implementing LLM-as-a-Judge systems?
A2: The main challenges include the absence of a systematic review, fragmented understanding, inconsistent practices, and ensuring the reliability of evaluations aligned with established standards.

## Discussion

The Smart FAQ Generator shows that LLMs can effectively summarize and restructure complex documents into FAQ form with minimal human intervention.

### Strengths

- **Automation:** Greatly reduces manual effort needed to write FAQs.
- **Domain Versatility:** Works on research papers, instructions, and idea documents.
- **Flexible Outputs:** Markdown and HTML formats integrate easily into existing documentation or websites.
- **Educational Utility:** Homework documents become easier to review and study.

### Limitations

- **Model Dependence:** The quality of FAQs depends heavily on the underlying LLM.
- **Chunking Artifacts:** If key information is split across chunks, some context may be lost.
- **No De-duplication:** Similar questions may appear in multiple chunks and need manual refinement.
- **Cost and Latency:** Long documents require multiple API calls, which increases time and cost.

### Unexpected Observations

- Idea-style documents often produced broader, more open-ended questions than expected.
- Homework documents yielded very clear, exam-style Q&A pairs, which are ideal for student revision.
- Dense research papers occasionally produced very technical questions that may be challenging for non-experts.

## Demo Video (for Course Submission)

The demo video (< 5 minutes) can:

1. Open this GitHub repository.
2. Briefly explain the goal of the project.
3. Open `smart_faq.ipynb` in Jupyter.
4. Show how a document is loaded, chunked, and processed.
5. Open one of the `*_faqs.html` files in a browser and scroll through the generated FAQ.
6. End with a short summary of what the system does and how it can be extended.

(After recording, add your video link here.)

---

## Author

**Jiaxuan Gong**  
USC ISE 547 – Project 1.2: Smart FAQ Generator from Documents


