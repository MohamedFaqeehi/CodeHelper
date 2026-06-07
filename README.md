# CodeHelper

An AI-powered coding assistant that runs in your terminal. Give it a prompt and it will autonomously read your files, write code, and execute Python scripts to help you get things done — powered by Google Gemini.

## Features

- 📂 Read files and directory structure in your project
- ✏️ Write and edit files based on your instructions
- 🐍 Execute Python scripts and report the output
- 🔁 Agentic loop — keeps working until the task is complete or the iteration limit is reached

## Requirements

- Python 3.11+
- A [Google Gemini API key](https://aistudio.google.com/app/apikey)
- [`uv`](https://docs.astral.sh/uv/) for dependency management

## Setup

```bash
git clone https://github.com/MohamedFaqeehi/CodeHelper.git
cd CodeHelper

# Install dependencies
uv sync

# Add your Gemini API key
echo "GEMINI_API_KEY=your_key_here" > .env
```

## Usage

```bash
uv run main.py "Your prompt here"
```

### Examples

```bash
# Ask it to explain your code
uv run main.py "Explain what main.py does"

# Ask it to fix a bug
uv run main.py "The calculator is returning wrong results for division, fix it"

# Ask it to add a feature
uv run main.py "Add a square root function to the calculator"
```

### Verbose mode

Use `--verbose` to see token usage and function call details:

```bash
uv run main.py "List all Python files in this project" --verbose
```

## Project Structure

```
CodeHelper/
├── main.py              # Entry point and agent loop
├── call_function.py     # Function dispatcher for Gemini tool calls
├── config.py            # Configuration (working dir, max iterations)
├── prompts.py           # System prompt for the AI
├── functions/
│   ├── get_files_info.py    # List files in a directory
│   ├── get_file_content.py  # Read a file's contents
│   ├── run_python_file.py   # Execute a Python file
│   └── write_file.py        # Write content to a file
└── calculator/          # Example project for testing
```
