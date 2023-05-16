# Minecraft Docker Repo

## 1. Run this to download the Repo

```bash
git clone https://github.com/nap01/mc ~/git/mc
```

*If you don't have git, follow [this guide](https://github.com/git-guides/install-git) to install.*

## 2. Add the directories that we will mount as volumes:

You can run `sudo chmod +x data.sh` & `sudo ./data.sh`

*or*

Run the following manually:

```bash
mkdir ./data
mkdir ./data/plugins
mkdir ./data/config
mkdir ./data/mods
```

## 3. Start/stop the container:

To test if the config works, run:

```bash
docker compose up
```

Typically, you start it detached with:

```bash
docker compose up -d
```

and stop it with:

```bash
docker compose down
```
## 4. Controlling the server 

RCON is enabled by default, so you can exec into the container to access the Minecraft server console:

```bash
docker exec -i mc rcon-cli
```

Note: The -i is required for interactive use of rcon-cli.

To run a simple, one-shot command, such as stopping a Minecraft server, pass the command as arguments to rcon-cli, such as:

```bash
docker exec mc rcon-cli stop
```

The -i is not needed in this case.

If rcon is disabled you can send commands by passing them as arguments to the packaged mc-send-to-console script. For example, a player can be op'ed in the container mc with:

```bash
docker exec mc mc-send-to-console op player
            |                     |
            +- container name     +- Minecraft commands start here
```

In order to attach and interact with the Minecraft server, add -it when starting the container, such as

```bash
docker run -d -it -p 25565:25565 --name mc itzg/minecraft-server
```

With that you can attach and interact at any time using

```bash
docker attach mc
```

and then Control-p Control-q to detach.
