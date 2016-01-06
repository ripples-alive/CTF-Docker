FROM phusion/baseimage:latest

# apt-get
RUN dpkg --add-architecture i386 && apt-get update \
    && apt-get install -y python2.7 python2.7-dev python-pip wget

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
    && pip install pwntools

# add user
RUN groupadd -r pwn && useradd -r -g pwn pwn
USER pwn

ENV PYTHONPATH /var/pwn/utils:$PYTHONPATH
WORKDIR /var/pwn/pwning

CMD ["python", "pwn_all.py"]
