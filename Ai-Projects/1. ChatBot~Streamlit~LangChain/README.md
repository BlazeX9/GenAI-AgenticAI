# AI Chat Assistant

A simple, beginner-friendly chatbot built with **Streamlit** and **LangChain**, powered by **Google Gemini**.

---

## Project Structure

```
project/
├── main.py             # Main Streamlit app
├── .env                # Secret API key
├── requirements.txt    # Python packages needed
└── README.md           # This file
```

---

## To Run on Local Machine

### 1. Prerequisites

- Python 3.10 or newer installed. Check with:
- 
  ```bash
  python --version
  ```
- A Google Gemini API key. You can get one for free from [Google AI Studio](https://aistudio.google.com/app/apikey).

### 2. Get the project

Put `main.py` in a new folder, or clone the repository:

```bash
git clone <repo-url>
cd <project-folder>
```

### 3. Create a virtual environment

```bash
python -m venv venv
venv\Scripts\activate
```

### 4. Install the packages

```bash
pip install -r requirements.txt
```

### 5. Add API key

Create a file named `.env` in the same folder:

```
GOOGLE_API_KEY=your_api_key_here
```

### 6. Start the app

```bash
streamlit run main.py
```
