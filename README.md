# 🧠 HealthGPT

**HealthGPT** is a domain-specific small language model (SLM) built for medical and healthcare-related tasks. 
It includes a FastAPI backend for inference and model management, a React + Vite frontend for interaction, and a full 
training and evaluation pipeline for scaling the model from 1M to 25M parameters.

---

## 📁 Project Structure

## 🔧 Backend (`/backend`)
The FastAPI backend handles:
- `/inference` — Accepts text input and returns a generated response
- `/train` (optional) — API to trigger training jobs
- Model loading and caching
- Middleware and service architecture

**Files:**
- `main.py`: Starts FastAPI app
- `routes/inference.py`: Core inference API
- `services/generator.py`: Wraps model logic
- `core/config.py`: Environment config
- `model_loader.py`: Loads tokenizer + model

### 🚀 Run backend

- cd backend
- pip install -r requirements.txt
- uvicorn app.main:app --reload

---

**🤖 Model (/model)**
This folder includes training, evaluation, and inference code for your small language model (starting at 1M parameters, scalable to 25M):
Files:
- `train.py:` Model training loop
- `evaluate.py:` Evaluate model on QA / NER tasks
- `inference.py:` Load model + generate text
- `config.yaml:` Hyperparameters and paths
- `checkpoints/:` Saved weights

---

**🛠️ Utilities (/utils)**
This contains helper functions used across training and backend services.
Files:
- `logger.py:` Custom logging setup
- `helpers.py:` Miscellaneous utility functions

---

**🧹 Scripts (/scripts)**
Data preprocessing tools for converting raw healthcare text into training-ready datasets.
Files:
- `collect_pubmed.py:` (Optional) PubMed data scraper
- `clean_text.py:` Lowercasing, punctuation stripping, deduplication
- `tokenize.py:` Tokenizes text using HuggingFace tokenizer
- `dataset_split.py:` Train/test/validation split

---

**💻 Frontend (/react-frontend)**
React + Vite UI to interact with the model. It lets users input a question and receive generated responses from the model.
Files:
- `components/InferenceForm.jsx:` Form + results display
- `api/inference.js:` Axios POST to FastAPI backend
- `App.jsx:` Renders core layout
- `main.jsx:` App entry point
  
**🚀 Run frontend**
  
- cd react-frontend
- npm install
- npm run dev

---

**🚀 Main Entry Script (main.py)**
This file orchestrates your full pipeline and can be used to:
- Clean data
- Tokenize and prepare dataset
- Launch training
- Run offline inference

---

**🙌 Credits**
- 🤖 HuggingFace Transformers
- ⚡ FastAPI
- ⚛️ React + Vite
- 🧠 PubMed / MIMIC datasets

---
