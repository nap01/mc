# Minecraft Docker Repo

1. Run this to download the Repo

```bash
git clone https://github.com/nap01/mc ~/mc
```

If you don't have git, follow this guide to download.

2. Run this to add the directories to mount as volumes if they do not already exist:

```bash
[[ ! -d ~/mc/data ]] && mkdir ~/mc/data
[[ ! -d ~/mc/data/plugins ]] && mkdir ~/mc/data/plugins
[[ ! -d ~/mc/data/config ]] && mkdir ~/mc/data/config
[[ ! -d mkdir ~/mc/data/mods ]] && mkdir ~/mc/data/mods
```
