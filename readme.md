![PalworldSaveTools Logo](Assets/resources/PalworldSaveTools.png)
---
- **Contact me on Discord:** Pylar1991
---
---
- **Please download the standalone folder from https://github.com/deafdudecomputers/PalworldSaveTools/releases/latest to be able to use the .exe!**
---

## Features:

- **Fast parsing/reading** tool—one of the quickest available.  
- Lists all players/guilds.  
- Lists all pals and their details.  
- Displays last online time for players.  
- Logs players and their data into `players.log`.  
- Logs and sorts players by the number of pals owned.  
- Provides a **base map view**.  
- Provides automated killnearestbase commands for PalDefender targeting inactive bases.  
- Transfers saves between dedicated servers and single/coop worlds.  
- Fix Host Save via GUID editing.  
- Includes Steam ID conversion.  
- Includes coordinate conversion.  
- Includes GamePass ⇔ Steam conversion.  
- Slot injector to increase slots per player on world/server, compatible with Bigger PalBox mod.  
- Automated backup between tool usages.
- All in One Deletion Tool (Delete Guilds, Delete Bases, Delete Players).

---

## Steps to Restore Your Map(Fog and icons):

### This only applies if you do NOT want to use the "Restore Map" option.

### 1. Find the Old Server/World ID:
- **Join your old server/world**.
- Open File Explorer and run the search for: 
	```
	%localappdata%\Pal\Saved\SaveGames\
	```
- Look for a folder with a **random ID** (this should be your **Steam ID**).
- Open that folder and **sort the subfolders by the "Last Modified" date**.
- Look for the folder that matches your **old server/world ID** (e.g., `FCC47F5F4DD6AC48D3C0E2B30059973D`). The folder with the most recent modification date is typically the one for your **old server/world**.
- Once you've found the correct folder, **copy** the `LocalData.sav` file from it.

### 2. Find the New Server/World ID:
- **Join your new server/world**.
- Open File Explorer and run the search for: 
	```
	%localappdata%\Pal\Saved\SaveGames\
	```
- Look for a folder with a **random ID** (this should be your **Steam ID**).
- Open that folder and **sort the subfolders by the "Last Modified" date**.
- Look for the folder that matches your **new server/world ID**.
- Once you've found the correct folder, **paste** the `LocalData.sav` file from the old server/world ID into this folder.
- If the `LocalData.sav` file already exists in the new folder, **confirm the overwrite** when prompted to replace the existing file.

### 3. Restore Your Map
- Now, go into your **new server/world**, and your map should be restored with the old server/world data.

Done! Your map is back in your **new server/world**!

## 🔁 To Move from Host/Co-op to Server or Vice Versa

For **host/co-op**, the save folder is typically located at:

```
%localappdata%\Pal\Saved\SaveGames\YOURID\RANDOMID\
```

For **dedicated servers**, the save folder is typically located at:

```
steamapps\common\Palworld\Pal\Saved\SaveGames\0\RANDOMSERVERID\
```

---

### 🧪 Transfer Process

1. Copy **`Level.sav` and the `Players` folder** from either your **host/co-op** or **dedicated server** save folder.
2. Paste **`Level.sav` and the `Players` folder** into the other save folder type (host ↔ server).
3. Start the game or server.
4. When prompted to create a **new character**, go ahead and do it.
5. Wait ~2 minutes for the auto-save, then close the game/server.
6. Copy the newly updated **`Level.sav` and `Players` folder** from that world.
7. Paste them into a **temporary folder** somewhere on your PC.
8. Open **PST(PalworldSaveTools)** and choose the **Fix Host Save** option.
9. Select the **`Level.sav`** from your temporary folder.
10. Choose:
    - The **old character** (from original save)
    - The **new character** (you just created)
11. Click **Migrate**.
12. After migration is complete, copy the updated **`Level.sav` and `Players` folder** from the temporary folder.
13. Paste them back into your actual save folder (host or server).
14. Start the game/server and enjoy your character with all progress intact! 

---

# Host Swap Process in Palworld (UID Explained)

## Background
- **Host always uses `0001.sav`** — same UID for whoever hosts.
- Each client uses a unique **regular UID save** (e.g. `123xxx.sav`, `987xxx.sav`).

## Key Prerequisite
Both players (old host and new host) **must have their regular saves generated**.  
This happens by joining the host’s world and creating a new character if none exists.

---

## Step-by-Step Host Swap

### 1. Ensure Regular Saves Exist
- Player A (old host) should have a regular save (e.g. `123xxx.sav`).
- Player B (new host) should have a regular save (e.g. `987xxx.sav`).

### 2. Swap Old Host’s Host Save to Regular Save
- Use PalworldSaveTools to swap:
  - Old host’s `0001.sav` → `123xxx.sav`  
  (This moves old host’s progress from host slot to their regular player slot.)

### 3. Swap New Host’s Regular Save to Host Save
- Use PalworldSaveTools to swap:
  - New host’s `987xxx.sav` → `0001.sav`  
  (This moves new host’s progress into the host slot.)

---

## Result
- Player B is now the host with their own character and pals in `0001.sav`.
- Player A becomes a client with their original progress in `123xxx.sav`.

---

## Summary
- **Swap old host’s `0001.sav` to their regular UID save.**
- **Swap new host’s regular UID save to `0001.sav`.**

---

This process lets both players keep their characters and pals intact while swapping host roles.

---


# Known bugs/issues:

1. **Hostile Pals After Character Transfer**  
   - After transferring a character, some Pals may act aggressive due to ownership issues.  
   - **Workaround:** Add the affected Pal to your party, drop it, then pick it up again to fix ownership.

2. **Steam to GamePass Converter Not Working or Not Keeping Changes**  
   - Please make sure to **close the game** on GamePass.  
   - Wait a few minutes.  
   - Run the **Steam to GamePass converter**.  
   - Wait a few more minutes.  
   - Open the game on GamePass and enjoy your updated save.

3. **Character Transfer: Guild Not Included**  
   - Guilds do **not** transfer with your character—this is intentional.  
   - `Character Transfer` is meant for **cross-world/server transfers**.  
   - It moves your **character, inventory, and Pals**, but **not your guild**.  
   - **Solutions:**  
     - Use `Fix Host Save` for transfers **within the same save** to keep your guild.  
     - Make someone else the **guild leader**, leave the guild, transfer, then get re-invited.

4. **struct.error when parsing the save**  
   - Put the outdated save on Solo, Coop, or Dedicated Server.
   - Load the save and play **once** to let the game auto-update the save file structure.  
   - Ensure your saves were updated **on or after** the current game patch to prevent `struct.error`.  
   - This works because the game rewrites save data structures between versions during play.