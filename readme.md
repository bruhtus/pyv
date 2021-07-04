## Pyv: Minimalist Python Venv Management Tool

Pyv is a simple shell function that let you make default python virtual environment (venv) decoupled from project directory. If you ever use conda (anaconda/miniconda), pyv is similar to how conda manage python virtual environment but without python version management. So, please keep in mind that pyv only manage python virtual environment and do not manage your version of python you use.

To make it simple, pyv is a wrapper around default python venv command `python -m venv` that move the virtual environment directory into `$PYV_DIR`. By default `$PYV_DIR` is `~/.cache/pyv`, you can change that by adding `export PYV_DIR=$HOME/directory/you/want` to your shell config or `.profile` file, or you can edit the `pyv` file directly.

### Setup

Pyv is so simple that honestly you don't really need an installer, but i might provide the installer in the future.

First of all, you can clone the repo to your local machine or you can download only the `pyv` file and place it anywhere you want. After that, add `source the/pyv-file/path/pyv` in your shell config such as zshrc or bashrc or something else.

Download only pyv file:
```sh
wget https://raw.githubusercontent.com/bruhtus/pyv/master/pyv -P /preferred/location
```

Example: <br>
I place the pyv file in `~/.config/zsh` directory, and because i use ZSH then i need to add `source ~/.config/zsh/pyv` to my ZSH config or `.zshrc`.

For more info, please check the [wiki](https://github.com/bruhtus/pyv/wiki).

### Shortcoming

The shortcoming of pyv is that the command pyv provide is simple, so it might not be able to fit all the use case. For example, it can't create an environment from `environment.yml` file like what conda did. And also, i only tested it in ZSH and BASH, so i'm not sure how it will perform in other shell.
