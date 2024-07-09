# chat-with-website
Simple Streamlit app to have interaction with your website URL. Use any website URL that don't have any authentication.

### Chat with your website 🚀
- [OpenAI model](https://platform.openai.com/docs/models) as Large Language model
- [Ollama](https://ollama.ai/) and `mistral` as Large Language model
- [LangChain](https://python.langchain.com/en/latest/modules/models/llms/integrations/huggingface_hub.html) as a Framework for LLM
- [Streamlit](https://streamlit.io/) for deploying.

## Brief explanation of how RAG works

A RAG bot is short for Retrieval-Augmented Generation. This means that we are going to "augment" the knowledge of our LLM with new information that we are going to pass in our prompt. We first vectorize all the text that we want to use as "augmented knowledge" and then look through the vectorized text to find the most similar text to our prompt. We then pass this text to our LLM as a prefix.

This is more clearly explained in the diagram that shows the process:

![RAG Diagram](docs/HTML-rag-diagram.jpg)

## System Requirements

You must have Python 3.9 or later installed. Earlier versions of python may not compile.  

---

## Steps to Replicate 

   
1. Create a virtualenv and activate it
   ```
   python3 -m venv .venv && source .venv/bin/activate
   ```

2. Fork this repository and create a codespace in GitHub OR Clone it locally.
```
https://github.com/ganeshkondaveeti/AI-Booth.git
cd AI-Booth
cd chat-with-websites
```

3. Rename example.env to .env with `cp example.env .env`and input the OpenAI API key as follows. Get OpenAI API key from this [URL](https://platform.openai.com/account/api-keys). You need to create an account in OpenAI webiste if you haven't already.
   ```
   OPENAI_API_KEY=your_openai_api_key
   ```

   For langsmith, take the environment variables from [LangSmith](https://smith.langchain.com/) website

4. Run the following command in the terminal to install necessary python packages:
   ```
   pip install -r requirements.txt
   ```
 
 5. Install the following:
   
- [Ollama](https://python.langchain.com/v0.2/docs/integrations/chat/ollama/) - Download and Install Ollama
   
   ```
   
   pip install --upgrade langchain
   pip install langchain-community langchain-core
   
   Fetch available LLM model via ollama pull <name-of-model>
   
   ollama pull llama3
   ollama pull llama2
   ollama pull nomic-embed-text
   ollama pull mistral
   ```

Example from my laptop after above steps:-

(chat-with-websites-Ollama) (base) gkondave@GKONDAVE-M-56JK chat-with-website % ollama --version
ollama version is 0.1.48

(chat-with-websites-Ollama) (base) gkondave@GKONDAVE-M-56JK chat-with-website % ollama list     
NAME                    ID              SIZE    MODIFIED   
mistral:latest          2ae6f6dd7a3d    4.1 GB  5 days ago
llama2:latest           78e26419b446    3.8 GB  5 days ago
llama3:latest           365c0bd3c000    4.7 GB  5 days ago
nomic-embed-text:latest 0a109f422b47    274 MB  5 days ago
(chat-with-websites-Ollama) (base) gkondave@GKONDAVE-M-56JK chat-with-website % 


6. Run the following command in your terminal to start the chat UI:
   ```
   streamlit run chat_with_website_openai.py
   streamlit run chat_with_website_ollama.py
   ```

Please provide your [Feedback](https://forms.office.com/r/2vyNdMU1eV)
