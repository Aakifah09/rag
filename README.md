# RAG
# University Course Assistant using RAG

## Project Overview

This project implements a Retrieval-Augmented Generation (RAG) system
using custom university course data.

The system allows users to ask questions about university courses.
Relevant information is retrieved from a Qdrant vector database and
then provided as context to a Large Language Model (LLM) to generate
the final answer.

## Problem Statement

A general-purpose Large Language Model may not have access to specific
information about university courses.

This project solves this problem by storing university course information
as vector embeddings in Qdrant. When a user asks a question, the system
retrieves the most relevant course information and provides it as context
to the LLM.

## Technologies Used

- Python
- Google Colab
- Sentence Transformers
- Qdrant
- Ollama
- Llama 3.2 1B

## What is RAG?

Retrieval-Augmented Generation (RAG) is a technique that combines
information retrieval with text generation.

Instead of asking an LLM to answer a question only using its
pre-trained knowledge, RAG first retrieves relevant information
from an external data source.

The retrieved information is then provided to the LLM as context,
which helps generate an answer based on the provided data.

## RAG Pipeline

The system follows these steps:

1. The user enters a question.
2. The question is converted into a numerical embedding using
   Sentence Transformers.
3. Qdrant searches for the most relevant information using
   vector similarity.
4. The relevant course information is retrieved.
5. The retrieved information is added to a prompt.
6. Llama 3.2 generates the final answer using the retrieved context.

### Pipeline

User Question
↓
Sentence Transformer
↓
Question Embedding
↓
Qdrant Vector Search
↓
Relevant Course Information
↓
RAG Prompt
↓
Llama 3.2
↓
Final Answer

## Custom Data

The project uses custom university course information, including:

- Machine Learning
- Database Systems
- Principles of Programming Languages
- Organizational Behaviour
- Computer Networks

## Example Questions

The system can answer questions such as:

- What topics are covered in Machine Learning?
- Which course covers SQL and normalization?
- What does Organizational Behaviour study?
- What topics are covered in Computer Networks?

## Example

### Question

Which course covers SQL and normalization?

### Answer

Database Systems covers relational databases, SQL, database design,
normalization, transactions, and database management.

## Technologies and Their Roles

### Sentence Transformers

Sentence Transformers are used to convert the course information
and user questions into numerical embeddings.

### Qdrant

Qdrant is used as the vector database. It stores the embeddings and
retrieves the most relevant course information when a question is asked.

### Ollama

Ollama is used to run the LLM locally and provide an API that the
Python application can communicate with.

### Llama 3.2

Llama 3.2 is the language model used to generate the final response
from the retrieved context.

## Setup

### Install Python Dependencies

Install the required Python libraries using:

```bash
pip install -r requirements.txt
