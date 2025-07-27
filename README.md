# cc-minecraft

Run a Minecraft server on [Clever Cloud](https://www.clever-cloud.com/).

Using the new [Linux application runtime](https://www.clever-cloud.com/developers/doc/applications/linux/)
we can run arbitrary scripts (without Docker) using [mise-en-place](https://mise.jdx.dev/).

## Requirements

Since Minecraft servers cannot run in parallel, we need to ensure that only one instance of the server is running at a time.

- Disable "Zero downtime deployment"
- Only use 1 instance on the "Horizontal scaling" slider

For persistent storage, use a [FS bucket](https://www.clever-cloud.com/developers/doc/addons/fs-bucket/) addon.

## Configuration

Environment variables:

- `MINECRAFT_VERSION`: The version of Minecraft to run. Defaults to `1.21.8`.
- `MINECRAFT_EULA`: The EULA to accept. Defaults to `false`.
- `MINECRAFT_DIR`: The directory to store the server in. Defaults to `/minecraft`.

- `MINECRAFT_SERVER_PROPERTIES_DIFFICULTY`: The difficulty of the server. Defaults to `easy`.
- `MINECRAFT_SERVER_PROPERTIES_GAMEMODE`: The game mode of the server. Defaults to `survival`.
- `MINECRAFT_SERVER_PROPERTIES_LEVEL_SEED`: The seed for the world. Defaults to "".
- `MINECRAFT_SERVER_PROPERTIES_MAX_PLAYERS`: The maximum number of players allowed on the server. Defaults to `20`.
- `MINECRAFT_SERVER_PROPERTIES_MOTD`: The message of the day displayed to players. Defaults to `A Minecraft Server`.
- `MINECRAFT_SERVER_PROPERTIES_ONLINE_MODE`: Whether the server requires players to be online. Defaults to `true`.
- `MINECRAFT_SERVER_PROPERTIES_SERVER_PORT`: The port to run the server on. Defaults to `4040` (Clever Cloud allows only TCP port `4040`)
- `MINECRAFT_SERVER_PROPERTIES_SIMULATION_DISTANCE`: The distance in chunks that the server simulates. Defaults to `10`.
- `MINECRAFT_SERVER_PROPERTIES_SPAWN_PROTECTION`: The radius in blocks around the spawn point that is protected. Defaults to `16`.
- `MINECRAFT_SERVER_PROPERTIES_VIEW_DISTANCE`: The distance in chunks that players can see. Defaults to `10`.
