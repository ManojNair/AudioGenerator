# Podcast Generator - Semantic Kernel Version

This is a converted version of the original CrewAI-based podcast generator by the awesome Data and AI Solutions Engineer @Lakshmy - https://github.com/Lakshmy/audiogenerator, now using Microsoft's Semantic Kernel framework.


## Installation

1. Install dependencies:
```bash
pip install -r requirements.txt
```

2. Set up environment variables in `.env`:
```env
AZURE_OPENAI_KEY=your_key_here
AZURE_OPENAI_ENDPOINT=your_endpoint_here
AZURE_OPENAI_MODEL_DEPLOYMENT=your_deployment_name
AZURE_OPENAI_API_VERSION=2024-02-15-preview
AZURE_SPEECH_KEY=your_speech_key
AZURE_SPEECH_REGION=your_speech_region
```

## Usage

Run the podcast generator:
```bash
python3 podcast_v1_sk.py
```

The script will:
1. Load and analyze the image (`pbi_image.jpg`)
2. Generate a business analysis report
3. Create a podcast script with voice tags
4. Format the script as SSML
5. Convert to speech and save as a WAV file
