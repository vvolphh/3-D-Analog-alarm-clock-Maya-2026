# 3D Analog Clock — Maya 2026 Project

## 📝 Description
This project showcases the complete creation of a stylized 3D analog alarm clock inside Autodesk Maya 2026.  
It demonstrates essential 3D production skills including polygon modeling, UV unwrapping, texturing, shading, lighting with Arnold, manual keyframe animation, and rendering an image sequence into a final MP4 video.

The final output includes:
- A high-quality product-style render
- A 10-second clock animation
- A poster summarizing the project
- A walkthrough video (3–5 minutes)
- GitHub version-controlled project files

---

## 🎯 Objective
To design, animate, and render a 3D analog clock while applying the 3D viewing pipeline, transformations, material creation, lighting, Z-buffer/frame buffer concepts, and rendering workflows.

---

## 🛠️ Methodology

### 1. Modeling
- Started with basic polygons: cylinders, spheres, torus, planes.
- Applied **extrusions**, **bevels**, **scale adjustments**, and **edge loops**.
- Built components: clock body, bells, legs, handle, hammer, hour/minute/second hands.
- Set proper **pivot points** for animation.

### 2. UV Mapping & Texturing
- Used **Planar UV Projection** for the clock face.
- Automatic/Planar UVs for the body and bells.
- Applied a custom **2K clock face PNG texture**.

### 3. Shading
Using Arnold’s `aiStandardSurface`:
- Glossy painted body  
- Metallic bells/legs with high metalness  
- Thin-walled transparent glass  
- Paper-style textured face  

### 4. Lighting
- HDRI-based Skydome Light for base illumination.
- Key and rim Arnold Area Lights for product-style highlights.
- Shadow-matte ground plane for clean reflections/shadows.

### 5. Animation
### **✔ Clock animation was done manually.**  
The hour, minute, and second hands were keyframed by hand along the timeline to ensure smooth rotation and correct timing.

### 6. Rendering
- Rendered at **1920 × 1080**, **24 fps**, Arnold Renderer.
- Samples: AA 4–5, Diffuse/Specular/Transmission = 2.
- Rendered a **PNG sequence**.
- Combined into MP4 using ffmpeg:
```bash
ffmpeg -framerate 24 -i clock_%04d.png -pix_fmt yuv420p -crf 18 clock_animation.mp4
