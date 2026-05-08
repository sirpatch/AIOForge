## 🧠 Current Status (Prototype)

AIOFORGE is currently a long-term prototype under active development. Core systems are functional, but many advanced features are incomplete or experimental.

---

## ✅ Working Features

### 🎚 Audio I/O Monitoring & Control
- Real-time input/output device monitoring  
- Mute / unmute per audio session  
- Volume control per device/session  
- Live stereo visualization (R / L channel peak meters)  

### 🧾 Driver & Device Information
- Audio codec detection  
- Driver information retrieval  
- API stack identification  
- Registry path mapping  
- Kernel Streaming (KS) device enumeration  

---

## ⚠️ Partially Working Features

### 🔌 Jack Retasking (Experimental)
- Basic audio jack detection works (inconsistent accuracy)
- Mode switching (e.g. Line-In → Headphones) is not reliable
- Hardware-dependent behavior (varies heavily by driver/codec)

---

## ❌ Not Yet Working

The following systems are currently non-functional or in early implementation:

- Set default audio device  
- Application audio detection / per-app tracking  
- Speaker configuration changes  
- Sample rate modification  
- Bit depth control  

---

## 🎯 Current Development Focus

The current priority of AIOFORGE is the **Audio Routing Engine**.

This includes:
- Reliable application audio session detection
- Stable per-process audio endpoint assignment
- Persistent routing across device and session changes

Once routing is stable, DSP and advanced processing features will be expanded.

---

## 🚧 Planned Features

### 🎛 DSP Engine
- Per-application EQ  
- Per-output device EQ  
- Optional per-input EQ  
- Real-time signal processing pipeline  

### 🎧 Application Audio Management
- Per-app routing to devices  
- Per-app volume control  
- Playback control integration (play / pause / next / previous where supported)  

### 🔄 System Features
- Automatic update checking on startup  
- Version validation and update notifications  
- Future support for modular feature expansion  

---

## ⚠️ Important Note

AIOFORGE is a **prototype system**, not a finished product.

Features may:
- behave inconsistently across different hardware
- depend heavily on audio drivers and Windows configuration
- change significantly between versions

---

## 🏛 Tested Audio Chips
- Realtek ALC897
