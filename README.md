
# 🧪 Potion Volume Simulation (Unity 2022.3.21f1)
This Unity project is an interactive simulation designed to teach the concept of **volume for cubes and cuboids** through a visual potion-filling activity. Students can select a shape, customize its size, and fill it using a virtual tap with real-time feedback, animations, and voice-overs.
---
## 📦 Project Setup
### ✅ Prerequisites
- Unity Editor **2022.3.21f1** (2D Template)
- [DOTween](http://dotween.demigiant.com/download.php) (Free Tweening Library)
- TextMeshPro (enabled by default in modern Unity projects)
---
## 🛠️ How to Run the Project
1. **Clone or Download** this repo into your Unity Projects folder.
2. Open it in Unity Editor (**2022.3.21f1**).
3. Make sure the following packages are ready:
- TMP_Text (TextMeshPro)
- DOTween (see below)
4. Navigate to `Scenes/Welcome.unity` and press **Play**.
---
## 🔌 Setting Up DOTween (Required)
1. Open Unity → **Tools → Demigiant → DOTween Utility Panel**
2. Click **Setup DOTween...**
3. Done! You're ready to animate fills and UI.
If DOTween is not installed:
- Go to **Window → Package Manager → My Assets**
- Search for **DOTween** → Import
---
## 🎮 Scenes Overview
| Scene | Purpose |
|-------|---------|
| `Welcome.unity` | Start screen + intro VO |
| `CustomizeShape.unity` | Select cube/cuboid and dimensions |
| `FillPotion.unity` | Interactive filling scene |
---
## 🎯 Key Features
- Shape selection with real-time preview
- Visual potion fill using slider or auto mode
- Cube/cuboid enters with animation from spawn point
- Tap bucket shows pre-filled volume
- Sync'd audio VOs: Welcome → Instruction → Success
- Feedback on perfect fill using shimmer particles
- DOTween used for UI text and transform animation
---
## 🔧 Inspector Setup Tips
In `FillPotionScene`:
- Assign these manually in the Inspector:
- `cubeObject`, `cuboidObject`
- `cubeFillOverlay`, `cuboidFillOverlay`
- `spawnPoint`, `targetPoint`
- `bucketFillOverlay`, `shimmer`, `AudioSource`
- UI: `fillSlider`, `startPourButton`, `resetButton`, `valueLabel`, `feedbackText`
- AudioClips: `voReady`, `voPouring`, `voPerfect`
---
## 📂 Folder Structure
Assets/ ├── Audio/ # Voice-over clips (voReady, voPouring, voPerfect) ├── Materials/ ├── Prefabs/ # Optional shape prefabs ├── Scenes/ │ ├── Welcome.unity │ ├── CustomizeShape.unity │ └── FillPotion.unity ├── Scripts/ │ ├── ShapeCustomizer.cs │ └── FillPotionScene.cs ├── Sprites/ # UI and object sprites (bucket, ramp, shapes) └── UI/ # Canvas elements, buttons, images, inputs


---

## 🧩 Scene Breakdown

### 🖼️ Scene 1: Welcome
- Title and **Start** button
- Plays **voReady** clip, transitions to CustomizeShape scene via `ShapeCustomizer.cs`

### 📐 Scene 2: Customize Shape
- Choose between **Cube** or **Cuboid**
- Input dimensions:
  - Cube: `a`
  - Cuboid: `l, b, h`
- Shape preview updates dynamically
- **Next** button activates on valid input and stores data in `PlayerPrefs`

### 🧪 Scene 3: Fill Potion
- Bucket visual with `bucketFillOverlay`
- Cube/Cuboid object animated from `spawnPoint` to `targetPoint` using DOTween
- Sliders, fill indicators, and feedback text
- Voice-over plays in sequence:
  1. `voReady`
  2. `voPouring`
  3. `voPerfect` (on full fill)

---

## 🧠 Script Overview

### 📜 ShapeCustomizer.cs
Handles:
- Shape selection
- Input validation
- Shape preview
- Data persistence via `PlayerPrefs`

### 📜 FillPotionScene.cs
Manages:
- Shape instantiation and movement
- Potion fill logic using `Mathf.Lerp` & `DOTween`
- Feedback system and AudioSource triggers
- Full scene reset and replay

---

## ⚙️ DOTween Integration

- 📦 Install via **Unity Package Manager** → My Assets → DOTween → Import
- ⚙️ Setup: Tools → Demigiant → DOTween Utility Panel → Setup DOTween
- Usage:
```csharp
transform.DOMove(targetPoint.position, 1.5f);
DOTween.To(() => currentFill, x => currentFill = x, targetFill, 0.3f);


🔊 Audio & Voice-Overs
🎧 Audio clips stored in Assets/Audio/

🔉 Controlled using AudioSource component

⏱️ Timing managed with Invoke() based on clip lengths

Clips: voReady, voPouring, voPerfect

🧪 Inspector Assignments
CustomizeShape Scene (ShapeCustomizer.cs)
Input fields: inputA, inputL, inputB, inputH

Buttons: Next, shape choices

Sprites: cubeSprite, cuboidSprite

FillPotion Scene (FillPotionScene.cs)
Transforms: spawnPoint, targetPoint

Objects: cubeObject, cuboidObject

UI: cubeFillOverlay, cuboidFillOverlay, bucketFillOverlay

Controls: fillSlider, startPourButton, resetButton

Text: valueLabel, feedbackText

Effects: shimmer

Audio: audioSource, voReady, voPouring, voPerfect

🚀 Future Enhancements
🌊 Animated potion stream using particle trails

📱 Touch-optimized sliders for mobile platforms

🧠 Math practice scenes: fill the shape when given volume

🔢 Visual math overlays (e.g., 3 × 3 × 3 = 27)

📊 User score tracking and performance analytics

🌍 Multi-language support for voice-over and UI

Created by Lalit Kumar Chauhan
📧 lk149466@gmail.com | 🔗 LinkedIn


---

