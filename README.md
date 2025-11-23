# Real-Time RAG AI Sales Agent

A real-time retrieval-augmented generation (RAG) AI agent for sales support that leverages live audio, speaker identification, and AI models to provide instant, factually grounded answers in a conversational style.

## Features

- **Live Audio Streaming**: Uses Deepgram for real-time speech recognition and speaker diarization.
- **Speaker Identification**: Differentiates between "Om" (agent) and customer voices.
- **Intent Classification**: Classifies incoming questions as factual, product-opinion, or personal (ignored) using Groq LLaMA models.
- **Context-Aware Query Rewriting**: Resolves ambiguous questions into standalone search queries.
- **Knowledge Retrieval**: Uses Tavily to search relevant documents and information.
- **Factual Answer Generation**: Uses Gemini AI to produce accurate, spoken-style answers based on retrieved context.
- **Conversation Memory**: Maintains a transcript of recent interactions for context-aware responses.
- **Asynchronous Processing**: Handles multiple concurrent tasks including audio streaming, query rewriting, and answer generation.

## Architecture

1. **Audio Capture**: `pyaudio` streams live audio to a queue.
2. **Deepgram Integration**: Streams audio to Deepgram WebSocket API for real-time transcription and speaker diarization.
3. **Intent Detection**: Classifies incoming questions using Groq LLaMA models.
4. **Query Rewriting**: Ambiguous questions are rewritten into standalone search queries.
5. **Search & Retrieval**: Tavily search returns relevant context for answering the question.
6. **Answer Generation**: Gemini AI produces concise, helpful responses based on search results.
7. **Transcript Management**: Keeps conversation history to provide context when needed.
