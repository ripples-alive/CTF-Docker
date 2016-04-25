# CTF Docker

This is a docker compose project for running some useful scripts in CTF competitions.

## Usage

```sh
git clone git@github.com:ripples-alive/CTF-Docker.git
cd CTF-Docker
docker-compose build
docker-compose up -d
```

If you need to install extra dependency to run the pwning scripts, exec a shell on the pwn_all container:

```sh
docker exec -it ctfdocker_pwn_all_1 /bin/bash
```

Then, you can freely run any dependency installation commands.
