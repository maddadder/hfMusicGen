1. Install conda

```bash
mkdir -p ~/miniconda3
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -O ~/miniconda3/miniconda.sh
bash ~/miniconda3/miniconda.sh -b -u -p ~/miniconda3
rm -rf ~/miniconda3/miniconda.sh
```

2. Follow these instructions to host the web server

```bash
conda create --name MusicGen python=3.9
conda activate MusicGen
pip install -r requirements.txt
pip install gradio
conda install "ffmpeg<5" -c conda-forge


conda activate MusicGen
python app.py --listen 0.0.0.0

```


3. Deploy as a service

```bash
chmod +x app.sh
sudo cp hfmusicgen.service /etc/systemd/system/hfmusicgen.service
sudo systemctl daemon-reload
sudo systemctl start hfmusicgen
sudo systemctl restart hfmusicgen
sudo systemctl enable hfmusicgen
sudo systemctl status hfmusicgen
```