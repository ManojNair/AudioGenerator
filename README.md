# Podcast Generator - Semantic Kernel Version

This is a converted version of the original CrewAI-based podcast generator, now using Microsoft's Semantic Kernel framework.

## What Changed

### From CrewAI to Semantic Kernel

The original `podcast_v1.py` used CrewAI's Agent and Task system. This version has been converted to use Semantic Kernel's plugin-based architecture:

- **Agents** → **Plugins**: Converted CrewAI agents to Semantic Kernel plugins
- **Tasks** → **Sequential Workflow**: Replaced CrewAI task orchestration with direct plugin calls
- **LLM Integration**: Now uses Semantic Kernel's Azure OpenAI connector
- **Async Support**: Added proper async/await support for better performance

### Plugin Structure

1. **ImageAnalysisPlugin**: Handles image loading and basic processing
2. **BusinessAnalysisPlugin**: Analyzes image data and creates business reports
3. **PodcastScriptPlugin**: Converts business analysis to podcast scripts
4. **SSMLPlugin**: Handles SSML formatting and speech synthesis

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
python podcast_v1.py
```

The script will:
1. Load and analyze the image (`pbi_image.jpg`)
2. Generate a business analysis report
3. Create a podcast script with voice tags
4. Format the script as SSML
5. Convert to speech and save as a WAV file

## Key Differences from CrewAI Version

### Architecture
- **Before**: CrewAI agents with complex task dependencies
- **After**: Simple plugin classes with direct method calls

### Workflow
- **Before**: CrewAI orchestrated task execution
- **After**: Sequential async function calls in main()

### LLM Integration
- **Before**: LangChain AzureChatOpenAI
- **After**: Semantic Kernel AzureChatCompletion

### Error Handling
- **Before**: CrewAI task-level error handling
- **After**: Try-catch blocks around each workflow step

## Benefits of Semantic Kernel

1. **Simpler Architecture**: No complex agent/task orchestration
2. **Better Performance**: Direct plugin calls instead of CrewAI overhead
3. **Microsoft Integration**: Native support for Azure services
4. **Async Support**: Built-in async/await patterns
5. **Plugin System**: Cleaner separation of concerns

## Limitations

- **Image Analysis**: Currently returns placeholder text (needs Azure OpenAI vision integration)
- **Error Recovery**: Less sophisticated than CrewAI's delegation system
- **Parallelization**: Sequential execution instead of potential parallel processing

## Future Improvements

1. Integrate Azure OpenAI vision capabilities for proper image analysis
2. Add Semantic Kernel planners for more complex workflows
3. Implement parallel processing where possible
4. Add more sophisticated error handling and retry logic
