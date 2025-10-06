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

#Run the interactive script:
python sdxl_interactive.py

#Configuration
You can adjust the generation parameters directly inside the script:


| Parameter                 | Description                     | Recommended                              |
| ------------------------- | ------------------------------- | ---------------------------------------- |
| `STEPS`                   | Number of inference steps       | 4–6 (Turbo), up to 12 for more detail    |
| `GUIDANCE`                | Prompt adherence                | 0.0 for Turbo, 1.5–2.0 for high fidelity |
| `IMG_WIDTH`, `IMG_HEIGHT` | Image resolution                | 768×768 or 1024×1024                     |
| `NUM_IMAGES`              | Number of variations per prompt | 1–3                                      |


#Example Prompts

Realistic food shot
Ultra realistic photo of a strawberry tart on a white plate, topped with whipped cream, soft natural lighting, shallow depth of field, 8k detail

Portrait
Ultra realistic portrait of a beautiful young woman, perfect symmetrical face, smooth skin, cinematic lighting, sharp focus, 8k ultra detailed

Cinematic scene
Ultra realistic photo of an old leather book on a wooden table, sunlight through a window, soft shadows, detailed textures

#Performance
| Mode           | Steps | Guidance | Example Size | Average Time (RTX 4060) |
| -------------- | ----- | -------- | ------------ | ----------------------- |
| Fast           | 4     | 0.0      | 512×512      | ~1.5 s                  |
| Normal         | 6     | 1.5      | 768×768      | ~2.5 s                  |
| High Precision | 12    | 2.0      | 1024×1024    | ~4.5 s                  |
