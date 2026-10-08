# 🏢 SeismoForge 3D — Earthquake Resistant Design Configurator

<div align="center">

![SeismoForge Banner](https://img.shields.io/badge/SeismoForge-3D%20BIM-00aaff?style=for-the-badge&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI+PHBhdGggZmlsbD0id2hpdGUiIGQ9Ik0xMiAyTDIgN2wxMCA1IDEwLTV6TTIgMTdsOCA0IDgtNHYtNGwtOCA0LTgtNHoiLz48L3N2Zz4=)
![IS 1893](https://img.shields.io/badge/IS%201893-2026%20Compliant-00ff88?style=for-the-badge)
![AI Powered](https://img.shields.io/badge/Seisma-AI%20Voice-cc44ff?style=for-the-badge)
![GPS](https://img.shields.io/badge/GPS-Auto%20Detect-ff8800?style=for-the-badge)
![No Backend](https://img.shields.io/badge/Backend-None%20Required-ff4444?style=for-the-badge)

**PS7 Hackathon · Acropolis Institute of Technology & Research, Indore, M.P.**

[🚀 Live Demo](#) · [📋 Features](#features) · [🛠 Tech Stack](#tech-stack) · [📖 IS 1893 Engine](#is-1893-engine)

</div>

---

## 🎯 Problem Statement (PS7)

> Most structural engineers in India rely on expensive desktop software (ETABS, SAP2000) or manual spreadsheets for earthquake-resistant design. There's no free, visual, AI-powered tool for rapid IS 1893:2026 seismic analysis.

**SeismoForge 3D solves this** — open one HTML file in Chrome and get:
- Complete IS 1893:2026 seismic analysis in seconds
- A full 3D interactive building with underground parking, elevator, staircase
- AI voice assistant that explains everything in plain language
- GPS-based automatic seismic zone detection

---

## ✨ Features

### 🎬 Cinematic Intro
- Full-screen animated seismic wave canvas with earthquake epicenter rings
- Glitch logo animation, geological loading messages
- Smooth flash transition into the main site

### 🏢 3D Interactive Building (Three.js)
- **360° rotation** — drag in any direction, scroll to zoom
- **Underground B1/B2 parking** with cars, markings, ramps
- **Animated glass elevator** — car moves up and down in real-time
- **Staircase** with steps and railings from basement to roof
- **Foundation piles** visible below basement floor
- **Roof** with penthouse, water tank, antenna, satellite dish, AC units
- **Click any floor** to inspect structural details
- **Earthquake simulation** — per-floor lateral displacement (parabolic mode shape)
- **Stress heat map** — color-coded seismic stress per floor
- **Section cut** — clip plane to see inside the building

### 📍 GPS Auto-Detection
- One-click GPS location detection
- Reverse geocoding via **Nominatim API** (free, no API key)
- Maps coordinates → IS 1893 Seismic Zone (II–V)
- **Acropolis, Indore** preset button (live location)

### ⚡ IS 1893:2026 Analysis Engine
| Formula | Description |
|---|---|
| `T = 0.075 × h^0.75` | Fundamental time period (RC MRF) |
| `Sa/g` (piecewise) | Design spectrum per Cl. 6.4.2 |
| `Ah = (Z/2) × (I/R) × Sa` | Design horizontal acceleration |
| `Vb = Ah × W` | Total base shear |
| `Qi = Vb × Wi·hi² / Σ(Wj·hj²)` | Lateral force distribution (Cl. 7.7.1) |

### 🎙 Seisma — AI Voice Assistant
- Female voice (auto-selects Samantha/Zira/Karen/Veena)
- Microphone input via Web Speech Recognition
- Context-aware responses based on YOUR building parameters
- Quick command chips for common questions

### 🔩 IS 13920:2016 Rebar Detailing
- Beam, Column, Slab cross-section diagrams
- Zone-specific requirements (135° hooks mandatory for Zones III–V)
- Visual reinforcement layout

---

## 🛠 Tech Stack

| Technology | Purpose |
|---|---|
| **Vanilla HTML/CSS/JS** | Entire app — zero frameworks, zero build tools |
| **Three.js r134** | 3D building engine (WebGL wrapper) |
| **OrbitControls** | 360° mouse drag rotation |
| **HTML5 Canvas** | 2D building, waveform, spectrum, soil, rebar diagrams |
| **Nominatim API** | Free reverse geocoding (OpenStreetMap) |
| **Web Speech API** | Voice synthesis + speech recognition (browser native) |
| **CSS3 Animations** | Intro screen, glitch effects, loading bar |

> ⚡ **Zero backend. Zero npm. Zero API keys.** One file, open in Chrome.

---

## 🏙 Supported Indian Cities

| Zone | Z Factor | Cities |
|---|---|---|
| Zone V (Extreme) | 0.36 | Guwahati, Srinagar, Imphal, Shillong, Patna, Kangra |
| Zone IV (Severe) | 0.24 | Delhi NCR, Mumbai, Jammu, Dehradun, Jabalpur |
| Zone III (Moderate) | 0.16 | Lucknow, Agra, Pune, Kolkata, Bhopal, **Indore ⭐**, Ahmedabad |
| Zone II (Low) | 0.10 | Bengaluru, Hyderabad, Chennai, Coimbatore, Thiruvananthapuram |

> ⭐ **Indore, M.P.** — Acropolis Institute of Technology & Research (Live Location)  
> Coordinates: 22.6983°N, 75.8795°E

---

## 🚀 Getting Started

```bash
# No installation needed!
# Just open indix.html in Chrome or Edge
```

1. Clone or download this repo
2. Open `indix.html` in **Google Chrome** or **Microsoft Edge**
3. Allow microphone permission for Seisma AI voice
4. Allow location permission for GPS auto-detect
5. Click **"🎓 Acropolis, Indore"** to set live location
6. Hit **"⚡ Analyze Seismic Design"** and explore!

> 💡 **Internet required** on first load for Three.js CDN (`cdn.jsdelivr.net`)

---

## 📐 IS 1893 Analysis — Quick Reference

```
Input Parameters:
├── Location → Zone (II/III/IV/V) → Z factor
├── Storeys (n) × Storey Height (h) → Total height H
├── Structural System → Response Reduction R
├── Soil Type (I/II/III) → Period TP
└── Importance Factor I

Calculations:
├── T  = 0.075 × H^0.75          (RC SMRF)
├── Sa = IS 1893 design spectrum
├── Ah = (Z/2) × (I/R) × Sa
├── W  = Σ Wi (seismic weight)
├── Vb = Ah × W                   (Base Shear)
└── Qi = Vb × Wi×hi² / Σ(Wj×hj²) (Storey Force)
```

---

## 🏗 Project Structure

```
hackathon 2/
└── indix.html          ← The entire app (single file ~116KB)
    ├── CSS Styles      ← Intro, 3D viewer, configurator, voice UI
    ├── HTML Structure  ← Intro screen, 3D viewer, configurator, panels
    └── JavaScript      ← Three.js engine, IS 1893 engine, GPS, Voice AI
        ├── Building3D class      (Three.js 3D building)
        ├── VA object             (Seisma voice assistant)
        ├── analyze()             (IS 1893 calculations)
        ├── detectGPS()           (Nominatim reverse geocoding)
        ├── setAcropolis()        (Indore live location preset)
        ├── simulate2D()          (2D earthquake animation)
        ├── drawRichter()         (Magnitude gauge)
        ├── drawSpectrum()        (IS 1893 response spectrum)
        ├── drawSoil()            (Soil profile visualization)
        └── drawStoreyChart()     (Lateral force distribution)
```

---

## 📊 IS 1893 Compliance Checks

SeismoForge automatically checks:
1. ✅ Structural system suitability per Cl. 7.2.1
2. ✅ Height limit for ESM per Cl. 7.3
3. ✅ Soil–Foundation compatibility per Cl. 6.5
4. ✅ Design acceleration Ah per Cl. 6.4.2
5. ✅ Time period validity per Cl. 7.6
6. ✅ Base shear computation per Cl. 7.6.1
7. ✅ Foundation depth adequacy per Cl. 6.3
8. ✅ IS 13920 ductile detailing requirement

---

## 🎓 About

Built for **PS7 — Earthquake Resistant Design Configurator**  
**Acropolis Institute of Technology & Research, Indore, M.P.**

> *"Turning complex IS 1893 seismic analysis into a 10-second GPS-powered, AI-narrated, 3D visual experience — free for every engineer in India."*

### Standards Referenced
- **IS 1893 (Part 1): 2026** — Criteria for Earthquake Resistant Design of Structures
- **IS 13920: 2016** — Ductile Detailing of Reinforced Concrete Structures
- **IS 456: 2000** — Plain and Reinforced Concrete Code of Practice
- **SP 22: 1982** — Handbook on Earthquake Engineering

---

<div align="center">

Made with ❤️ in Indore, India 🇮🇳

**[megh79870-maker](https://github.com/megh79870-maker)**

</div>
