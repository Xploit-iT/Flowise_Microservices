# 📚 Q&A Over Documents Microservice (Flowise + LLM)

This microservice allows users to upload documents (e.g., PDF files) and ask questions related to their content. The system intelligently extracts relevant answers using a language model, powered by Flowise and LangChain.

This project is part of my internship assignment to build modular AI-powered microservices using Flowise.

---

## 🚀 Features

- ❓ Ask questions about uploaded documents
- 🤖 Built with Flowise (no-code/low-code platform)
- 📄 Accepts PDF and text-based documents
- 🔍 Uses vector embeddings for context retrieval
- 🔗 Powered by LangChain and LLM (OpenAI, Groq, or Local Models)
- 🧪 API accessible via Postman, curl, or any HTTP client

---

## 📦 Tech Stack

- 🧩 Flowise
- 🔗 LangChain
- 🤗 HuggingFace
- 🤖 LLM (OpenAI, Groq, Local)
- 🧪 Postman (for API testing)

---

## 📂 Project Structure

document-qa/  
├── README.md  
├── flowise-chatflow/  
│ └── document_qa.chatflow.json  
├── postman/  
│ └── document_qa.postman_collection.json  
├── sample-docs/  
│ └── The_Timekeepers_Legacy.pdf  
├── screenshots/  
│ └── qa-demo.png  


---

## 🛠️ Setup Instructions

### 1. Clone the Repository

```
git clone https://github.com/Xploit-iT/document-qa.git
cd document-qa
```
### 2. Setup Flowise
```
npm install -g flowise
npx flowise start
```
> ✅ Pre-requisite: Node.js (v18.15.0 or v20+) must be installed

### 3. Launch Flowise
Visit: http://localhost:3000

## 🧠 Create Chatflow
Option A: Import Prebuilt Flow  
Navigate to Chatflows → Import

Upload: flowise-chatflow/document_qa.chatflow.json

Option B: Manually Create Chatflow  
Use the following nodes:

 - PDF Loader
 - Text Splitter
 - Embedding Model (HuggingFaceEmbeddings)
 - In-Memory Vector Store
 - RetrievalQA Chain
- LLM (OpenAI / Groq / Ollama)

Configure the flow to take:

 - User Question
 - Document Context
 - Return Answer

## 📫 API Usage
🔹 Endpoint
```
POST http://localhost:3000/api/v1/prediction/<flow-id>
```
🔹 Headers
```
Content-Type: application/json
```
🔹 Request Body Example
```
{
  "question": "What is the significance of the ChronoCrystal in the story?"
}
```
🔹 Sample Response
```
{
  "text": "The ChronoCrystal in the story serves as the artifact that enables Elara to traverse through time, unlocking her role as the new Timekeeper."
}
```
## 📄 Sample Document

This fictional story is used as a test document for the Q&A microservice.

🔗 [Download The Timekeeper’s Legacy (PDF)](The_Timekeepers_Legacy.pdf)

> ⚠️ **Note**: GitHub may not render this PDF in-browser. If you see a "Invalid PDF" error, simply download the file to view it locally.
## 🧪 Test With Postman
Open Postman  
Import: postman/document_qa.postman_collection.json  
Update flow ID in URL  
Click Send to receive the answer  

## 🌐 Credits

Flowise AI  
LangChain  
OpenAI  
Groq  
HuggingFace  

## ✨ Author
Mohammad Muzammil Abbasi    
B.Tech, CSE (AI & ML)    
LinkedIn | GitHub

## 📄 License
This project is part of an internship assignment and is intended for educational use only.
