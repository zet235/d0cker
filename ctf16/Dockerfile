FROM phusion/baseimage:0.9.19

RUN sed -i 's/archive.ubuntu.com/free.nchc.org.tw/g' /etc/apt/sources.list && \
    echo 'deb http://www.emdebian.org/debian/ squeeze main' >>  /etc/apt/sources.list && \
    apt-get update && \
    apt-get dist-upgrade -y && \
    # linux env
    apt-get install -y zsh man tmux wget sudo git zip unzip tar gzip bzip2 nasm && \
    # binary lib and package
    apt-get install -y gcc-multilib emdebian-archive-keyring zlib1g-dev liblzma-dev liblzo2-dev g++-4.8-multilib libssl-dev libffi-dev build-essential && \
    apt-get install -y --force-yes binutils-mips-linux-gnu binutils-mipsel-linux-gnu binutils-arm-linux-gnueabi && \
    # debug tools
    apt-get install -y strace ltrace gdb && \
    # other
    apt-get install -y mtd-utils arj lhasa p7zip p7zip-full cabextract cramfsprogs cramfsswap squashfs-tools sleuthkit default-jdk lzop srecord && \
    # qemu
    apt-get install -y qemu-user-static && \
    # python
    apt-get install -y python2.7 ipython python-pip python-dev python-lzma python-crypto && \
    pip install --upgrade pip && \
    pip install nose coverage && \
    # get CTF tools
    git clone --recursive https://github.com/zet235/ctf-tools.git ~/.ctf-tools && \
    # binwalk
    cd /root/.ctf-tools/binwalk  && \
    sudo python setup.py install && \
    cd /root/.ctf-tools/sasquatch  && ./build.sh && \
    # install ncat
    apt-get install -y netcat-traditional netcat-openbsd nmap && \
    # pwntools
    pip install --upgrade pwntools && \
    # ssh
    rm -f /etc/service/sshd/down && \
    /etc/my_init.d/00_regen_ssh_host_keys.sh && \
    
    chsh -s /bin/zsh


EXPOSE 22 3002 3003
