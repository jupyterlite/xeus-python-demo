# xeus-python + JupyterLite demo

[![lite-badge](https://jupyterlite.rtfd.io/en/latest/_static/badge.svg)](https://jupyterlite.github.io/xeus-python-demo/retro/notebooks/?path=demo.ipynb)

xeus-python + JupyterLite deployed as a static site to GitHub Pages, for demo purposes.

## ✨ Try it in your browser ✨

https://jupyterlite.github.io/xeus-python-demo/retro/notebooks/?path=demo.ipynb

## How does it compare to the Pyodide kernel?

#### Pyodide kernel:

- Is based on [Pyodide](https://github.com/pyodide/pyodide)
- Uses [IPython](https://github.com/ipython/ipython) for the code execution (access to IPython magics, support for the inline Matplotlib backend, *etc*)
- Provides a way to dynamically install packages with ``piplite`` (**e.g.** ``await piplite.install("ipywidgets")``)
- **Does not support** sleeping with ``from time import sleep``
- **Does not support** pre-installing packages

#### jupyterlite-xeus-python:

- Is based on [xeus-python](https://github.com/jupyter-xeus/xeus-python)
- Uses [IPython](https://github.com/ipython/ipython) for the code execution (access to IPython magics, support for the inline Matplotlib backend, *etc*)
- **Does not provide** a way to dynamically install packages (yet. We are working on building a ``mamba`` package manager for WASM)
- **Supports** sleeping with ``from time import sleep``
- **Supports** pre-installing packages from ``emscripten-forge`` and ``conda-forge``, by providing an ``environment.yml`` file defining the runtime environment

## How to make your own

TODO

## How to install extra packages

You can pre-install extra packages for xeus-python by adding them to the ``environment.yml`` file.

Only ``no-arch`` packages from ``conda-forge`` and packages from ``emscripten-forge`` can be installed.

For example, if you want to create a JupyterLite deployment with NumPy and Matplotlib pre-installed, you would need to edit the ``environment.yml`` file as following:

```yml
name: xeus-python-kernel
channels:
  - https://repo.mamba.pm/emscripten-forge
  - https://repo.mamba.pm/conda-forge
dependencies:
  - numpy
  - matplotlib
```
