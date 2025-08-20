AudioRAG: A Cross-Lingual Q&A System for Audio Content
AudioRAG is a complete, end-to-end system built in a Google Colab environment that enables natural language querying of audio content. It takes a Tamil song as audio input and allows a user to ask questions in English, receiving contextually-aware answers based solely on the song's lyrics.

Key Features 🚀
End-to-End Pipeline: Processes raw audio files directly to conversational answers without manual intervention.

Cross-Lingual Q&A: Seamlessly handles English questions on a Tamil-language knowledge base.

Retrieval-Augmented Generation (RAG): Implements a state-of-the-art RAG workflow to ensure answers are factually grounded in the source material.

Hallucination Mitigation: Uses advanced "few-shot" prompting to prevent the AI from inventing answers not found in the lyrics.

Interactive Interface: A simple ipywidgets interface for easy querying within the notebook.

Tech Stack & Tools 🛠️
Programming Language: Python

Environment: Google Colab

Core AI Libraries: LangChain, PyTorch, Transformers

Speech-to-Text Model: OpenAI - Whisper

Embedding Model: sentence-transformers/paraphrase-multilingual-MiniLM-L12-v2

Vector Database: Facebook AI - FAISS (faiss-cpu)

Generative LLM: Google - Gemini 1.5 Flash (via google-generativeai library)

Workflow ⚙️
Audio Transcription: An audio clip of a Tamil song is loaded and transcribed into raw text using Whisper.

Vector DB Creation: The resulting Tamil text is chunked and then converted into numerical vectors (embeddings) using the multilingual embedding model. These vectors are stored in a FAISS index, creating a searchable knowledge base.

Cross-Lingual Retrieval: A user's question in English is embedded using the same model. The system performs a similarity search in the FAISS index to find the most relevant Tamil text chunks.

Answer Generation: The retrieved Tamil chunks and the original English question are passed to the Gemini LLM with a carefully engineered prompt. The model synthesizes a final, accurate answer in English.
