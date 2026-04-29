Visit: https://vatsalvarma.github.io/3D-360-tour-view/

project-folder/
│── index.html
│── BEDROOM.jpg
│── BEDROOM TWO.jpg

🔄 How It Works
The viewer loads inside a <div>
First scene is displayed
User clicks hotspots
Scene changes

        ┌──────────────────────┐
        │   index.html         │
        │ (Main Application)   │
        └─────────┬────────────┘
                  │
                  ▼
        ┌──────────────────────┐
        │   Pannellum Viewer   │
        │ (360 Engine)         │
        └─────────┬────────────┘
                  │
        ┌─────────┴──────────┐
        ▼                    ▼
 ┌──────────────┐     ┌──────────────┐
 │   Scene 1     │     │   Scene 2     │
 │ BEDROOM.jpg   │     │ BEDROOM TWO   │
 └──────┬───────┘     └──────┬───────┘
        │                    │
        ▼                    ▼
              ┌──────────────┐
              │   Scene 3     │
              │ River Image   │
              └──────────────┘




                      [ Scene 1 ]
   🌳 Jungle Entrance
          |
          | (Go deeper 🌿)
          v
        [ Scene 2 ]
     🌴 Deep Jungle
       /       \
      /         \
(Go back)   (Go to river 🌊)
   |              |
   v              v
[ Scene 1 ]   [ Scene 3 ]
              🏞 River
                  |
                  | (Return 🌿)
                  v
              [ Scene 2 ]




                    (Pitch +)
                ↑
                |
   (Yaw -) ← User → (Yaw +)
                |
                ↓
             (Pitch -)


    ⚙️ Code Breakdown
1. Container
<div id="panorama"></div>

👉 This is where the 360 view appears

2. Initialize Viewer
pannellum.viewer('panorama', {...});

👉 Starts the 360 viewer

3. Default Settings
"default": {
    "firstScene": "scene1",
    "autoLoad": true,
    "sceneFadeDuration": 1000
}
firstScene → starting point
autoLoad → loads automatically
sceneFadeDuration → smooth transition
4. Scene Example
"scene1": {
    "title": "Jungle Entrance",
    "panorama": "BEDROOM.jpg"
}

👉 One image = one scene

5. Hotspot Example
{
    "pitch": 0,
    "yaw": 320,
    "type": "scene",
    "text": "Go deeper",
    "sceneId": "scene2"
}

👉 Click → moves to another scene

🎮 User Flow Diagram
User Opens Page
        │
        ▼
Scene 1 Loads
        │
        ▼
User Looks Around (Drag Mouse)
        │
        ▼
Clicks Hotspot
        │
        ▼
Scene Changes
        │
        ▼
Repeat Navigation         
