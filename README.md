# Room Acoustics & Reverb Designer

An interactive single-file HTML application for simulating room acoustics and designing algorithmic reverb using the Schroeder architecture.

## Features

### Room Simulator (2D Ray Tracing)
- Top-down view of a rectangular room with adjustable width and depth (2-50 metres)
- Drag-and-drop sound source (S) and listener (L) placement
- Configurable ray count (12-360) with adjustable max reflections (1-20)
- Per-wall absorption coefficients (0.0 - 1.0)
- Ray animation at speed of sound (343 m/s)
- Early reflection detection at listener position

### Impulse Response Display
- Computed IR from ray arrival times and attenuations
- Energy Decay Curve (Schroeder integral)
- RT60 and EDT markers on decay curve
- Export IR as WAV file
- Play IR as audio click

### Algorithmic Reverb Designer (Schroeder Architecture)
- 4 parallel comb filters with adjustable delay time (ms) and feedback gain
- 2 series allpass filters with adjustable delay time (ms) and gain coefficient
- Real-time audio processing via Web Audio API
- Interactive SVG signal flow diagram showing the complete Schroeder reverb topology

### Reverb Presets
- **Small Room** - tight early reflections, short tail
- **Large Hall** - spacious, long decay
- **Cathedral** - very long reverb with low absorption
- **Plate** - dense, bright artificial reverb character
- **Spring** - elongated geometry, characteristic spring sound
- **Chamber** - medium-sized studio reverb

### Test Signals
- Impulse (click)
- White noise burst (exponentially decaying)
- Sine sweep (20 Hz - 20 kHz logarithmic)
- Finger snap (synthesised transient)
- Microphone input (live processing)

### Acoustic Metrics
- **RT60** - Reverberation time (60 dB decay)
- **EDT** - Early Decay Time (first 10 dB, extrapolated)
- **C80** - Clarity index (early vs late energy, 80 ms boundary)
- **D50** - Definition (early energy ratio, 50 ms boundary)

### A/B Comparison
- Store two different configurations (presets, room parameters, reverb settings)
- Switch between A and B slots while audio is playing

## Usage

1. Open `index.html` in a modern browser (Chrome, Firefox, Edge)
2. Click **INIT AUDIO** to start the Web Audio context
3. Select a preset from the left panel or adjust room/reverb parameters on the right
4. Click/drag the source (S) and listener (L) in the room view
5. Select a test signal and click **PLAY** to hear the reverb
6. Switch tabs to view the impulse response, energy decay curve, or signal flow diagram
7. Click **ANIMATE RAYS** to see sound propagation in real time

## Technical Details

- Single-file HTML (~1900 lines), no external dependencies beyond Google Fonts
- Web Audio API: DelayNode + GainNode for comb and allpass filter implementation
- HTML5 Canvas for room visualisation and IR/EDC plots
- Inline SVG for signal flow diagram
- DM Sans + JetBrains Mono typography
- Dark professional audio aesthetic matching the Physical Modelling Synth suite

## Browser Requirements

- Modern browser with Web Audio API support
- Microphone access required for live input (optional)
