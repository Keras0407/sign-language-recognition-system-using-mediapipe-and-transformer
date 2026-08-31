# sign-language-recognition-system-using-mediapipe-and-transformer

Offline Windows kit for a **sign language recognition** paper pipeline:

- **MediaPipe** Hands / Face Mesh (lips) / Pose / Holistic as the landmark front-end
- **PyTorch** recognizer (BiLSTM / Transformer / ST-GCN) trained on cached landmarks
- Author laptop: Windows 10, Python 3.10, RTX 5060, CUDA 12.9 — see `dev_com_spec.txt`

This GitHub **git** tree is documentation and pointers only. The large wheels, papers, and companion code are in a **Release** (GitHub does not allow a 4.6 GB file inside `git push`).

## Download the project files

**Release page (all parts):**  
https://github.com/Keras0407/sign-language-recognition-system-using-mediapipe-and-transformer/releases/latest

Download **every** `ny_paper_offline_slim.part*.rar` into the **same folder**, then open **part 1** in WinRAR and extract. WinRAR joins the parts automatically.

| Part | What to click |
|------|----------------|
| Part 1 | [ny_paper_offline_slim.part1.rar](https://github.com/Keras0407/sign-language-recognition-system-using-mediapipe-and-transformer/releases/download/v1.0.0/ny_paper_offline_slim.part1.rar) |
| Part 2 | [ny_paper_offline_slim.part2.rar](https://github.com/Keras0407/sign-language-recognition-system-using-mediapipe-and-transformer/releases/download/v1.0.0/ny_paper_offline_slim.part2.rar) |
| Part 3 | [ny_paper_offline_slim.part3.rar](https://github.com/Keras0407/sign-language-recognition-system-using-mediapipe-and-transformer/releases/download/v1.0.0/ny_paper_offline_slim.part3.rar) |

After extract you get `python_libraries/`, `references/`, MediaPipe + unofficial trainers, and Deep Learning with PyTorch companion **code** (no LUNA/FreiHAND image dumps).

On the laptop:

```bat
python_libraries\INSTALL_OFFLINE.bat
```

Use **PyTorch 2.11.0+cu128** from that folder. Do not `pip install` from the internet.

## Not in this download (too large)

- `training_datasets/` (~66 GB): FreiHAND, WFLW, WIDER, MPII, LSP
- LUNA16 CT `data-unversioned/` (~18 GB)
- Official MediaPipe ~30K training images (Google never released them)

Those stay on the build machine. Papers and dataset **links** are in `references/`.

## License / cite

MediaPipe, dataset, and paper licenses still apply. Cite Zhang 2020 (Hands), Kartynnik 2019 (Face Mesh), Grishchenko 2020 (Attention Mesh), Bazarevsky 2020 (BlazePose) when you use those models.
