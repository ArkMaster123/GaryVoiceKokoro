# Gary Voice: Real-Time AI Voice Platform

A powerful voice AI platform combining LiveKit's real-time communication, Groq's AI processing, and Kokoro's text-to-speech API. Build production-ready voice agents in minutes.

## Quick Start Guide 🚀

### Prerequisites 📋
- Docker Engine 24.0+
- Python 3.9+
- Node.js & pnpm
- LiveKit Cloud account
- Groq API key

## Setup Instructions 🔧

### 1. Clone the Repository
```bash
git clone https://github.com/ArkMaster123/GaryVoiceKokoro.git
cd GaryVoiceKokoro
```

### 2. Start Kokoro TTS Server
```bash
# Run the pre-built Docker image (CPU version)
docker run -p 8880:8880 ghcr.io/remsky/kokoro-fastapi-cpu:v0.2.1

# For NVIDIA GPU support, use:
docker run --gpus all -p 8880:8880 ghcr.io/remsky/kokoro-fastapi-gpu:v0.2.1
```

### 3. Set Up LiveKit Agent
```bash
cd GaryVoiceDemo
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

Create `.env.local`:
```env
LIVEKIT_API_KEY=your_api_key
LIVEKIT_API_SECRET=your_api_secret
LIVEKIT_URL=wss://your-project.livekit.cloud
GROQ_API_KEY=your_groq_api_key
```

Start the agent:
```bash
python3 agent.py dev
```

### 4. Launch the Frontend
```bash
cd GaryVoiceFrontend
pnpm install
```

Create another `.env.local`:
```env
LIVEKIT_API_KEY=your_api_key
LIVEKIT_API_SECRET=your_api_secret
LIVEKIT_URL=wss://your-project.livekit.cloud
GROQ_API_KEY=your_groq_api_key
```

Start the frontend:
```bash
pnpm dev
```

Visit http://localhost:3000 to see your voice agent in action!

## Port Configuration 🔌
- Kokoro TTS: http://localhost:8880
- LiveKit Agent: http://localhost:7880
- Frontend: http://localhost:3000

## Need Help? 🤝
Email questions to: bornandbrand@gmail.com

## Resources 📚
- [LiveKit Cloud](https://cloud.livekit.io)
- [Groq Console](https://console.groq.com)

## Troubleshooting 🔍
- Ensure all services are running simultaneously
- Verify your API credentials
- Check port availability
- Confirm Docker is running

Would you like me to:
1. Add more detailed troubleshooting steps?
2. Include architecture diagrams?
3. Expand the setup instructions?
4. Add configuration options?