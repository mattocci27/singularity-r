# Singularity radian

[![Build Status](https://travis-ci.org/mattocci27/singularity-radian.svg?branch=master)](https://travis-ci.org/mattocci27/singularity-radian)
[![Singularity Hub](https://www.singularity-hub.org/static/img/hosted-singularity--hub-%23e32929.svg)](https://singularity-hub.org/collections/4481)
[![GitHub License](https://img.shields.io/badge/license-MIT-green.svg)](https://opensource.org/licenses/MIT)

Singularity image for [radian](https://github.com/randy3k/radian).

This is still a work in progress.

## Build

You can build a local Singularity image named `singularity-radian.sif` with:

```sh
sudo singularity build singularity-radian.sif Singularity
```

## Deploy

Instead of building it yourself you can download the pre-built image from
[Singularity Hub](https://www.singularity-hub.org) with:

```sh
singularity pull --name singularity-radian.sif shub://mattocci27/singularity-radian
```

## Run

### Radian

```sh
singularity run --app radian singularity-radian.sif
```

### Rscript

```sh
singularity run --app Rscript singularity-radian.sif
```

### Shell

```sh
singularity shell singularity-radian.sif
Singularity>
```

```

## Contributing

Bug reports and pull requests are welcome on GitHub at
https://github.com/mattocci27/singularity-radian.

## License

The code is available as open source under the terms of the [MIT License].

[R]: https://www.r-project.org/
[MIT License]: http://opensource.org/licenses/MIT
