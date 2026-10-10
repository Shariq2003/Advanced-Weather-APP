<div align="center">

# 🌦️ Advanced Weather App

**Real-time weather for where you are — or anywhere you search. Temperature, conditions, wind, humidity and cloud cover from the OpenWeatherMap API.**

[![Live Demo](https://img.shields.io/badge/Live_Demo-advanced--weather--app.vercel.app-000000?style=for-the-badge&logo=vercel&logoColor=white)](https://advanced-weather-app.vercel.app)

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![OpenWeatherMap](https://img.shields.io/badge/OpenWeatherMap_API-EB6E4B?style=flat-square&logo=openweathermap&logoColor=white)
![GitHub last commit](https://img.shields.io/github/last-commit/Shariq2003/Advanced-Weather-APP?style=flat-square)

[Features](#-features) · [How it works](#-how-it-works) · [Getting Started](#-getting-started) · [Structure](#-project-structure)

</div>

---

## ✨ Features

| | Feature | Details |
|---|---|---|
| 📍 | **Your Weather** | One-time location permission → weather for your exact coordinates |
| 🔎 | **Search Weather** | Look up any city in the world |
| 🌡️ | **Key readings** | Temperature (°C), description, weather icon and country flag |
| 💨 | **Details** | Wind speed (m/s), humidity (%) and cloudiness (%) |
| ⚡ | **Remembers you** | Coordinates are cached in `sessionStorage`, so switching tabs doesn't re-ask |
| ⏳ | **Loading & error states** | Spinner while fetching, and a "City Not Found" message for unknown cities |
| 📱 | **Responsive** | Works on phones, tablets and desktops |

## 🔄 How it works

```mermaid
flowchart TD
    A(["Open app"]) --> T{"Which tab?"}
    T -- "Your Weather" --> S{"Coordinates in<br/>sessionStorage?"}
    S -- "no" --> G["Grant Access →<br/>navigator.geolocation"]
    G --> C["Save coordinates"]
    S -- "yes" --> F1
    C --> F1["GET /weather?lat=…&lon=…"]
    T -- "Search Weather" --> Q["Type a city"] --> F2["GET /weather?q=city"]
    F1 --> R["Render temp, icon, wind,<br/>humidity, clouds"]
    F2 --> R
    F2 -- "404" --> N["😕 City Not Found"]
```

## 🚀 Getting Started

1. **Clone the repository**
   ```bash
   git clone https://github.com/Shariq2003/Advanced-Weather-APP.git
   cd Advanced-Weather-APP
   ```
2. **Get a free API key** from [OpenWeatherMap](https://openweathermap.org/api).
3. **Add your key** in `index.js`:
   ```js
   const API_KEY = "your_api_key_here"; // replace with your actual API key
   ```
4. **Open `index.html`** in your browser (or run `npx serve .`).

> 💡 Location access requires HTTPS or `localhost`, so serve the folder locally if "Grant Access" doesn't respond.

## 📁 Project Structure

<details>
<summary><b>Expand tree</b></summary>

```text
Advanced-Weather-APP/
├── index.html    # tabs, grant-access screen, search form, weather card
├── styles.css
├── index.js      # geolocation, API calls, rendering
└── assets/       # icons (wind, humidity, cloud, search…) and loading gif
```

</details>

---

<div align="center">

Built by **[Shariq](https://github.com/Shariq2003)** · [LinkedIn](https://www.linkedin.com/in/shariq-sd)

⭐ If you like this project, consider giving it a star!

</div>
