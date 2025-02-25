# Project-Artificial-Intelligence-RAG-Chatbot-With-Accuracy-Evaluation

---
# PROJECT - RAG CHATBOT WITH ACCURACY EVALUATION

## Project Overview
This project builds a **Retrieval-Augmented Generation (RAG) chatbot** that answers questions based on content extracted from a PDF document. The chatbot uses **FAISS for document retrieval** and a **Large Language Model (LLM) (DeepSeek or LLaMA-2-7B)** for response generation. Additionally, it evaluates the chatbot’s accuracy using **ROUGE-1 F1 Score**, ensuring that responses align with the actual content from the PDF.

## Motivation
Traditional chatbots often rely solely on pre-trained models, which may generate inaccurate or hallucinated responses. **RAG-based chatbots** improve response quality by retrieving relevant **document chunks** before answering. This project applies **AI-driven document search** to create an **accurate, explainable chatbot** capable of handling domain-specific queries.

## Steps Undertaken

### 1. PDF Data Processing
- **Dataset Used:** `DSUnit1.pdf` (contains structured text used for Q&A).
- **Processing Steps:**
  - Extracted text from the PDF using `PyMuPDF` (`fitz`).
  - Indexed text chunks into **FAISS** for efficient retrieval.
  - Used **Hugging Face’s Sentence Transformers** for text embeddings.

### 2. Retrieval-Augmented Response Generation
To improve accuracy, we implemented **FAISS for similarity search**:
- A user query is compared against PDF chunks to find the most relevant document section.
- The retrieved context is used to **generate an LLM response**.

### 3. Model Selection
We tested two different models for response generation:
- **DeepSeek (DeepSeek-R1-Distill-Qwen-1.5B)** - Optimized for inference speed.
- **LLaMA-2-7B** - A larger model providing more detailed responses.

### 4. Accuracy Evaluation Using ROUGE Score
To measure how well the chatbot’s responses align with the actual document, we implemented:
- **ROUGE-1 F1 Score** to compare word overlap between the chatbot’s generated answer and the correct answer from the PDF.
- Cosine similarity using **Sentence Transformers** to verify response relevance.

---

## Evaluation Results
We tested the chatbot using real queries from `DSUnit1.pdf`.

## Key Insights
1. **RAG significantly improves response accuracy** compared to standard LLM-based chatbots.
2. **Retrieval from FAISS enhances factual correctness**, reducing hallucinated responses.
3. **LLaMA-2-7B generates more detailed responses**, while **DeepSeek is faster** and more memory-efficient.
4. **ROUGE score provides a quantitative measure of chatbot accuracy**, allowing systematic improvement.

---

## Challenges and Lessons Learned
- **Balancing response creativity vs. accuracy:** Lower **temperature (0.3)** led to more factual responses.
- **Memory constraints in Colab:** LLaMA-2-7B required **GPU optimization** to run efficiently.
- **Improving FAISS retrieval quality:** Larger **chunk sizes (500 tokens)** improved retrieval accuracy.

---

## Future Work
1. **Fine-tuning the LLM** using domain-specific data for even better responses.
2. **Expanding document search** to multiple PDFs for broader Q&A.
3. **Integrating UI improvements** such as response confidence scores.
4. **Testing with other similarity metrics** (e.g., BERTScore) for more robust evaluation.

---

## Conclusion
This project demonstrated the effectiveness of **Retrieval-Augmented Generation (RAG) chatbots** for document-based Q&A. By integrating **FAISS, LLMs, and accuracy evaluation**, we created a system capable of answering **complex queries with high reliability**. The **ROUGE-based evaluation method** provided insights into response quality, paving the way for further enhancements in AI-driven knowledge retrieval.

---

## Closing Remarks
This project was a valuable experience in **NLP, retrieval-based AI, and chatbot evaluation**. By implementing **document search, response generation, and accuracy measurement**, we built a chatbot that ensures **fact-based answers** rather than relying on generic model responses.

🚀 **RAG chatbots represent the future of AI-driven knowledge assistants, making document retrieval more interactive and intelligent!**
