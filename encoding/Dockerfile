# FROM continuumio/anaconda
# # RUN conda install -c weiyan scikit-audiolab -y
# RUN apt-get update && apt-get upgrade -y
# RUN apt-get install mlocate -y
# RUN apt-get install libasound2-dev python-dev python-numpy python-setuptools libsndfile-dev -y
# RUN pip install https://grrrr.org/data/dev/purehuff/purehuff-0.2.tar.gz
# RUN ln -s /usr/lib/x86_64-linux-gnu/libsndfile.so.1 /usr/local/lib/libsndfile.so
# RUN ln -s /usr/lib/x86_64-linux-gnu/libasound.so.2 /usr/local/lib/libasound.so
# #RUN pip install scikits.audiolab
# ADD audio2huff.py /audio2huff.py
# #ENTRYPOINT ["python", "audio2huff.py"]
# ENTRYPOINT [ "bin/bash" ]

FROM ubuntu:latest
RUN apt-get update && apt-get upgrade -y
RUN apt-get install python-dev python-numpy python-setuptools python-pip libsndfile-dev -y &&\
  apt-get install libasound2-dev -y
RUN pip install scikits.audiolab
RUN pip install https://grrrr.org/data/dev/purehuff/purehuff-0.2.tar.gz
RUN apt-get install vim -y
ADD audio2huff.py /audio2huff.py
ADD sound.wav /sound.wav
RUN python audio2huff.py --sndfile=sound.wav --hdrfile=sounddata.h --bits=8 --name=creature
ENTRYPOINT [ "bin/bash" ]