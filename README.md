AI Learning Agent (V2 & V3 with DSPy)

A Python project for creating personalized AI-driven learning experiences, from syllabus negotiation to interactive tutoring, using Google Gemini. Version 3 leverages DSPy for advanced prompt management.

## Motivation: Unlock Your Learning Potential

In a world overflowing with information, learning effectively and efficiently is more crucial than ever. The AI Learning Agent is born from a desire to accelerate this journey, transforming how we acquire new knowledge and skills.

**The Challenge:** Ever felt overwhelmed trying to learn something new? Where do you start? How do you structure your learning? How do you stay motivated and ensure you truly understand complex topics?

**Our Solution: A Personalized AI Learning Companion**
This project aims to make learning:
*   **Personalized:** Crafting learning plans (syllabi) based on *your* goals, current knowledge, and preferred learning style.
*   **Resource-Aware:** Integrating your own materials (PDFs, Word documents, text files) into the learning journey.
*   **Interactive:** Engaging in natural conversations to define learning paths and then diving deep with an AI tutor designed to match your preferences.
*   **Powered by Cutting-Edge AI:** Utilizing Google's Gemini models, and (in Version 3) the power of DSPy for sophisticated and adaptable AI behaviors.

This agent is a step towards a future where anyone can have a personalized guide to master complex subjects efficiently.

## Core Functionality

*   Conversational Syllabus Generation (resource-aware)
*   AI Tutor Persona Crafting
*   Interactive Learning Loop
*   Resource Processing (PDF, DOCX, TXT)

## V3 Highlights (DSPy)

*   Modular design using DSPy Signatures & Modules.
*   `CustomGeminiDspyLM` for Gemini + LiteLLM integration.
*   Easier prompt experimentation and optimization.

## Tech Stack

*   Python 3, Google Colab
*   `google-generativeai`
*   `dspy-ai` (V3)
*   `PyPDF2`, `python-docx`

## Quick Setup & Run

1.  **Environment:** Google Colab.
2.  **API Key:** Add `GOOGLE_API_KEY` to Colab Secrets.
3.  **Notebooks:**
    *   `Learning_Agent_v2.ipynb` (Direct Gemini SDK)
    *   `Learning_Agent_v3_DSPy.ipynb` (DSPy version - Recommended)
4.  **Dependencies:** Run `!pip install ...` cells at the top of the chosen notebook.
5.  **Google Drive Mount:** Authorize drive access for resource handling. Configure `INPUT_DIRECTORY` in the notebook for your learning materials.
6.  **Execute:** Run all cells. Interact via `input()` when prompted by `run_learning_session()` or `run_learning_session_dspy()`.

## Project Structure Highlights

**Shared Components (Conceptual):**
*   **Resource Processor:** Extracts text from files.
*   **Rate Limiter:** Manages API call frequency.
*   **Core LLM Call Function:** (`llm_call` in V2, `CustomGeminiDspyLM` within DSPy in V3)

**V2 Key Functions:**
*   `extract_and_copy_text_files()`
*   `generate_syllabus_from_chat()` (uses various system prompts)
*   `summarize_single_resource_dynamically()`
*   `negotiate_syllabus_chat_dynamic()` (orchestrates V2 flow)
*   `run_learning_session()`

**V3 Key DSPy Modules & Signatures:**
*   `CustomGeminiDspyLM`: Bridges DSPy with Gemini via LiteLLM.
*   `SyllabusNegotiationSignature`, `ConversationManager`: Manages syllabus chat flow.
*   `SyllabusNoResourcesSignature`, `SyllabusWithRawTextSignature`, `SyllabusWithSummariesSignature`, `SyllabusGeneratorRouter`: Handles different syllabus generation scenarios.
*   `DynamicSummarizationSignature`, `DynamicResourceSummarizerModule`: For summarizing resources within the DSPy framework.
*   `PersonaPromptBodyPredictSignature`, `PersonaPromptGenerator`: Creates the AI tutor's persona.
*   `InitialResourceSummarySignature`, `InitialResourceSummarizer`: Provides an initial overview of uploaded files.
*   `LearningStyleSignature`, `LearningStyleQuestioner`: Asks user for learning preferences.
*   `negotiate_syllabus_chat_dspy()` (orchestrates V3 flow)
*   `run_learning_session_dspy()`

## Future Directions

*   RAG for explainer agent for enhanced factual accuracy.
*   Advanced DSPy prompt optimization (e.g., using `BootstrapFewShot`).
*   Enhanced UI/UX, especially for mathematical topics.
*   User preference management for more tailored interactions.

See the full code and comments in the notebooks for detailed implementation.
