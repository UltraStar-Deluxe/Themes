# UltraStar Deluxe Themes

This repository contains themes and skins for [UltraStar Deluxe](https://usdx.eu/).

**Note that except for the Modern and Deluxe theme, these themes do not work with the USDX Release version yet!**
Please use one of these versions if you want to use any of the other themes:
- https://github.com/UltraStar-Deluxe/USDX/pull/1129
- https://github.com/UltraStar-Deluxe/USDX/pull/1249

Themes define the position, size, color, text, and behavior of UI elements. Skins
map the texture names used by a theme to image, video, and other asset files.
Together they provide the visual appearance of the game menus, song selection,
singing screen, score screen, party mode, jukebox, editor, and popups.

## Included themes (with Screenshots)

### Modern
<img width="400" height="250" alt="screenshot0001" src="https://github.com/user-attachments/assets/ed14a959-b47c-43a8-b999-96dcc695105e" />

### Deluxe
<img width="400" height="250" alt="screenshot0002" src="https://github.com/user-attachments/assets/886c5ed8-6616-4b67-af37-1106168388f3" />

### Neon
<img width="400" height="250" alt="Screenshot_2026-05-16_00-24-39" src="https://github.com/user-attachments/assets/fe7eb656-2ed2-4b44-bcf9-08f944712ee5" />


### WorldPartyArgon
<img width="400" height="250" alt="screenshot0008" src="https://github.com/user-attachments/assets/468fe802-eb82-40aa-8d91-8bcdf10527eb" />
<img width="400" height="250" alt="screenshot0007" src="https://github.com/user-attachments/assets/65ec52cc-7dfc-447b-a2aa-89b14c395b54" />

### WorldPartyNeon
<img width="400" height="250" alt="screenshot0014" src="https://github.com/user-attachments/assets/0b05178b-4763-45b2-b54d-af0f8d0e8cd6" />
<img width="400" height="250" alt="screenshot0012" src="https://github.com/user-attachments/assets/e827d85a-776c-41c5-b2d7-96edd45dc59f" />
<img width="400" height="250" alt="screenshot0011" src="https://github.com/user-attachments/assets/c7a4e343-c76d-43e7-9ed2-4e8ebfe3238e" />
<img width="400" height="250" alt="screenshot0010" src="https://github.com/user-attachments/assets/73e490c0-9215-427f-bad6-90a8d13e0a33" />
<img width="400" height="250" alt="screenshot0009" src="https://github.com/user-attachments/assets/de2685a2-4e6e-4be1-aedd-a7b197512873" />


### Candy
<img width="400" height="300" alt="screenshot0002" src="https://github.com/user-attachments/assets/938998cd-08ef-45c4-897a-a8e46250432d" />
<img width="400" height="300" alt="screenshot0003" src="https://github.com/user-attachments/assets/dff3a6f8-1e16-46a7-9f0d-38b2e31dddc8" />

### Classic
<img width="400" height="300" alt="screenshot0004" src="https://github.com/user-attachments/assets/d04bbfc5-e369-4c24-9140-6f828cb1a159" />
<img width="400" height="300" alt="screenshot0005" src="https://github.com/user-attachments/assets/b376c9ef-c351-47b6-9da8-222b68ccad12" />
<img width="400" height="300" alt="screenshot0006" src="https://github.com/user-attachments/assets/6d1b1e93-5051-4746-a655-760eda31759d" />
<img width="400" height="300" alt="screenshot0007" src="https://github.com/user-attachments/assets/1b6ead29-9bb0-4b43-9749-9294cead55d6" />

### Temptation
<img width="400" height="300" alt="screenshot0006" src="https://github.com/user-attachments/assets/289afe61-9f80-4905-8abc-48a36fb96f81" />
<img width="400" height="300" alt="screenshot0005" src="https://github.com/user-attachments/assets/44eafa9b-01cd-4e57-acd8-9bc4a683af7b" />
<img width="400" height="300" alt="screenshot0004" src="https://github.com/user-attachments/assets/09a814a7-79f5-43e0-9753-3a4c5000f34f" />

### Verdure
<img width="400" height="300" alt="screenshot0003" src="https://github.com/user-attachments/assets/136190b0-2baf-4201-9596-6f6eadbbe5df" />
<img width="400" height="300" alt="screenshot0002" src="https://github.com/user-attachments/assets/e67c9592-9865-4fd6-85f4-526199aadc85" />
<img width="400" height="300" alt="screenshot0001" src="https://github.com/user-attachments/assets/de3695ee-c35d-47a4-9765-7c446deb5f3c" />

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
- Add a screenshot or video to visualize the change or the theme in general.

## Related project

UltraStar Deluxe source code and releases are maintained at:

https://github.com/UltraStar-Deluxe/USDX
