# docker-paper-server
A Paper server with an auto-updater

## Initial setup
1. Extract this repository's files into a directory and `cd` into it
2. Build the image with `docker-compose build --no-cache`
3. Configure your environment variables in `docker-compose.yml` (Refer to the [environment variables](#Environment-variables) section)
4. [Start the server](#starting-the-server)

The updater script will automatically install the Paper build and Minecraft version you have selected. To enable auto-updating, set `PAPER_BUILD` to `latest`.

## Command reference 
### Starting the server
```docker-compose up -d```

### Stopping the server
```docker-compose down```

### Attaching to the shell
```docker attach [CONTAINER_NAME]```

### Updating the server
Reboot the server with any method you desire

## Environment variables
|Name|Purpose|Default value|
|-|-|-|
|JVM_ARGS|Any JVM arguments such as GC options or memory amount|`-Xmx8G`|
|PAPER_ARGS|Paper launch arguments (It's best to leave `--nogui`, if making changes)|`--nogui`|
|MC_RELEASE|Minecraft version (See a list of supported versions [here](https://papermc.io/api/v1/paper))|`1.16.4`|
|PAPER_BUILD|Which build of Paper to download|`latest`|
|USER|Which user to set file permissions for|`1000`|
|GROUP|Which group to set file permissions for|`1000`|