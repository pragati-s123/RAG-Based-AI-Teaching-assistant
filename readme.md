# RAG-Based AI Teaching Assistant

An AI-powered teaching assistant that uses Retrieval-Augmented Generation (RAG) to answer questions from course lecture materials and help students locate relevant topics in video lectures.

## Problem Statement

Students often spend time searching through lengthy video lectures to find specific concepts, explanations, or topics. This project aims to simplify that process by retrieving relevant lecture segments and generating contextual answers with video references and timestamps.

## Features

- Extract audio from course videos using FFmpeg.
- Transcribe lecture audio using OpenAI Whisper.
- Generate structured transcripts with timestamps.
- Group transcript segments into larger chunks.
- Generate semantic embeddings using BGE-M3.
- Retrieve relevant lecture chunks using cosine similarity.
- Generate contextual responses using Llama 3.2.
- Provide relevant video numbers and timestamps in answers.

## Architecture

1. **Video Processing:** Extract audio from lecture videos using FFmpeg.
2. **Speech-to-Text:** Convert audio into timestamped transcript segments using Whisper.
3. **Data Preprocessing:** Organize transcripts into structured JSON and merge consecutive segments.
4. **Embedding Generation:** Generate vector embeddings using BGE-M3 through Ollama.
5. **Retrieval:** Convert user queries into embeddings and retrieve the top 5 most similar chunks using cosine similarity.
6. **Generation:** Pass retrieved context and the user's question to Llama 3.2.
7. **Response:** Generate an answer with relevant lecture references and timestamps.

## Tech Stack

- Python
- OpenAI Whisper (speech-to-text)
- FFmpeg (audio extraction)
- Ollama
- BGE-M3 (embeddings)
- Llama 3.2 (text generation)
- NumPy and Pandas
- Scikit-learn
- Joblib
- JSON

## Project Structure

- `video_to_mp3.py` – Extracts audio from lecture videos.
- `mp3_to_json.py` – Transcribes audio and generates timestamped JSON.
- `stt.py` – Standalone speech-to-text example.
- `merge_chunks.py` – Combines consecutive transcript segments.
- `preprocessed_json.py` – Generates embeddings and stores them.
- `process_incoming.py` – Performs query embedding, semantic retrieval, and answer generation.
- `prompt.txt` – Example generated prompt.
- `output.json` – Example transcription output.

## Installation

1. Clone the repository.
2. Create and activate a Python virtual environment.
3. Install dependencies using `pip install -r requirements.txt`.
4. Install FFmpeg separately.
5. Install Ollama and download the required models:

   - `ollama pull bge-m3`
   - `ollama pull llama3.2`

6. Create the required input directories and provide course videos.

## Running the Pipeline

Run the scripts in this order:

1. `python video_to_mp3.py`
2. `python mp3_to_json.py`
3. `python merge_chunks.py`
4. `python preprocessed_json.py`
5. `python process_incoming.py`

Ensure the expected input folders and files exist before executing each stage.

## Limitations

- Retrieval currently uses in-memory cosine similarity over stored embeddings.
- No dedicated vector database is integrated.
- The current query interface is command-line based.
- Retrieval quality depends on transcript quality and chunking.
- Answers depend on the relevance and completeness of retrieved context.

## Future Improvements

- Build an interactive web interface.
- Integrate a scalable vector database.
- Improve chunking and retrieval accuracy.
- Add similarity thresholds and evaluation metrics.
- Add error handling and input validation.
- Deploy the application as a web service.

## Author

Pragati Sharma  
B.Tech – Electronics Engineering
