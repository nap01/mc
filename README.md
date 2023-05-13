# Minecraft Docker Repo

1. Run this to download the Repo

```bash
git clone https://github.com/nap01/mc ~/mc
```

If you don't have git, follow this guide to download.

2. Run this to add the directories to mount as volumes:

```bash
mkdir ~/mc/data
mkdir ~/mc/data/plugins
mkdir ~/mc/data/config
mkdir ~/mc/data/mods
```

3. To start/stop the container run
4. 
```bash
docker compose up -d
```

or

```bash
docker compose down -d
```
