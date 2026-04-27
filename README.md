# Animated Gradient Shiny Loader

Animated Gradient Shiny Loader built using HTML, CSS and JavaScript.

![Demo screenshot](Screenshot%202024-07-02%20182433.png)

A simple, elegant circular gradient loader with a shiny/rainbow gradient and a percentage counter. Click the center to start the loader animation — it rotates the colorful ring and updates the percentage until it reaches 100%.

## Demo
Open `index.html` in your browser and click the center of the circle to start the loader.

## Files
- `index.html` — the markup and small JavaScript that controls the percentage counter and click behavior.
- `style.css` — styles and keyframe animations for the rotating gradient ring and text gradient.

## Features
- Pure HTML/CSS/JS (no frameworks)
- Animated gradient ring with smooth rotation
- Gradient-filled percentage text with clip effect
- Easy to customize colors, size and speed

## Usage
1. Clone or download this repository.
2. Open `index.html` in your browser.
3. Click the center (the percentage text) to start the loader.

## Customization
- Change the color stops: edit the `background: linear-gradient(...)` declaration for `.outer` (lines in `style.css`) to adjust the ring colors.
- Change the ring size: adjust `.outer` width/height and `.inner` width/height/line-height in `style.css`.
- Change the rotation speed: modify the `animation` duration on `.outer.active-loader` and `.outer.active-loader-2` (e.g., `2s` or `3s`).
- Change the percentage speed: open `index.html` and modify the `setInterval` delay (currently `200`) in the inline script.

## Small JavaScript fix (recommended)
In the current `index.html` the interval is started with `let loading = setInterval(...)` but the code calls `clearInterval()` without the interval id when the count reaches 100. To stop the interval correctly, change the clear call to:

```js
if (count == 100) {
  outer.classList.remove("active-loader");
  outer.classList.add("active-loader-2");
  clearInterval(loading); // <- pass the interval id here
}
```

Applying this change prevents the interval from continuing after reaching 100%.

## Contributing
Contributions, bug reports and improvements are welcome. Feel free to open a pull request or issue.

## Credits
Original small demo created by Disandu Perera.

