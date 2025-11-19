# Labs - Personal Learning Experiments

This folder contains personal experiments and learning code while working through the Gemini Cookbook.

## Structure

```
labs/
├── phase1/     # Foundation tutorials (Week 1)
├── phase2/     # Core features (Week 2)
└── phase3/     # Advanced agents (Week 3-4)
```

## Guidelines

1. **One file per tutorial** - Keep experiments focused
2. **Name format**: `tutorial-name-experiment.py` or `.ipynb`
3. **Add comments** - Future you will thank present you
4. **Break things** - This is a safe space to experiment
5. **Don't commit secrets** - Use environment variables

## Environment Setup

```bash
# Create virtual environment
python -m venv venv
source venv/bin/activate  # or `venv\Scripts\activate` on Windows

# Install Gemini SDK
pip install google-generativeai

# Set API key
export GOOGLE_API_KEY='your-api-key-here'
```

## Typical Lab File Structure

```python
"""
Tutorial: [Name]
Date: YYYY-MM-DD
Focus: [What you're testing]
"""

import google.generativeai as genai
import os

# Setup
genai.configure(api_key=os.environ.get('GOOGLE_API_KEY'))

# Your experiments here
def experiment_1():
    """Test basic functionality"""
    pass

def experiment_2():
    """Test variations"""
    pass

if __name__ == "__main__":
    experiment_1()
    experiment_2()
```

## Common Patterns to Explore

### 1. Function Calling Pattern
```python
tools = [
    {
        "function_declarations": [
            {
                "name": "get_weather",
                "description": "Get weather info",
                "parameters": {...}
            }
        ]
    }
]
```

### 2. Multi-turn Conversation
```python
chat = model.start_chat(history=[])
response1 = chat.send_message("Hello")
response2 = chat.send_message("Follow up")
```

### 3. Streaming Responses
```python
for chunk in model.generate_content("...", stream=True):
    print(chunk.text, end='')
```

## Resources
- [Gemini API Docs](https://ai.google.dev/gemini-api/docs)
- [Python SDK Reference](https://github.com/googleapis/python-genai)
- [Cookbook](https://github.com/google-gemini/cookbook)
