# Unity Essentials

This module is part of the Unity Essentials ecosystem and follows the same lightweight, editor-first approach.
Unity Essentials is a lightweight, modular set of editor utilities and helpers that streamline Unity development. It focuses on clean, dependency-free tools that work well together.

All utilities are under the `UnityEssentials` namespace.

```csharp
using UnityEssentials;
```

## Installation

Install the Unity Essentials entry package via Unity's Package Manager, then install modules from the Tools menu.

- Add the entry package (via Git URL)
    - Window → Package Manager
    - "+" → "Add package from git URL…"
    - Paste: `https://github.com/CanTalat-Yakan/UnityEssentials.git`

- Install or update Unity Essentials packages
    - Tools → Install & Update UnityEssentials
    - Install all or select individual modules; run again anytime to update

---

# IES

> Quick overview: Example IES photometric light profile for HDRP lights. Assign it to Point/Spot lights to get real‑world beam distributions, patterns, and falloffs.

This module provides a sample IES file you can use to validate your HDRP lighting setup or as a starting point for your own photometric profiles. IES (Illuminating Engineering Society) files encode real lamp distributions captured from luminaires.

![screenshot](Documentation/Screenshot.png)

## Features
- Ready‑to‑use example IES profile (placed under Resources)
- Works with HDRP Point and Spot lights (Light Shape) via the IES Profile slot
- Great for testing realistic beam shapes, wall patterns, and falloff

## Requirements
- Unity 6000.0+
- High Definition Render Pipeline (HDRP)
  - IES profiles are supported by HDRP lights (Point/Spot)

## Usage

Assign the IES profile to a light in HDRP:

1) Create or select a Point or Spot Light in your scene
2) In the Inspector (HDRP), expand the light settings
3) Locate the IES/Photometric section (IES Profile field)
4) Drag the included `.ies` file onto the IES Profile field:
   - `Assets/Repositories/Unity.Graphics.IES/Resources/LeoMoon Studios IES/area-light.ies`
5) Choose an appropriate Light Unit (e.g., Lumen or Candela) and adjust Intensity to taste
6) Tweak other light settings (range/spot angle/shape) according to your look

Tips
- Different IES profiles can produce very different beam shapes and intensities—try a variety to match your design
- When working with photometric data, prefer physically based units and keep exposure consistent across your project

## Notes and Limitations
- Pipeline: IES consumption is an HDRP feature; Built‑in/URP do not use `.ies` files out of the box
- Light types: IES profiles apply to Point and Spot lights; they do not affect Directional lights
- Intensity: Photometric data can be bright—set the Light Unit (Candela/Lumen) appropriately and adjust exposure/tonemapping
- Licensing: The included profile is provided for testing/demonstration; see LICENSE.md for licensing terms and attribution

## Files in This Package
- `Resources/LeoMoon Studios IES/area-light.ies` – Example IES photometric profile
- `package.json` – Package manifest metadata
- `LICENSE.md` – License and attribution

## Tags
unity, hdrp, ies, photometric, light, lighting, candela, lumen, point-light, spot-light, profile
