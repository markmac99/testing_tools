#FROM scratch
#LABEL version=0.1
#FROM dorowu/ubuntu-desktop-lxde-vnc
FROM ubuntu:20.04
RUN apt-get update
ENV DEBIAN_FRONTEND noninteractive

RUN apt-get install -y python3.8 python3-pip git \
   python3.8-tk libxslt-dev python-imaging-tk \
   libopencv-dev python3-opencv \
   ffmpeg imagemagick 

RUN ln -s /usr/bin/python3 /usr/local/bin/python
 
WORKDIR /root/source
RUN git clone https://github.com/CroatianMeteorNetwork/RMS.git
WORKDIR /root/source/RMS
RUN pip3 install -r requirements.txt
WORKDIR /
COPY test-data ./RMS_data/
COPY keys ./keys
RUN chmod 0600 ./keys/* && chmod 0700 ./keys
COPY ssh ./sshkeys
RUN chmod 0600 ./sshkeys/* && chmod 0700 ./sshkeys
#RUN python3 setup.py install

#ENV DOCKER_RUNNING true 
#CMD ["/root/RMS_data/config/configure_container.sh"]
