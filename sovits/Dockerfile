FROM pytorch/pytorch:1.13.1-cuda11.6-cudnn8-runtime
# other: pytorch/pytorch:1.12.1-cuda11.3-cudnn8-runtime

# Install dependencies for Go
RUN apt-get update && \
    apt-get install -y gcc g++

WORKDIR /app

# RUN git clone -b 4.0 https://github.com/svc-develop-team/so-vits-svc

RUN pip install fairseq==0.12.2 librosa==0.10.0.post2 matplotlib==3.7.1 praat-parselmouth==0.4.3
RUN pip install torchaudio==0.13.1 --index-url https://download.pytorch.org/whl/cu116
# WORKDIR /so-vits-svc
# RUN wget -P logs/44k/ https://huggingface.co/marcoc2/so-vits-svc-4.0-models/resolve/main/DavidBowie/G_7200.pth
# RUN wget -P hubert/ https://huggingface.co/cr941131/sovits-4.0-v2-hubert/resolve/main/checkpoint_best_legacy_500.pt
# RUN wget -P raw/ https://www2.cs.uic.edu/\~i101/SoundFiles/taunt.wav
# RUN wget -q https://huggingface.co/marcoc2/so-vits-svc-4.0-models/resolve/main/DavidBowie/config.json -o configs/config.json

# docker run -it -v $(pwd)/so-vits-svc:/app sov bash
cmd python inference_main.py -m "logs/44k/G_7200.pth" -c "configs/config.json" -n "taunt.wav" -t 0 -s "bowie"
