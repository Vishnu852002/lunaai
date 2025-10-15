# LUNA - Vision-Powered AI Assistant

Modern AI assistant that sees your screen using Gemma vision model! Like the classic Clippy, but actually intelligent and powered by local AI.
NOTE: WILL ADD THE FILE ONCE I COMPLETE IT. STILL WORK-IN-PROGRESS!

🌟 Features

- 👁️ Vision AI - Uses Gemma3:4B vision model to SEE and understand your screen
- 🎭 Multiple Personalities - Helpful, Witty, Professional, Friendly
- 💾 Memory - Remembers past observations and learns from your usage
- 🎨 Beautiful WPF UI - Modern Windows interface with smooth animations
- 🔒 100% Local & Private - All processing happens on your machine
- ⚙️ Customizable - Adjust intervals, personality, and more

📋 Requirements
For Python Backend:

- Python 3.8+
- Ollama installed and running
- Windows 10/11

For WPF Frontend:

- .NET 6.0 SDK or later
- Visual Studio Code with C# extension
- Windows 10/11

🚀 Setup Instructions
Step 1: Install Ollama & Model
bash# Install Ollama from https://ollama.ai

# Pull the vision model (IMPORTANT: Use gemma3:4b which has vision support)
ollama pull gemma3:4b
Step 2: Setup Python Backend
bash# Navigate to backend directory
cd backend

# Install dependencies
pip install -r requirements.txt

# Start the backend
python backend.py
You should see:
✅ Ollama connected successfully
🌐 Starting Flask server on http://localhost:5000
Step 3: Setup WPF Frontend
bash# Navigate to frontend directory
cd Luna

# Restore NuGet packages
dotnet restore

# Build the project
dotnet build

# Run the application
dotnet run

1. Start Backend - Run python backend.py (must be running first!)
2. Start Frontend - Run the WPF app with dotnet run
3. Click "START VISION AI" - AI begins monitoring your screen
4. Work normally - AI observes and provides insights
5. Change personality - Select different AI personalities from dropdown
6. Adjust interval - Change how often screenshots are taken
7. View history - Click "View History" to see past observations

⚙️ Configuration
Python Backend Settings (backend.py)
```python
# Core settings
SCREENSHOT_INTERVAL = 20        # How often to capture screen (seconds)
MIN_RESPONSE_INTERVAL = 25      # Minimum time between AI responses
SCREENSHOT_QUALITY = 60         # JPEG quality (1-100)
MAX_IMAGE_SIZE = (1280, 720)    # Resize screenshots for faster processing
TEMPERATURE = 0.8               # AI creativity (0.0-1.0)
```

WPF Frontend Settings

Adjust screenshot interval in the UI
Change personality from dropdown
All settings sync with backend automatically

🎭 Personalities

Helpful - Focused on providing useful suggestions
Witty - Clever and occasionally funny
Professional - Concise and business-focused
Friendly - Warm and encouraging

🔧 Troubleshooting
Backend won't start
bash# Check if Ollama is running
ollama list

# Verify model is installed
ollama pull gemma2:2b

# Check port 5000 is free
netstat -ano | findstr :5000

WPF app can't connect

- Ensure backend is running on http://localhost:5000
- Check firewall settings
- Verify Python backend shows "Flask server running"

AI responses are slow

- Reduce screenshot interval (increase seconds)
- Lower SCREENSHOT_QUALITY in backend.py
- Use smaller MAX_IMAGE_SIZE

Screenshots not saving

- Check if screenshots/ directory exists
- Verify write permissions
- Check disk space

📊 API Endpoints
The Python backend exposes these REST endpoints:

- GET /health - Check backend status
- POST /analyze - Analyze current screen
- POST /auto-monitor/start - Start automatic monitoring
- POST /auto-monitor/stop - Stop monitoring
- POST /personality - Change AI personality
- GET /history - Get observation history
- GET /config - Get current configuration
- POST /config - Update configuration

🔐 Privacy & Security

- 100% Local - No data leaves your machine (fully offline)
- No Cloud APIs - Everything runs via Ollama locally
- Screenshots stored locally - In screenshots/ folder
- Database is local - SQLite file on your machine
- You control everything - Delete data anytime

📝 License
MIT License - Feel free to modify and distribute!

🤝 Contributing
Pull requests welcome! This is a learning project, so all improvements are appreciated.

⚠️ Known Limitations
- Only works on Windows (WPF is Windows-only)
- Requires decent GPU/CPU for vision processing
- Screenshot interval minimum ~15 seconds for performance
- Gemma3:4B vision is good but not perfect (Please use better models ONLY IF YOU HAVE THE HARDWARE.)

🎉 Credits

- Built with ❤️ using Ollama and Gemma
- Inspired by the classic Microsoft Clippy
- Modern UI inspired by Windows 11 design language

📞 Support
If you encounter issues:
1. Check the logs (backend.log)
2. Verify all requirements are installed
3. Ensure Ollama is running with ollama list
4. Check that port 5000 is available



Check the logs (backend.log)
- Verify all requirements are installed
- Ensure Ollama is running with ollama list
- Check that port 5000 is available


Enjoy your AI-powered assistant! 📎✨
