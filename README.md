# Spicetify fixes for Spotify 1.3.6

Spotify **1.3.6** removed many of the class names that Spicetify themes and extensions relied on (`.Root__top-container`, `.main-nowPlayingBar-right`, `.main-globalNav-navRight`, …). This repo has fixed versions of two things that broke:

| | What was broken | Upstream PR |
|---|---|---|
| **StarryNight** theme | No stars or shooting stars, no round spinning cover art, square/black panels, player panel in the wrong place | [spicetify/spicetify-themes#1315](https://github.com/spicetify/spicetify-themes/pull/1315) |
| **Full Screen** extension | Full screen / TV mode buttons never appear ("Top Bar Component" missing) | [daksh2k/Spicetify-stuff#295](https://github.com/daksh2k/Spicetify-stuff/pull/295) |

Once those PRs are merged, just reinstall from Marketplace and you won't need this repo anymore.

Tested on Spotify 1.3.6.1921 with Spicetify 2.46.3 (macOS).

## Install

First, **uninstall the Marketplace version** of whichever one you're replacing (Marketplace → Installed → Uninstall). Otherwise the broken copy loads alongside the fixed one.

Find your Spicetify folder:

```sh
spicetify path userdata
```

### StarryNight

1. Copy the `StarryNight` folder into `<spicetify folder>/Themes/`
2. Run:
   ```sh
   spicetify config current_theme StarryNight color_scheme Base inject_theme_js 1
   spicetify apply
   ```

Other color schemes: `Cotton-candy`, `Forest`, `Galaxy`, `Orange`, `Sky`, `Sunrise`.

### Full Screen

1. Copy `full-screen/fullScreen.js` into `<spicetify folder>/Extensions/`
2. Run:
   ```sh
   spicetify config extensions fullScreen.js
   spicetify apply
   ```

Buttons: TV mode in the top bar, full screen in the player controls. Shortcuts: `F` full screen, `T` TV mode, `Esc` exit, right-click a button for settings.

## Credits

- StarryNight by Brandon Chen and Julissa Laignelet, from [spicetify/spicetify-themes](https://github.com/spicetify/spicetify-themes) (MIT)
- Full Screen by [daksh2k](https://github.com/daksh2k/Spicetify-stuff) (MIT), built from the source in the PR branch
- Shooting stars by [Delroy Prithvi](https://codepen.io/delroyprithvi/pen/LYyJROR) (MIT, notice in `StarryNight/theme.js`)

Each folder has its original license.
