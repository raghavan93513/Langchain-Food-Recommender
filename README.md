# Langchain-Food-Recommender
LangChain is a framework designed to simplify the creation of applications using large language models. Langchain is a Python library that provides various tools and functionalities for natural language processing (N.L.P.) tasks. It offers text-splitting capabilities, embedding generation, and integration with powerful N.L.P. models like OpenAI's GPT-3.5. F.A.I.S.S., on the other hand, is a library for efficient similarity search and clustering of dense vectors.

## About the Project

We will use Langchain to split the PDF text into smaller chunks, convert the chunks into embeddings using HuggingFaceEmbeddings, and create a knowledge base using FAISS - Basically a vector database. This knowledge base will allow us to perform an efficient similarity search when the user asks a question. We will use OpenAI's GPT-3.5 model through Langchain's LLM's. (Large Language Model as a Service) functionality for question-answering.

![alt text](https://github.com/raghavan93513/Langchain-Food-Recommender/blob/main/Sample%20Images/diagram.png)

### Installs, Imports and API Keys

```!pip install -q langchain==0.0.150 pypdf pandas matplotlib tiktoken textract transformers openai faiss-cpu sentence_transform PyPDF2 textract```
<br/>
run the above code in the first cell
<br/>

### Loading PDFs and chunking with LangChain
1) You MUST add your PDF to local files in this notebook
2) Convert PDF to text.
3) Create chunks of the document. Where, each chunk_size = 512 and chunk_overlap = 24.
4) Quick data visualization to ensure chunking was successful

![alt text](https://github.com/raghavan93513/Langchain-Food-Recommender/blob/main/Sample%20Images/chunksChart.png)

### Embed text and store embeddings

1) Use embedding model => HuggingFaceEmbeddings, which is a sentence-transformers model: It maps sentences & paragraphs to a 384 dimensional dense vector space and can be used for tasks like clustering or semantic search.
2) Create vector database => FAISS, which is an open-source library for efficient similarity search and clustering of dense vectors.

### Query to get information about Food Recommendation

Create QA chain to integrate similarity search with user queries (answer query from knowledge base)
![alt text](https://github.com/raghavan93513/Langchain-Food-Recommender/blob/main/Sample%20Images/textOutput.png)

### Create Food Recommending Chatbot

Create conversation chain that uses our vectorDB as a retriever; this also allows for chat history management
![alt text](https://github.com/raghavan93513/Langchain-Food-Recommender/blob/main/Sample%20Images/chat.png)



