# VON TILTS GOY BOX

**Real-time voice translation and dubbing application** with custom voice cloning using F5-TTS.

![Python](https://img.shields.io/badge/python-3.10+-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)
![Platform](https://img.shields.io/badge/platform-macOS%20%7C%20Windows-lightgrey.svg)

## ✨ Features

- 🎤 **Real-time voice dubbing** with custom voice models
- 🌍 **Russian ↔ English translation** with auto-detection
- 🔊 **F5-TTS voice cloning** (5-10x faster than XTTS v2)
- 🎨 **Modern, sleek UI** inspired by iOS design
- 🚀 **Apple Silicon optimized** (M1/M2/M3 Mac support)
- 📦 **Three custom voices included** (configurable)

## 🖥️ Screenshots

*Modern dark UI with smooth animations and clear status indicators*

## 🚀 Quick Start

### Prerequisites

- Python 3.10 or higher
- macOS (Apple Silicon recommended) or Windows
- ~2GB disk space for models

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/VonKleistL/von-tilts-goy-box.git
cd von-tilts-goy-box
```

2. **Install dependencies**
```bash
pip install -r requirements.txt
```

3. **Configure your voice files**

Edit `oyvey_f5tts.py` and update the paths to your voice files:
```python
VOICE_PATHS = {
    "Voice 1": "/path/to/your/voice1.wav",
    "Voice 2": "/path/to/your/voice2.wav",
    "Voice 3": "/path/to/your/voice3.wav"
}
```

4. **Run the app**
```bash
python3 oyvey_f5tts.py
```

## 📖 Usage

1. **First Launch**: App downloads F5-TTS model (~500MB, one-time)
2. **Select Voice**: Choose from your configured voice models
3. **Set Languages**: Pick input (Auto-detect/English/Russian) and output language
4. **Start Dubbing**: Click "Start Oy Vey Dubbing Ya Schlepper"
5. **Speak**: Your audio is translated and dubbed in the selected voice
6. **Stop**: Click "Oy Vey It's Anuddah Shoah" when done

## ⚙️ Configuration

### Voice Models

Place your WAV files in a dedicated directory and update `VOICE_PATHS` in the code:

```python
VOICE_PATHS = {
    "Custom Name": "/full/path/to/voice.wav"
}
```

**Requirements:**
- Format: WAV, MP3, or FLAC
- Length: 10+ seconds (app auto-extracts 10s clips)
- Quality: Higher quality = better cloning

### Translation API

Default: LibreTranslate (free, no API key)

For better quality, use DeepL:
```python
DEEPL_API_KEY = "your-api-key-here"
TRANSLATION_API = "deepl"
```

## 🏗️ Project Structure

```
von-tilts-goy-box/
├── oyvey_f5tts.py          # Main application
├── requirements.txt         # Python dependencies
├── README.md               # This file
├── LICENSE                 # MIT License
└── .gitignore             # Git ignore rules
```

## 🔧 Technical Details

### Architecture

- **TTS Engine**: F5-TTS (flow-matching based, 82M params)
- **Translation**: LibreTranslate API / DeepL API
- **Speech-to-Text**: Planned (Whisper/VOSK)
- **UI Framework**: PyQt6
- **Audio I/O**: sounddevice + soundfile

### Performance

| Component | Speed (M2 Mac) |
|-----------|----------------|
| Voice cloning (F5-TTS) | ~0.5-1s per sentence |
| Translation | ~0.2-0.5s |
| Total latency | ~1-2s end-to-end |

**vs. XTTS v2**: 5-10x faster on Apple Silicon

## 🐛 Troubleshooting

### "Model download is slow"
First launch downloads ~500MB. Use stable internet. Subsequent launches are instant.

### "Voice file not found"
Check that paths in `VOICE_PATHS` are absolute paths and files exist.

### "MPS not available"
On non-Apple Silicon Macs, app falls back to CPU (slower but works).

### "PYTHONHASHSEED error"
Already fixed in code. Update to latest version if you see this.

## 🤝 Contributing

Contributions welcome! Please:

1. Fork the repo
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit changes (`git commit -m 'Add amazing feature'`)
4. Push to branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- [F5-TTS](https://github.com/SWivid/F5-TTS) - Fast, high-quality TTS model
- [LibreTranslate](https://libretranslate.com/) - Free translation API
- PyQt6 - Modern UI framework

## 📧 Contact

- GitHub: [@VonKleistL](https://github.com/VonKleistL)
- Issues: [GitHub Issues](https://github.com/VonKleistL/von-tilts-goy-box/issues)

---

**Made with ❤️ for voice dubbing enthusiasts**