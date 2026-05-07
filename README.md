# Alien Blood Theme for Home Assistant

A bio-luminescent, terminal-inspired theme for Home Assistant — inspired by the classic **Alien Blood** color scheme. Deep, near-black backgrounds; muted moss-green text; and an electric phosphor-green accent that glows just enough to feel alive.

Bundled alongside Alien Blood is a complete family of **Metro** (flat, sharp-cornered) and **Fluent** (soft, rounded, slightly tinted) variants in Red, Blue, Green, Orange, Purple, and Slate — fourteen themes from a single install, all sharing one carefully-tuned typographic system.

[![hacs_badge](https://img.shields.io/badge/HACS-Custom-41BDF5.svg)](https://github.com/hacs/integration)

---

## Highlights

- **Alien Blood** — the headliner. Dark, atmospheric, with a phosphor-green accent (`#73fa91`) on a `rgb(0,14,7)` background.
- **Two design languages, one theme pack**
  - **Metro** — flat, zero-radius, sharp corners. Inspired by Windows 8 / Windows Phone tile design.
  - **Fluent** — softly rounded corners, subtly color-tinted backgrounds, blurred dialogs. Inspired by Windows 11.
- **Light & dark modes** that follow your Home Assistant preference automatically.
- **Refined typography** using the Segoe UI Variable stack with carefully-set weights, sizes, and line heights for headings, card titles, body, and captions.
- **Card-mod aware** — ships with thoughtful tweaks to entity rows, glance cards, more-info dialogs, the sidebar, and the app header (including a translucent, blurred header on supported browsers).
- **Mushroom-friendly** — variables for chips, badges, sliders, and shapes are pre-tuned.
- **Easy to extend** — themes are built from YAML anchors, so creating your own color variant is just a few lines.

## Available themes

| Metro (flat)         | Fluent (rounded)      |
| -------------------- | --------------------- |
| Metro Alien Blood    | Fluent Alien Blood    |
| Metro Red            | Fluent Red            |
| Metro Blue           | Fluent Blue           |
| Metro Green          | Fluent Green          |
| Metro Orange         | Fluent Orange         |
| Metro Purple         | Fluent Purple         |
| Metro Slate          | Fluent Slate          |

## Installation

### Via HACS (recommended)

1. Open **HACS** in Home Assistant.
2. Go to **Frontend**, click the menu in the top-right, and choose **Custom repositories**.
3. Add this repository's URL with category **Theme**.
4. Search for **Alien Blood Theme** and install it.
5. Make sure the following is in your `configuration.yaml`:
   ```yaml
   frontend:
     themes: !include_dir_merge_named themes
   ```
6. Restart Home Assistant (or reload themes from **Developer Tools → YAML → Themes**).
7. Open your **Profile**, scroll to **Theme**, and pick any of the Alien Blood / Metro / Fluent variants.

### Manual

1. Copy `themes/alien-blood.yaml` into your Home Assistant `config/themes/` directory.
2. Make sure `frontend: themes: !include_dir_merge_named themes` is in your `configuration.yaml`.
3. Restart Home Assistant and select the theme from your profile.

## Recommended companions

These aren't required, but the theme is designed with them in mind:

- [**card-mod**](https://github.com/thomasloven/lovelace-card-mod) — unlocks the deeper styling tweaks (translucent header, refined more-info dialogs, sidebar polish).
- [**Mushroom**](https://github.com/piitaya/lovelace-mushroom) — pre-tuned chip, badge, and shape sizing.

## Creating your own color variant

Every theme reuses the same shared anchors (`*common-card-mods`, `*metro-common-dark`, `*fluent-common-light`, etc.), so a new color is just a handful of lines. Drop something like this at the bottom of `alien-blood.yaml`:

```yaml
Metro Cyber:
  <<: *common-card-mods
  card-mod-theme: "Metro Cyber"

  primary-color: "#00e5ff"
  rgb-primary-color: "0,229,255"
  rgb-primary-color-darker: "0,180,200"
  rgb-primary-color-lighter: "120,240,255"
  hue-primary-color: "187deg"

  accent-color: "#78f0ff"
  rgb-accent-color: "120,240,255"

  modes:
    dark:
      <<: *metro-common-dark
    light:
      <<: *metro-common-light
```

That's it — typography, layout, card-mods, sidebar tweaks, and dialog blur all come along for free.

## Credits

- Color palette inspired by the **Alien Blood** terminal / VS Code color scheme.
- Bundled fonts: Segoe UI family in `www/` for local fallback.
- Thanks to the Home Assistant, HACS, card-mod, and Mushroom communities.

## License

See the repository for license details.
