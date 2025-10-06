# SDXL-Turbo Local Image Generator

A simple and efficient local Python tool to generate **ultra-realistic images** using the `stabilityai/sdxl-turbo` model from Hugging Face.  
It runs **entirely on your own GPU** (CUDA) for fast, high-quality image generation.

---

## Features
- Local generation — uses your GPU, no cloud API needed  
- Interactive prompt input directly in the terminal  
- Multiple detail levels (fast / normal / high precision)  
- Automatic image saving in the `outputs/` folder  
- Works with **NVIDIA GPUs (CUDA)** and can fall back to CPU (slower)  

---

## Requirements

- **Python 3.10** or **3.11** (PyTorch is not yet compatible with Python 3.13)
- **NVIDIA GPU with CUDA 12+** (recommended 6GB VRAM minimum)

---

## Installation

```bash
# Clone the repository
git clone https://github.com/<your-username>/sdxl-turbo-local.git
cd sdxl-turbo-local

# Create and activate virtual environment
python -m venv venv
.\venv\Scripts\activate   # (Windows)
# or: source venv/bin/activate (Linux/Mac)

# Install dependencies
pip install torch torchvision torchaudio diffusers transformers accelerate safetensors pillow --index-url https://download.pytorch.org/whl/cu121
