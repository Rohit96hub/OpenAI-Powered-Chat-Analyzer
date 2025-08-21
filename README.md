AI-Powered Chat Analyzer
This project is a simple yet powerful web application built with Gradio and Python that allows you to analyze and ask questions about your personal chat histories from services like WhatsApp and Telegram.

Instead of relying on fragile parsing methods, this app uses a modern Retrieval-Augmented Generation (RAG) pipeline powered by OpenAI's gpt-3.5-turbo. This means it can understand the content of almost any exported .txt chat file, regardless of its specific format, and provide intelligent, context-aware answers to your questions.

✨ Features
Universal Chat Support: Works with .txt exports from WhatsApp, Telegram, and other chat services. No need to worry about date/time formats.

Intelligent Analysis: Leverages a RAG pipeline to find the most relevant information in your chat history to answer your questions accurately.

Simple & Intuitive UI: A clean, multi-page web interface built with Gradio that guides you from setup to chat.

User-Friendly: Designed for learning, with heavily commented code that is easy to understand and modify.

Private & Secure: Your API key and chat files are processed in the session and not stored.

🚀 How It Works
The application uses a RAG pipeline to provide answers. Here’s a simple breakdown of the process:

Load & Chunk: When you upload your chat file, the app reads the text and splits it into small, overlapping chunks.

Embed & Index: Each chunk is converted into a numerical vector (an "embedding") using an OpenAI model. These vectors are then stored in a high-speed search index (FAISS).

Retrieve: When you ask a question, the app converts your question into a vector and uses the index to find the most semantically similar chunks from your chat history.

Generate: These relevant chunks are passed to the gpt-3.5-turbo model along with your original question. The model then generates a final answer based only on the context it was given.

🛠️ Setup and Usage
Follow these steps to get the application running on your local machine.

1. Prerequisites
Python 3.8 or higher

An active OpenAI API Key. You can get one from the OpenAI Platform.

2. Clone the Repository
First, clone the project repository to your local machine:

git clone [https://github.com/cloudyuga/mastering-genai-w-python.git](https://github.com/cloudyuga/mastering-genai-w-python.git)
cd mastering-genai-w-python/Module-07-Prompt-Engineering

3. Install Dependencies
The application's dependencies are listed in the Python script. You can install them all with a single command:

pip install -q gradio openai langchain langchain-community langchain-openai langchain_text_splitters faiss-cpu

4. Export Your Chat History
You need a .txt file of a chat conversation. See the detailed instructions below on how to export your chat history from WhatsApp or Telegram.

5. Run the Application
Execute the Python script from your terminal:

python your_script_name.py

The application will start, and you will see a local URL (like http://127.0.0.1:7860) in the terminal. Open this URL in your web browser to use the app.

📲 How to Export Your Chat History
WhatsApp
On Android:
Open the individual or group chat you want to export.

Tap the three-dot menu (⋮) in the top-right corner.

Select More > Export chat.

Choose Without media. This is important as the app only processes text.

Save the .txt file to your device or share it to your computer (e.g., via email or Google Drive).

On iOS (iPhone):
Open the individual or group chat you want to export.

Tap on the contact or group name at the top of the screen.

Scroll down and tap on Export Chat.

Choose Without Media.

Select how you want to save or send the .txt file (e.g., save to Files, AirDrop, or email it to yourself).

Telegram
On Telegram Desktop (Recommended):
Open the individual chat, group, or channel you want to export.

Click the three-dot menu (⋮) in the top-right corner.

Select Export chat history.

In the pop-up window, deselect all media types (Photos, Videos, etc.) to ensure you only get a text file.

Set the format to Human-readable (.html). Note: You may need to open the HTML file and copy-paste the text into a .txt file.

Click Export and choose a location to save the file.

💻 Technology Stack
Backend: Python

Web UI: Gradio

AI & NLP: OpenAI, LangChain

Vector Search: FAISS
