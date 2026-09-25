
---

## 1. What is Item Swapping?

Rocket League stores all cosmetic assets such as car bodies, boosts, wheels, and decals inside `.upk` (Unreal Package) files located in the game's `CookedPCConsole` folder.

When you equip an item in your garage (for example, **Standard Boost** or **Bubble**), the game engine loads the corresponding `.upk` file from disk into memory.

**Item Swapping** is the process of replacing the file for an item you own with the visual and audio assets of an exclusive or unobtainable item (such as **Gold Rush / Alpha Boost** or the **Alpha Dev Reward**).

---

## 2. Why Can't You Just Rename the Files?

If you try to take `boost_alphadevreward_SF.upk` and simply rename it to `Boost_Bubble_SF.upk`, the game will fail to load or crash. 

Why?
- Inside every `.upk` file is an internal **Name Table** and **Export Table**.
- When the game loads `Boost_Bubble_SF.upk`, it specifically searches inside the package for objects named `Bubble`. If it finds assets referencing `alphadevreward` instead, it rejects them as missing dependencies.
- Furthermore, modern Rocket League packages use encrypted headers and specialized compression formats.

**These replacement files have already been processed:**
- The internal name tables have been patched so the game engine recognizes all internal asset references under the base item's identity.
- The package structure, offsets, and header encryption are cleanly rebuilt so the game loads the file seamlessly without crashing.

---

## 3. Is It Client-Side?

**Yes, 100% client-side.**
- **Only you** see and hear the custom item on your screen.
- Other players in your match will see whatever item you actually have equipped in your garage.
- This is a direct file modification, no background cheat engines, memory injectors, or third-party hooks run while playing.

---

## 4. How to Install a Replacement File

### Step 1: Locate your `CookedPCConsole` folder
Default installation paths:
- **Steam**:
  ```text
  C:\Program Files (x86)\Steam\steamapps\common\rocketleague\TAGame\CookedPCConsole
  ```
- **Epic Games**:
  ```text
  C:\Program Files\Epic Games\rocketleague\TAGame\CookedPCConsole
  ```

### Step 2: Back up the original file
Before replacing any file, find the original `.upk` file in `CookedPCConsole` and create a backup copy:
1. Find the target file (e.g. `Boost_Bubble_SF.upk`).
2. Copy and rename it to `Boost_Bubble_SF.upk.bak`.

### Step 3: Copy the replacement file
1. Download the replacement `.upk` from this repository.
2. Place it into your `CookedPCConsole` folder, replacing the original file.

### Step 4: Launch Rocket League
Equip the base item (e.g. Bubble) in your garage. In game, you will see and hear the replacement visual effects!

---

## 5. How to Revert (Uninstall)

To restore your game back to its default state at any time:
1. Delete the modified `.upk` file from your `CookedPCConsole` folder.
2. Rename your `.bak` backup file back to `.upk`.
3. Alternatively, use the **Verify Game Files** option in Steam or the Epic Games Launcher to restore all original game files automatically.

---

## 6. Game Updates

When Rocket League receives a game update or patch, the game launcher will typically overwrite your modified `.upk` files with official versions. If this happens:
- Simply re-copy the replacement `.upk` file back into `CookedPCConsole` after the update finishes downloading.
