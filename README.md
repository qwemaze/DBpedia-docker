# DBpedia Docker Container

This repository contains all files needed to build a [Virtuoso Open Source](https://github.com/openlink/virtuoso-opensource) instance preloaded with the [latest DBpedia dataset](http://wiki.dbpedia.org/Downloads) inside a [Docker](http://docker.com/) container.

## Building

**Warning!**
> Building Virtuoso with DBpedia requires significant resources.
> The exact amount of resources would depend on languages you're using.
> Core requires about 50GB of disk space and 16GB of ram.
> Make sure to properly configure `virtuoso/virtuoso.ini`

* Download, unpack and prepare required DBpedia files:
```sh
$ make prepare
```
* Start new virtuoso instance:
```sh
$ make virtuoso
```
* Start import procedure:
```sh
$ make import
```

In the end it should yield a ready-to-use running dbpedia container and db directory filled with built db data.
Access point is http://localhost:8890/sparql.

## Additional languages

Currently scripts will only download and import core DBpedia files.
If you wish to add more languages, you'll need to edit `download`, `unpack` and `move` targets in Makefile as well as list of imported folders in `virtuoso/import.sh` file.
