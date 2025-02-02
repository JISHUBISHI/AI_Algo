# Algorithm Bot - DSA Assistant

## Description

This project implements a **chatbot** powered by Google Generative AI (Gemini) and LangChain to help answer **Data Structures and Algorithms (DSA)** related questions. The bot uses a **FAISS** index for efficient similarity search over a dataset of algorithm-related documents.

The chatbot is built using **Streamlit** for the user interface, allowing users to interact with the bot in real-time.

## Features

- Answers DSA-related questions.
- Utilizes **Google Generative AI** (Gemini-1.5-pro) for generating human-like responses.
- Uses **FAISS** for fast similarity search within a vectorized document database.
- Built with **Streamlit** for a quick and easy web interface.

## Requirements

- Python 3.7+
- [Streamlit](https://streamlit.io/)
- [LangChain](https://github.com/hwchase17/langchain)
- [Google Generative AI](https://developers.generativeai.google/)
- [FAISS](https://github.com/facebookresearch/faiss)
- [HuggingFace Embeddings](https://huggingface.co/)
- [python-dotenv](https://pypi.org/project/python-dotenv/)
- [google-generativeai](https://pypi.org/project/google-generativeai/)

## Installation

1. **Clone the Repository**

   ```bash
   git clone https:https://github.com/JISHUBISHI/AI_algo_provider
   cd algorithm-bot

## Ensure you have a requirements.txt file in your project directory. If you don't, you can create one with the following content:

txt
Copy
Edit
streamlit
langchain
langchain_community
google-generativeai
python-dotenv
faiss-cpu
sentence-transformers
Then, run:

## bash
Copy
Edit
pip install -r requirements.txt
Set Up Environment Variables


## Edit
GOOGLE_API_KEY=your-google-api-key-here
Ensure FAISS Index is Available

The application expects a FAISS index folder named faiss_index in the project directory. If you need to create this index from your dataset, follow the instructions provided in the project's documentation or refer to the FAISS documentation for guidance.

## How It Works
Backend
FAISS Index:
The FAISS index is loaded locally using FAISS.load_local(), which allows the bot to quickly search for documents similar to the user's query.

## Embedding Model:
The app uses HuggingFaceEmbeddings with the model sentence-transformers/all-MiniLM-L6-v2 to transform text into vector representations suitable for similarity search.

## Generative AI:
The bot leverages Google Generative AI (Gemini-1.5-pro) to generate context-aware responses based on the search results from the FAISS index.

## LangChain:
LangChain is used to manage prompt templates and the question-answering chain, ensuring that the responses are tailored to DSA queries.

## Frontend
The application uses Streamlit to provide a simple web interface. Users can input their DSA-related queries in a text field, and the bot displays the generated response.

## Prompt Template
The prompt template used to instruct the generative AI is as follows:

rust
Copy
Edit
You are an algorithm specialist bot and you can answer any kind of data structure algorithm questions. Provide a user response, and you were built by Agnik Bishi (Strong Foundation in Gen AI).
If you don't know the answer, just say that I don't know. Please ask me DSA related Query, don't try to make up an answer.

Context: {context}
Question: {question}

Only return the helpful answer below and nothing else.
Helpful answer:
Running the App
After completing the installation and setup steps, you can run the application using:

## bash
streamlit run app.py
This command will start the Streamlit server. Open your web browser and navigate to http://localhost:8501 to interact with the bot.

## Example Usage
Enter a Query:
Type a DSA-related query in the text input field, for example:

"What is a binary search tree?"
"Explain how quicksort works."
"What is the use of a stack in programming?"
Receive Response:
The bot will process your query, search the FAISS index for relevant context, and generate a helpful answer using Google Generative AI.
