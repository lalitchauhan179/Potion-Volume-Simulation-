
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
