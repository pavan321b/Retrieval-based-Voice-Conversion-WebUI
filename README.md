
# Step-by-Step Instructions for Setting Up Retrieval-based Voice Conversion WebUI

## 1. Install Python Dependencies
Ensure you have Python version 3.8 or higher.

## 2. Install Pytorch
Install Pytorch by running the following command:
```bash
pip install torch torchvision torchaudio
```

## 3. Install CUDA (For Nvidia GPUs)
If using Nvidia Ampere architecture (RTX 30xx), install the appropriate version of Pytorch with CUDA:
```bash
pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu117
```

## 4. Install Additional Requirements
- For Nvidia GPUs:
```bash
pip install -r requirements.txt
```
- For AMD or Intel GPUs:
```bash
pip install -r requirements-dml.txt
```

## 5. Install Poetry (Alternative Method)
If using Poetry for dependency management, install it:
```bash
curl -sSL https://install.python-poetry.org | python3 -
```

Then, initialize your environment and install dependencies:
```bash
poetry init -n
poetry env use "path to your python.exe"
poetry run pip install -r requirements.txt
```

## 6. MacOS Specific Installation
Run the following command to install dependencies:
```bash
sh ./run.sh
```

## 7. Download Pretrained Models
Download necessary models from Hugging Face:
  - `hubert_base.pt`
  - `pretrained`
  - `uvr5_weights`

Place them in the appropriate directories (`./assets/hubert`, `./assets/pretrained`, `./assets/uvr5_weights`).

## 8. Install ffmpeg
If not already installed, use the following commands based on your OS:
- **Ubuntu/Debian:**
```bash
sudo apt install ffmpeg
```
- **MacOS:**
```bash
brew install ffmpeg
```
- **Windows:**
Download and place `ffmpeg.exe` and `ffprobe.exe` in the root directory.

## 9. Download RMVPE Model for Pitch Extraction
Download the `rmvpe.pt` file from Hugging Face and place it in the RVC root directory.

## 10. Start WebUI
Launch the WebUI by running the following command:
```bash
python infer-web.py
```

If using Poetry:
```bash
poetry run python infer-web.py
```

## 11. Additional Setup for Specific GPUs
For AMD ROCm on Linux, install the necessary drivers and configure environment variables if needed.

## 12. Ready to Use
Once the setup is complete, you can start using the WebUI for voice conversion tasks.
