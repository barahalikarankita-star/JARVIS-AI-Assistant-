🤖 JARVIS — AI-Powered Personal Assistant
A futuristic AI-powered personal assistant with voice interaction, intelligent conversation, web search, and a JARVIS-inspired interface.
<img width="1600" height="736" alt="WhatsApp Image 2026-09-06 at 7 26 24 PM" src="https://github.com/user-attachments/assets/55e95dd2-067f-4684-97ea-c7933638268a" />

🧠 About The Project

JARVIS is a futuristic AI-powered personal assistant inspired by the intelligent assistant concept from the Iron Man universe.

The application combines modern web technologies, artificial intelligence, voice recognition, web search, text-to-speech, and real-time visual animations to create an interactive AI assistant experience.

Users can activate JARVIS using the wake word "Jarvis", speak naturally, receive AI-generated responses, search the web when current information is required, and hear responses using a natural AI-generated voice.

---

✨ Features

🟦 JARVIS Wake Word

JARVIS starts in an idle state and waits for the user to say:

«"Jarvis"»

When the wake word is detected, the assistant transitions into listening mode and responds:

«"Yes, sir?"»

🎙️ Voice Conversation

Users can interact with JARVIS using their microphone.

Voice flow:

Microphone
     ↓
Speech Recognition
     ↓
Text
     ↓
Backend
     ↓
GPT-4o mini
     ↓
Response
     ↓
ElevenLabs
     ↓
Audio
     ↓
JARVIS Voice

---

🧠 AI Conversation

JARVIS uses GPT-4o mini for conversation and reasoning.

The AI receives:

* System instructions
* Conversation history
* User questions
* Web search results when required

JARVIS is designed to maintain a personality that is:

* Intelligent
* Calm
* Concise
* Confident
* Helpful
* Futuristic

---

🔎 Web Search

JARVIS can determine when current information is required.

For example:

"Who is the current president of the United States?"

JARVIS can perform a web search.

Another example:

"What is the latest news about Apple?"

JARVIS can retrieve current information through SearchAPI.

For simple questions such as:

"What is 2 + 2?"

No web search is required.

Search Flow

User Question
      ↓
GPT-4o mini
      ↓
Does the question require current information?
      ↓
   ┌───────────────┐
   │               │
   │      YES      │──────→ SearchAPI
   │               │             ↓
   └───────────────┘       Search Results
                                  ↓
                            GPT-4o mini
                                  ↓
                            Final Answer

The interface displays:

«🔎 Searching the web...»

while the search is being performed.

---

🔊 ElevenLabs Voice

JARVIS uses ElevenLabs Text-to-Speech to generate natural voice responses.

GPT-4o mini
     ↓
Response Text
     ↓
ElevenLabs
     ↓
Generated Audio
     ↓
Browser Playback

While JARVIS is speaking, the central visualizer reacts to the generated audio.

---

🎨 Futuristic Sci-Fi Interface

The interface is designed as a futuristic AI command center.

The central JARVIS core provides visual feedback based on the assistant's current state.

Interface States

State| Visual Behavior
🟦 Idle| Slow glowing core
⚡ Wake Detected| Quick bright pulse
🎙️ Listening| Active waveform
🧠 Processing| Rotating core
🔎 Searching| Search/radar animation
🔊 Speaking| Audio-reactive animation
🔴 Error| Red warning glow

---

🧩 JARVIS State Machine

IDLE
  ↓
"Jarvis" detected
  ↓
WAKE_DETECTED
  ↓
LISTENING
  ↓
Speech → Text
  ↓
PROCESSING
  ↓
SEARCHING (if required)
  ↓
PROCESSING
  ↓
SPEAKING
  ↓
IDLE

The application uses the following states:

type JarvisState =
  | "idle"
  | "wake_detected"
  | "listening"
  | "processing"
  | "searching"
  | "speaking"
  | "error";

---

🚀 User Flow

1. User opens JARVIS
          ↓
2. Futuristic interface appears
          ↓
3. User grants microphone permission
          ↓
4. JARVIS enters IDLE state
          ↓
5. User says "Jarvis"
          ↓
6. Wake word is detected
          ↓
7. JARVIS responds "Yes, sir?"
          ↓
8. Microphone captures the question
          ↓
9. Speech is converted into text
          ↓
10. Question is sent to backend
          ↓
11. GPT-4o mini determines whether search is required
          ↓
12. SearchAPI retrieves current information if required
          ↓
13. GPT-4o mini generates the final response
          ↓
14. ElevenLabs converts response to speech
          ↓
15. JARVIS speaks the answer
          ↓
16. Interface returns to listening/idle mode

---

🛠️ Tech Stack

Frontend

* React
* TypeScript
* Vite
* Tailwind CSS
* Framer Motion
* Web Audio API
* Browser Speech Recognition API

Backend

* Node.js
* Express.js
* REST APIs

Artificial Intelligence

* OpenAI GPT-4o mini — conversation and reasoning
* SearchAPI — Google/web search and current information
* ElevenLabs — natural voice generation
* Browser Speech Recognition API — voice input

---

🏗️ Architecture

                    ┌─────────────────────┐
                    │       USER          │
                    │  Voice / Text Input │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │      React UI       │
                    │   TypeScript/Vite   │
                    └──────────┬──────────┘
                               │
                  ┌────────────┴────────────┐
                  │                         │
                  ▼                         ▼
        Speech Recognition            REST API
                  │                         │
                  └────────────┬────────────┘
                               ▼
                    ┌─────────────────────┐
                    │   Node.js + Express  │
                    │       Backend        │
                    └──────────┬──────────┘
                               │
              ┌────────────────┼─────────────────┐
              │                │                 │
              ▼                ▼                 ▼
        ┌───────────┐   ┌────────────┐   ┌─────────────┐
        │  OpenAI   │   │  SearchAPI │   │ ElevenLabs  │
        │ GPT-4o    │   │ Web Search │   │    TTS      │
        │   mini    │   │            │   │             │
        └─────┬─────┘   └──────┬─────┘   └──────┬──────┘
              │                │                 │
              └────────────────┼─────────────────┘
                               ▼
                    ┌─────────────────────┐
                    │    JARVIS Response  │
                    │ Text + Voice + UI   │
                    └─────────────────────┘

---

📁 Project Structure

jarvis/
│
├── client/
│   ├── src/
│   │   ├── components/
│   │   │   ├── JarvisCore.tsx
│   │   │   ├── VoiceVisualizer.tsx
│   │   │   ├── ChatPanel.tsx
│   │   │   ├── SearchResults.tsx
│   │   │   └── StatusIndicator.tsx
│   │   │
│   │   ├── hooks/
│   │   │   ├── useSpeechRecognition.ts
│   │   │   └── useJarvis.ts
│   │   │
│   │   ├── services/
│   │   │   └── api.ts
│   │   │
│   │   ├── App.tsx
│   │   └── main.tsx
│   │
│   └── index.html
│
├── server/
│   ├── routes/
│   │   ├── chat.ts
│   │   ├── search.ts
│   │   └── voice.ts
│   │
│   ├── services/
│   │   ├── openai.ts
│   │   ├── searchapi.ts
│   │   └── elevenlabs.ts
│   │
│   └── server.ts
│
├── .env
├── .env.example
├── .gitignore
├── package.json
└── README.md

---

⚙️ Installation

Prerequisites

Before running JARVIS, make sure you have:

* Node.js installed
* npm installed
* A modern web browser
* Microphone access
* OpenAI API key
* SearchAPI API key
* ElevenLabs API key

---

1. Clone the Repository

git clone <img width="1600" height="736" alt="WhatsApp Image 2026-09-06 at 7 26 24 PM" src="https://github.com/user-attachments/assets/55e95dd2-067f-4684-97ea-c7933638268a" />

https://github.com/barahalikarankita-star/JARVIS-AI-Assistant.git

Navigate into the project:

cd JARVIS-AI-Assistant

---

📦 2. Install Dependencies

Install the project dependencies:

npm install

If frontend and backend have separate package files, install dependencies inside each directory:

cd client
npm install

Then:

cd ../server
npm install

---

🔑 3. Configure Environment Variables

Create a ".env" file in the backend/server environment.

OPENAI_API_KEY=your_openai_api_key
SEARCHAPI_KEY=your_searchapi_api_key
ELEVENLABS_API_KEY=your_elevenlabs_api_key
ELEVENLABS_VOICE_ID=your_elevenlabs_voice_id

⚠️ IMPORTANT

Never upload your real API keys to GitHub.

Your ".env" file should be included in ".gitignore".

Example:

.env
node_modules/
dist/
build/
*.log

Instead, create ".env.example":

OPENAI_API_KEY=
SEARCHAPI_KEY=
ELEVENLABS_API_KEY=
ELEVENLABS_VOICE_ID=

Other developers can copy ".env.example" to ".env" and enter their own API keys.

---

▶️ Running the Project

Start the backend:

cd server
npm run dev

Start the frontend in another terminal:

cd client
npm run dev

Open the local URL displayed by Vite in your browser.

---

🎙️ Voice Usage

When JARVIS loads:

1. Allow microphone permission.
2. Wait for the assistant to enter IDLE mode.
3. Say:

Jarvis

4. JARVIS responds:

Yes, sir?

5. Ask your question.
6. JARVIS converts your speech into text.
7. The backend processes your request.
8. GPT-4o mini generates the response.
9. SearchAPI is used when current information is required.
10. ElevenLabs generates the voice response.
11. JARVIS speaks the answer.

---

💬 Text Chat Fallback

If voice interaction is unavailable, users can use the text chat interface.

Example:

User:
Explain artificial intelligence.

JARVIS:
Artificial Intelligence is the field of computer science
focused on creating systems capable of performing tasks
that normally require human intelligence.

---

📸 Screenshots

Add your screenshots inside:

assets/
└── screenshots/
    ├── jarvis-home.png
    ├── jarvis-listening.png
    ├── jarvis-processing.png
    ├── jarvis-searching.png
    └── jarvis-speaking.png

Then add them to this README.

JARVIS Interface




🔌 API Integration

OpenAI

Purpose: AI conversation and reasoning.

User Question
      ↓
Backend
      ↓
GPT-4o mini
      ↓
AI Response

---

SearchAPI

Purpose: Web search and current information.

Question
    ↓
SearchAPI
    ↓
Search Results
    ↓
GPT-4o mini
    ↓
Final Answer

---

ElevenLabs

Purpose: Text-to-Speech.

GPT Response
     ↓
ElevenLabs
     ↓
Audio
     ↓
Browser
     ↓
JARVIS Voice

---

Browser Speech Recognition

Purpose: Convert the user's microphone speech into text.

Microphone
     ↓
Browser Speech Recognition
     ↓
Text
     ↓
JARVIS

---

🎨 UI Design

The interface follows a futuristic AI command-center aesthetic.

Color Palette

Background:  #02060A
Primary:     #00E5FF
Secondary:   #0077FF
Text:        #D8F7FF
Error:       Red
Success:     Green

Animation System

Animations are implemented using:

* Framer Motion
* Web Audio API
* CSS animations
* Reactive visual states

The central JARVIS core changes its animation according to the assistant's current state.

---

🧠 Core State System

type JarvisState =
  | "idle"
  | "wake_detected"
  | "listening"
  | "processing"
  | "searching"
  | "speaking"
  | "error";

State Behavior

IDLE
→ Slow glowing core

WAKE_DETECTED
→ Bright pulse

LISTENING
→ Active waveform

PROCESSING
→ Rotating core

SEARCHING
→ Radar/search animation

SPEAKING
→ Audio-reactive animation

ERROR
→ Red warning glow

---

🛡️ Security

API keys are kept on the backend and should never be exposed in frontend code.

Never commit:

.env
API keys
Private credentials
Access tokens
Secret configuration

Use environment variables instead.

---

🚧 Current MVP

The MVP focuses on:

* Futuristic JARVIS interface
* Animated central core
* Microphone permission
* Wake-word activation
* Voice-to-text
* GPT-4o mini conversation
* Conversation history
* SearchAPI integration
* Current web information
* ElevenLabs voice output
* Audio-reactive speaking animation
* Listening animation
* Processing animation
* Searching animation
* Error handling
* Text chat fallback

---

🔮 Future Improvements

Possible future features include:

* 📱 Mobile application
* 🏠 Smart-home control
* 📧 Email automation
* 📱 Message automation
* 📞 Call assistance
* 📅 Calendar integration
* ⏰ Reminders
* 📂 Advanced file management
* 🧠 Long-term personalized memory
* 🌍 Multilingual voice support
* 👤 User authentication
* 🔐 Advanced security
* 🤖 Multi-agent task automation
* 🖥️ Desktop application
* ⚡ More system-level automation

---

🎯 Learning Outcomes

This project provides practical experience in:

* Artificial Intelligence
* Generative AI
* Natural Language Processing
* Voice AI
* Speech Recognition
* Text-to-Speech
* REST API development
* React development
* TypeScript
* Node.js
* Express.js
* API integration
* Web automation concepts
* Real-time UI animation
* Audio visualization
* Environment variable management

---

🌟 Why JARVIS?

JARVIS demonstrates how multiple modern technologies can be combined to create a practical AI assistant.

Instead of simply generating text, the system combines:

AI
+
Voice
+
Web Search
+
Automation
+
Real-Time UI
+
Audio Visualization
=
Interactive AI Assistant

---

👩‍💻 Author

Ankita Barahalikar

Artificial Intelligence & Machine Learning Student

Passionate about building real-world AI/ML projects, intelligent assistants, automation systems, and innovative technology solutions.

---

⭐ Support

If you find this project interesting, consider giving the repository a ⭐ on GitHub.

---

📄 License

This project is created for educational and development purposes.

If you plan to distribute the project publicly, consider adding an appropriate open-source license such as the MIT License.

---

<p align="center">
  Built with ❤️ and AI by <strong>Ankita Barahalikar</strong>
</p>
