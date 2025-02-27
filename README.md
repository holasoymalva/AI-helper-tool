# 🤖 AI Helper Tool

[![GitHub stars](https://img.shields.io/github/stars/holasoymalva/ai-helper-tool)](https://github.com/holasoymalva/ai-helper-tool/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/holasoymalva/ai-helper-tool)](https://github.com/holasoymalva/ai-helper-tool/network/members)
[![GitHub issues](https://img.shields.io/github/issues/holasoymalva/ai-helper-tool)](https://github.com/holasoymalva/ai-helper-tool/issues)
[![GitHub license](https://img.shields.io/github/license/holasoymalva/ai-helper-tool)](https://github.com/holasoymalva/ai-helper-tool/blob/main/LICENSE)

A toolkit for developing AI applications with Python, Streamlit, and language model APIs like Anthropic Claude or Google Gemini.

## 📋 Features

- 🚀 Quick setup for AI projects
- 🔌 Simplified integration with Anthropic and Google Gemini APIs
- 📊 Ready-to-use Streamlit interface templates
- 🛠️ Reusable components for common use cases
- 📝 Comprehensive examples to get started quickly

## 🚀 Quick Start

### Prerequisites

- Python 3.8 or higher
- Pip (Python package manager)
- API keys for services you plan to use (Anthropic, Google Gemini, etc.)

### Installation

```bash
# Clone the repository
git clone https://github.com/holasoymalva/ai-helper-tool.git
cd ai-helper-tool

# Create a virtual environment
python -m venv venv

# Activate the virtual environment
# On Windows:
venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt
```

### Configuration

1. Create a `.env` file in the project root
2. Add your API keys:

```
ANTHROPIC_API_KEY=your_anthropic_api_key
GOOGLE_API_KEY=your_google_api_key
```

### Run examples

```bash
# Run Anthropic demo
streamlit run examples/anthropic_demo.py

# Run Google Gemini demo
streamlit run examples/gemini_demo.py
```

## 🧩 Project Structure

```
ai-helper-tool/
├── examples/                  # Example applications
│   ├── anthropic_demo.py      # Demo using Anthropic API
│   └── gemini_demo.py         # Demo using Gemini API
├── helpers/                   # Shared utilities
│   ├── api_wrapper.py         # Wrapper for LLM APIs
│   └── prompt_templates.py    # Prompt templates
├── ui/                        # User interface components
│   ├── chat_interface.py      # Reusable chat interface
│   └── sidebar_components.py  # Sidebar components
├── .env.example               # Example environment variables
├── requirements.txt           # Project dependencies
└── README.md                  # This documentation
```

## 📚 Documentation

### Core Modules

#### API Wrapper

Provides a unified interface for different LLM API providers:

```python
from helpers.api_wrapper import AnthropicAPI, GeminiAPI

# Initialize Anthropic client
anthropic_client = AnthropicAPI()
response = anthropic_client.generate_text("Explain artificial intelligence")

# Initialize Gemini client
gemini_client = GeminiAPI()
response = gemini_client.generate_text("Explain artificial intelligence")
```

#### Chat Interface

Reusable component for creating chat interfaces:

```python
from ui.chat_interface import create_chat_ui

# Create a chat interface with Anthropic
create_chat_ui(api_client=anthropic_client, title="Chat with Claude")
```

## 🧪 Examples

### Basic Chat Application

```python
import streamlit as st
from helpers.api_wrapper import AnthropicAPI
from ui.chat_interface import create_chat_ui

st.set_page_config(page_title="AI Chat", layout="wide")
st.title("💬 Chat with Claude")

# Initialize API client
api_client = AnthropicAPI()

# Create chat interface
create_chat_ui(api_client)
```

### Text Analyzer

```python
import streamlit as st
from helpers.api_wrapper import GeminiAPI

st.set_page_config(page_title="Text Analyzer", layout="wide")
st.title("📝 AI Text Analyzer")

# Configure API client
api_client = GeminiAPI()

# Create text area for user input
user_input = st.text_area("Enter text to analyze:", height=200)

if st.button("Analyze"):
    with st.spinner("Analyzing..."):
        # Send request to API
        response = api_client.analyze_text(user_input)
        
        # Display results
        st.subheader("Analysis Results")
        st.write(response)
```

## 🤝 Contributing

Contributions are welcome! If you want to contribute:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/new-feature`)
3. Commit your changes (`git commit -m 'Add new feature'`)
4. Push the branch (`git push origin feature/new-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
