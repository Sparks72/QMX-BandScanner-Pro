# QMX BandScanner Pro

A sophisticated web-based band scanner for QMX transceivers using the Web Serial API. Features real-time spectrum analysis, waterfall displays, audio monitoring, and an interactive tuning dial.


**🚀 [Live Demo](https://sparks72.github.io/QMX-BandScanner-Pro/) - Try it now in your browser!**

A sophisticated web-based band scanner for QMX transceivers...
## Features

### Radio Control
- **Web Serial API Integration** - Direct browser-based control of QMX transceivers (115200 baud)
- **CAT Command Support** - Full Kenwood CAT protocol implementation
- **Multi-Band Support** - 160m through 2m bands (11 bands total)
- **Interactive VFO** - Large LCD-style frequency display with direct spectrum clicking

### Scanning Capabilities
- **Configurable Parameters**
  - Adjustable scan step size (100 Hz to 10 kHz)
  - Variable dwell time (1-50 ms per frequency)
  - Signal threshold adjustment (-130 to -40 dBm)
- **Real-Time Visualization**
  - Live spectrum display with signal strength indicators
  - Scrolling waterfall display
  - Signal peak tracking with visual markers
- **Pause on Signal** - Automatic pause when signals exceed threshold

### User Interface
- **Tuning Dial** - Realistic rotary knob for precise frequency adjustment
- **Audio Monitor** - Live audio visualization with volume control
- **Mode Selection** - USB/LSB/CW mode switching
- **Interactive Controls** - Hover tooltips and responsive buttons
- **Dark Theme** - Eye-friendly dark interface with LCD-style displays

### Performance
- **High-Speed Scanning** - Optimized for rapid frequency sweeps
- **60 FPS Rendering** - Smooth animation loop independent of scan speed
- **Efficient Data Handling** - Minimal DOM updates during scanning

## Requirements

- Modern web browser with Web Serial API support (Chrome 89+, Edge 89+, Opera 76+)
- QMX transceiver with CAT control capability
- USB serial connection to radio

## Installation

1. Clone or download this repository
2. No build process required - this is a standalone HTML file
3. Open `QMX_BandScanner_Enhanced_Layout__8_.html` in a supported browser

## Usage

### Initial Setup
1. **Connect Radio** - Click "Connect Radio" and select your QMX's serial port
2. **Select Band** - Choose your desired band from the dropdown menu
3. **Adjust Parameters**
   - Set scan step size (recommend 500 Hz for general use)
   - Set dwell time (5-10 ms for balance between speed and accuracy)
   - Set signal threshold (-80 to -90 dBm for typical HF conditions)

### Scanning
1. Click **"Start Scan"** to begin scanning the selected band
2. Watch the spectrum display for signals
3. Click anywhere on the spectrum to tune to that frequency
4. Scanner will pause automatically when strong signals are detected
5. Click **"Stop"** to end scanning

### Audio Monitoring
1. Click **"Enable Audio"** to activate audio monitoring
2. Adjust volume with the slider
3. Audio waveform displays in real-time

### Manual Tuning
1. Click **"Show Tuning Dial"** to reveal the rotary knob
2. Click and drag the knob to tune frequency
3. Frequency changes in real-time

## Configuration

Edit the `CONFIG` object in the code to adjust default settings:

```javascript
const CONFIG = {
    baudRate: 115200,        // Serial port baud rate
    defaultBand: '40m',      // Starting band
    defaultStep: 500,        // Scan step in Hz
    defaultDwell: 5,         // Dwell time in ms
    defaultThreshold: -80,   // Signal threshold in dBm
    maxRetries: 2,           // Command retry attempts
    commandTimeout: 100      // Command timeout in ms
};
```

## Band Coverage

- 160m: 1.8 - 2.0 MHz
- 80m: 3.5 - 4.0 MHz
- 60m: 5.3 - 5.4 MHz
- 40m: 7.0 - 7.3 MHz
- 30m: 10.1 - 10.15 MHz
- 20m: 14.0 - 14.35 MHz
- 17m: 18.068 - 18.168 MHz
- 15m: 21.0 - 21.45 MHz
- 12m: 24.89 - 24.99 MHz
- 10m: 28.0 - 29.7 MHz
- 6m: 50.0 - 54.0 MHz

## Technical Details

### Serial Communication
- Uses Web Serial API for direct browser-to-radio communication
- Command queuing system prevents conflicts
- Automatic retry on failures
- Supports both query and set commands

### Signal Processing
- Real-time S-meter reading via CAT SM command
- dBm conversion from S-meter values
- Rolling average for signal smoothing
- Peak detection with visual indicators

### Rendering Pipeline
- Independent 60 FPS animation loop
- Canvas-based spectrum and waterfall
- Throttled DOM updates during scanning
- Hardware-accelerated graphics

## Keyboard Shortcuts

- **Space** - Start/Stop scanning (when connected)
- **Arrow Keys** - Adjust frequency when tuning dial is visible
- **+/-** - Adjust scan step size
- **[/]** - Adjust dwell time

## Troubleshooting

**Connection Issues**
- Ensure QMX is powered on and CAT control is enabled
- Check USB cable connection
- Try closing other applications using the serial port
- Verify browser supports Web Serial API

**Slow Scanning**
- Reduce dwell time (try 1-3 ms)
- Increase step size
- Check serial baud rate matches radio settings (115200)

**No Signal Detection**
- Lower signal threshold
- Verify radio is receiving (check with known signal)
- Check antenna connection
- Ensure correct band is selected

**Audio Not Working**
- Grant microphone permissions in browser
- Check system audio input device selection
- Verify audio input is connected to radio output

## Browser Compatibility

- ✅ Chrome/Chromium 89+
- ✅ Microsoft Edge 89+
- ✅ Opera 76+
- ❌ Firefox (Web Serial API not supported)
- ❌ Safari (Web Serial API not supported)

## Author

Paul Harrison (DJ0CU)

## Contributing

Contributions welcome! This project helps the amateur radio community with modern web-based tools for radio control.

## Support

If you find this tool useful, coffee donations are appreciated and help support further development of amateur radio software tools.

## Version History

See [CHANGELOG.md](CHANGELOG.md) for version history.

## License

This project is open source. See LICENSE file for details.

---

**73 de DJ0CU**
