## Pyv: Minimalist Python Venv Management Tool
### (Decoupled From Project Directory)

Pyv is a simple shell function that let you make default python virtual environment (venv) management decoupled from project directory. If you ever use conda (anaconda/miniconda), pyv is similar to how conda manage python virtual environment but without python version management. So, please keep in mind that pyv only manage python virtual environment and do not manage your version of python you use.

To make it simpler, pyv is a wrapper around default python venv command `python -m venv` that move the virtual environment directory into `$PYV_DIR`. By default `$PYV_DIR` is `~/.cache/pyv`, you can change that by adding `export PYV_DIR=$HOME/directory/you/want` to your shell config or `.profile`, or you can edit the `pyv` file directly.

### Features

You might ask, "if pyv is only a wrapper around default python virtual environment command, then what makes it different from using default python virtual environment command directly?". Ok, so here's pyv key features:

#### The Command

Pyv command is much shorter than default python venv, here's a list of the command:
- `pce` (you can think it as abbrivation for "pyv create environment")
- `pre` (you can think it as abbrivation for "pyv remove environment")
- `pae` (you can think it as abbrivation for "pyv activate environment")
- `pde` (you can think it as abbrivation for "pyv deactivate environment")
- `pve` (you can think it as abbrivation for "pyv view-list environment")

#### Git Repo Name as Python Venv Name

If you're to lazy to give a name to every python venv you created (like myself), then you can use the git repo name as your python venv name.

#### Familiar Shell Command

Pyv goal is to be a minimalist approach to manage python venv, so you only need python (at least the one that has `python -m venv` command) and git (optional). So, to make pyv as minimal as possible, i only use simple POSIX compliant shell command. For example, the `pve` command is just an alias for `ls` command and `pre` is just an alias for `rm` command.

> Please keep in mind that i only test this in ZSH and BASH, that's why i'm using "POSIX compliant shell" term because i'm not sure how it will behave in non POSIX compliant shell.

#### Decoupled From Project Directory

You don't need to be in specific project directory to access python virtual environment, all you need to do is give pyv the name of virtual environment you want to access.

### Setup

Pyv is so simple that honestly you don't really need an installer, but i might provide the installer in the future.

First of all, you can clone the repo to your local machine or you can download only the `pyv` file and place it anywhere you want. After that, add `source the/pyv-file/path/pyv` in your shell config such as zshrc or bashrc or something else.

Example: <br>
I place the pyv file in `~/.config/zsh` directory, and because i use ZSH then i need to add `source ~/.config/zsh/pyv` to my ZSH config or `.zshrc`.

### Usage

#### Create Virtual Environment

If the current working directory is a git repo then you can use the command `pce` without any argument, then pyv gonna create python venv with the git repo name.

If you want to name your python venv then you can use `pce <name-venv>`, for example: `pce something-big`.

> Please use `-` or `_` instead of `space` as virtual environment name, for example: `something-big` or `something_big` instead of `something big`.

#### Remove Virtual Environment

If the current working directory is a git repo and you already created python venv before then you can use the command `pre` without any argument, then pyv gonna remove python venv directory with the same git repo name. So if you changed your git repo name, then you can't use `pre` without an argument to delete (previously) the same python venv.

If you want to delete specific python venv, you can use `pre <name-venv>`, for example: `pre something-big`.

#### Activate Virtual Environment

If the current working directory is a git repo and you already created python venv before then you can use the command `pae` without any argument, then pyv gonna activate the python venv.

If you want to activate a specific python venv, you can use `pae <name-venv>`, for example: `pae something-big`.

#### Deactivate Virtual Environment

If you already activate python venv, then you can use `pde` command to deactivate python venv.

#### List Virtual Environment

To list all virtual environment, you can use `pve` command.

### Shortcoming

The shortcoming of pyv is that the command pyv provide is simple, so it might not be able to fit all the use case. For example, it can't create an environment from `environment.yml` file like what conda did. And also, i only tested it in ZSH and BASH, so i'm not sure how it will perform in other shell.
