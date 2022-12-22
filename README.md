# xeus-python + JupyterLite demo

https://martinrenou.github.io/xeus-python-demo/retro/notebooks/?path=demo.ipynb

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
