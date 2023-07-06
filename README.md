# opensesame-macos-build-scripts
 
## Usage

Build environment from scratch

```
conda env create -f env/py311.yaml
```

Export environment to new `.yml`

```
conda activate opensesame
conda env export > env-export/opensesame_4.0.0a49-py37-macos-x64-1.yml
```

Edit yml
- Downgrade (in the yml) rapunzel (conda) and extention-osweb (pip) to test the updater
- replace:
`- expyriment==0.10.0+opensesame2` by `- http://files.cogsci.nl/expyriment-0.10.0+opensesame2-py3-none-any.whl`
- add reminder to install psychopy:
```

Remove env

```
conda deactivate
conda env remove -n opensesame
```

Rebuild with the new .yml

```
conda env create -f env-export/opensesame_4.0.0a49-py37-macos-x64-1.yml
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
- updater
- backends
- templates
- example experiments
- menu entries
- JATOS integration
- video playback