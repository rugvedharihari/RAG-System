# Simple Local RAG 
## Why RAG?

The main goal of RAG is to improve the generation outptus of LLMs.

Two primary improvements can be seen as:
1. **Preventing hallucinations** - LLMs are incredible but they are prone to potential hallucination, as in, generating something that *looks* correct but isn't. RAG pipelines can help LLMs generate more factual outputs by providing them with factual (retrieved) inputs. And even if the generated answer from a RAG pipeline doesn't seem correct, because of retrieval, you also have access to the sources where it came from.
2. **Work with custom data** - Many base LLMs are trained with internet-scale text data. This means they have a great ability to model language, however, they often lack specific knowledge. RAG systems can provide LLMs with domain-specific data such as medical information or company documentation and thus customized their outputs to suit specific use cases.

The authors of the original RAG paper mentioned above outlined these two points in their discussion.

> This work offers several positive societal benefits over previous work: the fact that it is more
strongly grounded in real factual knowledge (in this case Wikipedia) makes it “hallucinate” less
with generations that are more factual, and offers more control and interpretability. RAG could be
employed in a wide variety of scenarios with direct benefit to society, for example by endowing it
with a medical index and asking it open-domain questions on that topic, or by helping people be more
effective at their jobs.

RAG can also be a much quicker solution to implement than fine-tuning an LLM on specific data. 

RAG-Based Document Assistant

A production-ready Retrieval-Augmented Generation (RAG) system designed to provide accurate, context-aware responses using Large Language Models (LLMs) and semantic search. The project combines a scalable ingestion pipeline, vector search, and a smart query engine to deliver grounded answers backed by source documents.

Features

Scalable Ingestion Pipeline

Supports both URL-based ingestion and uploaded text files.

Automatically fetches, parses, and cleans data.

Uses LangChain’s UnstructuredURLLoader for reliable extraction.

Embedding & Vector Store

Generates text embeddings using OpenAI embedding models.

Stores vectors in FAISS for efficient similarity search.

Handles chunking and metadata tracking.

Semantic Search Retrieval

Retrieves top-k most relevant chunks using vector similarity.

Ensures contextual grounding for better LLM output.

Provides clear source attribution.

LLM-Powered Query Engine

Uses ChatGPT (or any supported LLM) to synthesize responses.

Merges retrieved context into meaningful answers.

Minimizes hallucinations through retrieval grounding.

Architecture Overview

User Query → Embed → FAISS Similarity Search → Retrieve Top-k Chunks → Prompt Construction → LLM → Final Answer + Sources

Ingestion Flow:
URL/File → Loader → Cleaning → Chunking → Embeddings → FAISS Index



