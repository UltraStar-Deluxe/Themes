# UltraStar Deluxe Themes

This repository contains themes and skins for [UltraStar Deluxe](https://usdx.eu/).

Themes define the position, size, color, text, and behavior of UI elements. Skins
map the texture names used by a theme to image, video, and other asset files.
Together they provide the visual appearance of the game menus, song selection,
singing screen, score screen, party mode, jukebox, editor, and popups.

## Included themes

- `Modern`
- `Deluxe`
- `Argon`
- `Neon`
- `Candy`
- `Classic`
- `Temptation`
- `Verdure`

## Installing

Copy this repository's contents into the `themes` directory of an UltraStar
Deluxe installation.

In the main USDX source tree this directory is:

```text
game/themes/
```

Each theme has a top-level `.ini` file, for example `Modern.ini`, and one
directory containing the skin `.ini` files and assets for that theme, for example
`Modern/`.

After copying or updating themes, restart UltraStar Deluxe. Themes and skins can
then be selected in:

```text
Options -> Themes
```

## Repository layout

```text
themes/
  Modern.ini          Theme definition
  Modern/             Skins and assets used by the Modern theme
    Blue.ini          Skin definition
    Winter.ini        Skin definition
    [main]button.png  Example texture asset
```

Top-level `.ini` files are loaded as themes. `.ini` files inside theme
directories are loaded as skins.

## Theme files

A theme file starts with a `[Theme]` section:

```ini
[Theme]
Name = My Theme
Creator = Your Name
US_Version = USD 110
DefaultSkin = Blue
BaseTheme = Modern
```

Useful fields:

- `Name`: display name shown by USDX.
- `Creator`: theme author.
- `US_Version`: supported USDX theme format. The included themes currently use
  `USD 110`.
- `DefaultSkin`: skin selected by default for this theme.
- `BaseTheme`: optional parent theme used for missing sections.

Themes can inherit from another theme. If a section is not present in the active
theme, USDX can resolve it from the `BaseTheme` chain. This is useful for themes
that only override selected screens or controls.

Colors are defined in the `[Colors]` section as RGB values:

```ini
[Colors]
White = 255 255 255
Black = 0 0 0
Accent = 40 160 220
```

Other sections define screen elements such as buttons, statics, text, select
slides, popups, and screen-specific layout objects.

## Skin files

A skin file starts with a `[Skin]` section:

```ini
[Skin]
Theme = Modern
Name = Blue
Color = Blue
```

The `[Textures]` section maps texture names used by the theme to files in the
skin directory:

```ini
[Textures]
Button = [main]button.png
MainBG = [bg-main]blue.jpg
Cursor = [interface]cursor.png
```

The `Theme` value should match the theme's `[Theme] Name`. USDX lists themes
when it can find at least one matching skin.

## Creating or Updating a Theme

One possible workflow:

1. Create or copy a top-level theme file, for example `MyTheme.ini`.
2. Set `[Theme] Name`, `Creator`, `US_Version = USD 110`, and `DefaultSkin`.
3. Create a matching directory, for example `MyTheme/`.
4. Add at least one skin `.ini` in that directory.
5. Set the skin's `[Skin] Theme` to the theme name.
6. Add texture mappings under `[Textures]` and place the referenced assets in
   the same directory.
7. Run USDX and check the screens or modes your change touches.

For smaller changes, prefer inheriting from an existing theme with `BaseTheme`
and overriding only the sections that differ.

## Compatibility Notes

- Use `US_Version = USD 110` for themes targeting the current format.
- Texture names are referenced directly by theme files, so changing shared names
  may also require updating the related theme sections.
- `BaseTheme` inheritance works best as a simple chain.
- A theme needs at least one matching skin before it appears in the game.
- File names referenced in skin `.ini` files need to match the files on disk.

## Contributing

When contributing a change, it helps to:

- Keep changes focused on the affected theme or skin.
- Include any new image, video, or font assets referenced by the `.ini` files.
- Preserve author and source attribution for third-party assets.
- Try the theme in UltraStar Deluxe before opening a pull request.
- Mention the USDX version and the screens or modes you checked.

## Related project

UltraStar Deluxe source code and releases are maintained at:

https://github.com/UltraStar-Deluxe/USDX
