## MongoDB Shell

### Installation

Install

```sh
brew install mongosh
```

### Usage

Connect:

```sh
mongosh "mongodb://localhost:28015"
```

Run script from file:

```sh
mongosh <uri> --file <file>
```

### Links

- https://www.mongodb.com/docs/mongodb-shell/install/

## Mongo Database Tools

### Installation

List Installation:

```sh
brew list | grep mongodb-database-tools
```

Install

```sh
brew tap mongodb/brew
brew install mongodb-database-tools
```

### Usage

Dump a database:

```sh
mongodump --uri=<uri> --db=gepdb
```

Export a collection:

```sh
mongoexport --uri=<uri> --db=gepdb  --collection=deals  --out=deals.json 
```

Restore a database:

```sh
mongorestore  dump/ --uri=<uri> --db=gepdb
```

### Links