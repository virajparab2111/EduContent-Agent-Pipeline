# 📚 EduContent-Agent-Pipeline

A UI-driven, dual-agent AI pipeline designed to generate and automatically review structured educational content. This project demonstrates a lightweight agentic architecture using **Gemini 2.5 Flash**, **Pydantic** for strict JSON schemas, and **Gradio** for an interactive frontend.

## ✨ Features
* **Two-Agent System**: 
  * **Generator Agent**: Drafts age-appropriate explanations and Multiple Choice Questions (MCQs) in JSON format.
  * **Reviewer Agent**: Evaluates the draft for conceptual correctness, clarity, and age-appropriateness.
* **Self-Refinement Loop**: If the Reviewer fails the draft, the feedback is automatically passed back to the Generator for one inline refinement pass.
* **Guaranteed Structured Output**: Uses the `google-genai` SDK and Pydantic models to strictly enforce JSON outputs without manual parsing errors.
* **Interactive UI**: Built with Gradio to clearly display the pipeline's step-by-step execution flow.

## 🏗️ Architecture

1. **Input**: User provides a Target Grade, Topic, and API Key via the UI.
2. **Generate (Draft)**: The Generator Agent creates a JSON payload with an explanation and MCQs.
3. **Review**: The Reviewer Agent analyzes the JSON and returns a `pass` or `fail` status along with specific feedback.
4. **Refine (Optional)**: If the status is `fail`, the Generator creates a new draft fixing the specific issues highlighted by the Reviewer.
5. **Output**: The UI displays the initial draft, the reviewer's evaluation, and the final refined content.

## 🚀 Quick Start (Google Colab)
The easiest way to test and interact with this pipeline is directly in your browser using Google Colab.
1. Open the [Colab Notebook](https://colab.research.google.com/drive/1owABAFa3ZaH7F7WbNb8Le7ZB_WSpMJF8?usp=sharing)
2. Run the code cell to install dependencies and launch the inline Gradio UI.
3. Enter your [Google Gemini API Key](https://aistudio.google.com/), input a topic, and click "Generate Content".
