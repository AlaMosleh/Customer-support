# 📩 AI-Powered Customer Support Workflow (n8n)

This project is an **automated customer support system** built using [n8n](https://n8n.io), integrating Gmail, OpenAI (GPT-4o), LangChain, and Pinecone vector search to respond intelligently and automatically to incoming emails.

## 🔧 Features

* **Gmail Trigger**: Automatically listens for new emails.
* **AI-Powered Classification**: Classifies incoming emails as either *Customer Support* or *Other* using a language model.
* **Intelligent Agent Response**:

  * If it's a support request, the system uses a GPT-4o-based AI agent with access to a Pinecone-powered FAQ knowledge base.
  * Generates friendly, emoji-enhanced replies.
* **Automated Replies**: Sends responses back through Gmail.
* **Vector Store**: Uses Pinecone to retrieve relevant policy/FAQ content.
* **Multimodal Embedding**: Uses Google Gemini for text embeddings.

## 📁 Workflow Overview

1. **Email Trigger**: Gmail node triggers on every new email.
2. **Text Classification**: Categorizes the email content using LangChain's `Text Classifier` node.
3. **Support Flow**:

   * If support-related, passes the content to an AI Agent (configured via LangChain) with Pinecone retrieval.
   * The agent formats a friendly response and signs off as *Mr. Helpful from Tech Solutions*.
   * The reply is sent back automatically via Gmail.


## 🧠 Tech Stack

* **n8n** – Workflow automation
* **Gmail API** – For receiving and sending emails
* **OpenAI GPT-4o** – For natural language understanding and response
* **LangChain** – Orchestrates LLM tools and agents
* **Pinecone** – Vector store for document retrieval (FAQ & policy)
* **Google Gemini (PaLM)** – For generating semantic embeddings

## 📌 Setup Instructions

1. **Clone the repository** and import the `Customer_Support.json` into your n8n instance.
2. **Configure credentials**:

   * Gmail OAuth2
   * OpenAI API
   * Pinecone API
   * Google Gemini (PaLM) API
3. **Set up Pinecone index** with your FAQ and policy documents under the namespace `FAQ`.
4. **Activate the workflow** and test by sending an email to your configured Gmail account.

## ✨ Output Example

> "Hi there! 😊 Thanks for reaching out. You can reset your password by clicking \[this link]. Let me know if you need more help!
>
> – Mr. Helpful from Tech Solutions"
