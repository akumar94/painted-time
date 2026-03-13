# painted-time

**What did a painting sound like to be around when it was made?**

Painted Time is a spatial audio experience built inside AI-generated 3D worlds from historical paintings. Where [Painted Worlds](https://github.com/akumar94/painted-worlds) lets you inhabit a painting spatially, Painted Time asks a different question: what was the *temporal* experience of standing in that place, in that moment?

The first painting is Canaletto's *Entrance to the Grand Canal, Venice* (c. 1730). You walk through it. The canal laps below you. A gondolier calls from your left. Church bells ring from the Salute dome. The Marangona bell, the great bell of St. Mark's campanile, tolls from deep in the distance. Every sound is historically grounded and spatially positioned in 3D space relative to what Canaletto actually painted.

---

## Demo

https://github.com/akumar94/painted-time/releases/download/v1.1/painted-time-demo-final.mp4

---

## How It Works

Painted Time uses [World Labs Marble API](https://worldlabs.ai) to generate a Gaussian splat from a painting, then renders it in WebGL via [SparkJS](https://sparkjs.dev) and Three.js. Spatial audio is handled entirely with the Web Audio API with no libraries, using `PannerNode` with `HRTF` panning to position each sound source in 3D space relative to the camera.

As you move through the scene, the audio mix changes. Walk toward the canal and the water gets louder. Turn left and the gondolier's call shifts into your left ear. Walk toward the open lagoon and the seagulls pull forward. The soundscape is not ambient. It is architectural.

---

## Stack

- **Three.js**: WebGL rendering and scene graph
- **SparkJS**: Gaussian splat rendering (`.spz` format)
- **World Labs Marble API**: 3D world generation from paintings
- **Web Audio API**: positional audio with HRTF panning, no libraries
- **Vanilla HTML/JS**: no framework, served with `npx serve`

---

## Audio Sources: Venice, 1730

Each source is positioned in 3D space corresponding to its location in the painting:

| Sound | Position | Source |
|---|---|---|
| Canal water | Foreground, below | Freesound (recorded at Venice pier) |
| Gondolier calls (x2) | Left and right, mid-distance | ElevenLabs |
| Ship rigging | Far left, trading vessels | Freesound |
| Church bells | High left, Santa Maria della Salute | Freesound (recorded in Venice, 2008) |
| Marangona bell | Very high, deep background, St. Mark's | Freesound |
| Seagulls | Above, open lagoon | Freesound |
| Lagoon wind | Horizon | Freesound |
| Crowd murmur | Right, the palazzos | Freesound (recorded in Venice) |

---

## Running Locally

```bash
git clone https://github.com/akumar94/painted-time
cd painted-time
npx serve .
```

Open `http://localhost:3000`. Click **Enter the World**. Click the canvas to lock your cursor. WASD to move, mouse to look.

---

## Relationship to Painted Worlds

Painted Worlds and Painted Time are companion projects exploring the same question from different angles. Painted Worlds is about **space**: what does it feel like to step inside a painting? Painted Time is about **time**: what did that space actually sound like in the moment it was painted? Together they form a larger research question about what happens to our relationship with historical art when we can inhabit it rather than observe it.

---

## What's Next

- Additional paintings and historical soundscapes
- More accurate historical audio research per painting
- Refined Gaussian splat rendering pipeline

---

*Built by Aditya Kumar*
