# README

Command-line license generator

If you like / use this project, please let me known by adding a ★ on the [GitHub repository](https://github.com/timonier/license).

## Installation

```sh
# Define installation folder

export INSTALL_DIRECTORY=/usr/bin

# Use local installation

sudo bin/installer install

# Use remote installation

curl --location "https://github.com/timonier/license/raw/master/bin/installer" | sudo sh -s -- install
```

__Note 1__: If you do not define `INSTALL_DIRECTORY`, `installer` will use in `/usr/local/bin`.

__Note 2__: `docker-for-mac` users have to configure [native NFS server](https://medium.com/@sean.handley/how-to-set-up-docker-for-mac-with-native-nfs-145151458adc).

## Usage

Run the command `license`:

```sh
# See all license options

license --help

# Run license

license --name Morgan --output LICENSE mit

cat LICENSE
# MIT License
#
# Copyright (c) 2017 Morgan
#
# Permission is hereby granted, free of charge, to any person obtaining a copy
# ...
```

## Links

* [image "timonier/license"](https://hub.docker.com/r/timonier/license/)
* [nishanths/license](https://github.com/nishanths/license)
* [set up docker for mac with native nfs](https://medium.com/@sean.handley/how-to-set-up-docker-for-mac-with-native-nfs-145151458adc)
* [timonier/license](https://github.com/timonier/license)
