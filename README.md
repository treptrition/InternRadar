# ⚡ InternRadar — Live Internship & Hackathon Tracker

> **Developed by Utkarsh Tiwari**

InternRadar is a fast, responsive, and privacy-first hiring radar built for engineering and computer science students. It aggregates active hiring windows, technical internships (FAANG, Unicorns & Global Tech), college hackathons (SIH, ICPC, Flipkart GRiD), research fellowships (Google MSR, MITACS), and government training schemes — filtered directly to your academic cohort.

Available as both a Progressive Web App (PWA) and a standalone native Android application via Capacitor.

---

## 🌟 Key Features

- **Cohort-Based Opportunity Filtering**: Filter opportunities tailored to your exact academic standing (1st, 2nd, 3rd, or 4th Year) with roadmap strategies for each year.
- **Customizable Reminder Tracker**: Decide what you want to track — Internships, Hackathons, Research Fellowships, or Government Schemes — with zero forced defaults.
- **Privacy-First & Secure**: AES-GCM-256 encrypted local storage for profiles and preferences. No third-party OAuth popups required.
- **Full Neo-Brutalist Design**: High-contrast, tactile UI with intuitive dark mode / light mode switching.
- **Multi-Platform**:
  - 🌐 **Web / PWA**: Installable on desktop & mobile directly from browser with offline service worker.
  - 📱 **Native Android**: Built with Capacitor & Gradle for direct USB debugging / APK distribution.

---

## 🛠️ Tech Stack

- **Frontend**: React 19, TypeScript, Vite 8, Tailwind CSS v4, Motion
- **Icons & Theme**: Lucide React, Space Grotesk
- **Security & Storage**: Web Crypto API (PBKDF2 + AES-GCM-256)
- **Mobile Engine**: Capacitor 8 (Android runtime) & Vite PWA Plugin
- **Build System**: Node.js & Gradle 8.14 (Android SDK 36)

---

## 🚀 Quick Start Guide

### Prerequisites
- [Node.js](https://nodejs.org/) (v18 or higher)
- [npm](https://www.npmjs.com/) (v9 or higher)

### 1. Clone the repository
```bash
git clone https://github.com/utkarshtiwari/internradar.git
cd internradar
```

### 2. Install dependencies
```bash
npm install
```

### 3. Run development server
```bash
npm run dev
```
Open [http://localhost:3000](http://localhost:3000) in your browser.

### 4. Build production web bundle
```bash
npm run build
```

---

## 📱 Android Development & USB Debugging

InternRadar comes with native Android support configured out of the box.

### Prerequisites for Android
- Android SDK (API Level 34–36)
- Java Development Kit (JDK 17 or 21)
- Android Debug Bridge (`adb`)

### Building & Installing to Connected Device:
```bash
# 1. Build web assets & sync to Android project
npm run build
npx cap sync

# 2. Build the Debug APK using Gradle
cd android
./gradlew assembleDebug
cd ..

# 3. Install directly onto your phone via USB Debugging
adb install -r android/app/build/outputs/apk/debug/app-debug.apk

# 4. Launch InternRadar on your phone
adb shell am start -n com.internradar.app/.MainActivity
```

---

## 📁 Project Structure

```
internradar/
├── android/                 # Native Android project (Capacitor)
│   ├── app/                 # Android application module & source
│   ├── build.gradle         # Project-level Gradle build script
│   └── gradlew.bat          # Windows Gradle wrapper
├── public/                  # Static assets, PWA icons, manifest
├── src/
│   ├── components/          # Reusable UI cards, modals, header, buttons
│   │   ├── Header.tsx       # Top bar with branding & year selector
│   │   ├── LoginScreen.tsx  # User-friendly onboarding & reminder setup
│   │   ├── ProfileView.tsx  # Student profile & notification preferences
│   │   ├── ...
│   ├── data/
│   │   └── seedOpportunities.ts # Curated technical opportunities database
│   ├── services/
│   │   ├── firebaseAuth.ts  # Session creation & authentication utilities
│   │   └── tokenStorage.ts  # AES-GCM-256 encryption engine
│   ├── types/
│   │   └── auth.ts          # Core TypeScript type definitions
│   ├── App.tsx              # Primary application container & routing
│   └── main.tsx             # Application entry point
├── capacitor.config.ts      # Capacitor configuration
├── vite.config.ts           # Vite + PWA configuration
└── package.json             # Scripts & dependencies
```

---

## 👨‍💻 Developer

**Utkarsh Tiwari**
- **Project**: InternRadar Live
- **GitHub**: [@utkarshtiwari](https://github.com/treptrition)

---

## 📄 License

This project is licensed under the Apache License 2.0.
