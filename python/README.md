## Pip

### Update

```sh
python3 -m pip install --upgrade pip
```

## Pyenv

### Installation

```sh
brew install pyenv
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.zprofile
echo 'command -v pyenv >/dev/null || export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.zprofile
echo 'eval "$(pyenv init -)"' >> ~/.zprofile
```

### Usage

Install version:
```sh
pyenv install 3.10
```

List versions:
```sh
pyenv install -l
```

Create 

```sh
pyenv virtualenv 3.10 gepbackend
```

Make sure the created virtual environment will always be used in a given folder:

```sh
pyenv local <venv name>
```

## Poetry

### Installation

```sh
pip install poetry
```

### Usage

Install required packages:

```sh
poetry install
```

Update outdated packages:

```sh
poetry update
```

## Conda

### Installation

```sh
brew install --cask anaconda
```

Add the following snippet to .zshrc:

```
export PATH=$PATH:/opt/homebrew/anaconda3/bin
```

Test if it works:

```sh
conda --version
```

### Update

```sh
conda update -n base -c defaults conda
```

### Usage

Init:

```sh
conda init
```

This will initialize a base enviroment. You have to source your .zshrc file so that changes will take effect.

Create env:

```sh
conda create -n testenv python=3.11 anaconda

conda activate testenv
```

Deactivate:

```sh
conda deactivate
```

Install scipoptsuite:

- https://github.com/conda-forge/scipoptsuite-feedstock

## pip-audit

### Installation

```sh
python -m pip install pip-audit
```

### Links

- https://pypi.org/project/pip-audit/

