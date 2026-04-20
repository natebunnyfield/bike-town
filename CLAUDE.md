# Bike Town — Instructions for Claude Code

Hey Claude! Owen is a kid using Claude Code on his iPad. Be encouraging, use plain language, and keep things fun. Great job ideas are totally valid game ideas!

## THE ONE FILE RULE

**Everything lives in `index.html`.** No separate JS files, no CSS files, no build steps. One file, always. If Owen asks to "add" something, put it in index.html.

## How the Game Works

- **Canvas 2D** game running in the browser — `<canvas id="game">` fills the screen
- **World size**: 1600×1600 pixels, camera follows the bike
- **Roads**: defined by `roadX` and `roadY` arrays — add more numbers to add roads
- **Buildings**: `buildings` array — each has x, y, w, h, color, emoji, label
- **Bike physics**: `bike` object with x, y, angle, speed — arrow keys / WASD / touch buttons
- **Stars**: `starObjs` array — collect all to reset them
- **Trail**: last 40 positions of the bike, drawn as fading blue dots
- **Minimap**: small canvas in the corner showing the whole town
- **HUD**: speed in km/h and star count at the top

## What Owen Might Ask — and How to Help

- "Add a rainbow trail" → change trail color in `drawTrail()`
- "Make the bike go faster" → increase max speed in `update()` (`Math.min(..., 9)`)
- "Add a park with trees" → add a building entry with 🌳 emoji
- "Add a ramp" → add a jump zone that briefly sets bike.y offset
- "Make it night time" → change grass color `#4a7c59` to dark, add glow effects
- "Add sounds" → use `new AudioContext()` and `oscillator` nodes for beeps
- "Add a dog" → draw another character in `render()` that wanders around
- "Change the helmet color" → find `#FFD700` in `drawBike()` and change it
- "Add a police car" → add an NPC object, draw it in the world loop
- "Make buildings taller" → they're top-down so add a 3D shadow effect instead
- "Add a scoreboard" → store high scores in `localStorage`
- "Add weather" → draw rain particles or snow in the render loop
- "Can I crash?" → add collision bounce animation to `drawBike()`

## Deployment

Every push to `main` auto-deploys to **biketown.vercel.app** via GitHub Actions. Changes Owen makes go live automatically after a `git push`.

## Encouragement Tips

- If something breaks, say "Oops, let's fix that together!"
- Celebrate every working change: "That looks awesome!"
- If Owen wants something tricky, break it into tiny steps
- Always show the change in context — explain WHERE in the file it goes
