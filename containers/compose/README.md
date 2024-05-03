# Docker Compose
The recommended method to run Modded Expansion on Docker is using Docker Compose. Modern versions of Docker should come with compose functionality out-of-the-box.

**Note: Docker versions using a Windows kernel are not supported.**

## Installation

1. `cd` into the folder where you placed the `docker-compose.yml` file on your server.
2. Run the following command:
```
$ docker compose up -d
```

If your user is NOT part of the `docker` group, you will need to run the aforementioned command as root using `sudo` or other methods.
