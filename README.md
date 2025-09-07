# Interactive Resume (AI-powered)

## Overview
This project is an AI-powered interactive resume web app. It allows users to chat with a virtual assistant representing your professional background, skills, and experience. The assistant answers questions based on your linkedin profile and summary, and can record user interest or unanswered questions using Pushover notifications.

## Features
- **AI Chatbot**: Users interact with a chatbot that answers questions about your career, skills, and experience.
- **Linkedin Profile & Summary Integration**: The assistant uses your linkedin profile (`linkedin.pdf`) and summary (`summary.txt`) for context.
- **Pushover Notifications**: Records user interest (email/name/notes) and logs unknown questions via Pushover API.
- **Gradio Web Interface**: Clean, interactive UI for chatting with the assistant.

## Setup Instructions

### 1. Clone the Repository
Clone this project to your local machine.

### 2. Install Python & [uv](https://github.com/charliermarsh/uv)
- Ensure you have Python 3.8+ installed.
- Install `uv` (a fast Python package manager):
  ```cmd
  pip install uv
  ```

### 3. Install Requirements
Install all dependencies using `uv`:
```cmd
uv pip install -r requirements.txt
```

### 4. API Keys & Environment Variables
Create a `.env` file in the project root with the following keys:
```
OPENAI_API_KEY=your_openai_key 
GROQ_API_KEY=your_groq_key
PUSHOVER_TOKEN=your_pushover_app_token
PUSHOVER_USER=your_pushover_user_key
```

The OPENAI key is optional—add it if you want to use OpenAI models for higher-quality responses. By default, Groq (free) is used and provides good results.
- Get your OpenAI key from [platform.openai.com](https://platform.openai.com/).
- Get your Groq key from [groq.com](https://groq.com/).

**Pushover notifications are optional.**
To enable notifications:
1. Create a free account at https://pushover.net/.
2. Create an application to get your token and user key.
3. Add `PUSHOVER_TOKEN` and `PUSHOVER_USER` to your `.env` file.
4. If you do not want notifications, simply comment out the `push()` function and its calls in `app.py`.

### 5. Personalize Your Information
- Replace `me/linkedin.pdf` with your own linkedin profile in PDF format. You can download it from linkedin Resources option under your profile.
- Replace `me/summary.txt` with your own professional and personal summary, completely upto you.
- Update your LinkedIn profile link and any other personal details in the summary as needed.

### 6. Run the App
Start the interactive resume web app:
```cmd
uv run app.py
```
The Gradio interface will launch in your browser.

## Customization
- **LinkedIn/Profile**: Update your LinkedIn or other profile links in `me/summary.txt`.
- **Assistant Name**: Change the name in the `Me` class in `app.py`.
- **Notification Logic**: Modify the `push` function in `app.py` to customize notifications.

## Folder Structure
```
app.py                # Main application
requirements.txt      # Python dependencies
me/
  linkedin.pdf        # Your linkedin profile (PDF)
  summary.txt         # Your professional summary
```
