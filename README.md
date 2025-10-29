# P.A.R.T.H

**Personalized Autonomous Robot with Thinking & Humanness**

P.A.R.T.H is an intelligent AI companion that combines real-time computer vision with conversational AI to create a curious, child-like robot personality. Built with a scalable architecture that supports both local development and cloud deployment.

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![FastAPI](https://img.shields.io/badge/FastAPI-Ready-green.svg)
![YOLO](https://img.shields.io/badge/YOLO-v8-orange.svg)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)

## Features

- **Real-time Computer Vision** - YOLO-based object detection with live camera feed
- **Conversational AI** - Powered by Ollama/HuggingFace models with contextual memory
- **Vector Memory** - PostgreSQL + pgvector for intelligent conversation retrieval
- **Curious Personality** - Child-like AI that questions everything it sees
- **Highly Configurable** - Zero hardcoding, everything driven by YAML config
- **API-Ready Architecture** - Built for easy scaling from local to cloud

## 🏗️ Architecture Overview

```
P.A.R.T.H/
├── main.py                # Entry point (CLI) / Future FastAPI server
├── config.yaml            # Complete system configuration
├── chat/                  # Conversational AI system
│   ├── runner.py          # Main orchestrator
│   ├── memory.py          # PostgreSQL + pgvector memory
│   └── prompt_manager.py  # Personality management
├── llm/                   # Language model backends
│   ├── ollama_client.py   # Ollama integration (active)
│   └── hf_client.py       # HuggingFace integration (planned)
├── vision/                # Computer vision system
│   └── vision.py          # YOLO-based object detection
├── prompts/               # AI personality definitions
│   ├── system.txt         # Curious child personality (JSON)
│   └── tools.md           # Available capabilities
└── voice/                 # Audio processing (future)
    └── txt_v.py           # Speech-to-text/text-to-speech
```

## 🚀 Quick Start

### Prerequisites

- **Python 3.8+**
- **NeonDB Account** (free serverless PostgreSQL with pgvector)
- **Ollama** (for local LLM inference)
- **Webcam** (for vision features)

### 1. Environment Setup

```bash
# Clone the repository
git clone https://github.com/Tez2213/P.A.R.T.H.git
cd P.A.R.T.H

# Create virtual environment
python -m venv venv

# Activate virtual environment
# Windows:
venv\Scripts\activate
# Linux/Mac:
source venv/bin/activate

# Install dependencies
pip install -r requirement.txt
```

### 2. Database Setup (NeonDB)

```bash
# 1. Create NeonDB account at https://neon.tech (free tier available)
# 2. Create a new project/database
# 3. Copy the connection string from your NeonDB dashboard

# Example connection string format:
# postgres://username:password@ep-xxxxx.us-east-1.aws.neon.tech/neondb?sslmode=require

# 4. pgvector extension is already available in NeonDB - no manual setup needed!
```

**NeonDB Setup Steps:**
1. Visit [neon.tech](https://neon.tech) and sign up (free)
2. Create new project → Choose region → Create database
3. Go to **Connection Details** → Copy **Connection String**
4. Update `config.yaml` with your connection string (see step 4)

### 3. Ollama Setup

```bash
# Install Ollama
curl -fsSL https://ollama.ai/install.sh | sh

# Pull the model (lightweight 1.5B parameter model)
ollama pull qwen2.5:1.5b

# Verify installation
ollama list
```

### 4. Configuration

The system is fully configurable via `config.yaml`. Key settings:

```yaml
# Model Selection
backend: ollama
models:
  ollama: "qwen2.5:1.5b"
  embedding: "sentence-transformers/all-MiniLM-L6-v2"

# Database Connection (NeonDB)
database:
  provider: neondb
  connection:
    url: "postgres://username:password@ep-xxxxx.us-east-1.aws.neon.tech/neondb?sslmode=require"

# Vision System
vision:
  enabled: true
  model_type: "yolov8n"
  camera:
    source: 0  # Default webcam
```

### 5. Run P.A.R.T.H

```bash
python main.py
```

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **Ultralytics** for YOLO models
- **Ollama** for local LLM inference
- **Sentence Transformers** for embeddings
- **pgvector** for vector similarity search
- **FastAPI** for future API framework

## 📞 Support

- **Issues**: [GitHub Issues](https://github.com/Tez2213/P.A.R.T.H/issues)
- **Discussions**: [GitHub Discussions](https://github.com/Tez2213/P.A.R.T.H/discussions)
- **Creator**: Tejasvi Kesarwani

---

**P.A.R.T.H** - Built with ❤️ for advancing humanoid robotics and AI companions
