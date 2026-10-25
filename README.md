# HardCraft

HardCraft is a data pack for **Minecraft Java Edition** (26.3 and below, back to 1.20.5) that kits you out with enchanted gear so you can jump straight into a Survival or Hardcore world.

> This repo currently holds the project's documentation. The pack itself is built and shared as a `.zip` you drop into a world's `datapacks` folder — see [Installation](#installation).

## Features

- **Full netherite kit** — max-enchanted netherite armor, sword, pickaxes (Fortune and Silk Touch), axe, shovel, hoe, bow and fishing rod, plus a shield.
- **Unbreakable gear** — every item with durability, kit-given or crafted later, is kept unbreakable automatically.
- **Totem shulker** — a shulker box holding 27 totems of undying.
- **Building supplies shulker** — a second shulker box stocked with basic blocks for a first base.
- **Spare turtle shell** — an enchanted turtle shell carried alongside your netherite helmet, with infinite Water Breathing while worn.
- **No cheats required** — the kit is given automatically on first join. Run it again anytime with `/trigger hardcraft`.
- **Version-tolerant** — ships separate command syntax for 1.21.5+ and 1.20.5–1.21.4, so one pack covers both.

## Installation

1. Download the latest `hardcraft.zip` for this pack.
2. Drop it into your world's `datapacks` folder:
   - **Existing world:** `saves/<world name>/datapacks/`
   - **New world:** add it on the Create World screen under *More → Data Packs*, or drag the zip onto that screen.
3. Open (or reopen) the world. No `/reload` and no cheats needed.
4. You should see **"HardCraft equipped. Good luck!"** in chat, with your armor on, tools in your hotbar, and the two shulker boxes in your inventory.

## Commands

| Command | What it does |
|---|---|
| `/trigger hardcraft` | Re-gives the full kit. Works without cheats. |
| `/function hardcore_kit:kit` | Same as above, if you have cheats enabled. |

## Compatibility

- **Minecraft:** 1.20.5 through 26.3.
- **Loaders:** Vanilla, and any mod loader that still loads vanilla data packs (Fabric, NeoForge, etc.) — no mod required.

## Troubleshooting

### `/trigger hardcraft` doesn't work

`/trigger` is a vanilla command that works for every player without cheats enabled, so this is rare. If it genuinely does nothing in your world:

1. Open the pack's `datapacks` folder and confirm `hardcraft.zip` (or its unzipped folder) is actually in your current world's folder, not a different save.
2. Reopen the world once so the pack's scoreboard objective (`hardcraft`) is created. `/trigger` can't work before that objective exists.
3. If it still fails and you have **no other way to run commands** — for example a Hardcore world with cheats off and no LAN option available — you can enable cheats directly on the save file with an NBT editor:
   - **Back up your world folder first.** Editing `level.dat` by hand can corrupt a save if done wrong.
   - Close the world completely.
   - Open `level.dat` from your world's save folder in an NBT editor (a desktop tool like NBTExplorer, or a browser-based NBT editor).
   - Under the `Data` compound, find `allowCommands` and set it from `0` to `1`.
   - Save the file, replace the original, and reopen the world. Cheats will now be enabled, and both `/trigger hardcraft` and `/function hardcore_kit:kit` will work.
   - This does not undo Hardcore's permadeath rule on its own — it only lets you run commands.

### Safe Mode on world load

If Minecraft offers "Safe Mode" instead of loading the world, a data pack failed to parse — usually because the pack and your Minecraft version don't match. Check the [Compatibility](#compatibility) section below, and make sure you deleted any older copy of the pack from `datapacks` before adding a new one.

## Known limitations

- The unbreakable effect only checks your own inventory slots (hotbar, main inventory, armor, offhand), not items sitting in chests, shulker boxes, or on the ground.
- A player must be in a world where the pack is active to receive or re-trigger the kit.

## License

No license has been set for this project yet.

---

PS: I'm too lazy to actually write this so I just asked Claude. Go fork it, download the zip, contribute — just hope I don't license this.  HardCraft is a datapack that aims to give you a kit to kickstart Hardcore or Survival in Minecraft Java Edition 26.3 and below!
