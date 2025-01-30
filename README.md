# COMPSCI-646 Information Retrieval Project - Personalized News Headline Generation using LLM-Based RAG Pipeline

## **Project Overview**
This project explores the role of linguistic style in personalizing Large Language Models (LLMs) and aims to bridge the gap between the universal capabilities of LLMs and the rising demand for individualized interactions. The core idea is to generate personalized news headlines by combining content-dependent and content-independent style representations.

---

## **Dataset: LAMP-4**
The LAMP-4 dataset was used for training and evaluation. 

---

## **Methodology**
### **Approach**
Our approach consists of the following key components:  

1. **Query Variants Generation**  
   - The original query is used to generate k variations using an LLM - Gemini Flash 1.5.  

2. **Dense Retrieval & FAISS Indexing**  
   - Retrieves the top m semantically similar documents using FAISS indexing.  

3. **Context Expansion & Headline Generation**  
   - The retrieved top k documents are appended to the query before generating the final headline using an LLM - Flan-T5 Base Model.  

4. **Style Embeddings for Personalization**  
   - Utilizes Wegmann et al. (2022)’s model to extract style embeddings from a user’s profile documents.  
   - Computes the average embedding to capture overall stylistic tendencies.  
   - Ranks retrieved documents based on cosine similarity to the author’s style embedding.  

5. **Hybrid Model for Personalization**  
   - A union of dense retrieval and style-based ranking is used to generate the final personalized headline.  

---

### **Key Findings**
✅ **Hybrid approach** (content + style embeddings) achieves the best performance in both ROUGE-1 and ROUGE-L.  
✅ **BM25** remains a strong baseline for text retrieval and headline generation.  
✅ **Dense Search & Style Embeddings alone** perform worse than hybrid models.  

---

## **Conclusions**
✔ **Hybrid Model Effectiveness** – Combining content-based and style-based methods enhances personalization. Encoding linguistic style improves the quality of generated headlines.  
✔ **Traditional IR Methods Still Work** – BM25 remains a competitive retrieval technique for LLM-based text generation.  

---

## **Future Work**
🚀 **Refining Sentence Embeddings** – Improve how style embeddings are extracted from document texts.  
🚀 **Exploring Alternative LLMs** – Evaluate different models for improved style adaptation.  

---

## **Installation & Usage**
### **Requirements**
- Python 3.8+
- Hugging Face Transformers
- FAISS
- NLTK
- PyTorch
- Scikit-learn
