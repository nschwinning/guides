## Installation

```sh
brew tap sdkman/tap
brew install sdkman-cli
```

Add the following lines to .zprofile:

```sh
export SDKMAN_DIR=$(brew --prefix sdkman-cli)/libexec
[[ -s "${SDKMAN_DIR}/bin/sdkman-init.sh" ]] && source "${SDKMAN_DIR}/bin/sdkman-init.sh"
```

## Usage

List candidates:

```sh
sdk list java
```

Install specific version:

```sh
sdk install java 17.0.6-tem
```

## Env Command

Want to switch to a specific JDK or SDK every time you visit a project? This can be achieved through an .sdkmanrc file in the base directory of your project. This file can be generated automatically by issuing the following command:

```sh
sdk env init
```

A config file with the following content has now been created in the current directory:

```sh
# Enable auto-env through the sdkman_auto_env config
# Add key=value pairs of SDKs to use below
java=17.0.6-tem
```

The file is pre-populated with the current JDK version in use, but can contain as many key-value pairs of supported SDKs as needed. To switch to the configuration present in your .sdkmanrc file, simply issue the following command:

```sh
sdk env
```

### Clear

```sh
sdk env clear
```

### Install required versions

```sh
sdk env install
```

## Links

- https://github.com/sdkman/homebrew-tap
- https://sdkman.io/usage