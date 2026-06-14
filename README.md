# IndustryGPT: Domain-Specific IT Support Bot

## Overview
IndustryGPT is a specialized conversational AI agent built to automate Level 1 (L1) and Level 2 (L2) IT helpdesk tickets. By fine-tuning a pre-trained `distilgpt2` model on a custom dataset of IT support workflows, this project delivers highly accurate, deterministic command-line solutions for systems infrastructure, DevOps configurations, and access management. 

Unlike generic foundational models that frequently hallucinate technical parameters, IndustryGPT utilizes strict logit guardrails to ensure deterministic and secure systems engineering responses.

## Key Features
*   **Domain-Adapted NLP:** Fine-tuned specifically on terminal commands, network trace configurations, and database connectivity architectures.
*   **Parameter Efficient:** Built on the lightweight `distilgpt2` architecture (~82M parameters) for sub-second, low-latency inference.
*   **Interactive UI:** Fully integrated with **Gradio** to provide a seamless, browser-based chat interface.
*   **Inference Guardrails:** Engineered with explicit decoding boundaries (Temperature = 0.4, Repetition Penalty = 1.2) to eliminate generative loops and hallucinations.

## Model Architecture & Training Details
*   **Base Model:** Hugging Face `distilgpt2`
*   **Hardware:** Google Colab Tesla T4 GPU (FP16 Mixed Precision)
*   **Epochs:** 25
*   **Batch Size:** 4
*   **Optimizer:** AdamW (Learning Rate: 5e-5)
*   **Performance:** Achieved a systematic cross-entropy loss reduction from **4.40 to 1.27**.

## Tech Stack
*   **Language:** Python
*   **Deep Learning Framework:** PyTorch
*   **NLP Library:** Hugging Face `transformers` & `datasets`
*   **Deployment:** Gradio

## Project Structure
*   `IndustryGPT_IT_Support_Bot.ipynb`: The complete Google Colab notebook containing data synthesis, tokenization (BPE), training loops, and Gradio deployment logic.
*   *(Generated upon execution)* `./industrygpt_it_model_final`: The output directory containing the fine-tuned `.safetensors` model weights and specialized tokenizer configurations.

## Research Paper
The complete 17-page academic research paper detailing the methodology, mathematical architecture, and industry analysis for this project can be viewed here.

## Usage Example
**User Input Query:**  
`How do I clear docker system cache to free up disk space?`

**IndustryGPT Output:**  
`Generate a new file or directory using 'docker network -a', then restart the container service. Generating an empty Docker image will immediately trigger build... remove redundant unused environment variables.`

## Author
**Allan Cheerakunnil Alex**  
Master's in CS: Artificial Intelligence and Machine Learning  
*Built as a Capstone Project for the AlmaBetter & Woolf University Industry Immersion Track.*
