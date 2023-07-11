# opensesame-macos-build-scripts
 
## Usage

Build environment from scratch

```
conda env create -f env/py311.yaml
```

Export environment to new `.yml`

```
conda activate opensesame
conda env export > env-export/opensesame_4.0.0a52-py311-macos-x64-1.yml
```

Edit yml
- replace expyriment with url:
    - http://files.cogsci.nl/expyriment-0.10.0+opensesame2-py3-none-any.whl

Remove env

```
conda deactivate
conda env remove -n opensesame
```

Rebuild with the new .yml

```
conda env create -f env-export/opensesame_4.0.0a52-py311-macos-x64-1.yml
```

Manually install psychopy

```
conda activate opensesame
pip install psychopy --no-deps
```

## Testing

Start opensesame

```
opensesame
```

Test:
- backends
- templates
- example experiments
- menu entries
- osweb
- JATOS integration
- video playback

## Building app and packaging


```
conda activate app-builder
python anaconda-env-to-osx-app/conda_env_to_app anaconda-env-to-osx-app/settings.py
```