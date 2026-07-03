# RileyJarvis Windows 11

A native Windows 11 desktop application version of RileyJarvis - an AI companion with realtime voice, powered by OpenAI Realtime API.

## Requirements

- Windows 11 (Build 22621 or later)
- .NET 8.0 SDK
- Visual Studio 2022 or Visual Studio Code with C# extension
- An OpenAI API key with Realtime and image generation access
- Optional: Exa API key for web search

## Quick Start

1. **Clone the repository**
   ```bash
   git clone https://github.com/YOUR_USERNAME/rileyjarvis.git
   cd rileyjarvis/RileyJarvis.Win11
   ```

2. **Set up environment variables**
   ```bash
   cp .env.example .env
   ```
   Edit `.env` and add your API keys:
   ```
   OPENAI_API_KEY=your_openai_api_key_here
   EXA_API_KEY=your_exa_api_key_here
   ```

3. **Install dependencies and build**
   ```bash
   dotnet restore
   dotnet build
   ```

4. **Run the application**
   ```bash
   dotnet run
   ```

## Development

### Using Visual Studio 2022
1. Open `RileyJarvis.Win11.csproj` in Visual Studio 2022
2. Restore NuGet packages (automatic on open)
3. Press `F5` to run with debugging

### Using Visual Studio Code
1. Open the project folder
2. The C# extension will prompt to install dependencies
3. Press `F5` to debug or run `dotnet run`

### Build for release
```bash
dotnet publish -c Release -r win-x64 --self-contained
```

## Features

- ✅ Realtime speech-to-speech conversation with OpenAI API
- ✅ Windows 11 native UI with WinUI 3
- ✅ Live transcript display
- 🚧 Voice settings configuration
- 🚧 Microphone selection
- 🚧 Model selection (GPT-4, GPT-4 Turbo, etc.)
- 📋 Future: Web search integration
- 📋 Future: Notes management
- 📋 Future: Image generation

## Project Structure

```
RileyJarvis.Win11/
├── Views/
│   ├── MainWindow.xaml          # Main UI
│   ├── MainWindow.xaml.cs       # Main logic
│   ├── SettingsPanel.xaml       # Settings UI
│   └── SettingsPanel.xaml.cs    # Settings logic
├── Services/
│   ├── OpenAIService.cs         # OpenAI API integration
│   └── SpeechService.cs         # Speech recognition & synthesis
├── App.xaml                      # Application resources
├── App.xaml.cs                   # Application startup
├── Program.cs                    # Entry point
└── RileyJarvis.Win11.csproj     # Project configuration
```

## Windows Permissions

The application requires the following permissions:

- **Microphone**: For voice input
- **Audio**: For voice output

Windows will prompt for these permissions on first use.

## Security Notes

- API keys are loaded from the local `.env` file only
- `.env` and all `.env.*` files are ignored by Git except `.env.example`
- Never commit your `.env.local` file with real API keys

## Troubleshooting

### "OPENAI_API_KEY not set"
Make sure your `.env` file exists in the application directory and contains:
```
OPENAI_API_KEY=your_key_here
```

### Speech recognition not working
- Ensure microphone permissions are granted
- Check microphone is properly connected and functional
- Verify language is set to English (US) in Windows settings

### Cannot connect to OpenAI API
- Verify your API key is correct and active
- Check your internet connection
- Ensure your OpenAI account has API access enabled

## License

MIT - Same as the original RileyJarvis project
