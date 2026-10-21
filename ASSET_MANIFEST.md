# Dragonbound Quest asset manifest

This manifest records assets that are actually embedded and drawn by the current game. The repository remains dependency-free: imported image data is embedded in `index.html` and loaded from local data URIs.

## Dungeon tiles and sprites

### Pixel Dungeon Top-down Tileset (16×16), by reodesuxz

- Source folder: `C:/Users/Brenda/Downloads/jadon rpg/Pixel_Dungeon_Tileset_v1.0/`
- Embedded file: `spritesheet.png` (160×128; 78 frames) with frame coordinates taken from the supplied `spritesheet.json`.
- License: the supplied `LICENSE.txt` permits use and modification in games and other projects, with no attribution required; it prohibits redistributing the assets as a standalone asset pack or library. The sheet is embedded as part of this game.
- In use: stone, dark, blue, and moss floor tiles; stone wall face, top, and edge caps; wooden/iron/open/portcullis doors; closed/open chests; animated torch frames; spike and pressure-plate tiles; and animated green slimes and bats plus skeleton sprites.
- Main character, dragon, brutes, wraiths, mirrors, rune mechanisms, and crystal-seal art continue to use their existing game art and drawing code.

### Kenney Tiny Dungeon 1.0 (16×16), by Kenney

- Source folder: `C:/Users/Brenda/Downloads/jadon rpg/kenney_tinyDungeon/`
- Embedded file: `Tilemap/tilemap_packed.png` (192×176; 12 columns × 11 rows). The sheet is drawn with nearest-neighbor scaling. Tile IDs match the supplied row-major 16×16 tile files.
- License: Creative Commons Zero (CC0), as documented in the supplied `License.txt`.
- In use: tile 63 bookshelf in Rune Antechamber and tile 66 barrel props in Brazier Gallery and Dragon’s Hoard. These props also have matching collision cells.
- The provided folder is **Tiny Dungeon**, which is distinct from the “Kenney Roguelike/RPG Pack” named in the pasted brief. This pack has dungeon props and characters, but does not supply the brief’s overworld buildings or vegetation; no such overworld integration is claimed.

## Existing assets retained

- The earlier `DarkDungeon.png` sheet remains embedded as a fallback for dungeon floor, wall, and torch rendering while the Pixel Dungeon atlas is unavailable.
- Existing Freeknight character frames and the game’s previously embedded overworld, interior, and environment art remain in place.

## Loading and fallback behavior

- Dungeon sprite sheets load from embedded PNG data; no external URLs or libraries are used.
- Pixel Dungeon frame drawing falls back to the existing DarkDungeon renderer and procedural dungeon details if the atlas is unavailable.
- Kenney barrel and bookshelf props have small procedural fallbacks, and their collision remains tied to their map cells.
- All drawing keeps pixel edges crisp with nearest-neighbor canvas scaling.
