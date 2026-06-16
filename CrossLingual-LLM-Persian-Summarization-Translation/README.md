 # Persian Dialogue Summarization & Translation
# Overview
This project explores the capabilities and limitations of large language models (LLMs) for Persian language understanding, including:
•	Zero-shot dialogue summarization
•	Machine translation (Persian → English)
•	Comparison of multilingual vs English-centric models
•	Evaluation of instruction-tuned vs general-purpose LLMs
The study compares three models:
•	FLAN-T5 (google/flan-t5-base)
•	mBART-50 (facebook/mbart-large-50-many-to-many-mmt)
•	Mistral-7B (mistralai/Mistral-7B-v0.1)
________________________________________
Objectives
The main goals of this project are:
•	Test LLM performance on Persian (low-resource language)
•	Analyze tokenizer limitations for non-English scripts
•	Compare multilingual and English-centric models
•	Perform:
o	Zero-shot summarization
o	Translation tasks
o	Prompt-based reasoning
•	Evaluate generation quality qualitatively
________________________________________
Models Used
1. FLAN-T5 (google/flan-t5-base)
•	Sequence-to-sequence instruction-tuned model
•	Strong in English NLP tasks
•	Limited performance on Persian text due to tokenizer coverage
 Observation:
•	Poor handling of Persian characters
•	Tokenizer struggles with non-Latin scripts
________________________________________
2. mBART-50 (facebook/mbart-large-50-many-to-many-mmt)
•	Multilingual seq2seq model (50 languages)
•	Supports Persian (fa_IR) explicitly
•	Designed for translation and cross-lingual tasks
 Observation:
•	Correctly tokenizes Persian text
•	Produces meaningful summaries and translations
•	Requires language-specific configuration (src_lang, tgt_lang)
________________________________________
3. Mistral-7B (mistralai/Mistral-7B-v0.1)
•	Large causal language model
•	Strong general reasoning ability
•	Works via prompting (no task-specific training)
 Observation:
•	Performs well with structured prompts
•	Handles both summarization and translation reasonably
•	Requires careful prompt design
________________________________________
Tasks
 Task 1: Zero-Shot Summarization (mBART-50)
A Persian dialogue is summarized without fine-tuning.
Prompt Example:
Summarize the following Persian text in Persian:
[Persian dialogue]
Key Techniques:
•	forced_bos_token_id = fa_IR
•	Ensures output is generated in Persian
 Result:
•	Coherent summaries in Persian
•	Good preservation of dialogue meaning
________________________________________
 Task 2: Persian → English Translation (mBART-50)
The same dialogue is translated into English.
Configuration:
•	src_lang = fa_IR
•	tgt_lang = en_XX
 Result:
•	High-quality translation
•	Preserves conversational structure
•	Strong performance due to multilingual training
________________________________________
 Task 3: LLM Comparison with Mistral-7B
The same tasks are performed using a causal LLM:
•	Summarization (Persian output)
•	Translation (English output)
Prompting Strategy:
•	Explicit instruction prompts:
o	“Summarize the following Persian dialogue…”
o	“Translate the following Persian dialogue into English…”
 Inference settings:
•	Beam search (num_beams=5)
•	Controlled decoding (no_repeat_ngram_size=2)
•	Early stopping enabled
________________________________________
 Key Findings
1. Tokenizer Limitations Matter
•	FLAN-T5 fails on Persian input due to tokenizer mismatch
•	Shows importance of language coverage in pretraining
2. Multilingual Models Perform Better
•	mBART-50 handles Persian naturally
•	Requires correct language ID configuration
3. Prompting is Powerful for Causal LLMs
•	Mistral performs reasonably well without fine-tuning
•	Output quality strongly depends on prompt design
4. Trade-offs Observed
Model	Strength	Weakness
FLAN-T5	Instruction following	Poor Persian support
mBART-50	Strong multilingual ability	Less flexible reasoning
Mistral-7B	Strong reasoning	Sensitive to prompts
________________________________________
 Technologies Used
•	Python
•	Hugging Face Transformers
•	mBART-50
•	FLAN-T5
•	Mistral-7B
•	PyTorch
•	Hugging Face Hub
________________________________________
 Conclusion
This project demonstrates that:
•	Language support in tokenizers is critical for LLM performance
•	Multilingual models outperform English-centric models on Persian tasks
•	Prompt engineering enables strong zero-shot performance in large causal models
•	Model selection significantly impacts performance in low-resource languages
________________________________________
Key Insight
“A model is only as multilingual as its tokenizer and pretraining data.”
