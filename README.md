# Experiment 13: RAG Chain Using LCEL

## Aim
To construct a basic Retrieval-Augmented Generation (RAG) chain using LangChain Expression Language (LCEL), FAISS, and an OpenAI language model.

## Problem Statement
Build a RAG chain that retrieves the top two relevant text chunks from a FAISS vector store and uses the retrieved context to answer questions about climate change.

## Technologies Used
- Python
- LangChain
- LCEL
- OpenAI GPT-3.5-turbo
- OpenAI Embeddings
- FAISS Vector Store

## Algorithm
1. Define the sample climate-change text.
2. Split the text using `RecursiveCharacterTextSplitter`.
3. Generate embeddings using `OpenAIEmbeddings`.
4. Create a FAISS vector store.
5. Convert the vector store into a retriever with `k=2`.
6. Define a prompt containing `{context}` and `{question}`.
7. Build the LCEL chain using `retriever`, `prompt`, `llm`, and `StrOutputParser`.
8. Invoke the chain with two test questions.
9. Print the answers and retrieved source chunks.

## Installation

```bash
pip install -r requirements.txt
```

## API Key Setup

**Windows Command Prompt:**

```cmd
set OPENAI_API_KEY=your_api_key_here
```

**Windows PowerShell:**

```powershell
$env:OPENAI_API_KEY="your_api_key_here"
```

Never upload your API key to GitHub.

## Execution

```bash
python src/main.py
```

## Expected Output

```text
Number of chunks: [calculated at runtime]

Question: What causes climate change?

Answer:
Climate change is driven in part by human activities,
especially burning fossil fuels, which increase
greenhouse gases in the atmosphere.

Retrieved Chunks:
Chunk 1: [retrieved source text]
Chunk 2: [retrieved source text]

Question: What are the effects of climate change?

Answer:
Climate change can cause rising sea levels, flooding
in coastal cities, heatwaves, droughts, and intense storms.

Retrieved Chunks:
Chunk 1: [retrieved source text]
Chunk 2: [retrieved source text]
```

*The output is illustrative. Actual answers and retrieved chunks depend on the embeddings and similarity search results.*

## Result
A basic LCEL-based RAG pipeline was implemented to retrieve relevant context from a FAISS vector store and generate answers grounded in the retrieved text.
