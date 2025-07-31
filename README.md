-----

# Namma BMTC AI Mitra 🚌✨

[](https://reactjs.org/)
[](https://tailwindcss.com/)
[](https://ai.google.dev/)
[](https://opensource.org/licenses/MIT)
[](https://www.google.com/search?q=https://github.com/YourUsername/YourRepo)

**Namma BMTC AI Mitra** is a modern, AI-powered, and offline-first web application designed to simplify navigating Bengaluru's extensive BMTC bus network. It intelligently combines the power of Google's Gemini AI for complex route planning with a robust offline database for unmatched reliability.

-----

### 📍 [Live Demo (Placeholder Link)](https://www.google.com/search?q=https://your-live-demo-url.com)

-----

*(A screenshot of the application interface, showing the search inputs and a sample result card.)*

## ✨ Key Features

  * 🧠 **AI-Powered Route Suggestions:** Leverages the **Google Gemini 1.5 Flash API** to provide not just direct routes, but also the best connecting routes, estimated fares, and helpful summaries.
  * ⚡ **Dual-Engine Search:** A unique hybrid system. If the AI service is unavailable, it seamlessly falls back to its comprehensive offline database, ensuring you're never left stranded.
  * 💾 **Comprehensive Offline Database:** Contains a meticulously compiled database of **over 770 BMTC routes** and thousands of stops, derived from official documentation. This allows the app to function even without an internet connection for direct route queries.
  * 🔄 **Resilient API Handling:** Implements an innovative **API key pooling system**. If one API key reaches its rate limit, the application automatically rotates to the next available key, maximizing uptime and reliability.
  * 📱 **Modern & Responsive UI:** Built with **React** and styled with **Tailwind CSS**, the interface is clean, intuitive, and works beautifully on both desktop and mobile devices.
  * 🔍 **Autocomplete Search:** Features a smart autocomplete for bus stops, making it quick and easy to enter your origin and destination.
  * 🌐 **Zero-Backend Architecture:** The entire application runs in the browser. It's a single `index.html` file that can be hosted on any static site provider (like GitHub Pages or Netlify) for incredible ease of deployment.
  * 💵 **Fare Calculation:** Estimates the fare for your journey based on the number of stages and the type of bus service (Ordinary or AC Vajra).

## 🛠️ How It Works

The application's logic is designed for resilience and a great user experience:

1.  **User Input:** The user enters their desired origin and destination from a pre-populated list of stops, assisted by an autocomplete feature.
2.  **AI First:** The app first sends a carefully crafted prompt to the **Google Gemini API**. This prompt asks the AI to act as a BMTC expert and return the best routes in a structured JSON format.
3.  **Successful AI Response:** If the API call is successful, the application parses the JSON response and displays the suggested routes—including direct and connecting options, bus types, and estimated fares—in a rich, user-friendly "AI Route Suggestion" card.
4.  **AI Failsafe (Offline Fallback):** If the Gemini API fails for any reason (e.g., network error, rate limiting on all keys, invalid API key), the application doesn't stop. It automatically triggers its offline search engine.
5.  **Offline Cache Search:** The app then queries the massive `bmtcData` object stored locally in `database.js`. It searches for any **direct routes** that contain both the origin and destination stops in the correct order.
6.  **Displaying Results:** The found routes (whether from the AI or the offline cache) are displayed to the user. The UI clearly indicates the source of the information, so the user knows if they are viewing a live AI suggestion or a potentially outdated offline result.

## 🚀 Getting Started

You can run this project locally with just a web browser. No complex setup is required\!

### Prerequisites

  * A modern web browser (Chrome, Firefox, Safari, Edge).
  * Your own Google Gemini API key(s). You can get one from [Google AI Studio](https://aistudio.google.com/app/apikey).

### Installation & Setup

1.  **Download the Project:**
    Clone the repository or download the `index.html` and `database.js` files.

    ```bash
    git clone https://github.com/your-username/namma-bmtc-ai-mitra.git
    cd namma-bmtc-ai-mitra
    ```

2.  **Add Your API Keys:**
    Open the `index.html` file in a text editor. Find the `apiKeys` array and replace the placeholder strings with your actual Gemini API keys. You can add one or multiple keys.

    ```javascript
    // Inside index.html, within the <script type="text/babel"> tag

    const apiKeys = [
        "REPLACE_WITH_YOUR_FIRST_API_KEY",
        "REPLACE_WITH_YOUR_SECOND_API_KEY", // Optional: for fallback
        // Add more keys here if you have them
    ];
    ```

3.  **Run the Application:**
    Simply open the `index.html` file directly in your web browser\!

## 📂 Project Structure

The project is intentionally simple, consisting of just two core files:

```
.
├── 📄 index.html      # The main file containing all HTML, CSS (via CDN), and React/JS logic.
└── 🗃️ database.js     # A massive offline database of all BMTC routes, stops, and fare info.
```

  * **`index.html`**: This is the heart of the application. It uses CDNs to pull in React, ReactDOM, Babel, and Tailwind CSS. The entire React application, including components, state management, and API logic, is written inside a `<script type="text/babel">` tag. This allows for rapid development and easy deployment without a build step.

  * **`database.js`**: This file contains the `bmtcData` object, which acts as the application's offline cache and fallback mechanism. It was meticulously constructed from PDF documentation and is crucial for the app's offline-first capability.

## 🤖 Technology Stack

  * **Frontend:** React 18, HTML5
  * **Styling:** Tailwind CSS
  * **AI & Machine Learning:** Google Gemini 1.5 Flash
  * **Core Language:** JavaScript (ES6+)
  * **In-browser Transpilation:** Babel

## ⚠️ Important Security Note on API Keys

This project manages API keys in a client-side array for demonstration and ease of use.

**❗️ In a real-world production application, you should NEVER expose your API keys directly in client-side code.**

For a production environment, you should implement a **backend proxy** or a **serverless function** (e.g., on Vercel, Netlify, or AWS Lambda) that receives the user's request, securely adds your API key on the server-side, and then forwards the request to the Google Gemini API. This prevents your keys from being stolen and abused.

## 🤝 Contributing

Contributions are what make the open-source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

If you have a suggestion that would make this better, please fork the repo and create a pull request. You can also simply open an issue with the tag "enhancement".

1.  Fork the Project
2.  Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3.  Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4.  Push to the Branch (`git push origin feature/AmazingFeature`)
5.  Open a Pull Request

## 📜 License

Distributed under the MIT License. See `LICENSE` file for more information.

## 📢 Disclaimer

This is a conceptual application. The AI-generated route information is for informational purposes only and may not be 100% accurate or up-to-date. Always verify critical travel information with official BMTC sources or real-time tracking apps before starting your journey.
