# Inside Inside Out

> A real-time voice AI console where five emotions talk, debate, and interrupt each other

<img src="frontend/public/hero-characters.png" width="70%" alt="Inside Inside Out Banner">

## What is this?

**Inside Inside Out** is a voice-first AI console built for the **AI Accelerate: Unlocking New Frontiers** challenge (Google Cloud + ElevenLabs).

Inspired by Pixar's *Inside Out*, this project lets you talk to five AI personalities (Joy, Sadness, Anger, Fear, and Disgust) who don't just respond to you. They debate with each other, interrupt, and react in real-time, creating genuinely dynamic conversations.

## How it works

We use a "think slow, act fast" approach:

**The Brain** → **Gemini 2.5 Flash Lite** analyzes your input and decides which emotion should respond and what they should say.

**The Voice** → **ElevenLabs Turbo v2.5** streams the speech back with ultra-low latency, so conversations feel natural and immediate.

**The Interface** → A React app with real-time audio visualization and smooth WebSocket streaming.

<img src="frontend/public/architecture.png" width="80%" alt="System Architecture">

## Tech Stack

### AI & Intelligence
- **Google Gemini 2.5 Flash Lite** (via Vertex AI): Handles emotional reasoning and dialogue generation
- Fast enough for real-time responses, smart enough for personality consistency

### Voice Synthesis
- **ElevenLabs Turbo v2.5**: Converts text to speech with minimal latency
- Each emotion has a distinct voice with expressive capabilities (sighs, shouts, whispers)

### Frontend
- **React + Vite**: Fast dev experience and smooth UI
- **Framer Motion**: Polished animations
- **WebSocket streaming**: Real-time audio playback

### Backend
- **FastAPI**: Handles routing and orchestration
- **Streaming architecture**: Audio chunks flow continuously from ElevenLabs to the browser

## Features

### War Room (Call Mode)
Have a continuous voice conversation with all five emotions. They'll debate your life choices, argue with each other, and interrupt when they feel strongly about something.

### Fun Mode
Give the emotions a scenario (like "It's Monday tomorrow") and watch them perform a scripted comedy skit. The Brain writes the dialogue on the fly, and all five emotions act it out.

### Judge Mode
For demos and hackathons. Just paste your API keys (Gemini + ElevenLabs) in the UI, and the system reconfigures itself instantly - no backend setup needed.

## Getting Started

### Prerequisites
- Python 3.10+
- Node.js 18+
- Gemini API Key (Google Cloud)
- ElevenLabs API Key

### Quick Start

1. **Clone and navigate**
   ```bash
   git clone https://github.com/PratikCreates/Inside-Inside-Out.git
   cd Inside-Inside-Out
   ```

2. **Add your API keys**
   ```bash
   # Copy the example file
   cp .env.example .env
   
   # Edit .env and add:
   # GEMINI_API_KEY=your_key_here
   # ELEVENLABS_API_KEY=your_key_here
   ```

3. **Install dependencies**
   ```bash
   cd backend && pip install -r requirements.txt && cd ..
   cd frontend && npm install && cd ..
   ```

4. **Launch the app**
   
   **Windows (Recommended):**
   ```powershell
   .\run_app.bat
   ```
   
   **Or manually** (any platform):
   ```bash
   # Terminal 1 - Backend
   cd backend && uvicorn main:app --reload
   
   # Terminal 2 - Frontend
   cd frontend && npm run dev
   ```

5. **Open** [http://localhost:5173](http://localhost:5173) 🎉

## Troubleshooting

<details>
<summary><b>PowerShell: "run_app.bat is not recognized"</b></summary>

PowerShell requires `.\` prefix for local scripts:
```powershell
.\run_app.bat
```
</details>

<details>
<summary><b>Port already in use</b></summary>

Kill the process using the port:
```bash
npx kill-port 8000 5173
```
</details>

<details>
<summary><b>Missing dependencies</b></summary>

Make sure you ran the install commands:
```bash
cd backend && pip install -r requirements.txt
cd frontend && npm install
```
</details>


## Contributing

Pull requests are welcome. Some ideas: add new emotions, optimize audio streaming, or improve the orchestration logic.

---

*Built for the AI Accelerate hackathon*
