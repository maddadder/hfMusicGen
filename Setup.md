1. Follow these instructions to host the web server

```bash
conda create --name MusicGen python=3.9
conda activate MusicGen
pip install -r requirements.txt
pip install gradio
conda install "ffmpeg<5" -c conda-forge


conda activate MusicGen
python app.py --listen 0.0.0.0

```
