# Gemma-7B-IT for Software Engineering Topics

## Overview
Utilized the DevGPT dataset and custom chat prompts to optimize semantic retrieval in the software engineering domain. Conducted experiments with the Gemma-7B-it model to explore advanced techniques for semantic retrieval and content summarization. Analyzed various prompt template strategies to improve retrieval quality and identified the most commonly queried topics by software engineers when interacting with ChatGPT. Additionally, employed the BART-large-MNLI model to perform zero-shot classification, enabling the extraction of the top 40 most frequent topics from developer queries.

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
- **Horizontal Bar Chart**: Top frequent topics.
  ![Horizontal Bar Chart](https://i.postimg.cc/MG21QDwQ/items-with-highest-frequency.png)
- **Bubble Chart**: Visualizes topic frequency with size and color.
  ![Bubble Chart](https://i.postimg.cc/gjJhWtVf/bubble-chart.png)
## Future Work
- Enhance the dataset with more diverse software engineering prompts.
- Optimize the RAG pipeline for faster inference.
- Integrate additional models for improved topic classification.

---

*This project is designed for academic research and educational purposes, offering a robust framework for exploring software engineering topics with state-of-the-art NLP techniques.*
