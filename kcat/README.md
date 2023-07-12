## Installation

```sh
brew install kcat
```

## Usage

Simple Consumer:

```sh
kcat -b localhost:8097 -t simple
```

Print headers:

```sh
kcat -b localhost:8097 -C -t simple -f 'Headers: %h: Message value: %s\n'
```
