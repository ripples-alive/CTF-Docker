# CTF Docker

This is a docker compose project for running some useful scripts in CTF competitions.

## Usage

```sh
git clone https://github.com/ripples-alive/CTF-Docker.git --recursive
cd CTF-Docker
docker-compose build
docker-compose up -d
```

If you need to install extra dependency to run the pwning scripts, exec a shell on the pwn_all container:

```sh
docker-compose exec bash
```

Then, you can freely run any dependency installation commands.
