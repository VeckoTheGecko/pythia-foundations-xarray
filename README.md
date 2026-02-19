# Xarray Pythia Foundations

On 19 Feb 2026 the notebook at Pythia Foundations was broken with the message:

```
ModuleNotFoundError: No module named 'pkg_resources'
```

They're working on making their environments more stable. But for the timebeing, there's this repo that creates a working environment using Pixi[^1] so we can do the xarray talk.

## Getting started

```bash
pixi install
pixi run jupyter
```

## How was the environment created?

```
pixi init --import environment.yaml
```
