# LLM-Based Sarcasm Generation and Cross-Model Verification

This repository contains an end-to-end LLM-based framework designed to generate novel sarcastic headlines from a given reference text, preserving the original satirical intent.

## Project Overview
The system uses a **Cross-Family Verification Architecture** to eliminate self-evaluation bias. It was tested on a 500-sample pipeline using the Kaggle Sarcasm Headlines Dataset.

### Models Used:
*   **LLM_X (Generator):** Qwen 2.5 (3B) - *Alibaba Family*
*   **LLM_Y (Evaluator 1):** Llama 3.2 (3B) - *Meta Family*
*   **LLM_Z (Evaluator 2):** Gemma 2 (2B) - *Google Family*

## Key Results
*   **Inter-Model Agreement:** 95.40%
*   **Bilateral Sarcasm Success:** 438 / 500
*   **Average Jaccard Similarity:** 0.1474 (Proving high lexical novelty)

## Failure Analysis
The pipeline successfully identified **Cross-Lingual Tokenization Bias** (Qwen occasionally outputting Chinese characters) and **Coreference Resolution Failures** (entity swapping), proving the necessity of multi-model verification.

## Files
*   `notebookd96b816d0b.ipynb`: The main Kaggle notebook with all code.
*   `final_500_master_file.csv`: The evaluated dataset.
*   `pie_chart.png` & `jaccard_hist.png`: Data visualizations.
