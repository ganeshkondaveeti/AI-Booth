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
git clone https://github.com/ganeshkondaveeti/AI-Booth.git
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

6. Run the following command in your terminal to start the chat UI:
   ```
   streamlit run chat_with_website_openai.py
   streamlit run chat_with_website_ollama.py
   ```

Please provide your [Feedback](https://forms.office.com/r/2vyNdMU1eV)
