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


2. Deploy as a service

```bash
chmod +x app.sh
sudo cp hfmusicgen.service /etc/systemd/system/hfmusicgen.service
sudo systemctl daemon-reload
sudo systemctl start hfmusicgen
sudo systemctl restart hfmusicgen
sudo systemctl enable hfmusicgen
sudo systemctl status hfmusicgen
```