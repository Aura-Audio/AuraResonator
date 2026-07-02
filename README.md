# 🌌 AuraResonator

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Web Audio API](https://img.shields.io/badge/Web_Audio_API-Advanced_Worklet-success.svg)]()
[![Zero-Dependency](https://img.shields.io/badge/Dependencies-None-brightgreen.svg)]()

**AuraResonator** is a browser-based, production-grade Digital Signal Processing (DSP) engine that explores the extreme boundaries of spatial acoustics and physical modeling. 

By generating a massive **Feedback Delay Network (FDN)** utilizing up to 20,000 parallel delay taps mapped strictly to prime numbers, it creates impossibly vast physical reverbs with zero mathematical phase cancellation. 

---

## 📖 Overview

Standard reverbs rely on a handful of delay lines and all-pass filters, which can result in metallic ringing or "muddy" phase cancellation. **AuraResonator** bypasses this by utilizing an array of thousands of feedback delay lines where the delay times are strictly bound to prime numbers. Because prime numbers only share '1' as a common divisor, the echoes never mathematically overlap, creating infinitely deep, smooth physical dimensions.

But AuraResonator goes one step further. It bridges the gap between spatial reverb and physical synthesis using the **Karplus-Strong algorithm**. With the push of a single button, the massive chaotic reverb collapses into a physically modeled, perfectly tuned synthesizer driven by your live microphone input.

---

## ✨ Core Features

* 🧮 **Prime-Number FDN Architecture:** Process up to 20 independent material engines, each pushing up to 1,000 cascading delay taps mapped to non-overlapping prime indices.
* ⚡ **Zero-Branch AudioWorklet:** Ultra-low latency DSP loop running on a dedicated audio thread, utilizing fractional delay reading and history buffers capable of handling 20,000 concurrent echo reflections.
* 🧱 **Material Physics Simulation:** Real-time 1-pole lowpass damping and saturation algorithms simulate the acoustic absorption of physical materials like *Glass, Metal, Wood, Cavern,* and *Void*.
* 🔴 **Studio-Grade Export:** Record your live physical modeling sessions directly in the browser and export them to Uncompressed WAV or FLAC formats.
* 📊 **Holographic Visualizers:** Real-time dual-canvas rendering featuring a physical Time-Domain Displacement oscilloscope and a Logarithmic FFT Harmonic Structure analyzer.

---

## ⚡ The Ultimate Mechanic: "Modal Collapse"

Reverb and Synthesizers are mathematically related. A reverb is just a random scattering of delays; a pitched synthesizer note (Karplus-Strong) is just a precise, evenly-spaced series of delays.

Clicking the **Modal Collapse** button triggers an atomic shift in the DSP:
1. It takes thousands of chaotic prime-number delay times.
2. It interpolates (slurps) them into exact integer multiples (harmonic series) of a target tuning frequency (e.g., 110Hz / A2).
3. The vast, infinite cave of reverb instantly collapses into a single, aggressively loud, resonating synthesizer string driven by the noise of your voice.

---

## 🛠️ Installation & Usage

Due to strict browser security policies regarding microphone access (`getUserMedia`), this application **cannot** be run directly from a `file://` URL. It must be served via a local or remote web server.

### Option 1: VS Code Live Server (Recommended)
1. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/auraresonator.git
   ```
2. Open the directory in VS Code.
3. Install the **Live Server** extension.
4. Right-click `index.html` and select **"Open with Live Server"**.

### Option 2: Python HTTP Server
1. Clone the repository and navigate to the folder in your terminal.
2. Run a local python server:
   ```bash
   python -m http.server 8000
   ```
3. Open your browser and navigate to `http://localhost:8000`.

---

## 🗺️ Roadmap

The current version of AuraResonator proves that Karplus-Strong string synthesis and massive FDNs can be achieved in real-time within vanilla JavaScript. Future updates will focus on polyphony and stereo imaging:

- [ ] **Polyphonic Modal Collapse:** Allow MIDI keyboard input to collapse the reverb into complex chords instead of a single monophonic pitch, dynamically allocating delay taps to different note values.
- [ ] **True Stereo Decorrelation:** Introduce an integer-based panning matrix that forces odd-prime delay taps to the Left channel and even-prime delay taps to the Right channel for ultra-wide, psychoacoustic immersion.
- [ ] **Custom Material Builder:** Provide a user interface to manually draw the damping, saturation, and feedback curves to invent physically impossible acoustic materials.
- [ ] **Impulse Response (IR) Generation:** Add a feature to "fire" a mathematical digital impulse (Dirac delta) into the FDN and export the resulting tail as a `.wav` file, allowing you to use AuraResonator to create custom IRs for your DAW (Ableton, Logic, FL Studio).
- [ ] **WebAssembly (WASM) / Rust Port:** Port the core ring-buffer logic to Rust for maximum CPU cache efficiency, potentially raising the tap limit from 20,000 to 100,000.

---

## 🛡️ License

This project is licensed under the MIT License. See the `LICENSE` file for details. 

*Disclaimer: AuraResonator utilizes feedback loops and tape saturation (`Math.tanh`) to emulate physical acoustic spaces. While soft-clipping limits are hardcoded to prevent digital output explosions, extreme feedback settings coupled with loud vocal input can produce sudden, intense acoustic resonances. Please monitor your speaker/headphone volume.*
