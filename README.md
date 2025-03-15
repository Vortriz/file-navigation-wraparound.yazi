# file-navigation-wraparound.yazi
Small Lua snippet to wraparound while navigating files in Yazi

Taken from [Yazi tips](https://yazi-rs.github.io/docs/tips/#navigation-wraparound) and put here for autofetching in my Nix configuration.

## Binds

- For normal people - add this to `keymap.toml`
```toml
[[manager.prepend_keymap]]
on  = "k"
run = "plugin arrow -1"
desc = "Move cursor up"

[[manager.prepend_keymap]]
on  = "j"
run = "plugin arrow 1"
desc = "Move cursor down"
```

- For nix people
```nix
programs.yazi.keymap.manager.prepend_keymap = [
    { on = "k"; run = "plugin file-navigation-wraparound -1"; desc = "Move cursor up"; }
    { on = "j"; run = "plugin file-navigation-wraparound 1"; desc = "Move cursor down"; }
]
```
