# sign-language-recognition-system-using-mediapipe-and-transformer

Offline Windows kit for a **sign language recognition** paper pipeline:

- **MediaPipe** Hands / Face Mesh (lips) / Pose / Holistic as the landmark front-end
- **PyTorch** recognizer (BiLSTM / Transformer / ST-GCN) trained on cached landmarks
- Author laptop: Windows 10, Python 3.10, RTX 5060, CUDA 12.9 — see `dev_com_spec.txt`

This GitHub **git** tree is the project page and download pointers. The wheels, papers, MediaPipe trees, and companion code are **not** inside `git push` (GitHub rejects files over 100 MB). They are attached to a **Release**.

## Download the project files

**Release page (all parts):**  
https://github.com/Keras0407/sign-language-recognition-system-using-mediapipe-and-transformer/releases/latest

GitHub allows at most **2 GB per Release file**. The archive is therefore split. Download **every** part into the **same folder**, then open **part 1** in **WinRAR** and Extract. WinRAR joins the parts automatically.

| Part | Direct download |
|------|-----------------|
| Part 1 | https://github.com/Keras0407/sign-language-recognition-system-using-mediapipe-and-transformer/releases/download/v1.0.0/ny_paper_offline_slim.part1.rar |
| Part 2 | https://github.com/Keras0407/sign-language-recognition-system-using-mediapipe-and-transformer/releases/download/v1.0.0/ny_paper_offline_slim.part2.rar |
| Part 3 | https://github.com/Keras0407/sign-language-recognition-system-using-mediapipe-and-transformer/releases/download/v1.0.0/ny_paper_offline_slim.part3.rar |

Unpacked contents: `python_libraries/`, `references/`, official MediaPipe + unofficial trainers, Deep Learning with PyTorch companion **code**. No FreiHAND/WFLW/WIDER/LUNA image dumps.

On the laptop:

```bat
python_libraries\INSTALL_OFFLINE.bat
```

Use **PyTorch 2.11.0+cu128** from that folder. Do not `pip install` from the internet.

## Not in this download (too large)

- `training_datasets/` (~66 GB): FreiHAND, WFLW, WIDER, MPII, LSP
- LUNA16 CT `data-unversioned/` (~18 GB)
- Official MediaPipe ~30K training images (Google never released them)

Papers and dataset **links** are in `references/` inside the RAR.

## Cite

Zhang 2020 (Hands), Kartynnik 2019 (Face Mesh), Grishchenko 2020 (Attention Mesh), Bazarevsky 2020 (BlazePose).
