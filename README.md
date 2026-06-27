# NoLightsRequirement

A mod for 7 Days to Die (V3.0) that removes the sunlight requirement for all crops.

Grow your food anywhere in bunkers, caves, and underground bases as long as you have fertile farmland.

![NoLightsRequirement Screenshot](https://github.com/user-attachments/assets/dff11240-05c4-43e5-9676-991e6e6f7275)

---

## Features

- All crops can grow in darkness
- Fertile farmland is still required (realistic farming)
- Server side MOD

---

## Installation

1. Download archive and unpack
2. Extract the NoLightsRequirement folder into your 7 Days to Die Mods directory
3. Make Sure EAC disabled in game launcher

---

## Compatibility

- Game Version: 7 Days to Die V3.0 (Stable / Experimental)
- Mod Type: 100% XML XPath Patch. No DLLs or custom assets required
- Overhauls: Works fine with vanilla. For massive overhaul mods (like Darkness Falls, Undead Legacy, or War3zuk), check if they already modify crop properties
- Save Games: Safe to add or remove mid-game. Will not corrupt your world save data

---

## Supported Crops

This mod modifies the vanilla PlantGrowing block property to remove the sun check. It applies to all standard crops and seeds:

- Super Corn Seed (Super Corn)
- Potato Seed (Potato)
- Blueberry Seed (Blueberry)
- Aloe Seed (Aloe Vera)
- Coffee Seed (Coffee)
- Chrysanthemum Seed and Goldenrod Seed
- Corn Seed, Pumpkin Seed, Yucca Seed
- Cotton Seed, Hop Seed
- Also compatible with custom modded seeds that utilize the default vanilla PlantGrowing logic

---

## Technical Details

This modlet uses a clean XML XPath patch to remove the sunlight restriction dynamically without overwriting core game files. It targets the following properties in blocks.xml:

```xml
<append xpath="/blocks/block[@name='cropsGrowingMaster']/property[@class='PlantGrowing']">
    <property name="LightLevelGrow" value="0"/>
    <property name="LightLevelStay" value="0"/>
</append>

<set xpath="/blocks/block[@name='cropsGrowingMaster']/property[@class='PlantGrowing']/property[@name='FertileLevel']/@value">15</set>

```

## Frequently Asked Questions

**Q: Can I use this for underground farming in a bunker?**
A: Yes. The mod allows all crops to grow in complete darkness, making it ideal for underground bases, bunkers, and caves in 7 Days to Die V3.0.

**Q: Do crops still require fertile farmland?**
A: Yes. You must still craft and place `farmPlotBlock` to grow crops. The mod only removes the sunlight requirement, not the need for proper soil.

**Q: Does this work on multiplayer servers?**
A: Yes. This is a server-side mod, so only the host or dedicated server needs to install it. Clients do not need to download anything.

**Q: Is it compatible with other mods?**
A: Yes. The mod uses minimal XPath patches on the master crop blocks (`cropsGrowingMaster` and `cropsHarvestableMaster`), ensuring high compatibility with most other XML mods.

**Q: Will this break my save game?**
A: No. The mod is safe to add or remove at any time without corrupting your world data.

**Q: How do I uninstall it?**
A: Simply delete the `NoLightsRequirement` folder from your `Mods` directory and restart the game. Crops will immediately require sunlight again.
