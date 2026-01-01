# 🌍 Global Currency Converter

A professional, real-time currency conversion application built with Python and Tkinter, featuring live exchange rates, persistent favorites, and an intuitive user interface.

![Python Version](https://img.shields.io/badge/python-3.7+-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)
![Status](https://img.shields.io/badge/status-production-brightgreen.svg)

## 📋 Table of Contents

- [Overview](#overview)
- [Key Features](#key-features)
- [Screenshots](#screenshots)
- [Installation](#installation)
- [Usage](#usage)
- [Technical Architecture](#technical-architecture)
- [API Integration](#api-integration)
- [File Structure](#file-structure)
- [Code Quality](#code-quality)
- [Future Enhancements](#future-enhancements)
- [Contributing](#contributing)
- [License](#license)

## 🎯 Overview

The Global Currency Converter is a desktop application that provides real-time currency conversion across 150+ currencies. Built with a focus on user experience and reliability, it features offline caching, favorite currency management, and automatic rate updates from trusted financial APIs.

### Why This Project?

This application demonstrates proficiency in:
- **GUI Development**: Clean, responsive interface using Tkinter
- **API Integration**: Real-time data fetching with error handling
- **Data Persistence**: JSON-based caching and favorites system
- **User Experience**: Intuitive design with keyboard shortcuts and instant feedback
- **Error Handling**: Robust exception management and graceful degradation

## ✨ Key Features

### Core Functionality
- **Real-Time Exchange Rates**: Live data from ExchangeRate-API
- **150+ Currencies**: Support for all major world currencies
- **Instant Conversion**: Real-time calculation as you type
- **Bidirectional Swap**: Quick currency pair reversal
- **Offline Mode**: Cached rates when internet is unavailable

### User Experience
- **Favorites System**: Star and save frequently used currencies
- **Persistent Storage**: Automatically saves preferences and cache
- **Clean UI**: Modern, professional interface with color-coded sections
- **Keyboard Support**: Full keyboard navigation and shortcuts
- **Error Messages**: Clear, user-friendly error notifications

### Technical Features
- **Automatic Caching**: Reduces API calls and enables offline usage
- **Rate Information**: Displays exchange rate and last update time
- **Thread-Safe**: Non-blocking API calls
- **Cross-Platform**: Works on Windows, macOS, and Linux

## 🖼️ Screenshots

```
┌─────────────────────────────────────────┐
│     🌍 Global Currency Converter        │
├─────────────────────────────────────────┤
│                                         │
│  Amount: [1.00____________]             │
│                                         │
│  From: [USD ▼]              [⭐]        │
│                                         │
│         [⇅ Swap]                        │
│                                         │
│  To:   [EUR ▼]              [⭐]        │
│                                         │
│  ┌───────────────────────────────────┐ │
│  │  1.00 USD = 0.92 EUR              │ │
│  └───────────────────────────────────┘ │
│                                         │
│  1 USD = 0.9234 EUR                     │
│                                         │
│  [🔄 Update] [⭐ Favorites]              │
│                    Last updated: 2026.. │
└─────────────────────────────────────────┘
```

## 🚀 Installation

### Prerequisites

- Python 3.7 or higher
- pip package manager
- Internet connection (for initial setup)

### Step 1: Clone the Repository

```bash
git clone https://github.com/yourusername/currency-converter.git
cd currency-converter
```

### Step 2: Install Dependencies

```bash
pip install -r requirements.txt
```

**requirements.txt:**
```
requests>=2.28.0
```

### Step 3: Run the Application

```bash
python currency_converter.py
```

### Alternative: Create Executable (Optional)

```bash
# Install PyInstaller
pip install pyinstaller

# Create standalone executable
pyinstaller --onefile --windowed --name="CurrencyConverter" currency_converter.py
```

## 💻 Usage

### Basic Conversion

1. **Enter Amount**: Type the amount you want to convert (e.g., 100)
2. **Select Source Currency**: Choose from dropdown (e.g., USD)
3. **Select Target Currency**: Choose destination currency (e.g., EUR)
4. **View Result**: Conversion happens automatically in real-time

### Advanced Features

#### Swap Currencies
Click the **⇅ Swap** button to instantly reverse the currency pair.

#### Add to Favorites
Click the **⭐** button next to any currency dropdown to save it to favorites for quick access.

#### View Favorites
Click **⭐ View Favorites** to see and manage your saved currencies.

#### Update Rates
Click **🔄 Update Rates** to fetch the latest exchange rates from the API.

### Keyboard Shortcuts

- `Tab`: Navigate between fields
- `Enter`: Confirm selection in dropdowns
- `Ctrl+C`: Copy result (when focused)

## 🏗️ Technical Architecture

### Application Structure

```
currency_converter.py
├── CurrencyConverter Class
│   ├── __init__()           # Initialize UI and load data
│   ├── create_widgets()     # Build GUI components
│   ├── update_exchange_rates() # Fetch live rates
│   ├── convert_currency()   # Perform conversion
│   ├── swap_currencies()    # Swap currency pair
│   ├── save_cache()         # Persist exchange rates
│   ├── load_cache()         # Load cached rates
│   ├── save_favorites()     # Save favorite currencies
│   └── load_favorites()     # Load favorite currencies
```

### Data Flow

```
User Input → Validation → API Call/Cache → Conversion → Display
     ↓                          ↓
  Cache Storage          Rate Information
```

### Design Patterns Used

1. **Singleton Pattern**: Single instance of CurrencyConverter
2. **Observer Pattern**: Event-driven UI updates
3. **Cache Pattern**: Local storage for offline functionality
4. **MVC-Inspired**: Separation of data, logic, and presentation

## 🔌 API Integration

### ExchangeRate-API

**Endpoint**: `https://api.exchangerate-api.com/v4/latest/USD`

**Features**:
- Free tier available (1,500 requests/month)
- No API key required for basic usage
- Real-time exchange rates
- 150+ currencies supported

**Response Format**:
```json
{
  "base": "USD",
  "date": "2026-01-02",
  "rates": {
    "EUR": 0.9234,
    "GBP": 0.7912,
    "JPY": 149.82,
    ...
  }
}
```

### Error Handling

The application implements comprehensive error handling:
- **Network Errors**: Falls back to cached rates
- **API Failures**: Displays user-friendly error messages
- **Invalid Input**: Real-time validation and feedback
- **Missing Data**: Graceful degradation with informative messages

## 📁 File Structure

```
currency-converter/
│
├── currency_converter.py        # Main application file
├── requirements.txt             # Python dependencies
├── README.md                    # Project documentation
│
├── exchange_rates_cache.json    # Auto-generated cache file
├── favorites.json               # Auto-generated favorites file
│
└── assets/                      # Optional: Screenshots/icons
    ├── screenshot1.png
    └── icon.ico
```

### Generated Files

**exchange_rates_cache.json**:
```json
{
  "rates": {
    "USD": 1.0,
    "EUR": 0.9234,
    "GBP": 0.7912
  },
  "timestamp": "2026-01-02T10:30:00"
}
```

**favorites.json**:
```json
["USD", "EUR", "GBP", "INR", "JPY"]
```

## 🎨 Code Quality

### Best Practices Implemented

✅ **Clean Code**
- Descriptive variable and function names
- Comprehensive docstrings (can be added)
- Consistent formatting and style
- Modular, reusable functions

✅ **Error Handling**
- Try-except blocks for all critical operations
- User-friendly error messages
- Graceful fallback to cached data

✅ **Performance**
- Efficient data structures (dictionaries for O(1) lookup)
- Minimal API calls with caching
- Non-blocking UI operations

✅ **User Experience**
- Real-time validation
- Instant feedback
- Keyboard navigation support
- Professional, intuitive interface

### Code Metrics

- **Lines of Code**: ~400
- **Functions**: 15+
- **Complexity**: Low-Medium (maintainable)
- **Test Coverage**: Ready for unit testing implementation

## 🔮 Future Enhancements

### Planned Features

- [ ] **Historical Data Charts**: Visualize exchange rate trends
- [ ] **Multiple Conversions**: Compare multiple currencies simultaneously
- [ ] **Currency Calculator**: Advanced mathematical operations
- [ ] **Export Functionality**: Save conversion results to CSV/PDF
- [ ] **Themes**: Dark mode and custom color schemes
- [ ] **Multi-language Support**: Internationalization (i18n)
- [ ] **Desktop Notifications**: Alert on significant rate changes
- [ ] **Unit Tests**: Comprehensive test suite with pytest

### Technical Improvements

- [ ] Async API calls with asyncio
- [ ] Database integration (SQLite) for better data management
- [ ] Logging system for debugging and monitoring
- [ ] Configuration file for user preferences
- [ ] Rate limiting and request throttling
- [ ] WebSocket support for real-time updates

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. **Fork the repository**
2. **Create a feature branch**: `git checkout -b feature/AmazingFeature`
3. **Commit your changes**: `git commit -m 'Add some AmazingFeature'`
4. **Push to the branch**: `git push origin feature/AmazingFeature`
5. **Open a Pull Request**

### Contribution Guidelines

- Follow PEP 8 style guide
- Add unit tests for new features
- Update documentation as needed
- Ensure backward compatibility

## 📄 License

This project is licensed under the MIT License - see below for details:

```
MIT License

Copyright (c) 2026 [Your Name]

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

## 👤 Author

**Your Name**
- GitHub: [@Yash14909](https://github.com/Yash14909)
- Email: yashvreddy2043@gmail.com

## 🙏 Acknowledgments

- Exchange rates provided by [ExchangeRate-API](https://www.currency_conv.github.io/)
- Built with Python and Tkinter
- Inspired by the need for a simple, offline-capable currency converter

## 📞 Support

If you need help or have questions:

- Open an issue on GitHub
- Check existing documentation
- Contact the maintainer via email

## 🌟 Star This Repository

If you find this project useful, please consider giving it a star on GitHub! It helps others discover the project and motivates continued development.

---

**Happy Converting! 💱**
