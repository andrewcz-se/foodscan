# 🥫 FoodScan UK — Mobile Barcode & Nutrition Scanner

A lightweight, self-contained, mobile-first web application for scanning food and drink barcodes. Designed for iPhone and Android devices, it delivers UK-focused nutritional traffic lights, mandatory allergen alerts, Nutri-Score, NOVA ratings, and complete ingredient breakdowns powered by the **Open Food Facts API**.

---

## 📱 Features

- **📷 Fast Barcode Scanner:** Real-time barcode scanning using device camera (`html5-qrcode`) with autofocus and rear-camera priority (`facingMode: "environment"`).
- **🔬 iPhone 15 & Modern Flagship Focus Solution:**
  - Solves the physical minimum-focus-distance limitation of modern large 48MP camera sensors (iPhone 13/14/15/15 Pro, Samsung S23/S24, Google Pixel).
  - High-resolution 1080p/4K video stream constraints.
  - **1x / 2x / 3x Zoom Controls:** Built-in hardware optical/sensor zoom support with smart default 2x zoom on launch.
  - Double-tap viewfinder to quickly toggle between 1x and 2x zoom.
  - Multi-camera lens cycle button for switching to Macro / Ultra-Wide lenses on supported devices.
  - 1D barcode aspect-ratio frame and contextual distance guidance.
- **🍎 iOS & Android Optimized:** Handles iOS Safari permissions, prevents fullscreen video takeover with `playsinline` and `webkit-playsinline`, and includes flashlight/torch controls (on supported devices).
- **🚦 UK FSA Front-of-Pack Traffic Lights:** Official UK Food Standards Agency color-coded thresholds (Low/Green, Medium/Amber, High/Red) and % Reference Intake (% RI) for Fat, Saturated Fat, Sugars, and Salt.
- **🌾 14 Mandatory UK Allergens Detection:** Automatically flags and highlights the 14 UK Food Standards Agency mandatory allergens:
  - Celery, Cereals containing Gluten, Crustaceans, Eggs, Fish, Lupin, Milk, Molluscs, Mustard, Tree Nuts, Peanuts, Sesame, Soya, Sulphur Dioxide / Sulphites.
- **🏷️ Nutri-Score & NOVA Classification:** Displays 5-color Nutri-Score spectrum (A to E) and NOVA food processing groups (1 to 4) with clear plain-English descriptions.
- **📊 Detailed Nutritional Breakdown:** Full per-100g and per-serving nutrition table (Energy kJ/kcal, Fat, Saturates, Carbs, Sugars, Fibre, Protein, Salt).
- **⏱️ Scan Debouncing & Feedback:** Instant Web Audio synthesized beep and haptic vibration (`navigator.vibrate`) upon barcode detection with scan debouncing to eliminate duplicate API requests.
- **📦 Fallback Modes:** Manual barcode number search, photo upload from camera roll/gallery, and quick 1-click sample barcodes (Heinz Beans, Marmite, KitKat, Coca-Cola).
- **🕒 Offline Detection & Scan History:** Caches recent scans in `localStorage` in a bottom tray with thumbnail previews, Nutri-Score badges, and quick reload.

---

## 🚀 Instant Deployment (GitHub Pages)

This project consists of a **single self-contained `index.html` file** with zero build steps or external dependencies.

1. Create a repository on GitHub (e.g. `foodscan-uk`).
2. Push `index.html` to the root of your repository:
   ```bash
   git init
   git add index.html README.md
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/<your-username>/foodscan-uk.git
   git push -u origin main
   ```
3. Go to **Repository Settings** > **Pages**.
4. Under **Branch**, select `main` / `root` and click **Save**.
5. Your scanner will be live over HTTPS at `https://<your-username>.github.io/foodscan-uk/`!

> [!NOTE]
> Modern mobile browsers (iOS Safari & Chrome) require an **HTTPS** connection to grant camera access. GitHub Pages automatically provides HTTPS.

---

## 🛠️ Tech Stack

- **HTML5 & Vanilla JavaScript (ES6+)**
- **Tailwind CSS (CDN)** for responsive mobile design & dark mode UI
- **[html5-qrcode](https://github.com/mebjas/html5-qrcode)** for barcode detection
- **[Open Food Facts v2 API](https://world.openfoodfacts.org/)** for open global food data
- **Web Audio API** for zero-dependency sound feedback
