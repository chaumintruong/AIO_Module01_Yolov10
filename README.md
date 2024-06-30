# Project: PDF Question-Answering with RAG and Chainlit

## Overview
This project uses Retrieval Augmented Generation (RAG) for question-answering from PDF documents.

## Requirements
- Google Colab with GPU
- Python libraries: transformers, bitsandbytes, accelerate, langchain, langchainhub, langchain-chroma, langchain-community, langchain_huggingface, python-dotenv, pypdf, numpy, chainlit

## Setup
1. Install the required libraries.
2. Load your PDF file and split it into chunks.
3. Create a vector database using the `langchain` and `Chroma`.
4. Initialize the Vicuna model for text generation.
5. Run the RAG pipeline to get answers to your questions.

## Usage
- Run the provided code in Google Colab.
- Use the Chainlit interface for an interactive chat experience.

## Notes
- Ensure to have a PDF document ready for question-answering.
- Modify paths and questions as needed for your use case.
