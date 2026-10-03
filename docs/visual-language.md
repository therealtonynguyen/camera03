# Visual Language

Standards for making footage read as a real device rather than a film camera.

## Core Principles

1. **The device decides the frame.** Mount height, lens and angle come from how the camera is installed or held.
2. **Imperfection is the costume.** Compression, noise, blown highlights and low frame rates are what sell the footage.
3. **No cinematography.** No camera moves, shallow depth of field, color grade or composed lighting unless the device would produce it.
4. **Match the overlay to the device.** Timestamps, IDs and UI elements should be consistent and believable without imitating a real brand.

## Device Reference

| Device | Mount / Height | Lens | Frame Rate | Color / Night | Overlay |
|--------|----------------|------|------------|---------------|---------|
| Doorbell camera | Door frame, ~1.2 m, angled down | Extreme fisheye | 15–30 fps | Color by day, IR B&W at night | Date/time, generic app UI |
| Dashcam | Windshield, behind mirror | Wide, slight barrel | 30 fps | Glare, crushed shadows at night | Date/time, speed, GPS |
| CCTV | High corner, 2.5–4 m | Wide | 5–15 fps | Flat, low-saturation; IR at night | CAM ID, date/time |
| Traffic camera | Pole, 8–12 m | Wide to medium | 1–10 fps | Washed out | Location label, time |
| Bodycam | Chest | Fisheye | 30 fps | Auto-exposure swings | Unit ID, date/time |
| Police dashcam | Cruiser windshield | Wide | 30 fps | Light bar reflections | Unit, speed, date/time |
| Baby monitor | Nursery corner, high | Wide | 10–15 fps | IR green/gray tint | Temperature, signal |
| Trail camera | Tree, 0.5–1 m | Wide | Bursts or short clips | Harsh IR flash | Temp, moon phase, date/time |
| Elevator camera | Ceiling corner | Fisheye, looking down | 10–15 fps | Fluorescent cast | Floor, CAM ID |
| Parking garage CCTV | Ceiling, low clearance | Wide, distorted | 5–15 fps | Sodium/fluorescent, deep shadow | Level, CAM ID |
| News helicopter | Gyro-stabilized gimbal | Long telephoto | 30 fps | Heat shimmer, haze | Station bug, chyron |
| Tourist cellphone | Handheld | Phone wide / digital zoom | 30–60 fps | Auto HDR, focus hunting | None |
| GoPro | Helmet, chest or board | Ultra-wide | 60+ fps | Saturated, water droplets | None |

## Overlay Standards

- Use a plain monospace font for timestamps and IDs.
- Keep timestamps continuous within a clip. Timecode jumps break the illusion.
- Use invented or generic UI. Never replicate a real manufacturer's branding.
- Place overlays where the device would: corners for CCTV, the bottom bar for dashcams.

## Audio Standards

- Device mics are small, compressed and often mono.
- Ambient noise (wind, hum, road rumble) does more than any score.
- Many surveillance devices record no audio. Silence is a valid choice.
- No music inside the clip.

## Common Failure Modes

| Problem | Fix |
|---------|-----|
| Model adds a slow dolly or push-in | Add "locked-off static camera, no camera movement"; regenerate from the still |
| Footage looks too clean | Add compression, noise and lower resolution in the image prompt; degrade in post |
| Cinematic shallow depth of field | Add "deep focus, everything in focus, small sensor" |
| Characters look rendered, not recorded | Reduce detail, add motion blur and exposure clipping |
| Lens distortion drifts between frames | Lock it in the reference frame; keep motion prompts short |
