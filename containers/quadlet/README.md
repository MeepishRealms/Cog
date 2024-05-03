# Quadlet for Podman
The recommended method to run Modded Expansion on Podman is using Quadlets. Modern versions of Podman should come with quadlet functionality out-of-the-box.

*You can also use `podman-compose` along with the `docker-compose.yml` file in the containers folder as well, but this functionality will need to be installed separately.*

To begin, download the `mrme.container` and `mrme.volume` files within this folder onto your Linux server.

Next, decide if you want to run Modded Expansion as a rootful or rootless container.

## Rootless Installation (Recommended)
1. `cd` into the folder where you placed the Quadlet files.
2. Move both `mrme.container` and `mrme.volume` into `~/.config/containers/systemd/`.
```
$ mv mrme.container mrme.volume ~/.config/containers/systemd/
```
3. Reload the systemd user daemon.
```
$ systemctl --user daemon-reload
```
4. Start the MR:ME service.
```
$ systemctl --user start mrme.service
```

The container will now automatically start and self-update on future boots.

## Rootful Installation
All commands for this set of instructions past the first step are required to be run as root, using `sudo` or otherwise.
1. `cd` into the folder where you placed the Quadlet files.
2. Move both `mrme.container` and `mrme.volume` into `/etc/containers/systemd/`.
```
# mv mrme.container mrme.volume /etc/containers/systemd/
```
3. Reload the systemd system daemon.
```
# systemctl daemon-reload
```
4. Start the MR:ME service.
```
# systemctl start mrme.service
```

The container will now automatically start and self-update on future boots.
