# 🌤️ Weather Dashboard

### Real-Time Weather Monitoring & 5-Day Forecasting

> A responsive, modern web application that lets users search for any city and instantly view current weather conditions and a 5-day forecast.

<p align="center">

**🔎 Search Cities · 🌡️ Live Weather · 📅 5-Day Forecast · 📍 Current Location · 🌗 °C / °F · 📱 Responsive**

</p>

---

## ✨ Overview

**Weather Dashboard** is a client-side web application designed to provide a simple and interactive way to check weather conditions for cities around the world.

The application connects to a public weather API over HTTPS and transforms the returned weather data into an easy-to-understand dashboard.

The project is designed according to the requirements defined in the project's SRS and focuses on:

* ⚡ Fast asynchronous API requests
* 🌍 City-based weather search
* 🌡️ Current weather information
* 📅 5-day weather forecasting
* 🔄 Celsius/Fahrenheit conversion
* 📍 Optional current-location weather
* 🕘 Recent search history
* 💾 Browser-based persistence
* 📱 Responsive design
* 🛡️ Graceful error handling

---

## 🎯 Project Objectives

The main objectives of the Weather Dashboard are to:

1. Provide real-time weather information for any searchable city.
2. Display important weather parameters in a clean interface.
3. Provide a short-term 5-day forecast.
4. Create a responsive experience across mobile, tablet, and desktop devices.
5. Demonstrate asynchronous JavaScript and REST API integration.
6. Implement client-side data persistence using `localStorage`.
7. Handle invalid searches, API failures, and network errors gracefully.

---

# 🚀 Features

## 🔎 1. City Weather Search

Search for weather information simply by entering a city name.

```text
Enter City → Search → API Request → Weather Dashboard
```

The application supports both:

* 🔘 Search button
* ⌨️ Enter key

Empty or whitespace-only searches are rejected before an API request is made.

---

## 🌡️ 2. Current Weather

After a successful search, the dashboard displays:

| Information      | Description                        |
| ---------------- | ---------------------------------- |
| 🌡️ Temperature  | Current temperature                |
| 🌤️ Condition    | Current weather condition          |
| 🖼️ Weather Icon | Visual representation of condition |
| 🌡️ Feels Like   | Perceived temperature              |
| 💧 Humidity      | Current humidity percentage        |
| 💨 Wind Speed    | Current wind speed                 |
| 📍 Location      | City and country information       |

The SRS specifies that the primary weather information should be visible together without unnecessary navigation.

---

# 📅 3. 5-Day Forecast

The dashboard provides a **5-day forecast** using weather data from 3-hour intervals.

The interval data is aggregated into daily summaries.

Each forecast card contains:

```text
┌─────────────────────┐
│       Monday        │
│         ☀️          │
│                     │
│   High: 32°C        │
│   Low:  24°C        │
└─────────────────────┘
```

### Forecast Features

* 📅 Day/date
* 🌤️ Representative weather icon
* 🔺 Daily high temperature
* 🔻 Daily low temperature
* 🔄 Automatic °C/°F conversion

The required behavior is five representative daily forecast cards rather than displaying every 3-hour API record directly.

---

# 🌡️ 4. Celsius / Fahrenheit Toggle

Users can switch between:

```text
°C  ⇄  °F
```

The conversion happens **on the client side**, meaning another API request is not required.

The selected unit is also saved using `localStorage`.

---

# 📍 5. Current Location Weather

The application can optionally use the browser's **Geolocation API**.

```text
📍 Allow Location
       ↓
Browser Geolocation
       ↓
Latitude + Longitude
       ↓
Weather API
       ↓
Current Weather
```

If the user denies location permission, the rest of the application remains usable.

---

# 🕘 6. Recent Searches

The dashboard remembers up to **5 recent distinct searches**.

Example:

```text
Recent Searches

┌─────────────┐
│ New Delhi   │
├─────────────┤
│ London      │
├─────────────┤
│ Tokyo       │
├─────────────┤
│ Dubai       │
├─────────────┤
│ Paris       │
└─────────────┘
```

Clicking a recent city performs the search again.

Duplicate searches are collapsed and moved to the top.

---

# 💾 7. Local Persistence

The application uses the browser's `localStorage` to remember:

```text
Last searched city
        +
Temperature unit
        +
Recent searches
```

Therefore, when the user reloads the page, the previous context can be restored.

---

# ⏳ 8. Loading State

Weather information is retrieved asynchronously.

During an API request, the dashboard displays a loading indicator rather than leaving the user wondering whether the application is responding.

```text
Search City
     ↓
⏳ Loading...
     ↓
🌤️ Weather Results
```

---

# ⚠️ 9. Smart Error Handling

The application handles common failure scenarios without crashing.

### Invalid City

```text
⚠️ We couldn't find that city.
   Check the spelling and try again.
```

### Network Failure

```text
⚠️ You appear to be offline.
   Check your internet connection.
```

### API Error

```text
⚠️ Something went wrong.
   Please try again shortly.
```

### Empty Search

```text
⚠️ Please enter a city name.
```

The SRS specifically requires user-friendly UI feedback instead of blank screens or console-only errors.

---

# 📱 Responsive Design

The interface is designed for multiple screen sizes.

| Device     |     Target |
| ---------- | ---------: |
| 📱 Mobile  |    ≤ 480px |
| 📲 Tablet  | 481–1024px |
| 💻 Desktop |   > 1024px |

### Mobile

```text
┌─────────────────────┐
│   Weather Dashboard │
├─────────────────────┤
│ 🔎 Search City      │
├─────────────────────┤
│                     │
│       28°C          │
│      ☀️ Clear       │
│                     │
├─────────────────────┤
│   5-Day Forecast    │
│                     │
│  ☀️  🌤️  🌧️  ☁️  ☀️ │
└─────────────────────┘
```

### Desktop

```text
┌──────────────────────────────────────────────────────┐
│ 🌤️ Weather Dashboard       🔎 Search    °C / °F     │
├──────────────────────────────────────────────────────┤
│                                                      │
│             CURRENT WEATHER                          │
│                                                      │
│                28°C ☀️                               │
│             New Delhi, IN                            │
│                                                      │
│      💧 65%     💨 12 km/h     🌡️ 29°C             │
│                                                      │
├──────────────────────────────────────────────────────┤
│                   5-DAY FORECAST                     │
│                                                      │
│  ☀️       🌤️       🌧️       ☁️       ☀️            │
│ Mon      Tue      Wed      Thu      Fri             │
└──────────────────────────────────────────────────────┘
```

The SRS requires no horizontal overflow and responsive reflow across mobile, tablet, and desktop layouts.

---

# 🏗️ System Architecture

The project follows a **client-centric layered architecture**.

```text
                   ┌───────────────────────┐
                   │       USER            │
                   └───────────┬───────────┘
                               │
                               ▼
                   ┌───────────────────────┐
                   │   PRESENTATION/UI     │
                   │   HTML + CSS + JS     │
                   └───────────┬───────────┘
                               │
                               ▼
                   ┌───────────────────────┐
                   │   APPLICATION LOGIC   │
                   │ Validation / State    │
                   │ Data Transformation   │
                   └───────────┬───────────┘
                               │
                    ┌──────────┴──────────┐
                    ▼                     ▼
          ┌──────────────────┐   ┌──────────────────┐
          │  WEATHER API     │   │   localStorage   │
          │  REST / JSON      │   │   Local Data     │
          └──────────────────┘   └──────────────────┘
```

The current release does not require a custom backend server. The browser communicates directly with the public weather API through HTTPS.

---

# 🔄 Application Data Flow

```text
User enters city
       │
       ▼
Input Validation
       │
       ▼
Show Loading State
       │
       ▼
Weather API Request
       │
       ▼
Receive JSON Response
       │
       ▼
Transform Weather Data
       │
       ▼
Render Dashboard
       │
       ├──────────────► Save Last City
       │
       └──────────────► Update Recent Searches
```

If an error occurs:

```text
API / Network Error
        │
        ▼
Error Handler
        │
        ▼
Friendly UI Message
        │
        ▼
User Can Retry
```

---

# 🛠️ Technology Stack

| Technology             | Purpose                           |
| ---------------------- | --------------------------------- |
| **HTML5**              | Application structure             |
| **CSS3**               | Styling and responsive layout     |
| **JavaScript ES2020+** | Application logic                 |
| **Fetch API**          | HTTP requests                     |
| **REST API**           | Weather data                      |
| **JSON**               | API data format                   |
| **localStorage**       | Client-side persistence           |
| **Geolocation API**    | Optional current-location weather |
| **Git / GitHub**       | Version control                   |

The SRS permits either vanilla HTML/CSS/JavaScript or React; the chosen approach should be kept consistent throughout the implementation.

---

# 📂 Suggested Project Structure

```text
weather-dashboard/
│
├── 📄 index.html
│
├── 📁 css/
│   └── styles.css
│
├── 📁 js/
│   ├── app.js
│   ├── weatherApi.js
│   ├── weatherController.js
│   └── storage.js
│
├── 📁 assets/
│   ├── icons/
│   └── images/
│
├── 🔐 .env
├── 🚫 .gitignore
├── 📄 README.md
└── 📄 package.json
```

> If the actual implementation uses a different structure, update this section to match the repository.

The SRS recommends separating API access, application logic, UI rendering, and persistence into distinct modules/components.

---

# ⚙️ Installation & Setup

## 1️⃣ Clone the Repository

```bash
git clone <YOUR_REPOSITORY_URL>
```

Move into the project directory:

```bash
cd weather-dashboard
```

---

## 2️⃣ Configure the Weather API

The project requires a public weather API such as **OpenWeatherMap or an equivalent provider**.

Create an environment/configuration file according to your implementation.

Example:

```env
WEATHER_API_KEY=your_api_key_here
```

⚠️ **Never commit your API key to GitHub.**

Add your environment file to `.gitignore`:

```gitignore
.env
.env.*
```

The SRS explicitly requires that the API key not be committed to public source control.

---

## 3️⃣ Run the Project

### If using a simple HTML/CSS/JS implementation

You can serve the project using a local development server.

For example:

```bash
npx serve .
```

or use the **Live Server** extension in VS Code.

### If using Vite

```bash
npm install
npm run dev
```

Then open the local URL shown by the development server.

---

# 🔑 Environment Variables

| Variable          | Purpose                               |
| ----------------- | ------------------------------------- |
| `WEATHER_API_KEY` | API authentication key                |
| `WEATHER_API_URL` | Weather API base URL, if configurable |

Example:

```env
WEATHER_API_KEY=xxxxxxxxxxxxxxxx
WEATHER_API_URL=https://api.example.com
```

> Do not upload `.env` files containing real credentials.

---

# 🧑‍💻 How to Use

### Step 1 — Open the Dashboard

Launch the application in a modern browser.

### Step 2 — Search

Enter a city:

```text
New Delhi
```

Press:

```text
Search
```

or hit:

```text
Enter
```

### Step 3 — View Current Weather

The dashboard displays:

```text
Temperature
Condition
Feels Like
Humidity
Wind Speed
Location
```

### Step 4 — Check Forecast

Scroll to the forecast section to view the next five days.

### Step 5 — Change Temperature Unit

Use:

```text
°C ⇄ °F
```

### Step 6 — Use Current Location

Click the location button and allow browser location access.

### Step 7 — Reuse Recent Searches

Select a city from the recent-search list to search it again.

---

# 🧪 Testing

The project follows a combination of:

* Manual exploratory testing
* Functional requirement testing
* UI/responsive testing
* Lightweight automated unit testing for pure logic

The SRS identifies testing targets including temperature conversion, forecast aggregation, input validation, and error mapping.

### Core Test Cases

| Test                | Expected Result         |
| ------------------- | ----------------------- |
| Search valid city   | Weather displayed       |
| Search empty input  | Validation message      |
| Search invalid city | Friendly error          |
| Disable network     | Network error shown     |
| Toggle °C/°F        | Temperatures update     |
| Search city         | 5-day forecast appears  |
| Reload page         | Last city restored      |
| Use location        | Weather for coordinates |
| Resize to mobile    | No horizontal overflow  |

---

# 📊 Performance Requirements

The project targets:

```text
⚡ Weather result rendering
   ≤ 3 seconds under normal API conditions

⚡ Temperature conversion
   ≤ 1 second

⚡ Initial page load
   ≤ 2 seconds excluding first weather request
```

These targets are defined in the project's SRS.

---

# 🔐 Security Considerations

The project follows several basic security practices:

* 🔒 HTTPS-only API communication
* 🔑 API key kept outside public source control
* 🧹 User input validation/sanitization
* 🚫 No unnecessary personal information storage
* 📍 Geolocation used only when the user grants permission

The current academic version uses direct browser-to-weather-API communication, which means a client-side API key can technically be inspectable. The SRS identifies a future backend proxy as the production-oriented solution.

---

# 🌐 Browser Compatibility

The application is intended for modern versions of:

* Google Chrome
* Mozilla Firefox
* Microsoft Edge
* Safari

Target environments include:

```text
📱 Mobile
   ≥ 360px

📲 Tablet
   ≥ 768px

💻 Desktop
   ≥ 1280px
```

---

# 🚀 Deployment

Because the current project is a client-side application, it can be deployed using a static hosting service.

Possible deployment platforms include:

* GitHub Pages
* Netlify
* Vercel

```text
GitHub Repository
       │
       ▼
Static Hosting
       │
       ▼
🌤️ Weather Dashboard
       │
       ▼
Weather API
```

The SRS identifies static deployment as suitable for the current release because no custom backend server is required.

---

# 📸 Screenshots

Add your actual screenshots here after completing the UI.

### 🖥️ Desktop

```markdown
![Desktop Dashboard](./assets/screenshots/desktop.png)
```

### 📱 Mobile

```markdown
![Mobile Dashboard](./assets/screenshots/mobile.png)
```

### 🌧️ Weather Search

```markdown
![Weather Search](./assets/screenshots/search.png)
```

### ⚠️ Error State

```markdown
![Error State](./assets/screenshots/error.png)
```

---

# 🗺️ Future Scope

The current release intentionally keeps the system focused. Possible future extensions identified in the SRS include:

### 🔐 Backend Security

Introduce a Node.js/Express backend proxy to hide the API key and provide server-side caching.

### 👤 User Accounts

Add:

* Registration
* Login
* User profiles
* Saved locations

### 📊 Weather Analytics

Possible future capabilities:

* Historical weather data
* Weather trends
* Search analytics
* Extended forecasts

### 🔔 Weather Alerts

Add:

* Weather notifications
* Severe weather alerts
* Push notifications
* Email/SMS notifications

### 🌍 Internationalization

Add multilingual support for:

* UI labels
* Weather conditions
* User-facing messages

### 🎨 Themes

Introduce:

```text
☀️ Light Mode
🌙 Dark Mode
```

### 🧪 Advanced Testing

Introduce automated end-to-end testing using tools such as Playwright or Cypress.

## These are **future-phase ideas**, not requirements of the current release.

# 📌 Project Scope

### ✅ Current Release

* [x] City weather search
* [x] Current weather
* [x] 5-day forecast
* [x] Celsius/Fahrenheit toggle
* [x] Loading state
* [x] Error handling
* [x] Responsive interface
* [x] Recent searches
* [x] localStorage persistence
* [x] Optional geolocation

### 🔮 Future Release

* [ ] Backend API proxy
* [ ] User authentication
* [ ] Saved locations
* [ ] Historical weather analytics
* [ ] Weather alerts
* [ ] Push notifications
* [ ] Multi-language support
* [ ] Dark/light theme
* [ ] End-to-end automated testing

---

# 👨‍💻 Developer

### **Amardeep Ranjan**

**B.Tech — Computer Science Engineering**
**GLA University, Greater Noida**

University Roll No.: `225155000018`

Faculty Guide / Evaluator: **Gautam Mukharjee**

---

# 🎓 Academic Project

This Weather Dashboard is developed as an academic software engineering project and follows the requirements documented in the project's Software Requirements Specification.

The SRS identifies the project as a responsive web application for real-time weather monitoring and forecasting.

---

# 📄 Documentation

| Document         | Description                         |
| ---------------- | ----------------------------------- |
| 📘 SRS           | Software Requirements Specification |
| 📖 README        | Project setup and usage             |
| 🧪 Test Plan     | Functional and responsive testing   |
| 🏗️ Architecture | System design and data flow         |

---

# ⭐ Project Highlights

```text
┌───────────────────────────────────────────────┐
│              🌤️ WEATHER DASHBOARD             │
├───────────────────────────────────────────────┤
│                                               │
│   🔎 Search Any City                          │
│                                               │
│   🌡️ Current Weather                         │
│                                               │
│   💧 Humidity   💨 Wind   🌡️ Feels Like       │
│                                               │
│   📅 5-Day Forecast                           │
│                                               │
│   🌡️ °C / °F Toggle                          │
│                                               │
│   📍 Current Location                         │
│                                               │
│   🕘 Recent Searches                          │
│                                               │
│   📱 Responsive Design                        │
│                                               │
│   ⚠️ Graceful Error Handling                  │
│                                               │
└───────────────────────────────────────────────┘
```

---

## 📜 License

This project is an academic project developed for educational purposes.

If you reuse or extend the project, please provide appropriate attribution to the original developer.

---

<p align="center">

### 🌤️ Built with HTML, CSS, JavaScript & Weather API

**Made with ❤️ by Amardeep Ranjan**

</p>
