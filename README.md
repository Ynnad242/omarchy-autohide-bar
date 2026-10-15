# Auto-hide Bar

The Omarchy status bar with Windows-style auto-hide. The bar slides off the
screen edge when you're not using it, leaving a thin strip. Push the pointer
against that edge and it slides back in. It stays out while a widget panel or
tooltip is open, then hides again shortly after the pointer leaves.

Everything else (widgets, layout, theming, dragging, `Super + Shift + Space`
to fully hide) works exactly like the stock `omarchy.bar`, which this is a
copy of.

## Install

```bash
omarchy plugin add https://github.com/Ynnad242/omarchy-autohide-bar
omarchy bar use ynnad.autohide-bar
```

Or copy this folder to `~/.config/omarchy/plugins/ynnad.autohide-bar/` and run
`omarchy bar use ynnad.autohide-bar`. If the bar doesn't change, run
`omarchy restart shell`.

To go back to the stock bar: `omarchy bar use omarchy.bar`.

## Options

Set these under `"bar"` in `~/.config/omarchy/shell.json` (hot-reloads):

| Key | Default | Meaning |
|---|---|---|
| `autohide` | `true` | `false` turns auto-hide off (behaves like the stock bar) |
| `autohideDelay` | `600` | ms after the pointer leaves before the bar hides |
| `autohideRevealDelay` | `120` | ms of hovering the edge before the bar shows |
| `autohidePeek` | `2` | px of the bar left on screen while hidden (the hover target) |

While auto-hide is on, the bar overlays windows instead of reserving space
for itself, so windows use the full screen height.

## Compatibility

Built from the stock Omarchy bar as of its September 2026 release. If a future
Omarchy update changes the bar's internals, re-clone it
(`omarchy plugin clone omarchy.bar`) and re-apply the auto-hide changes —
search `Bar.qml` for `autohide` to find them all.

## License

MIT. Based on the Omarchy bar; see [LICENSE](LICENSE).
