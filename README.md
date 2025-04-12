```
  ___      _                _    _ ___              _____         _    
 | _ \__ _| |_ __ _____ _ _| |__| / __| __ ___ ____|_   _|__  ___| |___
 |  _/ _` | \ V  V / _ \ '_| / _` \__ \/ _` \ V / -_)| |/ _ \/ _ \ (_-<
 |_| \__,_|_|\_/\_/\___/_| |_\__,_|___/\__,_|\_/\___||_|\___/\___/_/__/

```
---
- **Contact me on Discord:** Pylar1991
---
## Prerequisites

### 1. **Updated Saves**
- Ensure your saves were updated on/after the current patch.

### 2. **[Python Installation](https://www.python.org/downloads)**
- Download Python from the official website.  
- Before clicking **Install Now**, **CHECK** the box at the bottom that says:  
  **"Add Python to PATH"** 🟩  
  (*This ensures Python is accessible from the command line!*)  
  ![Add Python to PATH checkbox](https://i.imgur.com/SCJEkdJ.png)
  
### 3. ***Start Menu.cmd***

---

## Features:

- **Fast parsing/reading** tool—one of the quickest available.  
- Lists all players/guilds.  
- Lists all pals and their details.  
- Displays last online time for players.  
- Logs players and their data into `players.log`.  
- Filters and deletes players based on level, inactivity, or maximum number of pals, with filtering available through the players' UID in the `players_filtered.log`.
- Logs and sorts players by the number of pals owned.  
- Deletes players with fewer than a specified number of pals.   
- Provides a **base map view**.
- Provides automated killnearestbase commands to be used with PalDefender for inactive bases.
- Transfers saves between dedicated servers and single/coop worlds.  
- Includes Steam ID conversion.
- Includes coords conversion.  
- Includes GamePass ⇔ Steam conversion.
- Slot injector, a simple tool to increase slots each player can have on world/server. Works with Bigger PalBox mod.

---

## Automatically Delete Player Saves Based on Inactivity:

Follow these steps to delete inactive players based on your criteria (e.g., inactivity, level, or number of pals):

1. Copy Players folder and Level.sav from your server:

	```
	\Pal\Saved\SaveGames\0\RANDOMSERVERID\
	``` 

   to the (`PalworldSave`) folder. 
2. Select Scan Save.
3. Select Delete Inactive Players Saves.
4. Input your desired requirements, then let it finish.  
5. Copy the `Players` folder from the `PalworldSave` folder.  
6. Delete the original `Players` folder from the server:

	```
	\Pal\Saved\SaveGames\0\RANDOMSERVERID\
	```

7. Paste the copied `Players` folder into the server folder.  
8. Restart the server:  
   - Reboot once to clear the player from `Level.sav`.  
   - Reboot a second time to clear the player from RAM.  
9. Profit?  

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

## Where to find the save files:

The save files are usually located at:
```
C:\Users\YOURUSERNAME\AppData\Local\Pal\Saved\SaveGames\YOURSTEAMID\RANDOMID
``` 
for co-op saves.
For server saves, go to the dedicated server's file location through steam.
You need at least 4 files to complete the transfer:
```
- The source player character save in Players folder
- The source world's Level.sav
- The target player character save in Players folder
- The target world's Level.sav
```

## How to use Transfer Character:

⚠️WARNING⚠️: Make sure to disable the private locks on the "source" chests before transferring saves!!!

Let's say we want to transfer the character from a coop world of a friend to our own world.
The friend's world would be the source, our own world the destination.

SaveGames folder of our friend:
```
SaveGames
└── <steam-id>
    └── <source-world-id>
        ├── backup
        ├── Level.sav  ----------  <- The source world save
        ├── LevelMeta.sav
        ├── Players
        │   ├── 00000...0001.sav
        │   └── 12345...6789.sav   <- The source player save
        └── WorldOption.sav
```
Our SaveGames folder:
```
SaveGames
└── <steam-id>
    └── <destination-world-id>
        ├── backup
        ├── Level.sav  ----------  <- The target world save
        ├── LevelMeta.sav
        ├── Players
        │   ├── 00000...0001.sav   <- The target player save
        │   └── 98765...4321.sav
        └── WorldOption.sav
```

### Transferring from Host to Server (or vice versa):

# Palworld Save Transfer Guide

## 1. Backup Your Saves

### Solo/Co-op World Backup

1. Open **Palworld** and load into your world.
2. Open **File Explorer** and search for:
   ```
   %localappdata%\Pal\Saved\SaveGames\
   ```
3. Find the folder with a **random ID** (your **Steam ID**).
4. Open that folder and **sort subfolders by 'Last Modified' date**.
5. The most recent folder is your **world**—open it.
6. Copy the following files and folders:
   - `Level.sav`
   - `Players` folder
   - *(Optional)* `LocalData.sav`, `WorldOption.sav`
7. Paste them into a new **temporary folder**.

### Dedicated Server Backup

1. Navigate to your server save folder (default location):
   ```
   steamapps\common\Palworld\Pal\Saved\SaveGames\0\RANDOMSERVERID\
   ```
2. Copy:
   - `Level.sav`
   - `Players` folder
3. Paste them into a new **temporary folder**.

---

## 2. Transfer Saves

### Solo/Co-op to Server

1. **Start the server** and let it run for **2 minutes** to auto-save.
2. **Shut down the server**.
3. Copy files from the **temporary folder**.
4. Navigate to:
   ```
   steamapps\common\Palworld\Pal\Saved\SaveGames\0\RANDOMSERVERID\
   ```
5. Paste the copied files into this folder.
6. **Start the server** and join it.
7. **Create a new character** and wait for the **auto-save**.
8. **Shut down the server**.
9. Copy the updated files from:
   ```
   steamapps\common\Palworld\Pal\Saved\SaveGames\0\RANDOMSERVERID\
   ```
10. Paste them into a **new or existing temporary folder**.

### Server to Solo/Co-op

1. Copy the following from:
   ```
   steamapps\common\Palworld\Pal\Saved\SaveGames\0\RANDOMSERVERID\
   ```
   - `Level.sav`
   - `Players` folder
2. Paste them into a **temporary folder**.
3. Start **Palworld** and create a **new world**.
4. Create a **new character** and wait **2 minutes** for the auto-save.
5. **Close the game**.
6. Copy the files from the **temporary folder**.
7. Open **File Explorer** and search for:
   ```
   %localappdata%\Pal\Saved\SaveGames\
   ```
8. Find the **most recently modified** world folder and open it.
9. Paste the copied files into this folder.
10. Start **Palworld**, rejoin your world, and **create a new character**.
11. Wait **2 minutes** for the auto-save, then **close the game**.
12. Reopen the save folder and check the `Players` folder. It should contain:
    - `0001.sav` (host save)
    - `RANDOMID....000.sav` (your regular save)
13. Copy:
    - `Players` folder
    - `Level.sav`
14. Paste them into a **new or existing temporary folder**.

---

## 3. Character Transfer

1. Open the **Character Transfer** tool.
2. Click `Select Source Level File` and select `Level.sav` from your **temporary folder**.
3. Click `Select Target Level File` and select `Level.sav` from your same **temporary folder**.
3. After loading, select:
   - **Source Player** (your old character)
   - **Target Player** (your new character)
   - **Optional** (If you want to keep old guild id, to take old player's bases/etc, make sure to tick the option that says "Keep old Guild ID after Transfer".)
4. Click `Start Transfer!` once confirmed.

---

## 4. Update Saves

### Server to Solo/Co-op

1. Copy the migrated:
   - `Players` folder
   - `Level.sav`
2. Open **File Explorer** and search for:
   ```
   %localappdata%\Pal\Saved\SaveGames\
   ```
3. Find the **most recently modified** world folder and open it.
4. Paste the copied files into this folder.
5. Start **Palworld**, load your world, and enjoy your character with all progress intact.

### Solo/Co-op to Server

1. Copy the migrated:
   - `Players` folder
   - `Level.sav`
2. Navigate to:
   ```
   steamapps\common\Palworld\Pal\Saved\SaveGames\0\RANDOMSERVERID\
   ```
3. Paste the copied files into this folder.
4. Start **Palworld**, join the server, and enjoy your character with all progress intact.
