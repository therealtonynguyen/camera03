# OFF CAMERA

**What if another camera captured the story?**

---

## Overview

OFF CAMERA is an AI filmmaking project that revisits famous fictional moments through cameras the original films never cut to: a doorbell camera on a suburban porch, a dashcam on a desert highway, a CCTV unit mounted above a restaurant kitchen.

Each piece is a short, self-contained clip. It shows a scene the audience already knows, from a believable third-party point of view inside that world. The story stays the same and the angle changes. The angle comes with the visual grammar of real-world recording devices: fixed framing, wide-angle distortion, timestamps, compression, bad night exposure.

The project is a working studio and a public notebook. It holds the finished productions along with the prompts, workflows, failed experiments and lessons learned behind them.

---

## The Creative Rule

> **Boring cameras witnessing extraordinary events.**

Every production starts with one question: *what camera could plausibly have been there?*

The camera has to make sense in the world of the film. It should exist outside the original framing, be indifferent to the drama, and have no idea it is recording something remarkable. It doesn't track the action or frame the hero. It records what passes through its field of view.

That indifference is the point. When a mundane device catches an impossible moment, the moment feels more real, and the audience does the work of recognizing it.

**A good OFF CAMERA angle is:**

- **Plausible.** The device would realistically exist in that location.
- **Fixed or constrained.** Its framing is set by how it is mounted or used, not by artistic choice.
- **Outside the original coverage.** It shows the moment from somewhere the film never did.
- **Recognizable.** Viewers know the moment even though they have never seen it like this.

---

## Example Concepts

| Film | Moment | Alternate Camera |
|------|--------|------------------|
| Toy Story | Sid's mutant toys approach the porch | Doorbell camera, Sid's front door |
| Toy Story 2 | Al's Toy Barn rescue crossing | Traffic camera at the intersection |
| Toy Story 3 | Escape from Sunnyside Daycare | Daycare hallway CCTV |
| Cars | Lightning McQueen and Doc Hudson race past | Passing car dashcam |
| Coco | Miguel crosses into the Land of the Dead | Cemetery security camera |
| Monsters, Inc. | Activity in a child's bedroom at night | Baby monitor |
| Ratatouille | Remy moves through Gusteau's kitchen | Kitchen CCTV |
| The Incredibles | Mr. Incredible stops a runaway train | Commuter's cellphone |
| Up | The house lifts off on balloons | News helicopter |
| WALL-E | WALL-E compacting trash at dawn | Abandoned city traffic camera |
| Brave | Merida in the forest | Trail camera |
| Luca | Sea monsters change form on the shore | Tourist's GoPro |

---

## Production Workflow

```
Concept → Story Beat → Camera Type → Static Frame → Image-to-Video → Sound → Edit → Publish
```

1. **Concept.** Pick the film and the moment. It has to be recognizable without context.
2. **Story beat.** Narrow it to a single beat that can play out in one continuous shot.
3. **Select camera type.** Choose the device, where it is mounted and what it would actually see.
4. **Generate static reference frame.** Lock in composition, environment, lighting and camera artifacts as a still image.
5. **Generate image-to-video motion.** Animate the approved frame, with the prompt focused on movement and timing.
6. **Add sound design.** Build the device's audio: tinny mic, wind noise, compression, ambient hum, or silence.
7. **Edit.** Trim, add the overlay (timestamps, UI elements) and grade to match the device.
8. **Publish.** Export for the target platform and document the production in this repo.

### Frame first, motion second

We usually generate the static frame **before** moving to video instead of going straight from text to video.

Text-to-video asks a model to solve composition, lighting, character design, camera behavior and motion all at once, and it tends to drift toward cinematic defaults. Locking the frame first makes the video model's job narrower: keep this exact camera, move these things. The result is more control, fewer wasted generations, and clips that actually look like the device they claim to come from.

---

## Prompting Philosophy

Image prompts and motion prompts do different jobs. They are written separately.

### Image prompts set the world

The image prompt defines everything that should stay fixed:

- **Composition:** framing, horizon line, mounting height and angle
- **Environment:** location, time of day, weather, set dressing
- **Lens:** focal length, fisheye or wide-angle distortion, vignetting
- **Camera quality:** resolution, sensor noise, compression, dynamic range
- **Lighting:** practical sources, IR night vision, overexposed highlights
- **Subject placement:** where characters enter, stand or exit the frame

### Video prompts set the motion

The video prompt inherits the frame and focuses mostly on:

- **Movement:** what moves, in which direction, at what speed
- **Timing:** when things enter, pause, react or leave
- **Physics:** weight, momentum, contact with surfaces
- **Camera behavior:** usually none, or only what the device would really do (auto-exposure shifts, focus hunting, vehicle vibration)

### Constraints

Video models lean cinematic by default. Constraints keep the footage honest:

```
no cinematic camera movement
no dolly, no pan, no zoom
no dramatic depth of field
preserve fixed surveillance framing
preserve compression artifacts
preserve timestamp overlay
no color grading, no film look
no lens flares
```

Use whichever apply to the device. A bodycam *should* shake, and a dashcam *should* vibrate.

---

## Camera Language Library

| Camera | Visual Traits |
|--------|---------------|
| **Doorbell camera** | Extreme fisheye, high downward angle from about chest height, curved edges, IR black-and-white at night, motion-triggered start, timestamp and brand UI |
| **Dashcam** | Wide forward view through windshield glare, constant road vibration, hood edge in frame, speed and GPS overlay, blown-out skies |
| **CCTV** | High corner mount, wide static frame, low resolution, heavy compression, low frame rate, camera ID and timestamp, flat lighting |
| **Traffic camera** | Very high, distant vantage over an intersection, small figures, washed-out color, stuttering frame rate, location label |
| **Bodycam** | Chest-level POV, constant motion from walking, fisheye lens, arms and hands entering frame, muffled audio, agency watermark |
| **Police dashcam** | Forward view from a cruiser, light bar reflections on the hood, officer ID and speed overlay, radio chatter |
| **Baby monitor** | Grainy IR night vision, high corner of a nursery, soft focus, green or gray tint, low-fidelity audio with hiss |
| **Trail camera** | Low mount on a tree, motion-triggered bursts or short clips, harsh IR flash at night, temperature and moon-phase stamp |
| **Elevator camera** | Top-corner fisheye looking down into a small box, doors centered, floor indicator overlay, fluorescent lighting |
| **Parking garage CCTV** | Low concrete ceilings, sodium or fluorescent light, deep shadows, pillars blocking the view, wide distorted frame |
| **News helicopter** | Long telephoto from above, stabilized but drifting, heat shimmer, station bug and lower-third chyron, slow push-ins |
| **Tourist cellphone** | Handheld, vertical or horizontal, autofocus hunting, digital zoom, reactive framing, bystander audio |
| **GoPro** | Ultra-wide action POV, mounted on a helmet, chest or board, water droplets on the lens, high frame rate, saturated color |

Full per-device prompt templates live in [`prompt-library/`](prompt-library/).

---

## Story Structure

Every clip follows a four-part arc:

```
Normal → Weird → Recognition → Payoff
```

| Beat | Purpose |
|------|---------|
| **Normal** | An empty porch, an ordinary road. The camera's everyday reality. |
| **Weird** | Something enters the frame that doesn't belong. |
| **Recognition** | The viewer realizes what they are watching. |
| **Payoff** | The moment plays out, and ideally ends on a beat that rewards a rewatch. |

Many clips work best at **10–18 seconds**, even when the platform supports longer videos. Surveillance footage reads as real because it is brief and undramatic. Extra length dilutes the reveal and gives the model more time to break the illusion.

---

## Tools

The current toolchain. Tools change fast, and this table will change with them.

| Tool | Role |
|------|------|
| **ChatGPT** | Concepts, shot lists, prompt drafting, iteration |
| **Higgsfield** | Video workflow and generation hub |
| **Veo** | High-quality video generation |
| **Kling** | Motion experimentation |
| **Runway** | Controlled, iterative generation |
| **Premiere Pro / CapCut** | Editing, overlays, final assembly |
| **Adobe Audition / editor tools** | Sound design and audio cleanup |
| **Topaz Video AI** | Optional upscaling and cleanup |

The workflow matters more than any single tool. Each production's `notes.md` records which models were used and how they behaved.

---

## Repository Structure

```
off-camera/
├── README.md
├── docs/
│   ├── concept.md              # Project concept and creative rules
│   └── visual-language.md      # Device aesthetics and overlay standards
├── productions/
│   ├── 001-sids-porch/
│   │   ├── concept.md          # Film, moment, camera, why it works
│   │   ├── storyboard.md       # Beat-by-beat breakdown
│   │   ├── image-prompts.md    # Reference frame prompts and iterations
│   │   ├── video-prompts.md    # Motion prompts and constraints
│   │   ├── sound-design.md     # Audio layers and references
│   │   └── notes.md            # Tools used, results, lessons learned
│   ├── 002-radiator-springs-dashcam/
│   └── 003-miguel-security-camera/
└── prompt-library/
    ├── doorbell-camera.md
    ├── dashcam.md
    ├── cctv.md
    ├── bodycam.md
    └── trailcam.md
```

Productions are numbered in the order they start. Each folder should hold enough detail for someone else to reproduce or extend the work.

---

## First Production

### CAM 03 / 001: Toy Story, Sid's Porch

Sid's mutant toys crossing the front porch, seen through the house's doorbell camera.

This is the proof of concept because it tests the core idea under good conditions:

- **Instantly recognizable.** The characters and the house are iconic. A few frames are enough.
- **Believable fixed camera.** A doorbell camera on a suburban front door is completely ordinary.
- **Manageable generation challenge.** One location, fixed framing and small subjects keep the scope achievable with current models.
- **Strong reveal.** An empty porch, then something low and strange moving in from the edge of the frame. The Normal → Weird → Recognition arc builds itself.
- **A clean test of the premise.** If this one doesn't work, the concept needs rethinking. If it does, it sets the template for everything after.

---

## Branding

| Element | Usage |
|---------|-------|
| **Project** | OFF CAMERA |
| **Series designation** | CAM 03 (optional, internal) |
| **Production ID** | `CAM 03 / ###` |

Title card format:

```
CAM 03 / 001
Toy Story: Sid's Porch
```

---

## Disclaimer

OFF CAMERA is an **unofficial, fan-created project**. It is not affiliated with, endorsed by or sponsored by Disney, Pixar or any other rights holder.

All characters, worlds and related properties belong to their respective owners. The project is focused on transformative creative experimentation, filmmaking study and AI storytelling research.

Nothing here should be presented or redistributed as official or endorsed content.

---

## Goals

- Improve AI filmmaking skills through deliberate, documented practice
- Sharpen shot design and visual storytelling under tight constraints
- Build reusable prompt patterns for specific camera types and scenarios
- Learn how different video models behave: where they succeed, where they break, and why
- Build a strong creative and technical portfolio
- Eventually expand beyond Pixar-inspired concepts into other fictional worlds and original ideas

---

*Every story has more cameras than the ones we saw.*
