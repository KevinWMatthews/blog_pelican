# Notes

## Generate

```
$ pelican
```

Can also generate individual files.


## Deploy

The most basic way to host locally is to use python's built-in http server:

```
$ cd output
$ python -m http.server
```

A fancier way is to use the provided Makefile:
```
$ make devserver
```
This deploys to port `8000`.
