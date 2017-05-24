#ubuntu 14
FROM phusion/baseimage:0.9.17

RUN sed -i 's/archive.ubuntu.com/free.nchc.org.tw/g' /etc/apt/sources.list && \
    apt-get update && \
    apt-get dist-upgrade -y && \
    apt-get install -y mtd-utils gzip bzip2 tar arj lhasa p7zip p7zip-full cabextract cramfsprogs cramfsswap squashfs-tools sleuthkit default-jdk lzop srecord && \
    apt-get install -y python-lzma python-crypto && \
    pip install nose coverage