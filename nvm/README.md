## Installation

```sh
brew install nvm
```

Add the following lines to .zprofile:

```sh
 export NVM_DIR="$HOME/.nvm"
  [ -s "/opt/homebrew/opt/nvm/nvm.sh" ] && \. "/opt/homebrew/opt/nvm/nvm.sh"  # This loads nvm
  [ -s "/opt/homebrew/opt/nvm/etc/bash_completion.d/nvm" ] && \. "/opt/homebrew/opt/nvm/etc/bash_completion.d/nvm"
```

## Usage

Install Node Version

```sh
nvm install 16
```

Use Node Version

```sh
nvm use 16
```

List available versions:

```sh
nvm ls-remote
```

Migrate global packages:

```sh
nvm install node --reinstall-packages-from=node
```

Install latest npm version
```sh
nvm install-latest-npm
```

## Links

- https://github.com/nvm-sh/nvm