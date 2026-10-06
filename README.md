<div align="center">

<!-- PROJECT LOGO & TITLE -->
<img src="https://img.shields.io/badge/DOFX-Camera%20%26%20Optics-8B5A2B?style=for-the-badge&logo=materialdesign&logoColor=white" height="35" alt="DOFX Badge" />

# 📸 DOFX
### *Next-Gen Optical Depth of Field & Real-Time Bokeh Simulation Suite*

<p align="center">
  <b>Simulate optics. Calculate depth of field. Master your framing before you press the shutter.</b>
</p>

<!-- BADGES -->
[![Live Web / Download](https://img.shields.io/badge/🌐_Official_Web-dofx.netlify.app-blueviolet?style=for-the-badge)](https://dofx.netlify.app)
[![Platform](https://img.shields.io/badge/Platform-Android_|_Mobile_Web-3DDC84?style=for-the-badge&logo=android&logoColor=white)](https://dofx.netlify.app)
[![Material You](https://img.shields.io/badge/Design-Material_3-7B1FA2?style=for-the-badge&logo=material-design&logoColor=white)](https://m3.material.io)
[![Status](https://img.shields.io/badge/Status-Active_v1.0.0-success?style=for-the-badge)](#)
[![License](https://img.shields.io/badge/License-MIT-amber?style=for-the-badge)](#)

<br/>

<!-- EMBEDDED SHOWCASE IMAGE -->
<p align="center">
  <img src="https://i.ibb.co/rRhDbYhR/vlcsnap-2026-10-07-02h36m49s497.png" alt="vlcsnap-2026-10-07-02h36m49s497" border="0" width="100%" style="max-width: 480px; border-radius: 20px; box-shadow: 0 10px 30px rgba(0,0,0,0.35);" />
</p>

<!-- ACTION BUTTON -->
<p align="center">
  <a href="https://dofx.netlify.app">
    <img src="https://img.shields.io/badge/⬇️️_DOWNLOAD_NOW-dofx.netlify.app-8B4513?style=for-the-badge&logo=google-play&logoColor=white" alt="Download DOFX" height="42" />
  </a>
</p>

---

</div>

## 📑 Quick Navigation
- [✨ Key Features](#-key-features)
- [📱 Mobile App Tour](#-mobile-app-tour)
- [🔬 The Optical Physics Engine](#-the-optical-physics-engine)
- [⚙️ Technical Highlights](#️-technical-highlights)
- [📥 Download & Installation](#-download--installation)
- [🎨 Theming & Interface](#-theming--interface)
- [📄 License](#-license)

---

## ✨ Key Features
┌────────────────────────────────────────────────────────────────────────┐
│  ✦ 2D Ray Cone Visualization        ✦ Live CameraX Hardware Feed       │
│  ✦ Real-Time Bokeh Synthesis        ✦ Circle of Confusion (CoC) Math   │
│  ✦ Hyperfocal Range Locking         ✦ Full History & Instant Undo      │
│  ✦ Metric & Imperial Dual Engine    ✦ Material 3 Warm Bronze Theming   │
└────────────────────────────────────────────────────────────────────────┘
* **📐 Interactive 2D Ray Cone Ray-Tracing**: Real-time interactive silhouette showing subject distance, camera position, focus plane cut, and near/far focus falloff boundaries.
* **✨ Live CameraX & Synthetic Bokeh Simulation**: Switch seamlessly between real optical hardware feeds and procedural bokeh rendering with customizable point-source shapes (`City Lights`, `Sunset`, `Garden`).
* **🎯 Precision Depth of Field Computing**: Instant calculation of Near Limit, Far Limit, Total Depth of Field, and Hyperfocal Distance with zero latency.
* **🔄 10-Step History & Undo Stack**: Never lose a preset. Inspect past changes with active state rollbacks (`Sensor changed`, `Aperture adjusted`, etc.).
* **🌗 Dynamic High-Contrast & Dark Mode**: Handcrafted for extreme lighting conditions—from direct sunlight shoots to darkroom and night cinematography.
* **📏 Dual Measurement Units**: Instant 1-tap toggle between **Imperial** (`ft/in`) and **Metric** (`mm/cm/m`).

---

## 📱 Mobile App Tour

<div align="center">

| 📐 2D Ray Cone View | 🌃 Bokeh & CameraX | 📜 History & Rollback | 📖 Optical Science |
| :---: | :---: | :---: | :---: |
| Ray-cone visualizer, subject distance & plane calculation | Live aperture simulation (`f/1.4` to `f/22`), light characteristics | Full adjustment timeline with 1-click state restore | Onboard optical physics and CoC formulas |
| <sub>`Near 5' 5.1" | Far 6' 2.8"`</sub> | <sub>`City Lights | Sunset | Garden`</sub> | <sub>`10-Step Memory Stack`</sub> | <sub>`H = f + (f² / (N × c))`</sub> |

</div>

---

## 🔬 The Optical Physics Engine

DOFX implements standard optical physics without rounding shortcuts, calibrated against digital 35mm full-frame and crop sensor benchmarks:

### 1. 🎯 Hyperfocal Distance ($H$)
$$\mathbf{H = f + \frac{f^2}{N \times c}}$$

* $f$ = Focal Length (in millimeters)
* $N$ = Lens Aperture ($f$-number)
* $c$ = Circle of Confusion diameter ($\approx \frac{\text{Sensor Diagonal}}{1500} = 0.029\text{mm}$ for 35mm full frame)

> **Example benchmark:** $50\text{mm}$ at $f/3.5$ on a Full Frame sensor yields $H = 80\text{' } 11.7\text{"}$.

---

### 2. 📏 Depth of Field Limits ($D_{near}$ & $D_{far}$)

$$\mathbf{D_{near} = \frac{H \times s}{H + (s - f)}}$$

$$\mathbf{D_{far} = \frac{H \times s}{H - (s - f)}}$$

* $s$ = Subject Distance
* When $s \ge H$, $D_{far}$ extends infinitely ($\infty$).

---

## ⚙️ Technical Highlights

* **Architecture:** Modern Android MVVM with Clean Architecture principles.
* **UI Framework:** Material 3 (Material You) with custom Canvas vectors for ray paths.
* **Camera Pipeline:** AndroidX `CameraX` API providing zero-lag optical sensor control.
* **Calculations:** High-precision floating-point optical computation engine running off the main thread.
* **Distribution:** Static PWA & Progressive Android web package hosted on Netlify CDN.

---

## 📥 Download & Installation

### Option 1: Web App / Direct APK (Recommended)
Visit the official deployment portal to install directly on any device:
👉 **[https://dofx.netlify.app](https://dofx.netlify.app)**

```bash
# Add as a Progressive Web App (PWA)
1. Open [https://dofx.netlify.app](https://dofx.netlify.app) in Chrome / Safari on your mobile device.
2. Tap "Install DOFX" or "Add to Home Screen".
3. Launch DOFX with full offline capabilities!
