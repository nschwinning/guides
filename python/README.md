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

## pip-audit

### Installation

```sh
python -m pip install pip-audit
```

### Links

- https://pypi.org/project/pip-audit/

