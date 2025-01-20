# Document-AI-QA-Bot

## Table of Contents
- [Introduction](#introduction)
- [Features](#features)
- [Installation](#installation)
  - [Local Installation](#local-installation)
  - [Docker Installation](#docker-installation)
- [Usage](#usage)
- [Environment Variables](#environment-variables)
- [Commands](#commands)
- [Project Structure](#project-structure)
- [License](#license)

---

## Introduction

**Document-AI-QA-Bot** is an AI-powered question-answering application that enables users to upload documents (PDFs, Word files, or plain text) and ask questions based on the document's content. It leverages Hugging Face models for AI processing, FAISS for efficient document retrieval, and a user-friendly Streamlit interface.

This application is suitable for:
- Analyzing legal documents.
- Knowledge management.
- Academic research assistance.

---

## Features
- **Document Upload**: Supports PDF, Word, and plain text files.
- **AI Q&A**: Delivers accurate, context-based answers using Hugging Face models.
- **Vector Search**: Efficient and scalable document retrieval with FAISS.
- **Streamlit Interface**: Provides a clean and intuitive user experience.
- **Flexible Deployment**: Can be run locally or via Docker.

---

## Installation

### Local Installation

1. **Clone the Repository**
   ```bash
   git clone <repository-url>
   cd Document-AI-QA-Bot
