# Gemma-7B-IT for Software Engineering Topics

## Overview
This project implements a Retrieval-Augmented Generation (RAG) system using the Gemma-7B-IT model to address software engineering queries. It leverages FAISS for efficient vector search, a cross-encoder for re-ranking, and a dataset of translated prompts to provide accurate, context-aware responses. The system is optimized for GPU acceleration and uses 4-bit quantization to reduce memory usage.

## Key Features
- **Model**: Gemma-7B-IT, a 7-billion parameter language model fine-tuned for instruction tasks.
- **RAG Pipeline**: Combines FAISS vector search with cross-encoder re-ranking to retrieve and prioritize relevant software engineering content.
- **Dataset**: Utilizes a curated dataset of 3,395 translated prompts (`translated_merged_first_prompt_ans_code.csv`) for context.
- **Performance**: Processes queries in ~15 seconds on a single GPU (e.g., NVIDIA T4), with a total runtime of ~590 seconds for the notebook.
- **Visualization**: Includes insightful plots (bar, sunburst, bubble, spider, stock, and dendrogram) to analyze frequent software engineering topics.

## Methodology
1. **Data Loading**: Reads a CSV file containing translated software engineering prompts.
2. **Query Processing**: Uses a custom `hello_world` function to generate responses with Gemma-7B-IT, incorporating context from the dataset.
3. **Topic Analysis**: Extracts and clusters frequent topics using zero-shot classification (BART-large-MNLI) and hierarchical clustering.
4. **Visualization**: Generates interactive Plotly visualizations and a dendrogram to highlight key software engineering principles.

## Key Findings
- **Top Topics**: Modularization, Single Responsibility Principle, Design Patterns, and Abstraction are among the most frequent software engineering concepts.
- **Merged Categories**: Zero-shot classification consolidates topics into 20 distinct categories, visualized for easy interpretation.
- **Scalability**: The system efficiently handles large datasets and provides rapid query responses.

## Requirements
- **Hardware**: GPU (e.g., NVIDIA T4) recommended for optimal performance.
- **Software**:
  - Python 3.10
  - PyTorch, Transformers, FAISS, Plotly, Pandas, NumPy, Matplotlib, Seaborn
  - Install dependencies: `pip install torch transformers faiss-gpu plotly pandas numpy matplotlib seaborn kaleido`

## Usage
1. Clone the repository and navigate to the project directory.
2. Install required packages (see Requirements).
3. Run the Jupyter notebook `gemma-7b-it-rag-for-software-engineering-topics.ipynb`.
4. Query the system with software engineering questions, e.g., "Name 3/4 software engineering principles."

## Visualizations
The project includes:
- **Bar Chart**: Top 40 frequent topics.
- **Sunburst Chart**: Hierarchical view of topic frequencies.
- **Bubble Chart**: Visualizes topic frequency with size and color.
- **Spider Chart**: Displays topic distribution radially.
- **Stock Chart**: Simulates frequency trends.
- **Dendrogram**: Hierarchical clustering of topics.

## Future Work
- Enhance the dataset with more diverse software engineering prompts.
- Optimize the RAG pipeline for faster inference.
- Integrate additional models for improved topic classification.

---

*This project is designed for academic research and educational purposes, offering a robust framework for exploring software engineering topics with state-of-the-art NLP techniques.*
