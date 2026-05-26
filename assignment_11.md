# Lab 11: VR/AR Camera and controls

In this lab there are two paths to follow, depending on whether you're working on a VR or AR project. VR path will probably be a good fit for anyone having problems with AR support on their devices, as for most part of development, the VR app will use the simulator built into Unity.

# Path 1: VR

## Task 1 – Project Setup and XR Rig Configuration (20%)

1. Create a new 3D (URP) Unity project.
2. Install XR Plugin Management and enable OpenXR for your target platform.
3. Add an interaction profile (for now for simulator it's not needed, but I'll leave the note here for reference if you wanted to use a real headset - it usually is provided by the hardware manufacturer).
4. Install the XR Interaction Toolkit and import the Starter Assets sample.
5. Replace the default Main Camera with the **XR Origin (XR Rig)** prefab.
6. Set the Tracking Origin Mode to **Floor** and verify the camera is at the correct height.
7. Add a ground plane and several simple objects (cube, sphere, table) to the scene.
8. You can use [the XR Device Simulator](https://docs.unity3d.com/Packages/com.unity.xr.interaction.toolkit@3.0/manual/xr-device-simulator.html) to test your scene without a headset.

## Task 2 – Controller Representation (20%) 

1. Verify left and right controllers appear as child objects under the XR Origin.
2. Attach controller models to the controller GameObjects.


## Task 3 – Input Handling via the Input System (25%)

1. Create an Input Action Asset with bindings for trigger, grip, primary/secondary buttons, and thumbsticks.
2. Bind a custom action: pressing the primary button changes the color of an object in the scene.

## Task 4 – Interaction Basics (35%)

1. Make the objects in the scene grabbable and throwable.
2. Notify user visually if the object is in reach - you can use [this great highlight asset](https://assetstore.unity.com/packages/tools/particles-effects/quick-outline-115488) for this purpose.

## Submission Requirements

Please submit a PDF report with screenshots of editor with visible scene tree in each of the tasks alongside additional screenshots of the game running in the simulator. The PDF report should contain link to repository with the project.

---

# Path 2: AR

## Task 1 – Project Setup and AR Session Configuration (20%)

1. Create a new 3D (URP) Unity project.
2. Install AR Foundation and the appropriate XR provider plugin (ARCore / ARKit).
3. Configure XR Plugin Management for the target platform.
4. Create a scene containing: **AR Session**, **XR Origin (AR)**, and **AR Camera** (replacing the default Main Camera).
5. Configure player settings: camera usage description (iOS), minimum API level (Android), required device features.
6. Enable XR Simulation in Project Settings so the scene can be tested in the editor.

## Task 2 – Plane Detection and Visualization (30%)

1. Add the **AR Plane Manager** component to the XR Origin (if for any reason it's not available, make sure you have AR Foundation installed in `Window > Package Manager`).
2. Create a custom plane prefab with a semi-transparent material and a visible grid texture.

## Task 3 – Touch Input and Raycasting (30%)

1. Add the **AR Raycast Manager** component.
2. On screen tap, cast a ray from the touch position against detected planes.
3. At the hit point, instantiate a simple object (cube or 3D model).
4. Add a debug indicator showing the live raycast hit position as the user moves their finger.

## Task 4 – Object Placement and Anchors (20%)

1. Replace "instantiate at touch" with logic that creates an **AR Anchor** at the hit point and parents the object to it.
2. Add a **reticle** – a visual indicator that follows the screen center and snaps to detected planes.

## Task 5 - Object Manipulation (Bonus)

Try to implement additional object manipulation features:

- One-finger drag – move the object along the plane it's anchored to.
- Two-finger rotate – rotate around the vertical axis.
- Pinch – uniformly scale within a sensible min/max range.
- Tap selection – tap to select (highlight); tap empty space to deselect.

## Submission Requirements

Please submit a PDF report with screenshots of editor with visible scene tree in each of the tasks alongside additional screenshots of the app running on the phone. The PDF report should contain link to repository with the project.

## Official Unity Documentation

- **XR Interaction Toolkit manual:** <https://docs.unity3d.com/Packages/com.unity.xr.interaction.toolkit@3.0/>
- **XR Device Simulator overview:** <https://docs.unity3d.com/Packages/com.unity.xr.interaction.toolkit@3.0/manual/xr-device-simulator.html>
- **AR Foundation – XR Simulation:** <https://docs.unity3d.com/Packages/com.unity.xr.arfoundation@5.1/manual/xr-simulation/simulation.html>

_Note: you can easily change the plugin version in docs to the one your project is using._
