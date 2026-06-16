#  LLMs Research & Applications Portfolio

This repository contains a collection of Large Language Model (LLM) projects exploring modern NLP techniques, including prompt engineering, parameter-efficient fine-tuning, instruction tuning, retrieval-augmented generation (RAG), and multilingual NLP.

The goal of this work is to study and build efficient LLM systems for real-world applications such as **translation, summarization, document question answering, and preference alignment**.

---

# Repository Structure

```
llms/
├── flan_t5_summarization/
├── qlora_cnn_summarization/
├── persian_ner_lora/
├── mbart_translation_study/
├── gemma_prompt_tuning_translation/
├── dpo_qwen_alignment/
├── rag_pdf_qa_system/
```

---

#  Projects Overview

## 1. FLAN-T5 Dialogue Summarization (Prompt Engineering)

* Model: google/flan-t5-base
* Task: Dialogue summarization
* Methods: Zero-shot, one-shot, few-shot prompting, prompt templates

This project explores how prompt design affects model performance without fine-tuning.

---

## 2. QLoRA Fine-tuning on CNN/DailyMail

* Model: TinyLlama-1.1B
* Dataset: CNN/DailyMail
* Method: QLoRA (4-bit quantization + LoRA adapters)

Efficient fine-tuning for news summarization using minimal GPU resources.

---

## 3. Persian Named Entity Recognition (LoRA / PEFT)

* Model: HooshvareLab/bert-fa-base-uncased
* Task: Token classification (NER)
* Method: LoRA-based parameter-efficient fine-tuning

Demonstrates NLP modeling for low-resource Persian language.

---

## 4. Multilingual Translation Study (mBART, Mistral, FLAN-T5)

* Models:

  * facebook/mbart-large-50-many-to-many-mmt
  * mistralai/Mistral-7B
* Task: Persian ↔ English translation and summarization
* Evaluation: BLEU score

Shows comparison between multilingual models and instruction-tuned LLMs.

---

## 5. Prompt Tuning on Gemma-2 9B

* Model: gemma-2-9b-it
* Method: Prompt Tuning (PEFT)
* Task: English → Persian translation

Improves translation performance using lightweight trainable prompt tokens.

---

## 6. DPO Fine-tuning with Qwen 0.5B

* Model: Qwen2.5-0.5B-Instruct
* Dataset: Intel/orca_dpo_pairs
* Method: Direct Preference Optimization (DPO)

Improves instruction-following ability through preference learning.

---

## 7. RAG System for PDF Question Answering

* Model: Gemma-2-9B
* Framework: LangChain + FAISS + DocArray
* Embeddings:

  * sbunlp/fabert
  * sentence-transformers/paraphrase-multilingual-mpnet-base-v2

Retrieval-Augmented Generation system for answering questions from PDFs in Persian.

---

#  Key Skills Demonstrated

* Prompt Engineering (zero-shot / few-shot)
* Parameter-Efficient Fine-Tuning (LoRA, QLoRA, Prompt Tuning)
* Instruction Tuning and Preference Optimization (DPO)
* Retrieval-Augmented Generation (RAG)
* Multilingual NLP (Persian + English)
* Model Evaluation using BLEU and ROUGE
* Embedding-based semantic search

---

#  Key Insights

* Prompt design strongly influences LLM performance
* PEFT methods enable efficient training on limited hardware
* Better embeddings significantly improve RAG systems
* Instruction-tuned models perform better in open-ended tasks
* Preference optimization improves alignment with human intent
