# Conversational RAG Agent for "House of Shipping"

This project showcases the development of a sophisticated, conversational AI agent built from the ground up. The agent is designed to act as an expert on the "House of Shipping" company, using a Retrieval-Augmented Generation (RAG) pipeline to answer user questions based on the content of the company's official website.

This notebook documents the entire end-to-end process, from initial data scraping to building a conversational agent with memory and advanced retrieval techniques.

## 🚀 Project Overview

The goal of this project was to create a reliable and knowledgeable AI assistant that could answer questions about a specific domain—in this case, the services and insights of the "House of Shipping" company. The agent is designed to be:

* **Accurate:** Providing answers based only on the information scraped from the website.
* **Honest:** Admitting when it doesn't have enough information to answer a question, preventing hallucination.
* **Conversational:** Remembering the context of the conversation to answer follow-up questions naturally.

## ✨ Key Features

* **End-to-End RAG Pipeline:** The entire pipeline, from data collection to the final conversational chain, is implemented in the notebook.
* **Web Scraping with Selenium:** The agent's knowledge base is built by scraping the "House of Shipping" website, preserving the HTML structure for advanced processing.
* **Structural Chunking:** Instead of basic text splitting, the agent uses a sophisticated chunking strategy that respects the HTML structure (headings, paragraphs) to create context-aware knowledge chunks.
* **Advanced Retrieval with Re-ranking:** The retrieval process uses a two-stage approach: a fast initial search followed by a more precise re-ranking step to ensure the most relevant information is used to answer a question.
* **Conversational Memory:** The agent can remember the previous turns of a conversation, allowing it to understand and answer follow-up questions.
* **Rule-Based Prompting:** The agent's persona and behavior are controlled by a set of custom rules defined in an external prompt file, ensuring it remains professional and on-topic.

## 🛠️ Tech Stack

* **Core Framework:** LangChain
* **LLM:** Google Gemini 1.5 Flash
* **Web Scraping:** Selenium, BeautifulSoup4
* **Vector Database:** ChromaDB
* **Embeddings:** Hugging Face `all-MiniLM-L6-v2`
* **Re-ranking:** `cross-encoder/ms-marco-MiniLM-L-6-v2`
* **Data Handling:** Pandas, NumPy
* **Environment:** Google Colab

## 📂 Project Structure

* `AI_Agent_House_of_Shipping.ipynb`: The main Jupyter notebook containing the entire RAG pipeline.
* `structured_web_content.json`: The raw, structured HTML content scraped from the website.
* `manual_qa.txt`: A manually created Q&A file to enrich the agent's knowledge base.
* `contextualize_prompt.json` & `qa_prompt.json`: External prompt files that define the agent's behavior and rules.
* `/final_chroma_db`: The directory where the persistent vector store is saved.

## ⚙️ Setup and Installation

To run this project, follow these steps:

1.  **Clone the repository:**
    ```bash
    git clone <your-repo-url>
    ```
2.  **Install dependencies:** The notebook includes a consolidated installation cell at the top that will install all necessary Python libraries.
3.  **Set up API Keys:**
    * **Google Gemini:** Get a free API key from [Google AI Studio](https://aistudio.google.com/app/apikey) and save it as a secret named `GOOGLE_API_KEY` in your environment (e.g., Google Colab secrets).
    * **Cohere (Optional):** If you choose to use the Cohere re-ranker, get a free trial key from the [Cohere Dashboard](https://dashboard.cohere.com/api-keys) and save it as a secret named `COHERE_API_KEY`.

## ▶️ Usage

1.  Open the `AI_Agent_House_of_Shipping.ipynb` notebook in Google Colab or a local Jupyter environment.
2.  Run the cells sequentially from top to bottom. The notebook is designed to be run in order and will guide you through each step of the process:
    * Installation
    * Web Scraping
    * Data Analysis (EDA)
    * Knowledge Base Enrichment
    * Structural Chunking
    * Vector Store Creation
    * Building the Conversational RAG Engine
    * Testing the Agent
3.  The final cell contains a comprehensive test suite that will demonstrate the agent's capabilities.

## 🔮 Future Improvements

* **User Interface:** The agent can be deployed with a user-friendly interface using FastAPI for the backend and React for the frontend.
* **Advanced Query Transformation:** Implement a query transformation step to rephrase user questions for even more effective retrieval.
* **Database Integration:** For a production application, the chat history could be stored in a database to manage multiple user sessions.
