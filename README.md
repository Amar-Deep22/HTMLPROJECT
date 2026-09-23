<div align="center">

# 🌤️ WEATHER DASHBOARD

### **Real-Time Weather Monitoring & Forecasting**

*A modern, responsive web application for exploring current weather conditions and 5-day forecasts for cities around the world.*

<br>

[![Status](https://img.shields.io/badge/Status-Active-success?style=for-the-badge)](#)
[![Responsive](https://img.shields.io/badge/Responsive-Mobile%20%7C%20Tablet%20%7C%20Desktop-blue?style=for-the-badge)](#)
[![JavaScript](https://img.shields.io/badge/JavaScript-ES2020+-yellow?style=for-the-badge\&logo=javascript\&logoColor=white)](#)
[![API](https://img.shields.io/badge/API-REST%20%2F%20JSON-orange?style=for-the-badge)](#)
[![License](https://img.shields.io/badge/License-Academic-lightgrey?style=for-the-badge)](#)

<br>

### 🌍 Search Any City   •   🌡️ Live Weather   •   📅 5-Day Forecast

<br>

</div>

---

## ✨ EXPERIENCE THE WEATHER DIFFERENTLY

> **Weather Dashboard** transforms raw weather API data into a clean, interactive and responsive experience designed for fast everyday weather checking.

```text
                         🌤️ WEATHER DASHBOARD
                                  │
             ┌────────────────────┼────────────────────┐
             │                    │                    │
             ▼                    ▼                    ▼
       🔎 SEARCH CITY        📍 LOCATION         🕘 RECENT SEARCHES
             │                    │                    │
             └────────────────────┼────────────────────┘
                                  ▼
                         🌐 WEATHER API
                                  │
                    ┌─────────────┴─────────────┐
                    ▼                           ▼
              🌡️ CURRENT                  📅 5-DAY
               WEATHER                    FORECAST
                    │                           │
                    └─────────────┬─────────────┘
                                  ▼
                         🖥️ DASHBOARD UI
```

---

# 🧭 QUICK NAVIGATION

| 🚀    | Section                                |                           |
| ----- | -------------------------------------- | ------------------------- |
| 🌟    | [Overview](#-overview)                 | Project introduction      |
| ⚡     | [Features](#-features)                 | What the dashboard can do |
| 🖥️   | [Interface](#️-interface-preview)      | UI structure              |
| 🏗️   | [Architecture](#️-system-architecture) | How the system works      |
| 🛠️   | [Tech Stack](#️-technology-stack)      | Technologies used         |
| ⚙️    | [Installation](#️-installation)        | Run locally               |
| 🔑    | [API Setup](#-api-configuration)       | Configure weather API     |
| 🧪    | [Testing](#-testing)                   | Test coverage             |
| 🚀    | [Deployment](#-deployment)             | Deploy the project        |
| 🗺️   | [Roadmap](#️-future-roadmap)           | Future improvements       |
| 👨‍💻 | [Developer](#-developer)               | Project information       |

---

# 🌟 OVERVIEW

**Weather Dashboard** is a responsive client-side web application that provides real-time weather information and a short-term forecast through a public weather API.

The application is designed around a simple principle:

> ### **Search → Understand → Plan**

Users can search for a city and immediately see its current conditions, forecast, and essential weather statistics.

The project scope includes city search, current weather, 5-day forecast, temperature-unit switching, loading states, error handling, recent searches, local persistence, responsive layouts, and optional geolocation.

---

# ⚡ FEATURES

<div align="center">

| 🔎               | 🌡️                      | 📅                       |
| ---------------- | ------------------------ | ------------------------ |
| **Smart Search** | **Live Weather**         | **5-Day Forecast**       |
| Search any city  | Temperature & conditions | Daily forecast summaries |

| 🌡️                | 📍                   | 🕘                  |
| ------------------ | -------------------- | ------------------- |
| **°C / °F**        | **Location Weather** | **Recent Searches** |
| Instant conversion | Optional GPS lookup  | Last 5 cities       |

| ⏳                      | 🛡️                | 📱                |
| ---------------------- | ------------------ | ----------------- |
| **Loading States**     | **Error Handling** | **Responsive UI** |
| Clear request feedback | Friendly failures  | Mobile → Desktop  |

</div>

---

## 🔎 SMART CITY SEARCH

Search for weather using a city name.

```text
┌──────────────────────────────────────────────────────┐
│                                                      │
│   🔎  Search for a city...                    [↗]    │
│                                                      │
└──────────────────────────────────────────────────────┘
```

### Supports

* 🔎 City-name search
* ⌨️ Enter-key submission
* 🚫 Empty-input validation
* ⚡ Asynchronous requests
* 🛡️ Duplicate request protection

A valid search retrieves the city's current weather information and updates the dashboard.

---

# 🌡️ CURRENT WEATHER

Once a city is selected, the dashboard presents the most important weather information in one place.

```text
┌─────────────────────────────────────────────────────────┐
│                                                         │
│                    New Delhi, IN                        │
│                                                         │
│                         ☀️                              │
│                       28°C                              │
│                     Clear Sky                            │
│                                                         │
│      ───────────────────────────────────────────        │
│                                                         │
│       💧 Humidity       💨 Wind       🌡️ Feels Like    │
│          65%           12 km/h           29°C          │
│                                                         │
└─────────────────────────────────────────────────────────┘
```

### Weather information

**Temperature** · **Condition** · **Weather Icon** · **Feels Like** · **Humidity** · **Wind Speed**

These are the primary current-condition fields specified by the SRS.

---

# 📅 5-DAY FORECAST

The dashboard transforms 3-hour forecast information into easy-to-read daily summaries.

```text
       MON          TUE          WED          THU          FRI
    ┌────────┐   ┌────────┐   ┌────────┐   ┌────────┐   ┌────────┐
    │  ☀️    │   │  🌤️    │   │  🌧️    │   │  ☁️    │   │  ☀️    │
    │        │   │        │   │        │   │        │   │        │
    │  32°C  │   │  30°C  │   │  27°C  │   │  29°C  │   │  33°C  │
    │  24°C  │   │  23°C  │   │  22°C  │   │  23°C  │   │  25°C  │
    └────────┘   └────────┘   └────────┘   └────────┘   └────────┘
```

Each forecast card represents:

* 📅 Date
* 🌤️ Representative condition
* 🔺 High temperature
* 🔻 Low temperature

The SRS specifies exactly five daily forecast summaries.

---

# 🌡️ TEMPERATURE UNIT SWITCH

Switch between:

<div align="center">

### `°C`  ⇄  `°F`

</div>

The conversion occurs **client-side**, so changing units does not require another API request.

The selected preference can also persist across reloads through `localStorage`.

---

# 📍 CURRENT LOCATION

Don't want to type your city?

Use the location button:

```text
             📍
              │
              ▼
      Browser Permission
              │
              ▼
       Latitude / Longitude
              │
              ▼
          Weather API
              │
              ▼
       🌤️ Local Weather
```

The feature uses the browser's Geolocation API and requires user permission. If permission is denied, the dashboard continues working normally.

---

# 🕘 RECENT SEARCHES

Your last **5 distinct searches** can be stored locally.

```text
┌───────────────────────────────┐
│       🕘 RECENT SEARCHES       │
├───────────────────────────────┤
│  📍 New Delhi                 │
│  📍 London                    │
│  📍 Tokyo                     │
│  📍 Dubai                     │
│  📍 Paris                     │
└───────────────────────────────┘
```

Click any city to perform the search again.

Duplicate entries are collapsed and the latest search moves to the top.

---

# ⏳ LOADING EXPERIENCE

Weather data is fetched asynchronously.

Instead of leaving the interface blank:

```text
             🔎 Searching...
                    │
                    ▼
              ⏳ Loading...
                    │
                    ▼
             🌤️ Weather Data
```

The application provides visible feedback while requests are in progress.

---

# 🛡️ ERROR HANDLING

The application is designed to fail gracefully.

### ❌ Invalid City

```text
╭────────────────────────────────────────╮
│ ⚠️  City not found                     │
│                                        │
│ Check the spelling and try again.      │
╰────────────────────────────────────────╯
```

### 🌐 Network Error

```text
╭────────────────────────────────────────╮
│ ⚠️  Connection problem                 │
│                                        │
│ Check your internet connection.        │
╰────────────────────────────────────────╯
```

### 🚨 API Error

```text
╭────────────────────────────────────────╮
│ ⚠️  Something went wrong               │
│                                        │
│ Please try again shortly.              │
╰────────────────────────────────────────╯
```

Supported error scenarios include invalid cities, network failures, API errors such as 401/429/500, and empty searches.

---

# 🖥️ INTERFACE PREVIEW

> ### 📸 Add your actual project screenshots here

### 🖥️ Desktop Dashboard

<div align="center">

```text
┌──────────────────────────────────────────────────────────────┐
│ 🌤️ WEATHER DASHBOARD                         °C  °F   📍    │
├──────────────────────────────────────────────────────────────┤
│                                                              │
│  🔎 Search for a city...                         [ SEARCH ]  │
│                                                              │
├──────────────────────────────────────────────────────────────┤
│                                                              │
│                    🌤️  28°C                                 │
│                   New Delhi                                 │
│                    Clear Sky                                 │
│                                                              │
│       💧 65%      💨 12 km/h      🌡️ 29°C                  │
│                                                              │
├──────────────────────────────────────────────────────────────┤
│                                                              │
│                    5-DAY FORECAST                            │
│                                                              │
│   ☀️        🌤️        🌧️        ☁️        ☀️               │
│  32/24     30/23     27/22     29/23     33/25             │
│                                                              │
└──────────────────────────────────────────────────────────────┘
```

</div>

---

# 📱 RESPONSIVE EXPERIENCE

The dashboard adapts across:

```text
📱 MOBILE
   ↓
📲 TABLET
   ↓
💻 DESKTOP
```

### Target breakpoints

| Device     |      Width |
| ---------- | ---------: |
| 📱 Mobile  |    ≤ 480px |
| 📲 Tablet  | 481–1024px |
| 💻 Desktop |   > 1024px |

The SRS requires the interface to avoid horizontal overflow and maintain usable touch targets on smaller screens.

---

# 🏗️ SYSTEM ARCHITECTURE

```text
                         ┌────────────────┐
                         │      USER      │
                         └───────┬────────┘
                                 │
                                 ▼
                  ┌────────────────────────────┐
                  │      PRESENTATION LAYER    │
                  │                            │
                  │       HTML + CSS + UI      │
                  └──────────────┬─────────────┘
                                 │
                                 ▼
                  ┌────────────────────────────┐
                  │      APPLICATION LOGIC     │
                  │                            │
                  │ Validation                  │
                  │ State Management            │
                  │ Data Transformation        │
                  │ Error Handling              │
                  └──────────────┬─────────────┘
                                 │
                   ┌─────────────┴─────────────┐
                   │                           │
                   ▼                           ▼
        ┌────────────────────┐       ┌────────────────────┐
        │    WEATHER API     │       │    localStorage    │
        │                    │       │                    │
        │ REST / JSON / HTTPS│       │ Preferences        │
        └────────────────────┘       │ Recent Searches    │
                                     └────────────────────┘
```

The SRS defines this as a client-centric layered architecture with presentation, application logic, API service, and persistence responsibilities.

---

# 🔄 DATA FLOW

```text
┌───────────────┐
│ User Search   │
└───────┬───────┘
        │
        ▼
┌───────────────┐
│ Input Validate│
└───────┬───────┘
        │
        ▼
┌───────────────┐
│ Loading State  │
└───────┬───────┘
        │
        ▼
┌───────────────┐
│ Weather API   │
└───────┬───────┘
        │
        ▼
┌───────────────┐
│ JSON Response  │
└───────┬───────┘
        │
        ▼
┌───────────────┐
│ Transform Data │
└───────┬───────┘
        │
        ├─────────────────────┐
        ▼                     ▼
┌───────────────┐     ┌───────────────┐
│ Render UI     │     │ Save Search   │
└───────────────┘     └───────────────┘
```

---

# 🛠️ TECHNOLOGY STACK

<div align="center">

| Layer                  | Technology              |
| ---------------------- | ----------------------- |
| 🎨 **Structure**       | HTML5                   |
| 🎨 **Styling**         | CSS3 / Flexbox / Grid   |
| 🧠 **Logic**           | JavaScript ES2020+      |
| 🌐 **HTTP**            | Fetch API               |
| ☁️ **Data**            | REST / JSON Weather API |
| 💾 **Storage**         | Browser localStorage    |
| 📍 **Location**        | Browser Geolocation API |
| 🔀 **Version Control** | Git / GitHub            |

</div>

The SRS recommends HTML5/CSS3 with either vanilla JavaScript or React, native Fetch for HTTP, and localStorage for persistence.

---

# 📂 PROJECT STRUCTURE

```text
🌤️ weather-dashboard/
│
├── 📄 index.html
│
├── 🎨 css/
│   └── styles.css
│
├── 🧠 js/
│   ├── app.js
│   ├── weatherApi.js
│   ├── weatherController.js
│   └── storage.js
│
├── 🖼️ assets/
│   ├── icons/
│   └── screenshots/
│
├── 🔐 .env
├── 🚫 .gitignore
├── 📦 package.json
└── 📖 README.md
```

> Adjust the structure above to match the actual repository implementation.

---

# ⚙️ INSTALLATION

## 01 — Clone

```bash
git clone <YOUR_REPOSITORY_URL>
```

## 02 — Open

```bash
cd weather-dashboard
```

## 03 — Install Dependencies

If your project uses npm:

```bash
npm install
```

## 04 — Configure API

Create your environment/configuration file.

```env
WEATHER_API_KEY=your_api_key_here
```

## 05 — Start

For a Vite-based project:

```bash
npm run dev
```

For a simple static project, use VS Code **Live Server** or another local development server.

---

# 🔑 API CONFIGURATION

The application requires a public weather API such as OpenWeatherMap or another equivalent provider.

```text
                 YOUR APP
                    │
                    │ HTTPS
                    ▼
          ┌──────────────────┐
          │   WEATHER API    │
          └──────────────────┘
                    │
                    ▼
              JSON RESPONSE
```

### ⚠️ Important

Never upload your API key to GitHub.

```gitignore
.env
.env.*
```

The SRS explicitly identifies API-key protection as a security requirement.

---

# 🧪 TESTING

The project uses a combination of manual and lightweight automated testing.

### Test Matrix

| ID      | Test                 | Expected Result            |
| ------- | -------------------- | -------------------------- |
| `TC-01` | Search valid city    | Weather appears            |
| `TC-02` | Empty search         | Validation appears         |
| `TC-03` | Valid weather search | All weather fields visible |
| `TC-04` | Forecast             | 5 cards displayed          |
| `TC-05` | Toggle unit          | Values update              |
| `TC-06` | API request          | Loading indicator appears  |
| `TC-07` | Invalid city         | Friendly error             |
| `TC-08` | Offline              | Network error              |
| `TC-09` | Location             | Local weather displayed    |
| `TC-10` | Reload               | Previous city restored     |
| `TC-11` | Mobile width         | No horizontal overflow     |

The SRS defines these test cases and requires the Must-Have requirements to pass before project completion.

---

# ⚡ PERFORMANCE TARGETS

```text
┌─────────────────────────────────────────┐
│ ⚡ WEATHER SEARCH                       │
│    Target: ≤ 3 seconds                 │
├─────────────────────────────────────────┤
│ 🔄 UNIT CONVERSION                      │
│    Target: ≤ 1 second                  │
├─────────────────────────────────────────┤
│ 🚀 INITIAL PAGE LOAD                    │
│    Target: ≤ 2 seconds                 │
└─────────────────────────────────────────┘
```

These targets are specified in the SRS for normal operating conditions.

---

# 🔐 SECURITY

### Implemented principles

```text
🔒 HTTPS
     │
     ├── Weather API communication
     │
     ▼
🔑 Protected API Configuration
     │
     ├── .env / configuration
     │
     ▼
🧹 Input Validation
     │
     ▼
🛡️ Safe UI Rendering
```

The current academic architecture communicates directly with the weather API. The SRS documents a future Node.js/Express proxy as a way to hide the API key in a production-oriented version.

---

# 🚀 DEPLOYMENT

The current client-side architecture can be deployed using static hosting.

### Compatible deployment options

```text
┌────────────────────┐
│    GitHub Pages    │
└─────────┬──────────┘
          │
          ├──────────────┐
          │              │
          ▼              ▼
   ┌───────────┐   ┌───────────┐
   │  Netlify  │   │  Vercel   │
   └───────────┘   └───────────┘
```

The SRS identifies GitHub Pages, Netlify, and Vercel as suitable examples for static deployment.

---

# 🗺️ FUTURE ROADMAP

```text
CURRENT
   │
   ├── 🌤️ Weather Search
   ├── 📅 5-Day Forecast
   ├── 📍 Geolocation
   ├── 🕘 Recent Searches
   └── 📱 Responsive UI
          │
          ▼
PHASE 2
   │
   ├── 🔐 Backend Proxy
   ├── 👤 User Accounts
   ├── ⭐ Saved Locations
   └── 💾 Server-side Caching
          │
          ▼
PHASE 3
   │
   ├── 📊 Historical Analytics
   ├── 🔔 Weather Alerts
   ├── 🌍 Multi-language
   ├── 🌙 Dark / Light Theme
   └── 🧪 E2E Testing
```

These items represent future scope documented by the SRS rather than current-release requirements.

---

# 📊 PROJECT SNAPSHOT

<div align="center">

| 📌                    | Details                    |
| --------------------- | -------------------------- |
| **Project Type**      | Responsive Web Application |
| **Domain**            | Weather / Web Development  |
| **Architecture**      | Client-Centric Layered     |
| **Data Source**       | Public Weather API         |
| **Forecast**          | 5 Days                     |
| **Persistence**       | Browser localStorage       |
| **Location**          | Browser Geolocation API    |
| **Target Devices**    | Mobile / Tablet / Desktop  |
| **API Communication** | HTTPS                      |
| **Primary Language**  | JavaScript                 |

</div>

---

# 🎯 PROJECT SCOPE

### ✅ CURRENT RELEASE

```text
[x] 🔎 City Search
[x] 🌡️ Current Weather
[x] 📅 5-Day Forecast
[x] 🌡️ Celsius / Fahrenheit
[x] ⏳ Loading States
[x] 🛡️ Error Handling
[x] 📍 Geolocation
[x] 🕘 Recent Searches
[x] 💾 localStorage
[x] 📱 Responsive Design
```

### 🔮 FUTURE

```text
[ ] 🔐 Backend Proxy
[ ] 👤 User Authentication
[ ] ⭐ Saved Locations
[ ] 📊 Historical Analytics
[ ] 🔔 Weather Alerts
[ ] 📩 Notifications
[ ] 🌍 Multi-language
[ ] 🌙 Theme Switching
[ ] 🧪 End-to-End Testing
```

---

# 🎓 ACADEMIC INFORMATION

<div align="center">

### **Weather Dashboard**

**Software Requirements Specification Aligned Project**

<br>

**Developed By**

# 👨‍💻 Amardeep Ranjan

### B.Tech — Computer Science Engineering

**GLA University, Greater Noida**

University Roll No. `225155000018`

<br>

**Faculty Guide / Evaluator**

### Gautam Mukharjee

</div>

---

# 📚 DOCUMENTATION

| 📄 Document          | Purpose                            |
| -------------------- | ---------------------------------- |
| 📘 **SRS**           | Complete software requirements     |
| 📖 **README**        | Setup, usage & architecture        |
| 🧪 **Testing Plan**  | Functional & responsive validation |
| 🏗️ **Architecture** | System design & data flow          |

The SRS follows an IEEE 830 / ISO-IEC-IEEE 29148 aligned structure.

---

# ⭐ WHY THIS PROJECT?

> **A small project doesn't have to look like a small project.**

Weather Dashboard demonstrates practical implementation of:

```text
API Integration
      +
Asynchronous JavaScript
      +
Responsive UI
      +
Data Transformation
      +
Client-Side Persistence
      +
Error Handling
      +
Geolocation
      =
A Complete Web Application
```

---

<div align="center">

## 🌤️ WEATHER DASHBOARD

### **Search. Discover. Understand the Weather.**

<br>

**Built with ❤️ by Amardeep Ranjan**

<br>

`HTML` · `CSS` · `JavaScript` · `REST API` · `localStorage`

<br>

⭐ **If you find this project useful, consider giving it a star!** ⭐

</div>
