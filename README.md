# Angry Birds AR — Slingshot Challenge (WebAR)

An interactive Augmented Reality mini-game that transforms a static Angry Birds poster into a playable slingshot experience.

## How It Works

1. **Scan QR Code** → Opens the web-based AR experience
2. **Tap Start** → Camera activates and scans for the poster
3. **Point at Poster** → MindAR recognizes the image target and the 3D game world appears
4. **Red Bird Comes to Life** → Perched on a slingshot, ready to launch
5. **Pull & Aim** → Swipe down to set power, left/right to aim
6. **Launch!** → Release to fling the Red Bird at the pigs' wooden tower
7. **Destroy the Tower** → Structures collapse, pigs are defeated
8. **Score & Replay** → Final score shown with star rating; tap to replay

## Controls

| Action         | Gesture                        |
|----------------|--------------------------------|
| Aim            | Touch/click and drag **down**  |
| Adjust angle   | Drag **left/right** while held |
| Launch         | Release finger/mouse           |
| Power meter    | Shows percentage on screen     |

## Tech Stack

- **MindAR** — Marker-based image tracking (poster.mind compiled target)
- **A-Frame** — WebXR 3D framework
- **Procedural geometry** — All models (Red Bird, Pigs, Slingshot, Tower) are built from A-Frame primitives — no external 3D models needed
- **Procedural audio** — Sound effects generated via Web Audio API oscillators

## Files

```
webar/
├── index.html              ← Main game (self-contained)
├── README.md               ← This file
├── assets/
│   ├── poster.jpg          ← Angry Birds poster image
│   └── poster.mind         ← Compiled MindAR tracking target
└── lib/
    ├── aframe.min.js       ← A-Frame library
    └── mindar-image-aframe.prod.js  ← MindAR image tracking
```

## Deployment

1. Push this `webar/` folder to a GitHub repository
2. Go to **Settings → Pages → Deploy from branch** (main, `/` root)
3. Access at `https://<user>.github.io/<repo>/`
4. Open the link on a phone, tap **Start**, allow camera, point at the printed poster

## Game Design

- **3 birds** per round
- **3 pigs** to defeat (ground, middle, top of tower)
- **Scoring**: 500 pts per tower hit, 1000 pts per pig, 500 bonus per remaining bird
- **Stars**: ⭐⭐⭐ (2+ birds left), ⭐⭐ (1 bird left), ⭐ (0 birds left)
