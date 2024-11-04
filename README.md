
# Video Content Summarization

This repository contains a methodology and implementation for generating short, meaningful summaries of video content. The project leverages speech recognition, natural language processing (NLP) techniques, and machine learning models to produce concise, time-aligned summaries of video content.

## Project Overview

The objective of this project is to automate the process of summarizing video content by extracting meaningful segments and creating accurate and relevant text summaries. This involves four main stages: extraction, transcription, preprocessing, and summarization. The final output is a summary aligned with the video’s timestamps.

### Key Features
- **Automatic Transcription:** Converts video audio into text using Whisper ASR.
- **Preprocessing:** Cleans and normalizes text to improve summarization quality.
- **Summarization Techniques:** 
  - **TF-IDF-Based Summarization** for sentence ranking.
  - **Extractive Summarization Using a Large Language Model (LLM)** for deeper contextual understanding.
- **Evaluation Metrics:** ROUGE and Cosine Similarity for quality and relevance assessment.

## Methodology

### 1. Video Extraction and Transcription
The video content is extracted using the `yt-dlp` library, followed by audio extraction via `moviepy`. OpenAI’s Whisper ASR transcribes audio into text segments with corresponding timestamps.

### 2. Preprocessing of Transcriptions
Preprocessing includes converting text to lowercase and removing punctuation, resulting in normalized text stored alongside timestamps.

### 3. Summarization Techniques
This stage utilizes two summarization approaches:
- **TF-IDF Approach:** Sentences are ranked based on term frequency-inverse document frequency scores, capturing the most informative segments.
- **Extractive Summarization with LLM:** Using a transformer model (e.g., BERT2BERT), key sentences are extracted based on cosine similarity to the original text.

### 4. Model Selection
- **Whisper ASR Model:** Provides high accuracy in transcription with support for multiple languages and accents.
- **BERT2BERT Transformer:** Chosen for extractive summarization due to its efficiency and performance.
- **TF-IDF Vectorizer:** Complements the LLM by identifying key sentences based on word importance.

### 5. Evaluation Metrics
- **ROUGE Score:** Measures overlap between generated and reference summaries.
- **Cosine Similarity:** Evaluates relevance by measuring similarity between the summary and original text.
- **Manual Review:** Ensures contextual coherence and relevance.

## Getting Started

### Prerequisites
- Python 3.10
- `yt-dlp`, `moviepy`, `transformers`,`bitsandbytes`,`whisper`
