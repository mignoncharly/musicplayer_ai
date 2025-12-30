# AI Music Player

A production-grade, offline-first desktop music player with AI-powered features for smart playlist generation and vibe matching.

![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)
![PySide6](https://img.shields.io/badge/UI-PySide6-green.svg)
![SQLite](https://img.shields.io/badge/Database-SQLite-lightgrey.svg)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)

## Features

### Smart Vibe Matching
- **AI-Powered Playlists**: Auto-generate playlists based on BPM, energy, rhythm, and mood
- **Similar Track Discovery**: Right-click any track to find songs with matching vibe
- **Semantic Audio Analysis**: Uses CLAP embeddings for deep audio understanding
- **Smart Playlist Wizard**: Create playlists by mood, energy level, or musical characteristics

### Reliable Library Management
- **Audio Fingerprinting**: Detect moved or renamed files using Chromaprint/AcoustID
- **Duplicate Detection**: Find and manage duplicate tracks in your library
- **Missing File Recovery**: Locate and relink files that have been moved
- **Metadata Editing**: Full support for editing track metadata and cover art

### Modern User Experience
- **Professional Dark UI**: Clean, modern interface built with PySide6
- **Offline Voice Commands**: Control playback with voice (play, search, switch playlists)
- **Natural Language Search**: Search your library using natural language queries
- **Audio Conversion**: Convert between MP3, FLAC, WAV, OGG, M4A, and AAC formats
- **Equalizer**: 10-band equalizer with presets

## Screenshots

*Coming soon*

## Installation

### Prerequisites
- Python 3.10 or higher
- Windows 10/11 (primary platform)
- FFmpeg (optional, for audio conversion)

### Quick Start

1. **Clone the repository**
   ```bash
   git clone https://github.com/mignoncharly/musicplayer_ai.git
   cd musicplayer_ai
   ```

2. **Create virtual environment**
   ```bash
   python -m venv venv

   # Windows
   venv\Scripts\activate

   # Linux/Mac
   source venv/bin/activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Run the application**
   ```bash
   python main.py
   ```

### Optional: FFmpeg for Audio Conversion
To enable audio format conversion:

1. Download FFmpeg from https://ffmpeg.org/download.html
2. Extract to a folder (e.g., `C:\ffmpeg\bin`)
3. Add the folder to your system PATH
4. Install pydub: `pip install pydub`

## Technology Stack

### Core Audio Analysis (Offline)
| Library | Purpose |
|---------|---------|
| **Madmom** | BPM detection, beat tracking, tempo analysis |
| **Librosa** | Energy (RMS), spectral analysis, chroma features |
| **CLAP** | Semantic audio embeddings for mood/vibe similarity |
| **Chromaprint** | Audio fingerprinting, file relinking, duplicate detection |

### Voice & NLP (Offline)
| Library | Purpose |
|---------|---------|
| **Vosk** | Offline speech-to-text for voice commands |
| **Sentence-Transformers** | Intent detection, natural language matching |

### UI & Storage
| Library | Purpose |
|---------|---------|
| **PySide6** | Modern Qt-based user interface |
| **SQLite** | Local database for tracks, features, playlists |

## Usage

### Basic Playback
- **Double-click** a track to play
- Use playback controls (play/pause, next, previous, stop)
- **Shuffle**: Randomize playback order
- **Repeat**: Cycle through Off → Repeat One → Repeat All

### Smart Features
1. **Find Similar Tracks**: Right-click any track → "Play Similar Tracks"
2. **Smart Playlist**: Tools → Smart Playlist Wizard
3. **Voice Commands**: Click the Voice button and speak commands like:
   - "Play jazz"
   - "Play something energetic"
   - "Play chill music"

### Library Management
- **Import**: File → Import Folder or drag & drop
- **Edit Metadata**: Select track → Click Edit button
- **Find Duplicates**: Library → Find Duplicates
- **Find Missing Files**: Library → Find Missing Files

## Project Structure

```
musicplayer_ai/
├── app/                    # Application UI and controllers
│   ├── modern_mainwindow.py    # Main application window
│   ├── controller.py           # App controller
│   ├── settings_dialog.py      # Settings/preferences
│   └── ...
├── audio/                  # Audio playback
│   └── player.py              # Audio player implementation
├── ai/                     # AI/ML features
│   ├── feature_extractor.py   # Audio feature extraction
│   ├── clap_embeddings.py     # CLAP semantic embeddings
│   ├── playlist_engine.py     # Smart playlist generation
│   └── voice_commands.py      # Voice control
├── storage/                # Data persistence
│   ├── database.py            # SQLite database
│   └── library_manager.py     # Library management
├── utils/                  # Utilities
│   └── artwork.py             # Cover art handling
├── main.py                 # Application entry point
└── requirements.txt        # Python dependencies
```

## Configuration

Settings are accessible via **Tools → Preferences**:

- **Appearance**: Theme selection (Dark/Light)
- **Audio**: Default volume, crossfade settings
- **Library**: Auto-scan directories, metadata sources
- **Voice**: Enable/disable voice commands, language selection

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- [PySide6](https://doc.qt.io/qtforpython-6/) - Qt for Python
- [Librosa](https://librosa.org/) - Audio analysis
- [Madmom](https://github.com/CPJKU/madmom) - Music signal processing
- [CLAP](https://github.com/LAION-AI/CLAP) - Contrastive Language-Audio Pretraining
- [Vosk](https://alphacephei.com/vosk/) - Offline speech recognition
- [Chromaprint](https://acoustid.org/chromaprint) - Audio fingerprinting

## Support

If you encounter any issues or have questions:
- Open an issue on GitHub
- Check existing issues for solutions

---

**Note**: This is an offline-first application. All AI features work without an internet connection. Optional online features (metadata lookup, cover art) require explicit user opt-in.
