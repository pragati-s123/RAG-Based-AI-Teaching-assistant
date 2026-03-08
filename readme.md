# RAG-Based AI Teaching Assistant

An AI-powered teaching assistant that answers questions from course materials using a Retrieval Augmented Generation (RAG) pipeline.  
This project processes lecture videos, converts them to text, stores the information in structured form, and retrieves relevant knowledge to generate answers.

---

## Overview

This project builds a simple RAG pipeline that allows users to query lecture content.  
It processes video lectures step by step and prepares them for AI-based question answering.

---

## Features

- Convert lecture videos to audio
- Convert audio to text using speech-to-text
- Convert transcripts to structured JSON
- Generate embeddings for semantic search
- Retrieve relevant lecture content
- Generate answers using AI models

---

## Project Workflow

1. Convert video lectures to audio files
2. Convert audio to text using speech-to-text
3. Store transcripts in JSON format
4. Process and clean transcript data
5. Generate embeddings for semantic retrieval
6. Retrieve relevant content based on user query
7. Generate AI-powered responses

---

## Project Structure

```
RAG-Based-AI-Teaching-assistant
│
├── audios/                # Sample audio files
├── jsons/                 # Raw transcript JSON files
├── newjsons/              # Processed transcript files
│
├── video_to_mp3.py        # Convert video lectures to audio
├── mp3_to_json.py         # Convert audio transcripts to JSON
├── stt.py                 # Speech-to-text processing
├── process_incoming.py    # Process transcript data
├── merge_chunks.py        # Combine transcript chunks
├── preprocessed_json.py   # Data preprocessing
│
├── embeddings.joblib      # Stored embeddings for retrieval
├── prompt.txt             # Prompt template for LLM
├── output.json            # Example output
└── README.md              # Project documentation
```

---

## Technologies Used

- Python
- Speech-to-Text
- Embeddings
- Retrieval Augmented Generation (RAG)
- JSON data processing

---

## Example Use Case

A student can ask questions like:

> "What is SEO in web development?"

The system retrieves the relevant lecture segment and generates a contextual answer.

---

## Future Improvements

- Add web interface for queries
- Integrate vector database
- Improve retrieval accuracy
- Deploy as a web application

---

## Author

**Pragati Sharma**  
B.Tech Electronics Engineering  
Aspiring Data Scientist and AI Enthusiast
