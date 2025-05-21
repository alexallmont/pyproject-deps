# pyproject-deps

Lightweight tool reading deps from pyproject.toml

## Usage

Example using `-x` to ignore certain libs. Just use `$(pyproject-deps)` if you want all:

```sh
pip install $(pyproject-deps -x libname,grepname.*)`
```

This example would be if I was working on a lib, say `mylib` which is C++ being built with pybind11, and I depend on another lib `libname` which is also built with pybind11. I am building both locally as I want to debug, and I want to manage paths/symbols outside pip.

Exclude with `-x` or `--exclude`, with comma, space or semicolon delimited names. Excluded names are full expressions, but regex is used internally, so add `.*` to end if wildcard search is needed, as in above example which will also exclude anything starting with `grepname`.
