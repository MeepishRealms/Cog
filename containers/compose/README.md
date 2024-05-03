# Docker Compose
The recommended method to run Modded Expansion on Docker is using Docker Compose. Modern versions of Docker should come with compose functionality out-of-the-box.

**Note: Docker versions using a Windows kernel are not supported.**

## Installation

- Download the `docker-compose.yml` file within this folder onto your Linux server.
- `cd` into the directory where it is stored.
- Run the following command:
```
$ docker compose up -d
```

If your user is NOT part of the `docker` group, you will need to run the aforementioned command as root using `sudo` or other methods.