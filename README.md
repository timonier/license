# README

Command-line license generator

## Installation

Copy `bin/license` into your executable folder (like `/usr/local/bin` or `$HOME/bin`):

```sh
sudo curl --location --output /usr/local/bin/license "https://github.com/timonier/license/raw/master/bin/license"
sudo chmod +x /usr/local/bin/license
```

Linux users can use the [installer](https://github.com/timonier/license/blob/master/bin/installer):

```sh
curl --location "https://github.com/timonier/license/raw/master/bin/installer" | sudo sh -s -- install
```

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

## Contributing

1. Fork it.
2. Create your branch: `git checkout -b my-new-feature`.
3. Commit your changes: `git commit -am 'Add some feature'`.
4. Push to the branch: `git push origin my-new-feature`.
5. Submit a pull request.

__Note__: Use the script `bin/build` to test your modifications locally.

## Links

* [image "timonier/license"](https://hub.docker.com/r/timonier/license/)
* [nishanths/license](https://github.com/nishanths/license)
* [timonier/dumb-entrypoint](https://github.com/timonier/dumb-entrypoint)
* [timonier/version-lister](https://github.com/timonier/version-lister)