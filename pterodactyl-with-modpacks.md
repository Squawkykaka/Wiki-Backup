---
title: How to run a Pterodcatyl server with a Modpack
description: 
published: true
date: 2024-02-13T19:30:33.957Z
tags: servers, pterodactyl, minecraft, modpacks
editor: markdown
dateCreated: 2024-02-13T02:13:31.850Z
---

# Requirements
1. A working copy of pterodactyl. Look at [Setting up Pterodactyl](/setting-up-pterodactyl) for instructions on setup.

2. An [forge enhanced](https://github.com/parkervcp/eggs/tree/master/game_eggs/minecraft/java/forge/forge) egg from parkervcpegg added of the panel

# Guide
1. Create a new server in the panel using the forge enhanced egg, but set the startup flags to 
```bash
./run.sh {{SERVER_MEMORY}} {{SERVER_JARFILE}}
```
for a modded server with 60+ mods i recommend at least 12G of ram or else the server crashes.

2. After the server is installed open up the `run.sh` file and paste the following
```
#!/usr/bin/env sh

SERVER_MEMORY=$1
shift
SERVER_JARFILE=$1  
shift

# Start server
java -Xms128M -Xmx${SERVER_MEMORY}M -Dterminal.jline=false -Dterminal.ansi=true @unix_args.txt ${SERVER_JARFILE} "$@"
```

Using this script will mean you have to set a memory and you can't set it to zero.

3. Now you can run the server and everythiing should work.

## Using packwiz

