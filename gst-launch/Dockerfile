ARG UBUNTU_VERSION=20.04

FROM ubuntu:$UBUNTU_VERSION

ARG UBUNTU_VERSION

RUN sed -i 's/archive.ubuntu.com/mirrors.ustc.edu.cn/g' /etc/apt/sources.list && \
  sed -i 's/security.ubuntu.com/mirrors.ustc.edu.cn/g' /etc/apt/sources.list

# tzdata
RUN apt-get update && \
  apt-get install -y tzdata

RUN apt-get update && \
  apt-get install -y \
  gstreamer1.0-plugins-base \
  gstreamer1.0-plugins-good \
  gstreamer1.0-plugins-bad \
  gstreamer1.0-plugins-ugly \
  gstreamer1.0-libav \
  gstreamer1.0-vaapi \
  gstreamer1.0-tools \
  gstreamer1.0-rtsp \
  gstreamer1.0-nice

ENV TZ=Asia/Shanghai
ENV GST_DEBUG=WARN
ENV GST_DEBUG_NO_COLOR=1

# remove all package lists
RUN rm -rf /var/lib/apt/lists/*

CMD gst-launch-1.0 --version
