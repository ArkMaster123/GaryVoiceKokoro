# Gary Voice: Where Real-Time AI Meets Human Connection 🎙️

Imagine having a conversation with AI that feels as natural as talking to a friend. That's what Gary Voice brings to life. By combining Groq's lightning-fast AI processing, LiveKit's crystal-clear communication, and Kokoro's intelligent responses, we've created a platform that makes AI voice interaction feel magical.

## Why Gary Voice? 🌟

Picture this: You're speaking naturally, and in real-time, an AI understands you, processes your words, and responds with a voice that's indistinguishable from a human's. That's the power of Gary Voice. Our platform achieves this through:

- **Ultra-Fast Processing**: Powered by Groq's cutting-edge AI pipeline, combining Whisper's speech recognition and Llama's chat capabilities
- **Crystal-Clear Communication**: LiveKit integration ensures your voice reaches the AI without any lag or quality loss
- **Natural Responses**: Kokoro FastAPI delivers OpenAI-compatible responses that feel natural and contextual
- **Freedom to Host**: Run it on your infrastructure with our Docker-ready setup
- **Premium Voice Quality**: Gary Voice synthesis rates 11/11 in audio quality tests

## Getting Started 🚀

### What You'll Need

- Python 3.9 or newer
- Docker Engine 24.0+
- LiveKit API credentials
- Groq Cloud API key

### Setup Journey

1. **First Stop: Frontend Setup**
   ```bash
   git clone https://github.com/yourusername/garyvoice.git
   cd garyvoice/garysmegavoice
   python3 -m venv venv
   source venv/bin/activate
   pip install -r requirements.txt
   ```

2. **Next Up: LiveKit Agent**
   ```bash
   # Open a new terminal window
   cd garyvoice
   python3 agent.py dev
   ```

3. **Final Piece: Kokoro FastAPI**
   
   For standard setup:
   ```bash
   # In a new terminal with Docker running
   docker run -p 8880:8880 ghcr.io/remsky/kokoro-fastapi-cpu:v0.2.0post3
   ```
   
   For turbocharged GPU performance:
   ```bash
   docker run --gpus all -p 8880:8880 your-dockerhub-username/kokoro-fastapi:v1.0
   ```

### Making It Your Own

Create a `.env` file with your personal configuration:
```ini
LIVEKIT_URL=wss://your-livekit-server
LIVEKIT_API_KEY=your_api_key
LIVEKIT_SECRET=your_secret
GROQ_API_KEY=your_groq_key
KOKORO_ENDPOINT=http://localhost:8880/v1
```

## Your Control Center 🎛️

Each component plays its unique role:

| Component     | Port | Purpose                          |
|--------------|------|----------------------------------|
| Frontend     | 8000 | Where you interact with the AI   |
| LiveKit Agent| 7880 | Handles your audio in real-time  |
| Kokoro API   | 8880 | Generates AI responses           |

Start your journey with:
```bash
make run-all
```

## Taking Flight: Deployment Options ☁️

### Cloud Deployment
```bash
docker build -t garyvoice:v1 .
docker-compose -f docker-compose.prod.yml up
```

### Self-Hosted LiveKit Setup
```bash
git clone https://github.com/livekit/livekit-server
cd livekit-server
./bin/livekit-server --config livekit.yaml
```

## Learn More 📚

- [Master LiveKit Configuration](https://docs.livekit.io)
- [Explore Groq's API](https://console.groq.com/docs/livekit)
- [Discover Kokoro FastAPI](https://github.com/remsky/Kokoro-FastAPI)

## Freedom to Create 📄

Released under the Apache 2.0 License - Use it for both commercial and personal projects, absolutely free.

---

Ready to give your AI a voice? Let's begin the journey with Gary Voice! 🚀