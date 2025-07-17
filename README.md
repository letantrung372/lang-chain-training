# 💬 BonBon Support Chatbot using LangChain + Azure AI

This project demonstrates how to build a LangChain-based chatbot that indexes and retrieves information from a company FAQ PDF using Azure OpenAI and Azure AI Search, and responds conversationally using a hybrid of internal knowledge base and web search tools.

---

## 📂 Project Structure

All logic (indexing and chatbot interaction) is implemented in a single Jupyter notebook:

```
assignment.ipynb
```

---

## ✅ Features

- 🧠 Embeds and indexes BonBon FAQ.pdf using Azure OpenAI and Azure AI Search
- 🔍 Searches using semantic vector search via HNSW
- 🤖 Conversational ReAct agent powered by `gpt-4o`
- 🔌 Hybrid tools:
  - **Internal KB Tool** using AzureAISearchRetriever
  - **Web Search Tool** via DuckDuckGo

---

## 📦 Requirements

Ensure you have the following installed:

```bash
pip install -r requirements.txt
```

Example packages used:

- `langchain`
- `python-dotenv`
- `openai`
- `azure-search-documents`
- `PyMuPDF` (via `fitz`)
- `chromadb`
- `langchain-community`

---

## 🔐 Environment Variables (`.env`)

Create a `.env` file with the following keys:

```env
# Azure OpenAI
AZURE_OPENAI_SERVICE=your-service-name
AZURE_OPENAI_API_KEY=your-api-key
AZURE_OPENAI_EMBEDDING_DEPLOYMENT=text-embedding-deployment-name
AZURE_OPENAI_API_VERSION=2023-07-01-preview
OPENAI_API_KEY=your-api-key
OPENAI_API_BASE=https://your-service.openai.azure.com
OPENAI_API_TYPE=azure
OPENAI_API_VERSION=2023-07-01-preview

# Azure AI Search
AZURE_SEARCH_SERVICE=your-search-service-name
AZURE_SEARCH_API_KEY=your-search-api-key
AZURE_AI_SEARCH_SERVICE_NAME=your-search-service-name
AZURE_AI_SEARCH_INDEX_NAME=gptkbindex-pdf
AZURE_AI_SEARCH_API_KEY=your-search-api-key
```

---

## 🧪 How It Works

### 🔹 Indexing PDF
1. Load and split PDF into semantic chunks.
2. Generate embeddings with Azure OpenAI.
3. Upload to Azure AI Search with vector search configuration.

### 🔹 Conversational Agent
- Uses LangChain Conversational ReAct Agent.
- Includes memory and tool calling:
  - KB Tool for internal support FAQs.
  - DuckDuckGo for general queries.

---

## ▶️ Run the Notebook

Launch `assignment.ipynb` using Jupyter Notebook or VS Code.

---

## 📎 Example Interaction

```
Welcome to BonBon Support Chatbot!
You: How do I access shared network drives?
Bot: You can map a network drive by...
Source: bonbon_faq.pdf (page 5)

You: What's the latest iPhone model?
Bot: According to web search...
```

---

## 📁 Files

```
.
├── data/
│   └── BonBon FAQ.pdf
├── .env
├── assignment.ipynb
└── README.md
```

---

## 🧑‍💻 Author

Built by Trung Le as part of LangChain Assignment.

