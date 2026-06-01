<p align="center">
  <img src="./logo.png" width="850">
</p>

<h1 align="center">Assets — Untitled Shooting Game</h1>

<p align="center">
  Assets and data files used by Untitled Shooting Game
</p>

---

This repository contains the assets and data files used for **Untitled Shooting Game**, created by [JaseemTheGreat](https://github.com/JaseemTheGreat).

## General Format

Most files in this repository use arrays (`[]`) for data storage and parsing.

---

# Enemy Costumes

**Directory:**  
`/Costumes/Enemies/`

[Enemy Costumes Folder](./Costumes/Enemies/)

Enemy costume files contain Data URIs corresponding to enemy images.  
The game importer uses these values to automatically identify and load sprites.

## Format

```js
[
  "defaultCostume",
  "stunCostume",
  "punch1Costume",
  "punch2Costume"
]
```

Additional entries may exist for special animations or other abilities.

---

# Enemy Costumes Identifiers

**Directory:**  
`/CostumesIdentifiers/Enemies/`

[Enemy Costumes Identifiers Folder](./CostumesIdentifiers/Enemies/)

Enemy costume files contain suffixes corresponding to enemy images.  
The game importer uses these values to automatically identify and load the images with the correct names.

## Format

```js
[
  "",
  "-Stun",
  "-Punch-1",
  "-Punch-2"
]
```


So if paired with the Normal in the game, its costumes' will be named:

```text
Normal,
Normal-Stun,
Normal-Punch-1,
Normal-Punch-2
```

| Value | Description |
|---------|-------------|
| `""` | It represents the default costume's name (which has no suffixes) |
| `-Stun` | It represents the Stunned costume's name (THIS COSTUME MAY NOT EXIST IF THE ENEMY HAS STUN RESIST) |
| `-Punch-1` | It represents the suffix of first frame of the costume's punch |
| `-Punch-2` | Do I need to say more? |

Additional entries may exist for special animations or other abilities.

---

# Enemy Data

**Directory:**  
`/Data/Enemies/`

[Enemy Data Folder](./Data/Enemies/)

Enemy data uses the following structure:

```js
[
  "EnemyName",
  {
    "hp": "hp",
    "speed": "speed",
    "turnrate": "turnrate",
    "defense": "defense",
    "bossStatus": "boss-status"
  }
]
```

## Value Descriptions

| Value | Description |
|---------|-------------|
| `EnemyName` | Enemy name |
| `hp` | Health points |
| `speed` | Movement speed |
| `turnrate` | Rotation speed |
| `defense` | Damage resistance value |
| `bossStatus` | Boss state (`0 = false`, `1 = true`) |

---

# Enemy Abilities

**Directory:**  
`/Data/EnemiesAbilities/`

[Enemy Abilities Folder](./Data/EnemiesAbilities/)

These contain abilities the enemies can perform and the abilities data.

## Format

```js
["abilityname"[abilitydata]]
```

| Abilities | Description |
|---------|-------------|
| `["Punch", ["size", "dmg", "range"]]` | This is the usual ability most enemies use, the size of the punch shockwave, the damage and range is controlled by the second array |
| `["Kick", ["size, "dmg", "range"]]` | basically like punch but much more faster |
| `["Stomp", ["size", "dmg", "range"]]` | the Enemy raises their foot and get ready to stomp. |
| `"Summon", ["CemeteryWorker", 15, 40, "each-anim-summon"]]` | Do I need to say more? |

Additional entries may exist for special animations or other abilities.

---

# Gun Costumes

**Directory:**  
`/Costumes/Guns/`

[Gun Costumes Folder](./Costumes/Guns/)

Gun costume files contain Data URIs corresponding to weapon images.

Although these only contain one value, they remain stored inside arrays to keep the asset format consistent across the project.

## Format

```js
[
  "gunCostume"
]
```

---

# Gun Data

**Directory:**  
`/Data/Guns/`

[Gun Data Folder](./Data/Guns/)

Gun data uses the following structure:

```js
[
  "GunName",
  {
    "range": "value",
    "dmg": "value",
    "rpm": "value",
    "bulletSpeed": "value",
    "recoil": "value",
    "offset": "value",
    "type": "value",
    "bulletSize": "value",
    "magazineSize": "value"
  }
]
```

## Value Descriptions

| Value | Description |
|---------|-------------|
| `GunName` | Weapon name |
| `range` | Maximum weapon range |
| `dmg` | Damage dealt per shot |
| `rpm` | Fire rate (rounds per minute) |
| `bulletSpeed` | Projectile speed |
| `recoil` | Recoil amount |
| `offset` | Offset from the center of the arm sprite |
| `type` | Weapon type (`pistol`, `rifle`, `sniper`, `shotgun`, etc.) |
| `bulletSize` | Projectile size |
| `magazineSize` | Maximum ammo per magazine |

---

# Sounds

**Directory:**  
`/Sounds/[random directory]`

Contains raw Data URI audio files used for sound effects and music.

For example:
```js
["dataURIofaudio"]
```

These files store firing sounds and boss music only. Other sounds (reloads, effects, etc.) are handled internally by the game.

---

# Wave Spawning

**Directory:**  
`/Gamemode/[GamemodeName]/`

Wave spawning data uses the following structure:

```js
[["enemy1", "enemyamount", "enemyspawnspeed"], ["enemy2", "enemyamount", "enemyspawnspeed"]]
```

## Value Descriptions

| Value | Description |
|---------|-------------|
| `enemy1` & `enemy2` | Name of Enemy |
| `enemyamount` | The amount of enemies that spawn per array (usually an integer like `1, 2, 3`) |
| `enemyspawnspeed` | The speed the enemies spawn (usually a float like `0.15, 0.5, 1.5`) |

---

# Notes

- Array order matters.
- Changing array order **will break compatibility** with the game importer.
- Object key order does **not** matter:

```js
{
  "hp": 50,
  "speed": 5
}
```

As long as the correct key names are used, objects can be ordered however you want.

```js
{
  "speed": 5,
  "hp": 50
}
```


- Some files may contain additional values for special enemy behaviors or future features.
