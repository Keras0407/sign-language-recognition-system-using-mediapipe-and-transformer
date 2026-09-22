# Sign Language Recognition System

Sign language recognition using **MediaPipe** and a **Transformer**, with a **VGB-style start/end confirmer** (AdaBoost + Random Forest + hangover) that runs offline on Windows 10 / Python 3.10 / RTX 5060.

## Download (GitHub Release — each file is under 1.5 GB)

GitHub will not keep a single file over ~1.5–2 GB. The offline bundle is therefore **three split zip volumes**. `training_datasets/` (66 GB of images) is **not** included.

- [Part 1](https://github.com/Keras0407/sign-language-recognition-system-using-mediapipe-and-transformer/releases/download/v1.0.0/ny_paper_offline.zip.001) — 1.37 GiB (1400 MiB)
- [Part 2](https://github.com/Keras0407/sign-language-recognition-system-using-mediapipe-and-transformer/releases/download/v1.0.0/ny_paper_offline.zip.002) — 1.37 GiB (1400 MiB)
- [Part 3](https://github.com/Keras0407/sign-language-recognition-system-using-mediapipe-and-transformer/releases/download/v1.0.0/ny_paper_offline.zip.003) — 726 MiB

**How to extract on the offline laptop**

1. Download **all three** files into the **same folder**. Do not rename them.
2. Open **`ny_paper_offline.zip.001`** in **7-Zip** or **WinRAR**.
3. Extract. Windows Explorer cannot open a split zip.
4. Do **not** join/merge the parts with `copy /b`.

Inside: `python_libraries/` (76 wheels), `vgb/` (VGB GitHub + papers), `github_projects/`, `references/` (papers), `endpointing/`, `slr_vgb/` (working confirmer), `paper/` (thesis).

## Install on the offline RTX 5060 laptop

CUDA 12.9 and cuDNN 9.12 are already on the machine. Do not reinstall them.

1. `python_libraries\INSTALL.bat` — creates `slr_venv`, installs **PyTorch 2.11.0+cu128** from the local wheels (no internet).
2. `slr_vgb\00_SELFTEST.bat` — proves hold ≠ rest (no videos, no CUDA).
3. Put isolated `.mp4` files in `slr_vgb\data\videos\`, then `01_EXTRACT.bat` → `02b_WEAK_LABEL.bat` → `02_TRAIN.bat`.

## Start and end of a sign

MediaPipe does not cut signs. Read `HOW_SLR_CONFIRMS_START_END.txt`.

- Today’s translation systems (CTC / Transformer) usually do **not** output frame times.
- When they need cuts they use **BIO** tags (`github_projects/sign_boundaries/`).
- VGB (Kinect AdaBoost False→True / True→False + hangover) is reimplemented for this laptop in `slr_vgb/`.
