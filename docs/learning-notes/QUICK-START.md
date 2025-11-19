# Quick Start Guide

## Right Now - Get Started Today!

### 1. Get Your API Key (5 minutes)
```bash
# Visit https://aistudio.google.com/app/apikey
# Create a new API key
# Add to your shell profile

echo 'export GOOGLE_API_KEY="your-key-here"' >> ~/.zshrc
source ~/.zshrc
```

### 2. Setup Python Environment (5 minutes)
```bash
cd /Users/hai/hub/big/gemini/cookbook-gemini-learn

# Create virtual environment
python3 -m venv venv
source venv/bin/activate

# Install Gemini SDK
pip install google-generativeai jupyter ipykernel

# Add kernel to Jupyter
python -m ipykernel install --user --name=gemini-learn
```

### 3. Run Your First Example (10 minutes)
```bash
# Open first tutorial
jupyter notebook quickstarts/Get_started.ipynb

# Or run a quick test:
python3 << 'EOF'
import google.generativeai as genai
import os

genai.configure(api_key=os.environ.get('GOOGLE_API_KEY'))
model = genai.GenerativeModel('gemini-2.5-flash')

response = model.generate_content("Explain what an AI code agent is in one sentence")
print(response.text)
EOF
```

## Today's Goal: Complete Authentication Tutorial

**File**: `quickstarts/Authentication.ipynb`

**What You'll Learn**:
- How to set up API authentication
- Best practices for API key management
- Different authentication methods
- Rate limits and quotas

**Time**: 30-60 minutes

**Lab Exercise**: Create `labs/phase1/01-auth-test.py`
```python
"""
Test different authentication methods and API configurations
"""
import google.generativeai as genai
import os

def test_basic_auth():
    """Test basic API key authentication"""
    genai.configure(api_key=os.environ.get('GOOGLE_API_KEY'))
    model = genai.GenerativeModel('gemini-2.5-flash')

    response = model.generate_content("Hello, Gemini!")
    print(f"✓ Basic auth works: {response.text[:50]}...")

def test_model_listing():
    """List available models"""
    for model in genai.list_models():
        if 'generateContent' in model.supported_generation_methods:
            print(f"✓ Model: {model.name}")

if __name__ == "__main__":
    print("Testing Gemini API Authentication...")
    test_basic_auth()
    test_model_listing()
    print("\n✅ All tests passed!")
```

## This Week's Schedule

### Monday (Today)
- ✅ Setup dev branch
- ✅ Create learning structure
- ⏳ Get API key
- ⏳ Authentication tutorial

### Tuesday
- `Get_started.ipynb` - Basic prompting
- Lab: Test different prompting styles

### Wednesday
- `Counting_Tokens.ipynb` - Token management
- Lab: Token optimization experiments

### Thursday
- `Function_calling.ipynb` - Tool use basics
- Lab: Build a simple calculator agent

### Friday
- Review week's learnings
- Document key insights
- Plan Phase 2

## Common Commands Reference

### Git Workflow
```bash
# Check status
git status

# Stage and commit progress
git add docs/learning-notes labs/
git commit -m "Learning: [tutorial] - [insight]"

# View commits
git log --oneline -5
```

### Jupyter
```bash
# Start Jupyter
jupyter notebook

# Or use Jupyter Lab
jupyter lab

# List running servers
jupyter notebook list
```

### Python/Gemini
```python
# Quick test in Python REPL
import google.generativeai as genai
genai.configure(api_key="your-key")
model = genai.GenerativeModel('gemini-2.5-flash')
response = model.generate_content("test")
print(response.text)
```

## Troubleshooting

### "No module named 'google.generativeai'"
```bash
# Activate venv first
source venv/bin/activate
pip install google-generativeai
```

### "API key not found"
```bash
# Check environment variable
echo $GOOGLE_API_KEY

# If empty, export it
export GOOGLE_API_KEY="your-key-here"
```

### "Rate limit exceeded"
```python
# Add delay between requests
import time
time.sleep(1)  # Wait 1 second

# Or use exponential backoff
```

## Pro Tips

1. **Keep Notes Immediately** - Don't wait until the end
2. **Break Things** - Experiment in the `labs/` folder
3. **Use Gemini 2.5 Flash** - Fast and cost-effective for learning
4. **Commit Often** - Small, focused commits
5. **Ask Questions** - Use the Google AI forum

## Quick Links

- **API Key**: https://aistudio.google.com/app/apikey
- **Docs**: https://ai.google.dev/gemini-api/docs
- **Forum**: https://discuss.ai.google.dev/
- **Python SDK**: https://github.com/googleapis/python-genai
- **Pricing**: https://ai.google.dev/pricing

## Your Learning Goal

> **By Week 4**: Build a working AI code agent that can review pull requests and suggest improvements.

**Track Progress**: Update checkboxes in `2025-11-18-learning-strategy.md`

---

**Ready?** Let's start with the Authentication tutorial! 🚀

```bash
jupyter notebook quickstarts/Authentication.ipynb
```
