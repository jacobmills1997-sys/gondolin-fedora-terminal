# Gondolin — terminal palette for Fedora (kitty · Konsole · Claude Code)

A dark, gold-led terminal palette drawn from the heraldry of the **Twelve
Houses of Gondolin** (*The Fall of Gondolin*), with Laurelin's gold as the
signature accent. Tuned for a translucent, frosted-glass background.

Pairs with the [gondolin-vim](../gondolin-vim) colorscheme.

## The 16 colours

| | normal | bright (kindled) | House |
|---|---|---|---|
| black   | `#2b3040` | `#5a6072` | Mole (sable) |
| red     | `#cf3a37` | `#f25b50` | Hammer of Wrath (forge-flame) |
| green   | `#5fa64a` | `#8ace66` | Tree (vert) |
| yellow  | `#d99a3c` | `#f4b56a` | Golden Flower / Laurelin (or) |
| blue    | `#4f7cb0` | `#84aad0` | Fountain (azure) |
| magenta | `#9457b0` | `#bd8ad8` | Heavenly Arch (purpure) |
| cyan    | `#3fa3aa` | `#74c9cf` | Fountain-spray (silver water) |
| white   | `#d8d4ca` | `#efe7d4` | Tower of Snow (argent) |

- **foreground** `#e8dfc8` (parchment) · **background** `#11161f`
- **cursor / selection** `#f4b56a` (Laurelin gold) on `#131c2e`

## kitty

The palette lives in `kitty/gondolin.conf` and deliberately does **not** set the
background, so your existing background / opacity / blur are preserved.

1. Copy it next to your kitty config:
   ```sh
   cp kitty/gondolin.conf ~/.config/kitty/gondolin.conf
   ```
2. In `~/.config/kitty/kitty.conf`, keep your background + frosted-glass lines
   and add the include (see `kitty/kitty.conf.example`):
   ```conf
   background            #11161f
   background_opacity    0.75
   background_blur       30
   dynamic_background_opacity yes

   include gondolin.conf
   ```
3. Reload kitty: `Ctrl+Shift+F5` (or open a new window).

## Konsole

`konsole/Gondolin.colorscheme` includes `Blur=true` and `Opacity=0.75` for the
same frosted-glass look, and `konsole/Gondolin.profile` is a ready-made profile
that selects it (with Source Code Pro to match the rest of the set).

**One-click apply** — drop both files into Konsole's data dir:

```sh
cp konsole/Gondolin.colorscheme konsole/Gondolin.profile ~/.local/share/konsole/
```
Then in Konsole: **Settings → Manage Profiles → Gondolin → Set as Default**
(or **View → Switch Profile → Gondolin** for the current window).

> The profile references the `Gondolin` colorscheme by name, so both files must
> be installed together. For the blur/transparency, ensure your compositor —
> KWin on KDE — has the "Blur" desktop effect enabled.

## Claude Code

`claude-code/gondolin.json` is a custom theme for [Claude
Code](https://claude.com/claude-code) (v2.1.118+).

```sh
mkdir -p ~/.claude/themes
cp claude-code/gondolin.json ~/.claude/themes/
```
Then either run `/theme` and pick **Gondolin**, or set it directly in
`~/.claude/settings.json`:
```json
{ "theme": "custom:gondolin" }
```

## License

MIT — see `LICENSE`.
