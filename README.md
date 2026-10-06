<div align="center">

<!-- PROJECT LOGO & BADGE -->
<img src="https://img.shields.io/badge/DOFX-Camera%20%26%20Optics-8B5A2B?style=for-the-badge&logo=materialdesign&logoColor=white" height="35" alt="DOFX Badge" />

# 📸 DOFX
### *Real-Time Depth of Field & Optical Bokeh Simulator*

<p align="center">
  <b>Calculate optical depth of field, simulate aperture bokeh, and preview ray cones directly on mobile.</b>
</p>

<!-- ACTION BUTTONS: DIRECT APK & WEB APP -->
<p align="center">
  <a href="https://github.com/your-username/dofx/releases/latest/download/DOFX.apk">
    <img src="https://img.shields.io/badge/⬇%EF%B8%8F_DOWNLOAD_APK-Direct_Install_(GitHub)-E65100?style=for-the-badge&logo=android&logoColor=white" alt="Download APK" height="45" />
  </a>
  <a href="https://dofx.netlify.app">
    <img src="https://img.shields.io/badge/🌐_LIVE_WEB_APP-dofx.netlify.app-4E342E?style=for-the-badge&logo=google-chrome&logoColor=white" alt="Web Version" height="45" />
  </a>
</p>

<!-- STATUS BADGES -->
[![GitHub Release](https://img.shields.io/github/v/release/your-username/dofx?color=E65100&label=APK%20Build&style=flat-square)](https://github.com/your-username/dofx/releases)
[![Platform](https://img.shields.io/badge/Platform-Android%20%7C%20Web-3DDC84?style=flat-square&logo=android&logoColor=white)](https://dofx.netlify.app)
[![Design](https://img.shields.io/badge/Design-Material_3-7B1FA2?style=flat-square&logo=material-design&logoColor=white)](https://m3.material.io)
[![License](https://img.shields.io/badge/License-MIT-amber?style=flat-square)](#)

<br/>

<!-- EMBEDDED PREVIEW IMAGE -->
<p align="center">
  <img src="https://i.ibb.co/rRhDbYhR/vlcsnap-2026-10-07-02h36m49s497.png" alt="vlcsnap-2026-10-07-02h36m49s497" border="0" width="100%" style="max-width: 440px; border-radius: 20px; box-shadow: 0 10px 30px rgba(0,0,0,0.35);" />
</p>

---

</div>

## 📲 Direct APK Download

Click below to download the latest compiled Android package directly to your device:

<div align="center">

[![Download DOFX APK](https://img.shields.io/badge/⚡_DOWNLOAD_DOFX.APK-v1.0.0_(Direct_Download)-success?style=for-the-badge&logo=android&logoColor=white)](https://github.com/your-username/dofx/releases/latest/download/DOFX.apk)

*Alternative web app mirror: [dofx.netlify.app](https://dofx.netlify.app)*

</div>

```bash
# How to install the APK on Android:
1. Tap the "DOWNLOAD DOFX.APK" button above.
2. Open the downloaded DOFX.apk file on your phone.
3. If prompted, select "Allow from this source" in Chrome/Files.
4. Tap "Install" and launch DOFX!

📑 Quick Navigation
✨ Key Features
📱 Mobile App Tour
🔬 The Optical Physics Engine
⚙️ Technical Highlights
🎨 Theming & Interface
📄 License

✨ Key Features
┌────────────────────────────────────────────────────────────────────────┐
│  ✦ 2D Ray Cone Visualization        ✦ Live CameraX Hardware Feed       │
│  ✦ Real-Time Bokeh Synthesis        ✦ Circle of Confusion (CoC) Math   │
│  ✦ Hyperfocal Range Locking         ✦ Full History & Instant Undo      │
│  ✦ Metric & Imperial Dual Engine    ✦ Material 3 Warm Bronze Theming   │
└────────────────────────────────────────────────────────────────────────┘
📐 Interactive 2D Ray Cone Ray-Tracing: Real-time interactive silhouette showing subject distance, camera position, focus plane cut, and near/far focus falloff boundaries[cite: 1, 4].✨ Live CameraX & Synthetic Bokeh Simulation: Switch seamlessly between real optical hardware feeds and procedural bokeh rendering with customizable point-source shapes (City Lights, Sunset, Garden)[cite: 3, 7].🎯 Precision Depth of Field Computing: Instant calculation of Near Limit, Far Limit, Total Depth of Field, and Hyperfocal Distance with zero latency[cite: 1, 4].🔄 10-Step History & Undo Stack: Never lose a preset. Inspect past changes with active state rollbacks (Sensor changed, Aperture adjusted, etc.)[cite: 2].🌗 Dynamic High-Contrast & Dark Mode: Handcrafted for extreme lighting conditions—from direct sunlight shoots to darkroom and night cinematography[cite: 1, 4, 6].📏 Dual Measurement Units: Instant 1-tap toggle between Imperial (ft/in) and Metric (mm/cm/m)[cite: 1, 4].📱 Mobile App Tour📐 2D Ray Cone View🌃 Bokeh & CameraX📜 History & Rollback📖 Optical ScienceRay-cone visualizer, subject distance & plane calculation[cite: 1, 4]Live aperture simulation (f/1.4 to f/22), light characteristics[cite: 3, 7]Full adjustment timeline with 1-click state restore[cite: 2]Onboard optical physics and CoC formulas[cite: 5]`Near 5' 5.1"Far 6' 2.8"`[cite: 1]`City LightsSunset

🔬 The Optical Physics EngineDOFX implements standard optical physics without rounding shortcuts, calibrated against digital 35mm full-frame and crop sensor benchmarks[cite: 5]:1. 🎯 Hyperfocal Distance ($H$)$$\mathbf{H = f + \frac{f^2}{N \times c}}$$$f$ = Focal Length (in millimeters)[cite: 5]$N$ = Lens Aperture ($f$-number)[cite: 5]$c$ = Circle of Confusion diameter ($\approx \frac{\text{Sensor Diagonal}}{1500} = 0.029\text{mm}$ for 35mm full frame)[cite: 5]Example benchmark: $50\text{mm}$ at $f/3.5$ on a Full Frame sensor yields $H = 80\text{' } 11.7\text{"}$[cite: 5].2. 📏 Depth of Field Limits ($D_{near}$ & $D_{far}$)$$\mathbf{D_{near} = \frac{H \times s}{H + (s - f)}}$$$$\mathbf{D_{far} = \frac{H \times s}{H - (s - f)}}$$$s$ = Subject Distance[cite: 5]When $s \ge H$, $D_{far}$ extends infinitely ($\infty$)[cite: 5].⚙️ Technical HighlightsArchitecture: Modern Android MVVM with Clean Architecture principles.UI Framework: Material 3 (Material You) with custom Canvas vectors for ray paths.Camera Pipeline: AndroidX CameraX API providing zero-lag optical sensor control.Calculations: High-precision floating-point optical computation engine running off the main thread.Distribution: Static PWA & Progressive Android web package hosted on Netlify CDN.🎨 Theming & InterfaceDOFX follows an intentional, warm-editorial color system inspired by vintage optical equipment and film cameras:☕ Espresso Surface : #1E1916 (Dark Theme Base)
🌾 Cream Canvas     : #FBF8F5 (Light Theme Base)
🪵 Warm Amber Brand : #8B5A2B (Primary Accents & Ray Highlights)
🌿 Active Status    : #4CAF50 (Sensor Active Indicators)
Built for Cinematographers, Directors of Photography, and Optical Enthusiasts.© DOFX Project • Built with precision optics • Released under the MIT License
