# Automatic Audio Description Generation for YouTube Shorts

## MSc Data Science Dissertation
**University of Surrey — 2025/2026**
**Student:** Spoorti Halappanavar (6950243)
**Supervisor:** Dr Diptesh Kanojia

---

## Overview

This repository contains the complete code for the MSc dissertation:

**"Automatic Audio Description Generation for YouTube Shorts: A Comparative Study of Vision Language Models"**

This research investigates the automatic generation of audio descriptions for cooking YouTube Shorts using two Vision Language Models  Gemini 3.5 Flash and Qwen3 Omni  across zero-shot and five-shot prompting strategies. The work focuses on hallucination detection, prompt engineering, and comparative model evaluation.

---

## Repository Structure

 code/
   01_data_collection.ipynb     — YouTube Data API collection pipeline
   02_gemini_generation.ipynb   — Gemini 3.5 Flash description generation
   03_evaluation.ipynb          — BERTScore + GPT-4o judge evaluation

 prompts/
   zero_shot_prompt.txt         — Zero-shot prompting strategy
   five_shot_prompt.txt         — Five-shot prompting strategy
   llm_judge_prompt.txt         — GPT-4o judge evaluation prompt

 youtube-ad-qwen3omni/        — Qwen3 Omni generation code (submodule)

requirements.txt                — Required Python libraries

---

## Key Results

| Model | Overall Score | Hallucination Rate |
|---|---|---|
| Gemini Zero Shot  | 4.60/5 | 53.9% |
| Gemini Five Shot | 4.41/5 | 66.1% |
| Qwen Zero Shot | 4.00/5 | 86.6% |
| Qwen Five Shot | 3.91/5 | 83.7% |

---

## How to Run

### Install Requirements

pip install -r requirements.txt

### Run Notebooks in Order

Step 1 - Data Collection
data_collection.ipynb
Collects 467 cooking YouTube Shorts
Output: cooking_clean.csv

Step 2 - Description Generation
gemini_generation.ipynb
Generates descriptions using Gemini 3.5 Flash
Output: dataset with gemini_zero_shot and gemini_five_shot columns

Step 3 - Evaluation
evaluation.ipynb
Runs BERTScore and GPT-4o evaluation
Output: bertscore_results.xlsx, gpt_judge_results.xlsx, graphs/

---

## API Keys Required

| API | Purpose | Get From |
|---|---|---|
| YouTube Data API v3 | Data collection | console.cloud.google.com |
| Google AI Studio API | Gemini generation | aistudio.google.com |
| OpenAI API | GPT-4o judge | platform.openai.com |

Add all API keys to Google Colab Secrets before running!

---

## Dataset

- Total videos: 467 cooking YouTube Shorts
- Channels: 17 YouTube channels
- Duration: 60 to 180 seconds per video
- Descriptions: 4 sets of AI descriptions per video
- Reference: 467 human post-edited descriptions

---

## Related Repository

Qwen3 Omni generation code
https://github.com/surrey-nlp/youtube-ad-qwen3omni

---


## Acknowledgements

- Dr Diptesh Kanojia - Project supervision
- University of Surrey AI Cluster — GPU resources for Qwen3 Omni
- Google AI Studio - Gemini 3.5 Flash API access
