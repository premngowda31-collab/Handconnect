# Handconnect - Advanced Hand Tracking AR Experience

A cutting-edge augmented reality application that uses real-time hand tracking to create immersive visual and audio experiences. Handconnect combines MediaPipe's advanced hand detection with Web Audio API and dynamic visual effects to deliver an interactive neon-themed AR experience.

## ✨ Features

### Hand Tracking
- **Real-time hand detection** using MediaPipe Hands (supports up to 2 hands)
- **21-point hand skeleton** tracking with fingertip detection
- **Smooth hand tracking** with high confidence detection

### Visual Effects
- **Multiple color themes**: Rainbow, Cyberpunk, Lava, Ocean, Galaxy
- **Neon glow effects** with shadow blurs and screen blending modes
- **Particle system** with gravity physics
- **Shockwave/ripple effects** triggered by pinch gestures
- **Matrix rain background** that responds to hand movement speed
- **Mandala patterns** when both hands are detected
- **Lightning arcs** between fingertips of both hands
- **Gradient connecting lines** between corresponding fingertips

### Audio Integration
- **Continuous hum** that modulates based on hand proximity
- **Pitch modulation** - closer hands = higher pitch
- **Volume control** - distance-based amplitude adjustment
- **Zap sound effects** triggered by pinch gestures

### Gesture Recognition
- **Pinch detection** - thumb and index finger proximity
- **Hand spread detection** - measurements of open hand vs. fist
- **Gesture status display** in real-time HUD

### Performance Monitoring
- **FPS counter** for real-time performance tracking
- **Hand detection counter** showing active hands
- **Spread percentage** indicator
- **Gesture name display**

## 🚀 Getting Started

### Prerequisites
- Modern web browser with WebGL support (Chrome, Firefox, Edge, Safari)
- Working webcam
- The following will be requested:
  - Camera permissions (for hand tracking)
  - Microphone permissions (for audio context initialization)

### Installation

1. Clone the repository:
```bash
git clone https://github.com/premngowda31-collab/Handconnect.git
cd Handconnect
```

2. Open `index.html` in a modern web browser or serve it locally:
```bash
# Using Python 3
python -m http.server 8000

# Using Node.js http-server
npx http-server
```

3. Click "Enter Experience" to grant camera permissions and start

## 🎮 How to Use

1. **Grant Permissions**: Allow camera access when prompted
2. **Start Experience**: Click the "Enter Experience" button
3. **Interact**:
   - Move your hands to generate particles and trails
   - Pinch (thumb + index finger) to create shockwaves
   - Look at the HUD (top-left) for real-time stats
   - Switch themes using buttons at the bottom

### Controls
- **Mouse/Touch**: Theme buttons at the bottom to switch between visual themes
- **Hand Gestures**:
  - **Pinch**: Thumb and index finger together triggers effects
  - **Open Hand**: Spread your fingers for maximum spread reading
  - **Two-Hand Interactions**: Bring both hands close for lightning effects

## 🎨 Visual Themes

- **Rainbow**: Full spectrum color cycling
- **Cyberpunk**: High contrast red and cyan neon
- **Lava**: Hot orange and red with pulsing effects
- **Ocean**: Cool blues and teals
- **Galaxy**: Purple and indigo cosmic vibes

## 🛠️ Technologies Used

### Frontend
- **HTML5 Canvas** - Rendering and animation
- **MediaPipe Hands** - Hand detection and tracking
- **Web Audio API** - Real-time audio synthesis
- **CSS3 Glassmorphism** - Modern UI effects
- **Vanilla JavaScript** - Core application logic

### Libraries & CDNs
- `@mediapipe/hands` - Hand detection model
- `@mediapipe/camera_utils` - Camera handling
- `@mediapipe/drawing_utils` - Hand visualization utilities
- `@mediapipe/control_utils` - Control interface utilities

## 📊 Performance

- **Detection Confidence**: 70% minimum for optimal tracking
- **Max Hands**: 2 simultaneous hands
- **Model Complexity**: 1 (balanced for performance)
- **Recommended Resolution**: 1280x720
- **Target FPS**: 30+ for smooth experience

## 🎯 Physics & Effects

### Particle System
- Spawns particles at fingertips during hand movement
- Physics simulation with gravity
- Fade-out effect over time
- Color-coded by fingertip position

### Ripple/Shockwave System
- Triggered by pinch gestures
- Easing out radius expansion
- Customizable max radius
- Dynamic color from current theme

### Background Effects
- **Matrix Rain**: Responsive to hand velocity
- **Destination-out compositing**: Creates trailing motion blur
- **Dynamic speed multiplier**: Based on hand movement speed

## 🔧 Configuration

Edit the `const` variables in the script section for customization:

```javascript
// Hand detection confidence thresholds
minDetectionConfidence: 0.7    // Lower = more detection, higher = more accuracy
minTrackingConfidence: 0.7     // Lower = smoother tracking

// Pinch detection threshold
const isPinching = dist < 0.05;  // Adjust for sensitivity

// Audio hum parameters
humOsc.frequency.value = 100;    // Base frequency in Hz
targetVolume = 0.15;              // Maximum volume when hands close

// Visual effects
ctx.shadowBlur = 15;              // Glow intensity
ctx.lineWidth = 4;                // Connector line thickness
```

## 🌐 Browser Compatibility

| Browser | Status | Notes |
|---------|--------|-------|
| Chrome | ✅ Fully Supported | Recommended |
| Firefox | ✅ Fully Supported | |
| Edge | ✅ Fully Supported | |
| Safari | ✅ Supported | May need explicit permissions |
| Opera | ✅ Supported | |

## 🎓 How It Works

1. **Hand Detection**: MediaPipe's ML model detects hand landmarks in real-time
2. **Gesture Analysis**: Finger distances and positions are calculated for gesture recognition
3. **Physics Simulation**: Particles, ripples, and effects are updated each frame
4. **Audio Rendering**: Hand proximity drives oscillator frequency and gain
5. **Visual Rendering**: Canvas draws effects with blending modes for neon appearance

## 📱 Tips for Best Experience

- Use good lighting for accurate hand detection
- Keep hands within the camera frame
- Ensure sufficient distance between both hands for lightning effects
- Use full-screen mode for immersive experience
- Test in a quiet environment to enjoy audio effects

## 🤝 Contributing

Contributions are welcome! Feel free to:
- Report issues
- Suggest new features
- Submit pull requests

## 📜 License

This project is available as-is for educational and personal use.

## 👨‍💻 Author

Created as an advanced AR/VR demonstration project using MediaPipe and Web APIs.

## 🔗 Resources

- [MediaPipe Hands Documentation](https://google.github.io/mediapipe/solutions/hands.html)
- [Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API)
- [Canvas API](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API)

## 📝 Changelog

### v1.0.0 (Initial Release)
- Hand tracking with MediaPipe
- Multiple visual themes
- Audio synthesis and gesture effects
- Real-time performance monitoring
- Cross-hand interactions

---

**Enjoy the experience!** 🎉 For the best results, use in a well-lit environment with good camera quality.
