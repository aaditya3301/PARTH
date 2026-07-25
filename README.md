# P.A.R.T.H

**Personalized Autonomous Robot with Thinking & Humanness**

P.A.R.T.H is an AI-powered robotic companion that combines computer vision, conversational AI, and long-term memory to create a curious, human-like personality.

## Features

* Real-time object detection using YOLO
* Conversational AI with contextual memory
* PostgreSQL and pgvector-based memory
* Curious, child-like personality
* Fully configurable through YAML
* Supports local and cloud deployment

## Tech Stack

* **Language:** Python
* **AI:** Ollama, Hugging Face
* **Vision:** YOLO
* **Database:** PostgreSQL, pgvector, NeonDB
* **Embeddings:** Sentence Transformers
* **API:** FastAPI

## Project Structure

```text
P.A.R.T.H/
├── main.py          # Application entry point
├── config.yaml      # System configuration
├── chat/            # Conversation and memory
├── llm/             # LLM integrations
├── vision/          # Object detection
├── prompts/         # Personality prompts
└── voice/           # Voice features
```

## Setup

```bash
git clone
cd P.A.R.T.H

python -m venv venv
```

Activate the environment:

```bash
# Windows
venv\Scripts\activate

# Linux/macOS
source venv/bin/activate
```

Install dependencies:

```bash
pip install -r requirement.txt
```

Install and configure Ollama:

```bash
ollama pull qwen2.5:1.5b
```

Add your NeonDB connection string inside `config.yaml`, then run:

```bash
python main.py
```

## License

Licensed under the MIT License.

Built for exploring humanoid robotics and AI companions.
