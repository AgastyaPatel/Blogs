---
title: "FastAI Setup"
author: "Agastya Patel"
date: "2023-12-29"
date-modified: "2023-12-30"
categories: [Notes, FastAI, Tools]
---
In this section we'll be going through the setting up the wsl for FastAI.

> Read more about mamba, conda and all package managers in [Package Manager and Environment](../Utility/Package Manager and Virtual Environments.md)

## Setting up Windows Subsystem

- Set wsl 
- get the miniforge/mambaforge(deprected)
- run the miniforge.sh
- `mamba install ipython`
- `mamba install jupyter lab`
- `mamba install pytorch`
- `conda install fastai`

# Useful Bash Commands Tables
| Command | Action |
| ---- | ---- |
| `ls -l` | get long form (file, data, size-bytes) |
| `ls -l -h` | human readable data like the size of the file in MB |
| `less <filename>` | Open the file |
| `wget <url>` | Download file |
| `sudo -u <user> -i` | Change user |
| ctrl+d | Exit any application running in shell |
| `! <some_letter>` | Opens similar letter recent application Eg; `!ju` # Might open jupyterLab |
| `!!` | Opens last command |
| `cd --` | Most recent Directory |
| `pushd ~` | Stash Dir |
| `popd` | Unstash Dir (Pop Dir) |
| echo $ENV_VAR<br>`echo $PATH` | Returns value of environment variables like Path Variable |
| `df -h` | disk usage |
| `logout` | exit |
| ls . \| Head | Show first 10 |
| ls . \| Tail | Show last 10 |
| ls . \| wc -l | Gives number of lines (items) |
| ls . \| grep 33 | Search 33 |
|  |  |

# Mamba Commands
1. Create new environment
   ==`mamba create -n <env_name> <dependency>`==
   `mamba create -n tmp 'python<3.10' fastcore` 
2. Activate/deactivate
   `mamba activate <env_name>`
   `mamba deactivate`

# PIP Commands
`pip -U <library>` : Upgrade library
`pip -U --user <library>` : Installs library in User Directory in `.local` folder

# Miscellaneous

### tmux
`sudo apt install tmux`

| Command | Action |
| ---- | ---- |
| `ctrl + b %`<br>`ctrl + b "` | Split Pane horizontal and vertical |
| `ctrl + b Arrow` | Focus around Panes |
| `ctrl + b d` | Delete Pane |
| `ctrl + b z` | Zoom into/out-of pane |
|  |  |

## nvidia-smi
`nvidia-smi dmon`: Chec for sm and mem column

## Symblinks
### Linux
`ln -s target-path` : Creates a symblink of the target directory in current directory
`ln -la` : Displays the folders who are made up of symblink

### Windows
[Youtube Tutorial](https://www.youtube.com/watch?v=2uy4mR3q_jM)

## Cloud Environments
### Paperspace
Q. How to set common library?

1. pip install `--user` with this flag so that the lib is installed in `.local`
2. move the `.local` to `/storage/.local`
3. create symblink from `/storage/.local` as target and it would create `.bash.local` in `storage` which would fire up time new instance has been called