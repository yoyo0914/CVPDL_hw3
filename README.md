# Stable Diffusion Image Generation Pipeline

A streamlined pipeline for generating industrial and safety-related images using Stable Diffusion models, incorporating image captioning and multiple generation approaches.

## Requirements

- Python 3.7+
- CUDA-capable GPU
- Google Colab environment
- Google Drive mounted

## Installation

```bash
pip install torch-fidelity torchmetrics[image] torchmetrics
pip install -q diffusers transformers accelerate huggingface_hub
```

## Directory Structure

```
/content/drive/MyDrive/hw/
├── images/            # Source images
├── label.json        # Labels and bounding boxes
├── generated_images/ # Generated outputs
└── checkpoint.json   # Progress tracking
```

## Pipeline Components

1. **Image Captioning (BLIP-2)**
   - Generates image descriptions
   - Adds safety-focused prompts
   - Creates final_generated_prompts.json

2. **Basic Generation (Realistic Vision V2.0)**
   - Generates three versions per image
   - Resolution: 512x512
   - Includes safety prompts

3. **Layout Generation**
   - Uses bounding box information
   - Maintains original composition
   - Generates layout-aware images

## Quick Start

1. Mount Google Drive:
```python
from google.colab import drive
drive.mount('/content/drive')
```

2. Run cells:

## Features

- Batch processing with checkpoints
- Automatic error recovery
- Memory optimization
- Progress tracking
- Safety-focused prompt generation

## Output Types

- Basic generated images
- Label-enhanced images
- Safety-prompt images
- Layout-aware images

## Models Used

- Image Captioning: Salesforce/blip2-opt-2.7b
- Image Generation: SG161222/Realistic_Vision_V2.0

For more details or issues, please check the code comments or raise an issue.
