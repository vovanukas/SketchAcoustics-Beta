# SketchAcoustics Beta

Professional acoustic analysis tools for SketchUp.

**⚠️ This is a closed beta** - You need a beta license key to use this extension.

---

## 🎯 Current Beta Features

- ✅ **First Reflections Calculator** - Visualize sound ray paths and reflections in 3D
- ✅ **Listener Placement** - Mark objects as listeners for targeted analysis
- ✅ **Advanced Dispersion Controls** - Configurable horizontal/vertical dispersion angles
- ✅ **Ray Filtering** - Filter rays to only those hitting listeners
- ✅ **Multiple Reflection Orders** - Calculate up to nth-order reflections
- ✅ **Room Mode Analysis** - Select walls and run a room mode simulation
- ✅ **RT60 Calculator** - Assign Materials and Run a Room Acoustics Simulation

---

## 📦 Installation

### Step 1: Get Beta Access

[**Request beta access here**](https://tally.so/r/WOrx8J) - I'll email you a license key

### Step 2: Download Extension

1. Go to [**Releases**](https://github.com/vovanukas/SketchAcoustics-Beta/releases/)
2. Download the latest `SketchAcoustics-*.rbz` file

### Step 3: Install in SketchUp

1. Open **SketchUp**
2. Go to **Extensions** → **Extension Manager**
3. Click **Install Extension**
4. Select the downloaded `.rbz` file
5. Restart SketchUp (recommended)

### Step 4: Activate License

1. In SketchUp: **Plugins** → **SketchAcoustics** → **License**
2. Enter your beta key (from email)
3. Click **Activate**

---

## 🚀 Usage Guide

### First Reflections Tool

Calculate and visualize how sound reflects in your 3D model:

1. Click the **First Reflections** button in the SketchAcoustics toolbar
2. Click on any surface to place a sound source
3. Configure settings:
   - **Rays**: Number of ray paths to calculate (default: 20)
   - **Reflections**: Reflection order 1-5 (default: 2)
   - **Dispersion**: Horizontal/vertical angles (default: 90°)
   - **Filter to Listener**: Only show rays hitting listeners
4. Click **OK** to calculate

**Visual Legend:**
NOTE: I use tags to manage reflections orders, so you will only see visualisation if you enable "Color by Tag" in the "Tags" window. Learn more about tags [here](https://help.sketchup.com/en/sketchup/controlling-visibility-tags). 
- 🔴 Red lines = Direct sound (0th order)
- 🟣 Purple-ish lines = 1st reflections
- 🔵 Blue lines = Higher-order reflections

### Listener Placement

Mark objects in your model as listeners (audience positions, microphones, etc.):

1. Right-click any object in your model
2. Select **SketchAcoustics** → **Mark as Listener**
3. The object becomes a listener marker
4. Use "Filter to Listener" mode to see only rays hitting this position

**Removing Listeners:**
- Plugins → SketchAcoustics → Delete Listeners
OR
1. Right-click an object you marked as listener
2. Select **SketchAcoustics** → **✓Listener**

### Room Mode Calculator

Analyse the acoustic resonance modes of a room using wave-based finite element simulation.

[Room Mode Calculator Usage Guide.webm](https://github.com/user-attachments/assets/42a6de9e-ffef-4600-8acd-dce1fc00c17b)

1. Click the **Room Modes** button in the SketchAcoustics toolbar
2. Select all faces that form your room boundary (walls, floor, ceiling)
3. Run analysis with configured analysis settings
4. Results appear in the dialog and a 3D pressure visualization overlays your model

### Material Assignment Tool

Assign materials to surfaces to use the absorption/diffusion coefficients for Acoustic Analysis

https://github.com/user-attachments/assets/580cd794-1732-41ea-959e-ff7a38f6d09c

1. Click on the **Manage Acoustic Materials** button in the SketchAcoustics toolbar
2. Click ... to add materials into your scene/materials palette
3. Create custom materials or select from existing ones
4. Click back (<-) and select a material to start painting faces
5. To see which faces you have already painted, you can click the overlay button to show material colours on model

### Room Acoustics Simulation

Simulate how sound travels, reflects, and decays inside a room using particle tracing across octave bands.

https://github.com/user-attachments/assets/84b2112e-0a51-4215-a022-1b534a58a1fd

1. Assign materials to all room surfaces using the Material Assignment Tool before running the simulation - absorption and diffusion coefficients are used directly in the calculation
2. Use Section Planes instead of hiding geometry to expose interior surfaces — hidden faces are excluded from the simulation
3. Click the Room Acoustics Simulator button in the SketchAcoustics toolbar
4. Click to place one or more sound sources (emitters) inside the room, then press Enter to confirm
5. Click to place one or more receivers (listeners) inside the room, then press Enter to start the simulation
6. Once complete, results appear as charts showing reverberation time (RT30), early decay time (EDT), clarity (C50/C80), and other ISO 3382 metrics per octave band
7. To visualise sound propagation, run the Sound Billiard — an animated ray visualisation showing particle paths through the room

---

## 🔧 Requirements

- **SketchUp**: 2023 or newer
- **Platforms**: Windows, macOS
- **License**: Active beta key (free during beta period)

---

## 💬 Feedback & Support

I'd love to hear from you!

- 💡 **Share feedback & request features**: [acoustics.fider.io](https://acoustics.fider.io/)
- 🐛 **Report bugs**: [acoustics.fider.io](https://acoustics.fider.io/)
- 🔑 **Request beta access**: [tally.so/r/WOrx8J](https://tally.so/r/WOrx8J)

---

## 📋 Changelog

See [**CHANGELOG.md**](CHANGELOG.md) for version history and release notes.

---

## 📜 License

Commercial license. Beta access is free during the testing period.

© 2026 Vladimiras Malyskinas

---

## 🙏 Acknowledgments

Thank you to our beta testers - acoustic consultants who are helping shape this tool!
