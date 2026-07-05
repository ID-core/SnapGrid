# SnapGrid

Gesture-driven photobooth puzzle game that runs entirely in the browser. It uses a webcam, hand tracking, and a 3x3 photo puzzle to turn a simple capture into a short interactive challenge. No backend, no framework, and no install step.

## Core idea

The flow is intentionally simple: frame the shot with your hands, pinch to capture, solve the puzzle with finger gestures, and finish the round by saving the result as a polaroid-style strip. Everything stays inside one browser tab.

## Quick start

1. Clone the repository.
```bash
git clone https://github.com/ID-core/SnapGrid.git
cd SnapGrid
```

2. Open the folder in VS Code and start a local server.
Install the Live Server extension if needed, then click Go Live from the editor status bar.

3. Open the local address in Chrome or Edge.
```text
http://localhost:5500
```
Camera permission is required. The first load also downloads the MediaPipe hand model, which is about 10 MB, so internet is needed once before it can run offline.

## How it works

SnapGrid is built around hand gestures instead of mouse input. Raise both hands to let the app track your fingers, use a two-hand pinch to define the capture frame and start the 3 second countdown, and use a one-hand pinch to pick up and move puzzle pieces. When a piece is near the right spot, it snaps into place automatically. Hold a closed fist to save the solved puzzle or reset the board.

The full session looks like this:

1. Raise both hands so the space between your index fingers becomes the camera frame.
2. Pinch with both hands to trigger the 3 second countdown, flash, and black-and-white capture.
3. Rebuild the 3x3 puzzle by dragging pieces with finger pinches.
4. Make a fist when finished so the puzzle shatters and saves as a color polaroid with its date and photo number.
5. Finish 3 puzzles to reveal the full photo strip and download it.

## What the app includes

- Black-and-white puzzles while solving, followed by a color reveal when a puzzle is saved.
- A camera flash effect right at capture time.
- Polaroid borders with the date and photo number stamped on each print.
- Countdown beeps, piece snap sounds, a shatter burst, and a completion chime generated with the Web Audio API.
- Automatic video recording for each solved puzzle, downloadable as WebM.
- A popup photo strip that appears after all 3 puzzles are completed.
- Pure browser execution with no React, no npm, and no build step.

## Technology notes

- MediaPipe Tasks Vision `v0.10.14` for hand landmark detection.
- Canvas 2D for rendering, visual effects, puzzle layout, and shatter behavior.
- Web Audio API for all sound effects.
- MediaRecorder API for video capture.
- Vanilla JavaScript modules for the application logic.

## Browser support

| Browser | Status |
|---|---|
| Chrome / Edge | Best experience |
| Firefox | Works |
| Safari | Limited |
| Mobile | Not recommended |

