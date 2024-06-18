# Coding notes
Just setting up.

# Assesment task
The Assesment is to demonstate different elements of the use BabylonJS such as lights, physics and Menus.

# Element 1
In this element i have demonstrated the use of lights such as:
* Hemispheric lights
* SpotLights
* Point Lights

Using theses light on a cube to cast shadows and expirment with the brightness, size and colours.

# Element 2
This element is to build a village.
I have demonatrate the following:
* skyboxes
* mesh panels 
* contstruting terrian
* height maps

# Element 3 
Learning the use of Physics using Havok and importing meshes
* Using a player mesh to push a sphere mesh around

# Element 4 
Learning to create a GUI
* implementing audio
* Have Multiple Scenes

# Element 5
This element allows more us be more creative.
this element has inclueded the following:
* Arc Rotated camera
* Gui menu
* GUI Buttons to control camera
* Multiple Imported Meshes
* Hemisheric Lighting
* Audio
The idea of this element is a car viewer as if it was to be implimented into a game with car customisation like for example in gta v when the player enters los santos customs.

an example of the camera controls 
```typescript
function addCameraControlButtons(sceneData: SceneData) {
  const advancedTexture = GUI.AdvancedDynamicTexture.CreateFullscreenUI("UI");

  const createButton = (text: string, callback: () => void) => {
    const button = GUI.Button.CreateSimpleButton(text, text);
    button.width = "120px";
    button.height = "40px";
    button.color = "white";
    button.background = "black";
    button.onPointerUpObservable.add(callback);
    return button;
  };

  const panel = new GUI.StackPanel();
  panel.width = "100%";
  panel.isVertical = false;
  panel.horizontalAlignment = GUI.Control.HORIZONTAL_ALIGNMENT_CENTER;
  panel.verticalAlignment = GUI.Control.VERTICAL_ALIGNMENT_TOP;
  panel.top = "10px"; // Position panel 10px from the top
  advancedTexture.addControl(panel);

  const buttons = [
    { text: "Front View", position: new Vector3(0, 3, 5) },
    { text: "Back View", position: new Vector3(0, 1, -5) },
    { text: "Left View", position: new Vector3(5, 1, 0) },
    { text: "Right View", position: new Vector3(-5, 1, 0) },
    { text: "Free Cam", position: new Vector3(3, 3, 3) },
  ];

  buttons.forEach((btn) => {
    const button = createButton(btn.text, () => {
      if (sceneData.camera) {
        animateCamera(sceneData.camera!, btn.position, new Vector3(0, 1, 0), 120);
      }
    });
    panel.addControl(button);
  });


```

