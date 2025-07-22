# FastAPI NLP Chatbot

An intelligent chatbot for customer support and FAQs using FastAPI, spaCy (NLP), and SQLite for logging user interactions.

## Features
- Contextual responses to user questions using NLP (spaCy)
- FAQ matching (easily extendable)
- User interaction logging in SQLite database
- REST API for chat interaction

## Setup Instructions

1. Clone the repository and navigate to the project directory**

2. Create and activate a virtual environment
   ```sh
   python -m venv venv
   venv\Scripts\activate  # On Windows
   # source venv/bin/activate  # On Linux/Mac
   ```

3. Install dependencies
   ```sh
   pip install -r requirements.txt
   ```

4. Download the spaCy English model
   ```sh
   python -m spacy download en_core_web_sm
   ```

5. Run the FastAPI server
   ```sh
   uvicorn main:app --reload
   ```

6. Test the API
   - Open your browser at [http://127.0.0.1:8000/docs](http://127.0.0.1:8000/docs)
   - Use the `/chat` endpoint to interact with the chatbot.

## Example Chat Request
```
POST /chat
{
  "user_id": "user123",
  "message": "How can I reset my password?"
}
```

## Extending the Bot
- Add more FAQs in `nlp.py` under the `FAQS` dictionary.
- For advanced NLP, integrate with OpenAI GPT or similar APIs.

## Viewing Logs
- All user interactions are stored in `chatbot.db` (SQLite).
- Use a tool like [DB Browser for SQLite](https://sqlitebrowser.org/) to view logs.

## Deployment
- For production, run with:
  ```sh
  uvicorn main:app --host 0.0.0.0 --port 80
  ```
- Consider using a process manager (e.g., systemd, supervisor) or deploying to a cloud service.

---

Feel free to ask for help with frontend integration, log viewing endpoints, or advanced features!
