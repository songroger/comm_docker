FROM deezer/spleeter:3.6-5stems

WORKDIR /input

# RUN wget https://github.com/deezer/spleeter/raw/master/audio_example.mp3

# sudo docker run -v $(pwd)/output:/output -v $(pwd)/input:/input -v $(pwd)/model:/model -e MODEL_PATH=/model image_tag separate -p spleeter:2stems -o /output /input/te.mp3
# sudo docker run --rm -v $(pwd)/output:/output -v $(pwd)/input:/input sp separate -p spleeter:2stems -o /output /input/te.mp3 -f {foldername}/{filename}_{instrument}.mp3

ENTRYPOINT ["spleeter"]
