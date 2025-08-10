# Webpage-Summarizer-with-LLM
his project scrapes a given website and parse the data , extracts relevant text, and summarizes it using a Large Language Model (LLM). It supports both Ollama (local models like gemma:2-27b or llama3.2) and OpenAI models (like gpt-4o-mini).

🚀 Features
1.Web Scraping — Fetches HTML content and cleans it with BeautifulSoup
2.Custom Headers — Avoids blocking by sending browser-like headers
3.Text Parsing — Removes unnecessary elements like scripts, styles, images, and inputs
4.LLM Summarization — Sends extracted text to an LLM for a concise summary
5.Flexible Backends — Choose between local Ollama models or OpenAI API

🛠 Requirements
Install dependencies:
pip install requests beautifulsoup4 python-dotenv openai
📦 Setup
1️⃣ Using Ollama (Local)
Install Ollama from: https://ollama.com/download
Pull your desired model:
bash
ollama pull llama3.2
Start Ollama:
from openai import OpenAI
MODEL = "gemma:2-27b"
openai = OpenAI(base_url="http://localhost:11434/v1", api_key="ollama")

2️⃣ Using OpenAI API
Create an .env file in the project root:
OPENAI_API_KEY=your_openai_api_key_here
from openai import OpenAI
MODEL = "gpt-4o-mini"
openai = OpenAI()
▶️ Running the Script
Example:
from summarizer import display_summary
display_summary("https://example.com")
🧠 How It Works
1.Website class → Downloads and parses HTML
2.messages_for() → Prepares the system and user prompts for the LLM
3.summarize() → Sends extracted text to the model and gets a summary
4.display_summary() → Displays the summary in Markdown format

🔄 Switching Between Ollama & OpenAI
For Ollama:
MODEL = "gemma:2-27b"
openai = OpenAI(base_url="http://localhost:11434/v1", api_key="ollama")
For OpenAI:
MODEL = "gpt-4o-mini"
openai = OpenAI()

text
Copy
Edit
$ python summarizer.py
Website: https://example.com
Summary: This summary is generated using OpenAI’s GPT-4o-mini API, offering faster but cloud-based process
