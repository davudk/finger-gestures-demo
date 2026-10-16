# Finger Gestures Demo

A small browser demo of multi-finger gestures on a canvas: pan with two fingers, pinch to zoom, and twist to rotate. It is a single HTML file with no dependencies.

**Live demo: https://davudk.github.io/finger-gestures-demo/**

| Input | Pan | Zoom | Rotate |
|---|---|---|---|
| Touchscreen | One or two fingers | Pinch | Two-finger twist |
| Mac trackpad | Two-finger scroll | Pinch | Twist (Safari), or ⌥ Option + scroll |
| Mouse | Drag | ⌘/Ctrl + wheel | ⌥ Option + wheel |

Press **0** or the Reset button to reset the view.

## How it works

- **Touch** uses Pointer Events. The two active fingers give a midpoint, a distance and an angle; each move pans by the change in midpoint, zooms by the ratio of distances and rotates by the change in angle, all around the point between the fingers.
- **Trackpad** gestures arrive as `wheel` events. Chrome, Firefox and Edge report a pinch as a wheel event with `ctrlKey` set.
- **Safari** also sends `gesturestart` / `gesturechange` / `gestureend` with `scale` and `rotation`, which is the only way a web page can read trackpad rotation.
- `touch-action: none` and `overscroll-behavior: none` keep the browser from scrolling, zooming or swiping back while you use the demo.

## Run

Open `index.html` in a browser, or serve the folder to try it on a phone:

```bash
python3 -m http.server 8737
```

## License

[MIT](LICENSE)
