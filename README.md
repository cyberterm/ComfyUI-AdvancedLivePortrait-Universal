# ComfyUI-AdvancedLivePortrait (Universal Support Fork)

> Advanced LivePortrait with interactive facial expression editor, animation chaining, and real-time preview — engineered for native cross-platform execution.

### 🌐 Universal Device & Hardware Support
Unlike the original CUDA-only implementation, this fork integrates seamlessly with ComfyUI's native device management:

-  **Intel Arc & Data Center GPUs (XPU)** — Full acceleration via PyTorch XPU backend
-  **NVIDIA GPUs (CUDA)** — Native CUDA acceleration
-  **Apple Silicon (MPS)** — Metal Performance Shaders acceleration on Mac (M1/M2/M3/M4)
-  **AMD GPUs (ROCm / DirectML)** — Supported through ComfyUI device mapping
-  **CPU Fallback** — Automatically supported if ComfyUI is launched in CPU mode (`--cpu`)

### Features
- **ExpressionEditor**: Interactive slider-based expression adjustments (smile, wink, eyebrow, gaze, mouth shapes, head pose) with real-time UI preview.
- **Animation Chaining**: Multi-keyframe facial expression sequences with automated smoothing and interpolation.
- **Expression Presets**: Save and load lightweight reusable `.exp` expression files (`SaveExpData`, `LoadExpData`).

---

## Introduction

AdvancedLivePortrait is faster and has real-time preview

https://github.com/user-attachments/assets/90b78639-6477-48af-ba49-7945488df581

- Edit facial expressions in photos.
- Insert facial expressions into videos.
- Create animations using multiple facial expressions (with or without driving video).
- Extract facial expressions from sample photos.
- Track faces across video frames.

## Installation

Clone this repository into your `ComfyUI/custom_nodes/` directory:

```bash
cd custom_nodes
git clone https://github.com/cyberterm/ComfyUI-AdvancedLivePortrait-Universal.git
```

## Usage

Workflows and sample data are located in `custom_nodes/ComfyUI-AdvancedLivePortrait-Universal/sample/workflows/`

-----

You can add expressions to the video. See `Advanced_Inserting_expressions_into_vid.json` or other sample workflows.

Describes the 'command' in the workflow:

![readme](https://github.com/user-attachments/assets/339568b2-ad52-4aaf-a6ab-fcd877449c56)

`[Motion index] = [Changing frame length] : [Length of frames waiting for next motion]`

- Motion index 0 is the original source image.
- They are numbered in the order they lead to the `motion_link`.
- Linking the driving video to `src_images` will add facial expressions to the driving video.

-----

You can save and load expressions with the **Load Exp Data** and **Save Exp Data** nodes.

Expression data is saved to `\ComfyUI\output\exp_data\`.

-----

## Thanks

- Original author's link : https://liveportrait.github.io/
- Upstream ComfyUI implementation: https://github.com/PowerHouseMan/ComfyUI-AdvancedLivePortrait
- This project uses models converted by kijai: https://github.com/kijai/ComfyUI-LivePortraitKJ