﻿# Telescope_Automation
🌌 Astronomy Forecast Tool
A Python tool for generating detailed astronomy observation forecasts. This script combines Skyfield's precise astronomical data with OpenWeatherMap forecasts to help amateur astronomers and stargazers plan their night sky viewing. It also generates a professional PDF report.

✨ Features
📡 Real-time astronomical calculations using the Skyfield library
🌙 Moon phase and moonrise/moonset times
🔭 Visible planets and deep-sky objects (e.g., Messier and NGC catalog)
☁️ Hourly weather forecast (cloud cover, humidity, temperature)
📈 Limiting magnitude based on telescope aperture and Bortle scale
📄 PDF report generation with forecast summary

📦 Requirements
Install dependencies with:

bash
Copy
Edit
pip install skyfield reportlab requests
🔑 API Key
This project uses OpenWeatherMap One Call API for weather data.
Get your free API key and replace the placeholder in astronomy_forecast.py:

python
Copy
Edit
OPENWEATHERMAP_API_KEY = 'your_api_key_here'
🛠️ How to Use
python
Copy
Edit
from astronomy_forecast import astronomy_forecast, generate_pdf
from datetime import datetime

# Input your parameters
aperture = 6.0             # in inches
bortle = 4                 # 1 (dark) to 9 (urban)
latitude = 19.07           # example: Mumbai, India
longitude = 72.87
date = datetime(2025, 4, 24)

# Get forecast
forecast = astronomy_forecast(aperture, bortle, latitude, longitude, date)

# Add date for reporting
forecast['date'] = date

# Generate PDF
generate_pdf([forecast], filename='stargazing_report.pdf')
📊 Example Output
The PDF report includes:
Date and limiting magnitude
Moon phase and events (rise/set)
List of visible planets and deep-sky objects above the horizon
Hourly weather forecast

🪐 Deep Sky Catalog
A small embedded catalog of Messier and NGC objects is included. You can expand it or load from a custom file.

python
Copy
Edit
DEEP_SKY_CATALOG = [
    {'name': 'M31', 'ra_h': 0.712, 'dec_deg': 41.269, 'mag': 3.4},  # Andromeda Galaxy
    {'name': 'M42', 'ra_h': 5.591, 'dec_deg': -5.391, 'mag': 4.0},  # Orion Nebula
    ...
]
📘 License
This project is open-source under the MIT License. Contributions welcome!

📮 Contact
For feedback or contributions, feel free to reach out or create a pull request.
