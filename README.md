# 🤖 Flowise Microservices  
  
A collection of AI-powered microservices built with Flowise for document processing and text analysis. This repository contains modular services that can be deployed independently while sharing common infrastructure.  
  
## 🏗️ Architecture  
  
This repository implements a microservices architecture with two independent AI services:  
  
- **Q&A over Document Service**: Retrieval-Augmented Generation (RAG) for document-based question answering  
- **Text Summarizer Service**: Intelligent text condensation using LLM prompting  
  
Both services leverage the Flowise platform for low-code orchestration and expose REST APIs through a common gateway.  
  
## 📦 Services Overview  
  
### 📚 Q&A over Document Microservice  
- **Purpose**: Upload documents and ask questions about their content  
- **Features**: PDF processing, vector embeddings, context retrieval  
- **Tech Stack**: Flowise, LangChain, HuggingFace, Vector Storage  
- **API**: `POST /api/v1/prediction/<qa-flow-id>`  
  
### 🧠 Text Summarizer Microservice    
- **Purpose**: Summarize long text into concise summaries  
- **Features**: LLM-powered text condensation, prompt templates  
- **Tech Stack**: Flowise, LangChain, Groq API  
- **API**: `POST /api/v1/prediction/<summarizer-flow-id>`  
  
## 🚀 Quick Start  
  
### Prerequisites  
- Node.js v18.15.0 or v20+  
- npm or yarn package manager  
  
### Installation  
```bash  
# Install Flowise globally
npm install -g flowise  
  
# Start Flowise server
npx flowise start
```
### Access Flowise Dashboard
Visit: http://localhost:3000

### Import Services
1. Navigate to Chatflows → Import
2. Upload the respective .chatflow.json files:
    - module/Q&A over Document/document_qa.chatflow.json
    - module/Text_Summarizer/summarizer.chatflow.json    
## 📂 Repository Structure
Flowise_Microservices/  
├── module/  
│   ├── Q&A over Document/  
│   │   ├── readme.md  
│   │   ├── document_qa.chatflow.json  
│   │   ├── Q&A.postman_collection.json  
│   │   └── The_Timekeepers_Legacy.pdf  
│   └── Text_Summarizer/  
│       ├── README.md  
│       ├── summarizer.chatflow.json  
│       └── text-summarizer.postman_collection.json  
└── README.md  
## 🔧 API Usage
Both services follow a consistent REST API pattern:

### Request Format
```
POST http://localhost:3000/api/v1/prediction/<flow-id>  
Content-Type: application/json  
  
{  
  "question": "<input_text>"  
}
```
### Response Format
```
{  
  "text": "<generated_output>"  
}
```
## 🧪 Testing
Each service includes Postman collections for API testing:

  - Import the respective .postman_collection.json files
  - Up date flow IDs in the request URLs
  - Execute pre-configured test requests
## 🛠️ Tech Stack
| Component | Purpose | Implementation |  
|-----------|---------|----------------|  
| **Flowise** | Orchestration Platform | Visual chatflow builder, API gateway |  
| **LangChain** | AI Pipeline Framework | Chains, embeddings, retrieval |  
| **Vector Storage** | Document Retrieval | In-memory vector store |  
| **LLM Providers** | Text Generation | OpenAI, Groq, Ollama |  
| **HuggingFace** | Embeddings | Text vectorization |
## 📖 Service Documentation
For detailed setup and usage instructions:

  - Q&A over Document Service
  - Text Summarizer Service
## 🤝 Contributing
This project is part of an internship assignment focused on building modular AI microservices. Contributions and improvements are welcome.

## 📄 License
This project is intended for educational use and internship purposes.

## ✨ Author
Mohammad Muzammil Abbasi
B.Tech, CSE (AI & ML)
LinkedIn | GitHub
