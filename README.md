# 🌍 Global Currency Converter

A powerful and user-friendly desktop application for converting currencies in real-time using live exchange rates. Built with Python and Tkinter, this application provides a clean interface for quick currency conversions with support for favorites and offline caching.

## ✨ Features

- **Real-time Exchange Rates**: Fetches current exchange rates from exchangerate-api.com
- **160+ Currencies**: Support for all major world currencies
- **Favorites System**: Save frequently used currencies for quick access
- **Offline Mode**: Cached exchange rates allow conversions without internet connection
- **Swap Function**: Quickly reverse currency pairs with one click
- **Clean Interface**: Modern, intuitive UI with professional color scheme
- **Rate Information**: Display conversion rates and last update timestamp

## 📋 Prerequisites

Before installing the Global Currency Converter, ensure you have the following:

- Python 3.7 or higher
- pip (Python package installer)
- Internet connection (for fetching exchange rates)

## 🚀 Installation

### Step 1: Clone the Repository

```bash
git clone https://github.com/yourusername/global-currency-converter.git
cd global-currency-converter
```

### Step 2: Install Required Dependencies

```bash
pip install -r requirements.txt
```

If `requirements.txt` is not available, install the dependencies manually:

```bash
pip install requests
```

Note: `tkinter` comes pre-installed with most Python distributions. If you encounter issues, install it using:

**On Ubuntu/Debian:**
```bash
sudo apt-get install python3-tk
```

**On macOS:**
```bash
brew install python-tk
```

**On Windows:**
Tkinter is typically included with Python. If not, reinstall Python from python.org with the Tk/Tcl option enabled.

### Step 3: Run the Application

```bash
python currency_converter.py
```

## 📖 Usage

### Basic Conversion

1. **Launch the application** by running the Python script
2. **Enter an amount** in the amount field (default is 1.00)
3. **Select source currency** from the "From" dropdown menu
4. **Select target currency** from the "To" dropdown menu
5. The conversion result appears automatically in the result display

### Updating Exchange Rates

Click the **"🔄 Update Rates"** button at the bottom of the window to fetch the latest exchange rates from the API. The application will display a success message and show the last update timestamp.

### Using the Swap Feature

Click the **"⇅ Swap"** button to instantly reverse the source and target currencies, making it easy to see conversions in both directions.

### Managing Favorites

1. **Add to Favorites**: Click the **⭐** button next to any currency dropdown to save that currency to your favorites
2. **View Favorites**: Click the **"⭐ View Favorites"** button to see all saved currencies
3. **Remove Favorites**: In the favorites window, select a currency and click **"Remove Selected"**

### Offline Usage

The application automatically caches exchange rates in `exchange_rates_cache.json`. When internet is unavailable, the app uses these cached rates, allowing continued operation without connectivity.

## 🏗️ Project Structure

```
global-currency-converter/
│
├── currency_converter.py       # Main application file
├── exchange_rates_cache.json   # Cached exchange rates (auto-generated)
├── favorites.json              # User's favorite currencies (auto-generated)
├── requirements.txt            # Python dependencies
├── README.md                   # Project documentation
└── LICENSE                     # License file
```

## 🛠️ Configuration

### Changing the Base Currency

By default, the application uses USD as the base currency. To change this, modify the `base_currency` variable in the `__init__` method:

```python
self.base_currency = "EUR"  # Change to your preferred base currency
```

### API Provider

The application uses exchangerate-api.com's free tier. For higher rate limits or additional features, you can sign up for an API key and modify the URL in the `update_exchange_rates` method:

```python
url = f"https://v6.exchangerate-api.com/v6/YOUR_API_KEY/latest/{self.base_currency}"
```

## 🤝 Contributing

Contributions are welcome! Here's how you can help improve the Global Currency Converter:

### How to Contribute

1. **Fork the repository** to your GitHub account
2. **Create a new branch** for your feature or bugfix:
   ```bash
   git checkout -b feature/your-feature-name
   ```
3. **Make your changes** and commit them with clear, descriptive messages:
   ```bash
   git commit -m "Add feature: description of your changes"
   ```
4. **Push to your branch**:
   ```bash
   git push origin feature/your-feature-name
   ```
5. **Open a Pull Request** with a detailed description of your changes

### Contribution Guidelines

- Follow PEP 8 style guidelines for Python code
- Add comments for complex logic
- Test your changes thoroughly before submitting
- Update documentation if you add new features
- Keep commits focused and atomic
- Be respectful and constructive in discussions

### Reporting Issues

If you encounter bugs or have feature suggestions:

1. Check existing issues to avoid duplicates
2. Create a new issue with a clear title and description
3. Include steps to reproduce bugs
4. Provide system information (OS, Python version) when relevant

## 🧪 Testing

To test the application:

1. Verify all currencies load correctly
2. Test conversions with various amounts
3. Check offline functionality by disconnecting internet
4. Test favorites add/remove operations
5. Verify swap functionality works correctly
6. Ensure cache files are created properly

## 📝 Known Issues

- The free API tier has rate limits (typically 1500 requests per month)
- Some currencies may have delayed updates depending on the API provider
- UI scaling may vary on different display resolutions

## 🔮 Future Enhancements

- Historical exchange rate charts
- Multiple currency comparison
- Currency conversion calculator mode
- Custom API key configuration in UI
- Dark mode theme option
- Export conversion history

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

### MIT License Summary

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files, to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software.

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
