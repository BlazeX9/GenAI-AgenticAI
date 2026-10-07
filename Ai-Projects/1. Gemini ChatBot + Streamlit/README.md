# AI Chat Assistant

A simple, beginner-friendly chatbot built with **Streamlit** and **LangChain**, powered by **Google Gemini**.

## Project Structure

```
project/
├── main.py             # Main Streamlit app
├── .env                # API key
├── requirements.txt    # Python packages needed
└── README.md           # This file
```

---

## How to Run on Your Local Machine

### 1. Prerequisites

- Python 3.10 or newer installed. Check with:
   
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

```bash
python -m venv venv
venv\Scripts\activate
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

---

## Author

Developed by **Abhik Chatterjee** (2026).
