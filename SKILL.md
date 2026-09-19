---
name: app-icon-designer
description: >
  Design, generate, refine, QA, and productionize app icons for an existing app repository.
  Use when the user asks for an app icon, launcher icon, desktop icon, macOS icon, iOS icon,
  Tauri icon, icon redesign, icon replacement, or production icon asset. Inspect the repository
  first, derive one concrete product metaphor, preserve the project's visual language, use the
  available image-generation capability for actual rendering, validate small-size legibility,
  and adapt output to the real target platform.
---

# App Icon Designer

Create app icons as product assets, not isolated illustrations.

Core rule:

**Choose one concrete object first. Then turn that object into an app icon.**

Avoid symbol collages such as:
- folder + arrow + waveform + atom
- coin + candlestick + chart + sparkle
- clock + calendar + checklist + spreadsheet

The icon should still read at roughly 32×32 px.

## 1. Inspect the repository first

Do not ask the user to repeat information already present in the repo.

Inspect:
1. README, PRD/spec/product docs, package metadata.
2. App/project name and product purpose.
3. Target platform: Tauri / macOS / iOS / Windows / Electron / PWA / cross-platform.
4. Existing theme colors, tokens, screenshots, UI style, marketing artwork.
5. Existing icon assets.
6. Prior icon concepts/backups.
7. Packaging/build config that determines output paths.

Search terms:
`icon`, `app-icon`, `AppIcon`, `launcher`, `favicon`, `logo`, `brand`, `design`, `theme`.

Common paths:
- Tauri: `src-tauri/icons/`, `src-tauri/tauri.conf.json`
- Xcode: `Assets.xcassets/AppIcon.appiconset/`
- Electron: `build/`, `resources/`, packaging config
- PWA: `public/`, manifest files
- Android: `mipmap-*`, adaptive icon resources

If an icon already exists:
- inspect the real image, not just filenames;
- identify what already works;
- inspect small sizes if present;
- do not overwrite it unless the user explicitly asks to replace production assets.

If prior concepts exist, treat them as design research.

## 2. Build an internal icon brief

Determine:
- product purpose: one sentence;
- primary value: one phrase;
- target platform;
- brand tone: 3–5 adjectives;
- existing palette: base / foreground / accent;
- 4–8 concrete noun candidates;
- forbidden directions/clichés.

Do not dump a long strategy document unless asked.

## 3. Choose the metaphor

If the user already supplied a strong metaphor, use it.

Otherwise:
1. Think of 4–8 single-object concepts.
2. Reject concepts that need text, multiple symbols, or tiny details.
3. Reject concepts that resemble famous app icons too closely.
4. Prefer the object that best combines semantic fit, silhouette strength, distinctiveness,
   material opportunity, palette compatibility, and 32px legibility.
5. Continue with the strongest concept automatically unless the user explicitly asks to choose.

Do not rescue a weak metaphor with decoration.

## 4. Default visual language

Use this as calibration, not a rigid template.

Prefer:
- contemporary high-end app-icon aesthetic;
- centered composition;
- balanced optical padding;
- front-facing or very slight three-quarter perspective;
- softly modeled semi-skeuomorphic geometry;
- restrained gradients;
- tactile materials;
- subtle edge highlights;
- gentle ambient depth;
- clean, friendly, professional finish.

Avoid:
- gratuitous futurism;
- neon/cyberpunk unless appropriate;
- AI sparkles;
- excessive glow;
- heavy bevels;
- dramatic perspective;
- miniature UI screenshots;
- tiny particles;
- floating cards;
- complex isometric scenes.

Use no more than three meaningful visual layers:
1. base/background;
2. main object;
3. optional small accent.

Glass is optional. Use translucent/frosted material only when it naturally fits the object.

A reliable color structure is:
1. calm base;
2. main-object color;
3. one small accent.

Do not default every project to blue; read the repo palette first.

## 5. Style calibration

A successful scientific workflow pattern is:
- pale ice-gray base;
- one substantial translucent blue sample tube;
- one narrow amber band;
- restrained highlights;
- soft depth.

Why it works:
- one physical metaphor;
- one memorable accent;
- no atom/spectrum/flask collage;
- strong small-size silhouette.

Transfer the structure, not the literal sample tube or colors.

For productivity apps, do not automatically combine clock + calendar + checkmark + spreadsheet.

For finance/strategy apps, do not automatically use coin + dollar sign + candlestick + arrow +
black-and-gold luxury styling.

## 6. Work in two passes

### Pass A — silhouette
First solve:
- object;
- proportion;
- orientation;
- placement;
- negative space;
- accent location.

The silhouette must survive around 32px.

### Pass B — finish
Once silhouette works, keep composition fixed and refine only:
- material;
- surface thickness;
- highlight placement;
- shadow softness;
- gradient restraint;
- accent saturation;
- optical centering.

Recommended refinement instruction:

> Retain the exact composition, object silhouette, proportions, orientation, and accent placement.
> Refine only materials, lighting, surface thickness, edge highlights, ambient shadow, gradient
> restraint, and optical balance. Do not introduce new symbols or decorative objects.

## 7. Build the generation prompt

Use this order:
1. asset + product;
2. core metaphor;
3. visual direction;
4. composition;
5. color;
6. platform/output;
7. avoid.

Prefer concrete spatial wording over adjective stacks.

Bad:
> futuristic scientific premium elegant glassy advanced data icon

Better:
> a substantial translucent blue laboratory sample tube containing one thin horizontal amber
> liquid band suspended near the lower third

Reusable prompt:

```text
Design one polished production-ready app icon for “[PROJECT NAME]”, an application for
[ONE-SENTENCE PRODUCT PURPOSE].

Core metaphor:
[ONE SIMPLE CONCRETE OBJECT].
[OPTIONAL SENTENCE FIXING A CRITICAL SPATIAL DETAIL].

The [OBJECT] must be the only dominant metaphor.

Visual direction:
Use a refined contemporary application-icon aesthetic with softly modeled semi-skeuomorphic
geometry, restrained gradients, tactile materials, subtle edge highlights, and gentle ambient
depth.

Keep the design [3–5 PROJECT-SPECIFIC TONE WORDS].

Use translucent or frosted material only where it naturally supports the object.

Composition:
Center the main object with balanced optical padding. Keep the silhouette bold and simple, with
no more than three meaningful visual layers.

Use a front-facing or very slight three-quarter perspective. Avoid dramatic perspective.

The icon must remain immediately recognizable at approximately 32×32 pixels.

Color:
[BASE / BACKGROUND]
[MAIN OBJECT]
[OPTIONAL ACCENT]

Output:
[PLATFORM-SPECIFIC REQUIREMENTS]

Avoid:
No text, letters, numbers, labels, measurement marks, interface screenshots, tiny decorative
elements, icon grids, Dock/home-screen mockups, device mockups, external presentation canvas,
unrelated secondary objects, Apple logo, trademarks, or watermark.

Do not copy or closely imitate any existing app icon.
```

Silhouette exploration:

```text
Focus on silhouette and composition rather than surface effects.

Create [N] controlled variations of the same [OBJECT] metaphor.
Keep the object centered and visually bold. Vary only proportion, orientation, negative space,
and accent placement.

Use minimal material rendering. Do not add new symbols.
All versions must remain recognizable at 32×32 pixels.
```

Finish/refinement:

```text
Retain the exact composition, object silhouette, proportions, orientation, and accent placement.

Refine only materials, lighting, surface thickness, edge highlights, ambient shadow, gradient
restraint, and optical balance.

Do not introduce new symbols, labels, particles, secondary objects, or a presentation background.
Preserve small-size legibility.
```

Common corrections:

Presentation mockup:
```text
Return only the production icon asset. Remove the presentation canvas, floor, device, Dock,
caption, frame, and external shadow.
```

Extra symbols:
```text
Remove every secondary symbol. Keep only [OBJECT] and the small [ACCENT].
```

Too photorealistic:
```text
Simplify geometry and surface detail. Keep tactile material and soft depth, but return to a clean
application-icon illustration rather than a product photograph.
```

Too flat:
```text
Keep the same silhouette. Add restrained material thickness, one controlled highlight family,
and a soft ambient shadow. Do not add decorative layers.
```

Muddy at 32px:
```text
Increase shape separation and simplify internal detail. Make the accent larger or remove it if it
cannot survive at 32px. Preserve the main silhouette.
```

## 8. Use the available image-generation capability

When the environment provides image generation/editing, use it for actual rendering.

This skill is responsible for:
- repo inspection;
- metaphor selection;
- art direction;
- prompt construction;
- iteration strategy;
- QA;
- platform adaptation;
- repo integration.

Do not pretend an image was generated if image generation is unavailable.

If unavailable, still produce:
- selected metaphor;
- final generation prompt;
- intended output path;
- integration instructions.

Generation defaults:
- if the user asks for exactly one icon, generate exactly one;
- otherwise prefer one strong concept with 2–4 controlled variations;
- vary proportion/material/palette, not the basic metaphor;
- inspect every output;
- reject text, multiple icons, mockups, or unrelated objects;
- refine the best candidate instead of endlessly resetting.

## 9. Platform-aware production

Visual style and packaging are separate decisions.

### Tauri / flattened desktop asset

For Tauri, a flattened 1024×1024 PNG or SVG master is appropriate.

A macOS-like visual treatment may include:
- modeled rounded-square/squircle base;
- transparent canvas outside the modeled base;
- softly rendered central object.

After approval, inspect the project package manager and existing scripts.

Typical Tauri v2 command forms:
```text
pnpm tauri icon path/to/app-icon.png
npm run tauri icon path/to/app-icon.png
cargo tauri icon path/to/app-icon.png
```

Do not invent the command without inspecting the repo.

Common output path:
`src-tauri/icons/`

### Native Apple production

For current native iOS/iPadOS/macOS icon production, do not automatically treat a pre-rounded PNG
as the final source.

Modern Apple icon workflows use a 1024×1024 square design canvas/layers and let the system apply
platform masking/material behavior.

For native Apple output:
- keep main content safely centered;
- avoid baking an outer rounded mask into imported source layers;
- avoid unnecessary baked blur, large static shadows, and excessive specular effects when the
  system workflow supplies them;
- separate background and foreground when the project uses a layered icon workflow;
- preserve the approved metaphor and composition.

If the user only wants a flattened concept preview, label it as a concept/preview.

For release-critical work, verify current Apple documentation before modifying production assets.

### Windows desktop

Prioritize:
- strong 16/24/32px silhouette;
- sufficiently thick edges;
- clear foreground/background separation;
- no dependence on tiny highlights.

Use the project's normal build/framework pipeline for `.ico`.

Windows desktop `.ico` assets carry their own silhouette: do not expect the shell to apply
an iOS-style rounded-square mask. A square opaque PNG produces a square background in the
desktop shortcut, even if the app's web UI uses CSS `border-radius`.

Choose the outline from the user's reference and existing design. For a rounded-tile design,
bake the rounded silhouette into the Windows raster asset, with genuine alpha=0 outside the
tile and antialiased edges. Rounded tiles are a design choice, not a Windows requirement;
freeform silhouettes and deliberately square designs remain valid.

Keep a separate unmasked source when other platforms need it. Do not fix transparency noise
by flattening onto an opaque square and calling it finished. Repair the alpha edge while
preserving the approved object and composition. Reject painted checkerboards, stray opaque
pixels, pale corner wedges, and dark or white edge halos.

Export through the existing framework pipeline, preserving alpha. Inspect the actual `.ico`
frames, not only the source PNG: check the small sizes the pipeline includes (especially
16/24/32/48px where available) and the largest frame. Do not assume a successful conversion
means the outline survived. See Microsoft's [icon construction guidance](https://learn.microsoft.com/en-us/windows/apps/design/iconography/app-icon-construction)
for required sizes in the chosen packaging format.

### PWA/web

Generate:
- clean 1024 master;
- safe margins;
- maskable adaptations if required by the manifest.

Do not assume transparent squircle corners are correct for every maskable PWA icon.

### Cross-platform rule

Maintain one canonical **concept**, not necessarily one canonical **file**.

Metaphor, proportion, palette, and accent should remain recognizable while masking, alpha,
background treatment, and layer structure may differ.

## 10. Candidate output location

Unless the repo already has a design-asset convention, use:

`design/app-icon/`

Suggested names:
- `concept-01.png`
- `concept-02.png`
- `app-icon-master-1024.png`
- `preview-128.png`
- `preview-32.png`

Do not overwrite production assets during exploration.

## 11. QA before integration

Inspect at:
- 1024px;
- 128px;
- 32px.

Check:
- exactly one icon;
- one dominant metaphor;
- no more than three meaningful visual layers;
- no accidental text/letters/numbers unless explicitly required;
- no Apple logo/trademark copying;
- no UI screenshot miniature;
- no unrelated object;
- silhouette reads at 32px;
- accent survives without becoming noise;
- optical margins are balanced;
- no clipped highlight/shadow;
- square output;
- correct target resolution;
- alpha/mask behavior matches target platform;
- palette fits the actual app UI.

Do not call an icon production-ready before QA.

Optional local QA if Python + Pillow are already available:

```python
from pathlib import Path
from PIL import Image

path = Path("design/app-icon/app-icon-master-1024.png")
img = Image.open(path).convert("RGBA")

assert img.width == img.height, "icon must be square"
print("size:", img.size)
print("alpha extrema:", img.getchannel("A").getextrema())

out = path.parent / "qa"
out.mkdir(exist_ok=True)

for size in (128, 32):
    img.resize((size, size), Image.Resampling.LANCZOS).save(out / f"preview-{size}.png")

print("Inspect:", out / "preview-128.png", out / "preview-32.png")
```

If Pillow is unavailable, do not install dependencies unless appropriate. Use available image
inspection tools and continue manually.

The 32px preview requires visual inspection; numeric checks are not enough.

For assets intended to have transparent surroundings, inspect the alpha channel and composite
the exported icon over light and dark backgrounds at native size. Check transparent corners,
smooth contours, and detached pixels; an alpha range of 0–255 alone does not prove a clean mask.
For Windows, include frames decoded from the final ICO in this check.

## 12. Safe integration

When the user explicitly asks to replace/install the icon:
1. inspect git status;
2. preserve existing assets through git history or a backup if appropriate;
3. place the approved master in the intended source location;
4. run the platform icon-generation step when applicable;
5. inspect changed files;
6. verify no unrelated files changed;
7. run a build/config sanity check where practical.

Trace the icon through the app's actual entry points: executable/bundle, window/tray, installer,
and in-app branding where applicable. Replacing source assets does not update an already-built
EXE or an installed shortcut. When delivering a usable replacement build, rebuild the executable
and installer and inspect the embedded executable icon; report whether installation was tested.
Follow the repository's version/signing/release rules, and do not publish an app release merely
because icon replacement was requested.

If Windows still displays an old shape, first verify the built executable and the shortcut's
target/icon location. Consider shell icon caching only after checking the real artifact. Do not
delete system caches, restart Explorer, or terminate a running production app as a routine fix.

Never overwrite current production icon assets merely because a candidate looks promising.

## 13. Completion report

Keep the final report concise.

State:
- selected metaphor;
- one-sentence art direction;
- generated master path;
- target platform mode;
- 32px QA result;
- production files changed, if any;
- remaining platform-specific handoff, if any.

Do not dump the full prompt unless the user asks.

## 14. Trigger examples

Use this skill for:
- “给这个项目做一个 app icon”
- “重新设计 Tauri 图标”
- “根据这个 repo 自动生成 icon”
- “做一个 macOS 风格桌面图标”
- “帮我换掉现在的 launcher icon”
- “生成一个能直接进项目的 1024 icon”
- “用现有 UI 风格重做 AppIcon”

Recommended explicit invocation:

`$app-icon-designer 给这个项目设计并生成一个 production-ready app icon，先读仓库再决定视觉隐喻。`
