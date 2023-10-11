:shells:

# Nushell Notes

## Equivalent Commands

### Zsh/Bash or any POSIX-compliant shell

```sh
osc -A https://api.opensuse.org checkout home:uncomfyhalomacro:branches:utilities/fzf && cd $_
```

### Nushell

> No known equivalent

It seems bash/zsh `mkdir somedir && $_` has a nushell equivalent - `mkdir -v somedir | cd $in.0`
or `cd (mkdir -v somedir | first)`.

