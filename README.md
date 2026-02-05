# Mr Verse - Bible Verse Presentation Software

[![Go Version](https://img.shields.io/badge/Go-1.24.0-blue.svg)](https://golang.org/doc/devel/release.html)
[![Fyne UI](https://img.shields.io/badge/Fyne-v2.5.4-success)](https://fyne.io/)
[![SQLite](https://img.shields.io/badge/SQLite-Database-lightgrey)](https://sqlite.org/)
[![License](https://img.shields.io/badge/License-Open%20Source-green)](LICENSE)

Mr Verse is a lightweight live Bible verse presentation tool written in Go using Fyne for the UI and SQLite for storage. It emphasises efficient performance on modest hardware and a codebase structured for future expansion. Built for churches and small ministries that need a simple, fast way to display scripture on a projector or secondary screen.

![Status](https://img.shields.io/badge/status-early%20development-orange)

## Features

### **Core Functionality**

- **Dual-Screen Presentation** - Dedicated live presentation window optimized for projectors and secondary monitors
- **Intuitive Controller** - Clean, easy-to-use control interface for seamless verse management
- **Lightning-Fast Navigation** - Instant previous/next verse navigation with smart cross-chapter and cross-book transitions
- **Smart Search** - Quick Bible reference lookup using natural format (e.g., "John 3:16", "Romans 8:28")
- **Multi-Translation Support** - Switch between multiple Bible translations on the fly
- **Multi-Monitor Configuration** - Flexible secondary monitor positioning and sizing
- **Presentation-Optimized UI** - Large, readable text with dark backgrounds for optimal visibility

### **Bible Data Management**

- **SQLite Database** - Efficient local storage with automatic JSON-to-database seeding
- **Dynamic Translation Loading** - Automatic detection and loading of Bible translation files
- **Smart Caching** - Optimized verse retrieval and navigation performance
- **Contextual Navigation** - Intelligent verse sequencing across chapters and books

### **Technical Excellence**

- **Observer Pattern** - Real-time verse updates across all windows
- **Thread-Safe Operations** - Concurrent-safe verse presentation management
- **Comprehensive Logging** - Detailed application logs for troubleshooting
- **Configuration Management** - Persistent settings for monitor setup and preferences

## Quick Start

### Prerequisites

- **Go 1.24** or later ([Download](https://golang.org/dl/))
- **GCC** or compatible C compiler (required for Fyne UI framework)
- **Operating System**: Windows, macOS, or Linux

### Installation

#### Option 1: Build from Source

```bash
# Clone the powerhouse
git clone https://github.com/mr-ministry/mr-verse.git
cd mr-verse

# Build the application
make build

# Launch and inspire!
./mr-verse
```

#### Option 2: Cross-Platform Builds

```bash
# Build for all platforms
make build-all

# Or target specific platforms
make build-windows    # Windows executable
make build-macos      # macOS binary
make build-linux      # Linux binary
```

### **Adding Bible Translations**

Place your Bible translation JSON files in the `data/` directory. The application automatically detects and loads them on startup.

**Supported format:**

```json
{
  "version": "NIV",
  "books": {
    "Genesis": {
      "1": {
        "header": "Genesis 1",
        "verses": {
          "1": "In the beginning God created the heavens and the earth.",
          "2": "Now the earth was formless and empty..."
        }
      }
    }
  }
}
```

## Usage Guide

### **Controller Window**

The command center for your presentation:

- **Search Bar** - Type any Bible reference (e.g., "Psalm 23:1", "1 Corinthians 13:4")
- **Navigation** - Previous/Next buttons for seamless verse flow
- **Translation Selector** - Switch between available Bible versions instantly
- **Go Live Button** - Open/close the presentation window
- **Update Live** - Push current verse to the live display
- **Settings** - Configure secondary monitor positioning

### **Live Presentation Window**

Optimized for maximum visual impact:

- **Dark Background** - Reduces eye strain and enhances readability
- **Auto-Scaling Text** - Dynamically adjusts to window size
- **Centered Layout** - Professional presentation formatting
- **Real-Time Updates** - Instant verse changes from controller

### 🖥️ **Multi-Monitor Setup**

1. Click **Settings** in the controller window
2. Enter your secondary monitor coordinates:
   - **X, Y Position** - Where the window should appear
   - **Width, Height** - Display dimensions
3. Click **Save** - Settings persist automatically
4. Next **Go Live** will position perfectly on your projector!

## Architecture

```txt
 Project Structure
├── cmd/                 # Application entry point
│   └── main.go            # Startup logic & initialization
├── internal/            # Core application logic
│   ├── bible/          # Bible data management
│   │   ├── db.go          # SQLite database operations
│   │   └── query.go       # Verse retrieval & navigation
│   ├── config/         # Settings & preferences
│   ├── presentation/   # Verse display logic
│   └── ui/             # User interface components
│       ├── controller_window.go  # Main control interface
│       ├── live_window.go        # Presentation display
│       └── custom_theme.go       # Visual styling
├── data/               # Bible translation files (JSON)
├── assets/             # Application resources
└── logs/               # Application logs
```

## Development

### **Available Commands**

```bash
make build          # Build for current platform
make run            # Run in development mode
make test           # Execute test suite
make clean          # Clean build artifacts
make deps           # Update dependencies
make build-all      # Cross-platform build
```

### **Testing & Quality**

- **Unit Tests** - Comprehensive test coverage for core functionality
- **Thread Safety** - Concurrent operations tested and verified
- **Memory Management** - Optimized resource usage patterns
- **Error Handling** - Graceful degradation and user feedback

## Bible Translations

Pre-configured support for popular translations:

- **NIV** - New International Version
- **NKJV** - New King James Version
- **NLT** - New Living Translation
- **RCPV** - Revised Common Prayer Version

 **Add More Translations**: Simply place JSON files in the `data/` directory!

## Contributing

We welcome contributions that help spread the Word!

1. Fork the repository
2. Create your feature branch (`git checkout -b feat/amazing-feature`)
3. Make your changes
4. Test thoroughly
5. Submit a pull request

### **Commit Guidelines**

- `feat:` - New features
- `fix:` - Bug fixes
- `refactor:` - Code improvements
- `docs:` - Documentation updates

## Ministry Impact

Built with love for the global church community. Whether you're:

- **Churches** - Enhance your worship services
- **Bible Study Groups** - Engage your participants
- **Teachers** - Create impactful presentations
- **Home Use** - Personal scripture meditation

Mr Verse empowers you to share God's Word with clarity and beauty.

## ROADMAP

- [x] Bible reference in the same language as the selected version
- [ ] Searching with a translation suffix automatically selects that translation
- [ ] Verse preview before showing in live view
- [ ] Showing multiple verses at a time
- [ ] Clickable exit button

## License

Open source with - check [LICENSE](./LICENSE) for details.

---

<div align="center">

**Built with Go • Powered by Fyne • Designed for Ministry**

"Faith comes by hearing, and hearing by the word of God." - Romans 10:17

</div>
