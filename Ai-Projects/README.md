# AI Chat Assistant

A simple, beginner-friendly chatbot built with **Streamlit** and **LangChain**, powered by **Google Gemini**. It has a modern chat interface with message bubbles, Material icons, and conversation memory.

The assistant replies in simple English and stays on topic.

---

## Features

- Modern chat UI with user and assistant bubbles
- Remembers the whole conversation (chat memory)
- "Thinking..." spinner while the model replies
- Clear chat button in the sidebar
- Clean Material icons (easy to change)
- Short, easy-to-read code, good for learning
- Easy to switch between Gemini and OpenAI models

---

## Tech Stack

| Tool | Purpose |
|------|---------|
| [Python 3.9+](https://www.python.org/) | Programming language |
| [Streamlit](https://streamlit.io/) | Web app and chat UI |
| [LangChain](https://www.langchain.com/) | Connects the app to the AI model |
| [Google Gemini](https://ai.google.dev/) | The AI model |
| [python-dotenv](https://pypi.org/project/python-dotenv/) | Loads the API key from a `.env` file |

---

## Project Structure

```
your-project/
├── app.py              # Main Streamlit app
├── .env                # Your secret API key (do NOT share or upload this)
├── requirements.txt    # Python packages needed
└── README.md           # This file
```

---

## How to Run on Your Local Machine

### 1. Prerequisites

- Python 3.9 or newer installed. Check with:
  ```bash
  python --version
  ```
- A Google Gemini API key. You can get one for free from [Google AI Studio](https://aistudio.google.com/app/apikey).

### 2. Get the project

Put `app.py` in a new folder, or clone the repository if you have one:

```bash
git clone <your-repo-url>
cd <your-project-folder>
```

### 3. Create a virtual environment (recommended)

**Windows**
```bash
python -m venv venv
venv\Scripts\activate
```

**Mac / Linux**
```bash
python3 -m venv venv
source venv/bin/activate
```

### 4. Install the packages

Create a file named `requirements.txt` with this content:

```
streamlit
python-dotenv
langchain-core
langchain-google-genai
```

Then run:

```bash
pip install -r requirements.txt
```

### 5. Add your API key

Create a file named `.env` in the same folder as `app.py` and add:

```
GOOGLE_API_KEY=your_api_key_here
```

> Do not put quotes around the key and do not share this file with anyone.

### 6. Start the app

```bash
streamlit run app.py
```

Your browser will open automatically at **http://localhost:8501**. If it doesn't, open that link yourself.

To stop the app, press `Ctrl + C` in the terminal.

---

## How It Works

1. `load_dotenv()` reads your API key from the `.env` file.
2. The Gemini model is connected to LangChain using `chain = llm | StrOutputParser()`.
3. A **system prompt** tells the assistant how to behave.
4. Streamlit re-runs the script after every message, so the conversation is saved in `st.session_state.chat_history`.
5. When you send a message:
   - It is added to the chat history
   - The full history is sent to the model
   - The reply is shown and saved back to the history

---

## Customization

### Change the assistant's behavior

Edit the `prompt` variable in `app.py`:

```python
prompt = """
You are a helpful assistant who replies in simple english and on topic.
"""
```

### Change the icons

Edit these two lines near the top of the UI section:

```python
USER_ICON = ":material/person:"
AI_ICON = ":material/smart_toy:"
```

Browse more icons at [fonts.google.com/icons](https://fonts.google.com/icons). Use the icon name with underscores, like `account_circle`.

### Change the model

Change the `model` value in the `ChatGoogleGenerativeAI(...)` line to any Gemini model available to your API key.

### Use OpenAI instead of Gemini

1. Install the package: `pip install langchain-openai`
2. Add `OPENAI_API_KEY=your_key` to your `.env` file
3. In `app.py`, uncomment the OpenAI lines and comment out the Gemini lines

---

## Troubleshooting

| Problem | Fix |
|---------|-----|
| `ModuleNotFoundError` | Run `pip install -r requirements.txt` again, and make sure your virtual environment is active |
| API key error or empty responses | Check that `.env` is in the same folder as `app.py` and the key name is exactly `GOOGLE_API_KEY` |
| Icons are not showing | Update Streamlit: `pip install --upgrade streamlit` |
| Model not found error | The model name may be wrong or unavailable for your key. Check the available models in Google AI Studio |
| `streamlit` command not found | Try `python -m streamlit run app.py` |

---

## Security Notes

- Never upload your `.env` file to GitHub. Add it to a `.gitignore` file:
  ```
  .env
  venv/
  __pycache__/
  ```
- Never write your API key directly in the code.

---

## Ideas for Improvement

- Stream the reply word by word using `chain.stream()` and `st.write_stream()`
- Let users download the chat history
- Add a sidebar slider for model temperature
- Add file upload so the assistant can answer questions about documents
- Deploy for free on [Streamlit Community Cloud](https://streamlit.io/cloud)

---

## Author

Developed by **Abhik Chatterjee** (2026).
