FROM phusion/baseimage:latest

# apt-get
RUN dpkg --add-architecture i386 && apt-get update \
    && apt-get install -y python2.7 python2.7-dev python-pip wget git

# pwntools
RUN apt-get install -y software-properties-common \
    && apt-add-repository -y ppa:pwntools/binutils \
    && apt-get update \
    && apt-get install -y \
        binutils-i386-linux-gnu \
        binutils-arm-linux-gnu \
        binutils-aarch64-linux-gnu \
        binutils-mips-linux-gnu \
        binutils-mips64-linux-gnu \
    && pip install git+https://github.com/Gallopsled/pwntools#egg=pwntools --upgrade

# add user
RUN groupadd -r pwn && useradd -r -g pwn pwn
USER pwn

ENV TERM linux
ENV PYTHONPATH /var/pwn/utils:$PYTHONPATH
WORKDIR /var/pwn/pwning

CMD ["python", "-u", "pwn_all.py"]
