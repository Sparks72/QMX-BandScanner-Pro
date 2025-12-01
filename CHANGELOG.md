# Changelog

All notable changes to QMX BandScanner Pro will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.0.0] - 2024-12-01

### Initial Release

#### Added
- **Core Scanning Features**
  - Web Serial API integration for direct browser-to-QMX communication
  - High-speed band scanning with configurable parameters
  - Real-time spectrum display with 60 FPS rendering
  - Scrolling waterfall display for signal visualization
  - Automatic pause-on-signal detection
  
- **User Interface**
  - Large LCD-style VFO frequency display
  - Interactive tuning dial with realistic rotary knob
  - Hover tooltips for all controls
  - Dark theme optimized for readability
  - Responsive canvas-based visualizations
  
- **Radio Control**
  - Full CAT command support (Kenwood protocol)
  - USB/LSB/CW mode selection
  - 11 amateur radio bands (160m through 2m)
  - Direct frequency tuning via spectrum clicking
  - S-meter reading with dBm conversion
  
- **Audio Features**
  - Live audio monitoring with waveform display
  - Volume control with real-time adjustment
  - Web Audio API integration
  
- **Performance Optimizations**
  - Independent animation loop (60 FPS) decoupled from scan speed
  - Efficient command queuing system
  - Minimal DOM updates during scanning
  - Hardware-accelerated canvas rendering
  - Increased baud rate to 115200 for faster scanning
  
- **Configuration Options**
  - Adjustable scan step size (100 Hz - 10 kHz)
  - Variable dwell time (1-50 ms)
  - Signal threshold control (-130 to -40 dBm)
  - Configurable retry and timeout parameters

### Technical Details
- Standalone HTML file (no build process required)
- Compatible with Chrome 89+, Edge 89+, Opera 76+
- Requires Web Serial API support
- Optimized for QMX transceivers

---

## Development Notes

### Performance Improvements Over Previous Versions
- Upgraded from 9600 to 115200 baud for 12x faster communication
- Implemented decoupled render loop for smooth 60 FPS display
- Reduced command overhead with efficient queuing
- Added visual feedback during high-speed scanning

### Known Limitations
- Web Serial API not supported in Firefox or Safari
- Requires USB connection to radio (no network/Bluetooth support)
- Audio monitoring requires system microphone permissions

### Future Enhancements (Planned)
- Memory channel storage and recall
- QSO logging integration
- Signal recording and playback
- Multi-band comparison view
- Export scan data to CSV
- Preset scan configurations
- Band activity heatmaps

---

**Author:** Paul Mitchell (VK2AAQ)  
**License:** See LICENSE file  
**Repository:** [Add your repository URL here]
