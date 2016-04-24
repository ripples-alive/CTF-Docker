FROM phusion/baseimage:latest

# apt-get
RUN apt-get update && apt-get install -y python2.7 python-requests

# add user
RUN groupadd -r pwn && useradd -r -g pwn pwn
USER pwn

WORKDIR /var/pwn/pwning
EXPOSE 8888

CMD ["python2.7", "-u", "receive_flag.py"]
