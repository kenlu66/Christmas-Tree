# 🎄 Grand Luxury Interactive 3D Christmas Tree

> A high-fidelity 3D Christmas Tree web application based on **React**, **Three.js (R3F)**, and **AI Gesture Recognition**.

This project is more than just a tree—it's an interactive gallery that carries memories. Thousands of particles, dazzling fairy lights, floating polaroid photos, custom decorations, and falling snow come together to form a luxurious Christmas tree. Users can control the tree's form (assemble/disperse) and rotate the view through gestures, experiencing a cinematic visual feast.

![Project Preview](public/preview.png)
*(Note: It's recommended to upload a screenshot of your running project here)*

## ✨ Core Features

* **Ultimate Visual Experience**: Tree body composed of 10,000+ glowing particles, combined with dynamic bloom and glow effects to create a dreamy atmosphere.
* **Memory Gallery**: Photos float on the tree in "polaroid" style, each one an independent glowing body with double-sided rendering support. Photos automatically scale smaller at the top for a natural tapering effect.
* **AI Gesture Control**: No mouse needed—control the tree's form (assemble/disperse) and view rotation through camera-captured gestures.
* **Rich Details**: Includes dynamically flickering fairy lights, falling snowflakes, randomly distributed Christmas gifts, candy decorations, and custom image-based decorations (like Hello Kitty!).
* **Snow Effect**: Beautiful falling snow animation with 2000+ snowflakes drifting naturally across the scene.
* **Custom Decorations**: Add your own image-based decorations (characters, icons, etc.) that appear on the tree alongside traditional Christmas elements.
* **Highly Customizable**: **Supports users easily replacing with their own photos, adding custom decorations, and freely adjusting all visual parameters.**

## 🛠️ Tech Stack

* **Framework**: React 18, Vite
* **3D Engine**: React Three Fiber (Three.js)
* **Utility Libraries**: @react-three/drei, Maath
* **Post-Processing**: @react-three/postprocessing
* **AI Vision**: MediaPipe Tasks Vision (Google)

## 🚀 Quick Start

### 1. Environment Setup
Make sure your computer has [Node.js](https://nodejs.org/) installed (recommended v18 or higher).

### 2. Install Dependencies
Open a terminal in the project root directory and run:
```bash
npm install
```

### 3. Start the Project
```bash
npm run dev
```

## 🖼️ Customize Photos

### 1. Prepare Photos
Find the `public/photos/` folder in the project directory.

**Top/Cover Image**: Name it `top.jpg` (will be displayed on the 3D star at the top of the tree).

**Tree Body Photos**: Name them `1.jpg`, `2.jpg`, `3.jpg` ... and so on.

**Recommendations**: Use square or 4:3 aspect ratio images, file size should not be too large (recommended under 500kb per image for smooth performance).

### 2. Replace Photos
Simply copy your own photos to the `public/photos/` folder, overwriting the existing images. Please keep the filename format unchanged (`1.jpg`, `2.jpg`, etc.).

### 3. Modify Photo Count (Increase or Decrease)
If you've added more photos (e.g., increased from the default 20 to 50), you need to modify the code to tell the program to load them.

Open the file: `src/App.tsx`

Find the code around line 19:
```typescript
// --- Dynamically generate photo list (top.jpg + 1.jpg to 20.jpg) ---
const TOTAL_NUMBERED_PHOTOS = 20; // <--- Change this number! (Currently set to 20)
```

## 🎨 Custom Decorations

### Add Your Own Decoration Images

You can add custom image-based decorations (like Hello Kitty, characters, icons, etc.) that will appear on the tree alongside traditional Christmas elements.

1. **Place your images** in the `public/decorations/` folder
2. **Update the code** in `src/App.tsx` around line 257:
   ```typescript
   const customDecorationPaths = [
     '/decorations/hello-kitty.png',
     '/decorations/hello-kitty2.png',
     // Add more images here...
   ];
   ```
3. **Refresh your browser** to see your custom decorations on the tree!

**Tips**:
- Use PNG format with transparent backgrounds for best results
- Square images (1:1 aspect ratio) work best
- Keep file sizes under 500KB each
- Custom decorations appear 3x larger than other elements by default

## 🖐️ Gesture Control Instructions

* **This project has a built-in AI gesture recognition system. Please stand in front of the camera to operate (there's a DEBUG button in the bottom-right corner to view the camera feed)**:

| Gesture | Action | Effect |
|---------|--------|--------|
| 🖐 Open Palm | Disperse | Christmas tree explodes into particles and photos flying everywhere |
| ✊ Closed Fist | Assemble | All elements instantly assemble into a perfect Christmas tree |
| 👋 Move hand left/right | Rotate view | Hand moves left, tree rotates left; hand moves right, tree rotates right (faster rotation enabled) |
| 👋 Move hand up/down | Tilt view | Hand moves up, view angle raises; hand moves down, view angle lowers |

## ⚙️ Advanced Configuration

* **If you're familiar with code, you can adjust more visual parameters in the CONFIG object in `src/App.tsx`**:
  ```typescript
  const CONFIG = {
    colors: { ... }, // Modify tree, lights, and border colors
    counts: {
      foliage: 10000,   // Modify foliage particle count (optimized to default 10000, adjust based on performance)
      ornaments: 150,   // Modify number of hanging photos/polaroids (optimized to default 150, adjust based on performance)
      elements: 100,    // Modify number of Christmas elements (optimized to default 100)
      lights: 250       // Modify number of fairy lights (optimized to default 250, adjust based on performance)
    },
    tree: { height: 33, radius: 14 }, // Modify tree size (currently set to 33/14 for a larger tree)
    // ...
  };
  ```

### Other Customizations

- **Snow Effect**: Adjust snow count and speed in the `Snow` component (around line 402)
- **Photo Scaling**: Photos automatically scale smaller at the top (50% at top, 100% at bottom)
- **Rotation Speed**: Gesture-based rotation speed can be adjusted (line 586)
- **Title**: Customize the title "Merry Christmas Vicky" in the UI section (around line 656)

## 📄 License
MIT License. Feel free to use and modify for your own holiday celebrations!

## Merry Christmas! 🎄✨
