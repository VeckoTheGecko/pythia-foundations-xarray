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

## How was the working environment created?

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
