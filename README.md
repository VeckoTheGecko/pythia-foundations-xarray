# Xarray Pythia Foundations

On 19 Feb 2026 the notebook at Pythia Foundations was broken with the message:

```
ModuleNotFoundError: No module named 'pkg_resources'
```

This is due to updates in dependencies (in this case, Python itself) that caused the notebook to break.

They're working on making their environments more stable. But for the timebeing, there's this repo that creates a working environment "as if its 2023" using Pixi[^1] so we can do the xarray talk. The vast majority of things will be the same if you're using the latest Xarray.

## Getting started

```bash
pixi install
pixi run jupyter lab
```

## How was the working environment created?

> For the curious, 

```bash
pixi init --import environment.yaml
```

Edit the `pixi.toml` with

```diff
diff --git a/pixi.toml b/pixi.toml
index 59ed295..966e5ef 100644
--- a/pixi.toml
+++ b/pixi.toml
@@ -4,6 +4,7 @@ channels = ["conda-forge"]
 name = "pythia-book-dev"
 platforms = ["osx-arm64"]
 version = "0.1.0"
+exclude-newer = "2023-02-01"
 
 [tasks]
 
```

Done! We're off to the races
