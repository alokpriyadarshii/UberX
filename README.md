# UberX

An Uber style **ride booking UI clone** built with **Vue 3 (Vue CLI) + Tailwind CSS + Pinia** and **Google Maps**.  
This is a **UI/learning project** — it demonstrates pickup/destination search, route display, ETA/distance, and a simple fare estimate.

---

## ✨ What’s inside
- Home screen service cards (Ride / Food / etc.)
- Pickup + destination flow with **Places Autocomplete**
- Live **Google Maps route** (DirectionsService + custom map styling)
- Shows **distance + duration** and a simple **fare estimate** (UberX / Comfort / UberXL)
- Lightweight **Node/Express proxy API** for Places + Distance Matrix
- PWA ready via Vue CLI PWA plugin

---

## ✅ Requirements
- Node.js 18+ (recommended)
- A Google Cloud API key with:
  - Maps JavaScript API
  - Places API
  - Directions API
  - Distance Matrix API

---

## 🚀 Quick Start (two terminals)

### 1) Backend (proxy API)

~~~bash
set -euo pipefail
cd "/Users/alok/Desktop/UberX/server"
npm install
cp .env.example .env
npm run watch
~~~

Edit `server/.env`:

~~~env
GOOGLE_MAPS_API_URL=https://maps.googleapis.com/maps/api/
GOOGLE_MAPS_API_KEY=YOUR_KEY_HERE
~~~

Backend runs on `http://localhost:4001`.

### 2) Frontend (Vue app)

~~~bash
set -euo pipefail
cd "/Users/alok/Desktop/UberX"
npm install
cp .env.example .env
npm run serve
~~~

Edit `.env`:

~~~env
VUE_APP_API_URL=http://localhost:4001/api/
~~~

Update the Google Maps script key in `public/index.html`:

~~~html
<script async defer src="https://maps.googleapis.com/maps/api/js?key=YOUR_GOOGLE_MAPS_JS_KEY&libraries=places"></script>
~~~

---

## 🧹 If install / build issues (optional)

~~~bash
set -euo pipefail
cd "/Users/alok/Desktop/UberX"
rm -rf node_modules package-lock.json
npm install
cd server
rm -rf node_modules package-lock.json
npm install
~~~

---

## 📦 PWA mode (optional)

~~~bash
set -euo pipefail
cd "/Users/alok/Desktop/UberX"
npm run pwa
~~~

---

## 📁 Project structure (high level)

~~~text
UberX/
  public/
    index.html
    img/
      uber/
      icons/
  server/
    index.js
    .env.example
    package.json
  src/
    views/
      HomeView.vue
      DirectionsView.vue
      MapView.vue
    components/
      AutoCompleteInput.vue
      ServiceSelectLarge.vue
      ServiceSelectSmall.vue
    store/
      direction-store.js
    router/
      index.js
    mapStyles.js
    main.js
  .env.example
  tailwind.config.js
  vue.config.js
  package.json
~~~

---

## 🛠 Customize
- **Fare math**: `src/views/MapView.vue` (`calculatePrice`)
- **Map styling**: `src/mapStyles.js`
- **Proxy endpoints**:
  - `GET /api/address/:address` (Places Autocomplete)
  - `GET /api/distance/:pickup/:destination` (Distance Matrix)

---

## 🔐 API Key note
Never commit real API keys. Keep `.env` files local and rotate keys if one was exposed publicly.
README
