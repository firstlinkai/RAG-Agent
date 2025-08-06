# 🔁 Fully Automated RAG Chatbot with n8n, Google Drive, Gemini AI, and Qdrant

This project is a no-code Retrieval-Augmented Generation (RAG) chatbot system built using **n8n**, **Google Gemini AI**, **OpenAI embeddings**, **Qdrant**, and **Google Drive**. It enables conversational access to documents stored in Google Drive by combining semantic search and generative AI.

## 📌 What It Does

- Automatically fetches documents from a specified Google Drive folder.
- Extracts content and structured metadata using **Google Gemini**.
- Splits content into chunks and embeds them using **OpenAI’s embedding model**.
- Stores embeddings in **Qdrant** for fast vector search.
- Lets users chat with their documents via a conversational interface (using **LangChain**).
- Adds Telegram-based approval before deleting any vectors (human-in-the-loop).
- Sends real-time notifications and logs chat sessions.

---

## ⚙️ Tech Stack

| Component         | Role                                                   |
|------------------|--------------------------------------------------------|
| n8n              | Workflow orchestration (self-hosted or cloud)          |
| Google Drive     | Document storage                                       |
| Google Gemini AI | Metadata extraction and reasoning engine               |
| OpenAI API       | Embedding generation (text-embedding-3-large)          |
| Qdrant           | Vector database for semantic search                    |
| LangChain        | RAG orchestration + ChatTrigger                        |
| Telegram API     | Notifications and approvals                            |

---

## 🔄 Workflow Overview

### 1. Document Ingestion

- Monitors a Google Drive folder.
- Pulls new files and extracts content.
- Uses **Gemini AI** to analyze and extract:
  - Topics
  - Pain points
  - Conclusions
  - Keywords
  - Themes

### 2. Embedding & Storage

- Splits text into token-based chunks.
- Generates vector embeddings via OpenAI.
- Upserts data into **Qdrant** collection.

### 3. Conversational Search (RAG)

- Triggered via **LangChain** AI agent.
- Searches for relevant document chunks.
- Uses **Gemini** to answer based on retrieved content.
- Avoids hallucinations by limiting context to retrieved data.
- Logs each conversation to Google Docs.

### 4. Human-in-the-Loop (Optional)

- Requests deletion approval via Telegram.
- Deletes specific vectors only after confirmation.

---

## ✅ Features

- 🧠 Conversational document querying (RAG)
- 🔐 Telegram-based data deletion approval
- 🗂️ Batch processing of multiple documents
- 📄 Transparent logging of all chat sessions
- 📬 Real-time Telegram notifications
- 🔧 Dynamic configuration via n8n Set nodes

---

## 🧪 Use Cases

- Internal document chatbots
- Semantic search over PDFs, reports, and SOPs
- Customer support tools trained on internal docs
- Knowledge base chatbots for teams

---

## 🛠️ Setup Instructions

1. **Install n8n** (Cloud or self-hosted)
2. Import the provided workflow JSON
3. Set up the following credentials:
   - Google Drive API
   - Gemini AI Key
   - OpenAI API Key
   - Qdrant endpoint and collection
   - Telegram Bot token
4. Configure your Drive folder ID and Qdrant collection in the workflow.
5. Deploy the workflow or run it manually to test.

---

