# upload-haddocks by Richard Cook

[![View on PyPI](https://img.shields.io/pypi/v/upload-haddocks.svg)](https://pypi.python.org/pypi/upload-haddocks)
[![Licence](https://img.shields.io/badge/license-MIT-blue.svg)](https://raw.githubusercontent.com/rcook/upload-haddocks/master/LICENSE)

Simple script that fixes hyperlinks in Haskell documentation generated using
`stack haddock` and then uploads it to the appropriate location on [Hackage][hackage]

## Clone repository

```
git clone https://github.com/rcook/upload-haddocks.git
```
## Set up Python virtual environment

```
script/virtualenv
```

## Dev-install main script into virtual environment

```
script\env pip install -e .
```

This will allow edits to the scripts to be picked up automatically

## Run main script in virtual environment

```
script/env upload-haddocks --version
```

## Build package

```
script/env python setup.py build
```

## Test package

```
script/env python setup.py test
```

## Upload package

```
script/env python setup.py sdist upload
```

## Install package into global site packages

```
python setup.py install --record files.txt
```

Note that this calls the `python` global Python instead of the Python in the project's virtual environment.

## Notes

Various package properties are defined in `upload-haddocks/__init__py`:

* `__project_name__`
* `__version__`
* `__description__`

When publishing a new build of the package, ensure that `__version__` is incremented as appropriate.

## User-level installation

```
pip install --user upload-haddocks
```

This will perform a user-level installation of the package. The scripts will be placed at:

* Windows: `%APPDATA%\Python\Scripts`
* Linux/macOS: `$HOME/.local/bin`

## Global installation

```
pip install upload-haddocks
```

This will perform a global installation of the package and should add the script to `PATH`.

## Licence

[MIT License][licence]

Released under [MIT License][licence]

[licence]: LICENSE
[hackage]: http://hackage.haskell.org/
