# Gary Voice: Real-Time AI Voice Platform

A powerful voice AI platform that combines LiveKit's real-time communication, Groq's AI processing, and Kokoro's OpenAI-compatible API. This project consists of three main components that work together to create a seamless voice AI experience.

## Project Structure 📁

```
.
├── GaryVoiceDemo/          # LiveKit Cloud integration & Groq agent
├── Kokoro-FastAPI/         # OpenAI-compatible API server
└── GaryVoiceFrontend/     # Next.js frontend for LiveKit demo
```

## Quick Start Guide 🚀

You'll need to run three separate instances:
1. Kokoro FastAPI server
2. LiveKit agent
3. Frontend demo

### Prerequisites 📋

- Docker Engine 24.0+
- Python 3.9+
- Node.js & pnpm
- LiveKit Cloud account
- Groq API key

## Component Setup Instructions 🔧

### 1. Kokoro FastAPI Server

Choose one of these options:

**Option A: Using Pre-built Docker Image (Recommended)**
```bash
# For CPU
docker run -p 8880:8880 ghcr.io/remsky/kokoro-fastapi-cpu:v0.2.1

# For NVIDIA GPU
docker run --gpus all -p 8880:8880 ghcr.io/remsky/kokoro-fastapi-gpu:v0.2.1
```

**Option B: Building Locally**
```bash
cd Kokoro-FastAPI/docker/cpu
docker compose up --build
```

### 2. LiveKit Agent Setup

Navigate to the GaryVoiceDemo directory:
```bash
cd GaryVoiceDemo
python3 -m venv venv
source venv/bin/activate
python3 -m pip install -r requirements.txt
python3 agent.py dev
```

Required environment variables (`.env.local`):
```ini
LIVEKIT_API_KEY=<your_api_key>
LIVEKIT_API_SECRET=<your_api_secret>
LIVEKIT_URL=wss://<project-subdomain>.livekit.cloud
```

### 3. Frontend Setup

Navigate to the GaryVoiceFrontend directory:
```bash
cd GaryVoiceFrontend
pnpm install
pnpm dev
```

Access the demo at: http://localhost:3000

## Environment Setup 🔐

### LiveKit Cloud Setup
1. Sign up for LiveKit Cloud
2. Create a new project
3. Copy your API credentials
4. Set up your environment variables as shown above

## Ports Used 🔌

| Component        | Port | URL                      |
|-----------------|------|--------------------------|
| Kokoro FastAPI  | 8880 | http://localhost:8880    |
| LiveKit Agent   | 7880 | http://localhost:7880    |
| Frontend        | 3000 | http://localhost:3000    |

## Troubleshooting 🔍

- Ensure all three components are running simultaneously
- Verify your LiveKit Cloud credentials are correct
- Check that ports 8880, 7880, and 3000 are available
- Make sure Docker is running for Kokoro FastAPI

## Additional Resources 📚

- [LiveKit Cloud Dashboard](https://cloud.livekit.io)
- [Kokoro FastAPI Documentation](https://github.com/remsky/Kokoro-FastAPI)
- [Groq API Documentation](https://console.groq.com/docs)

## License 📄

This project is licensed under the Apache 2.0 License - see the LICENSE file for details.

---

Need help? Open an issue in the respective repository for specific component-related questions.

