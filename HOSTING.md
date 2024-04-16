# Server Hosting
We only have two official methods of hosting Project Cog, for self-hosting and for use with a server provider.

## Server Providers
Project Cog works with server providers that support custom file upload. We recommend [WitherHosting](https://witherhosting.com/). In the future, Project Cog will also support providers that support Modrinth modpacks.

For providers that support custom file upload, download the `cog_vX.X.X-server.zip` file, extract the files out, and upload the contents into your server's root (.minecraft) directory. If your provider supports server-side extraction, upload the `.zip` file and extract it server-side.

If you have a server provider wonderful enough to support custom Modrinth modpack upload, the process should be seamless. Just upload the latest `.mrpack` release. (Curseforge may not work on servers!)

## Containerized Hosting
For VPS/Cloud hosting or self-hosting on your own hardware, we only officially support containerized hosting on Linux. If you wish to host the traditional way, you can install Forge server for Minecraft 1.20.1, and extract `cog_vX.X.X-server.zip` to your server directory. 

### via Docker Compose
1. Make sure Docker is installed and up-to-date.
2. Download `docker-compose.yml` from the root of this repository onto your server. 
3. `cd` into the directory where you stored the Compose file on your server.
4. Run `docker compose up -d`.

### via Quadlet for Podman (Recommended)
1. Make sure your system and Podman is up-to-date.
2. Download `cog.container` from the root of this repository onto your server.
3. Move `cog.container` to to `~/.config/systemd/containers/`
4. Run `systemctl --user daemon-reload`.
5. Run `systemctl --user start cog`.

### How to Delete or Manage World Data
- To delete your data, run `docker volume rm cog_data` or `podman volume rm cog_data`.
- For file modification purposes, your data is stored at `/var/lib/docker/volumes/cog_data` for Docker or `~/.local/share/containers/storage/volumes/cog_data` for Podman.
- **Warning**: Manually editing files is NOT recommended and will likely mess up file permissions and cause the server to fail to start. Make sure to check the file ownership of the files before editing, and then `sudo chown` it back.
