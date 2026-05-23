<p align="center">
  <img src="./logo.png" width="850">
</p>

<h1 align="center">Assets — Untitled Shooting Game</h1>

<p align="center">
  Assets and data files for Untitled Shooting Game
</p>

---

This repository contains the assets and data files used for **Untitled Shooting Game**, a project created by [JaseemTheGreat](https://github.com/JaseemTheGreat)

## General Format

Most files use arrays `[]` for data storage and parsing.

---

# Enemy Costumes

Directory:
`/Costumes/Enemies/`
[Direct Link to Enemy Costumes](./Costumes/Enemies/)

Each enemy contains a Data URI corresponding to its image.  
This allows the game to automatically recognise and import enemy sprites.

## Format

```js
[
  "defaultcostume",
  "stuncostume",
  "punch1costume",
  "punch2costume"
]
```

Additional array entries may correspond to extra enemy abilities or animations.

---

# Enemy Data

Directory:
`/Data/Enemies/`
[Direct Link to Enemy Data](./Data/Enemies/)

Enemy data is stored using the following format:

```js
[
  "name",
  {
    hp: "hp",
    speed: "speed",
    turnrate: "turnrate",
    defense: "defense",
    bossStatus: "boss-status"
  }
]
```

## Value Descriptions

| Value | Description |
|---|---|
| `name` | Enemy name |
| `hp` | Enemy health points |
| `speed` | Enemy movement speed |
| `turnrate` | Rotation / turning speed |
| `defense` | Damage resistance value |
| `boss-status` | Whether the enemy is a boss (`0` or `1`) |

---

# Gun Costumes

Directory:
`/Costumes/Guns/`
[Direct Link to Gun Costumes](./Costumes/Guns/)

Gun costumes are stored as Data URIs corresponding to their image.  
These are used by the game importer to automatically recognise weapon sprites.

Although gun costumes only contain a single object, they are still stored in arrays to maintain consistency with the rest of the asset system.

## Format

```js
[
  "guncostume"
]
```

---

# Gun Data

Directory:
`/Data/Guns/`
[Direct Link to Gun Data](./Data/Guns/)

Gun data is stored using the following format:

```js
[
  "GunName",
  "GunRange",
  "GunDMG",
  "GunRPM",
  "BulletSpeed",
  "GunRecoil",
  "GunOffset",
  "GunType",
  "BulletSize",
  "MagazineSize"
]
```

## Value Descriptions

| Value | Description |
|---|---|
| `GunName` | Name of the weapon |
| `GunRange` | Maximum range of the weapon |
| `GunDMG` | Damage dealt per shot |
| `GunRPM` | Fire rate in rounds per minute |
| `BulletSpeed` | Speed of the projectile |
| `GunRecoil` | Amount of recoil produced when firing |
| `GunOffset` | Offset from the centre of the arm sprite |
| `GunType` | Weapon category (`pistol`, `rifle`, `sniper`, `shotgun`, etc.) |
| `BulletSize` | Size of the projectile |
| `MagazineSize` | Maximum ammo capacity per magazine |

---

# Sounds

Directory:
`/Sounds/Guns/File/`
[Direct Link to Sound Files](./Sounds/Guns/File/)

This directory contains the raw audio files used for weapon sound effects.

Supported formats may include:

- `.mp3`
- `.wav`

These files contain audio firing sounds, reload and other effects are handled within the game itself

---

# Gun Sounds

Directory:
`/Sounds/Guns/Link/`
[Direct Link to Gun Sound Links](./Sounds/Guns/Link/)

Gun sound link files are stored as `.dat` files containing a direct Raw GitHub URL to the corresponding sound file.

This system exists because Scratch cannot easily read and import `.mp3` or `.wav` files directly from normal GitHub file pages. Using Raw GitHub links allows the game importer to access the audio files more reliably.

Although these files only contain a single value, they are still stored using arrays to maintain consistency throughout the repository.

## Format

```js
[
  "rawgithubsoundurl"
]
```

Example:

```js
[
  "https://raw.githubusercontent.com/user/repository/main/Sounds/Guns/File/PistolFire.mp3"
]
```

---

# Notes

- Array order matters.
- Changing the order of values ***WILL*** break compatibility with the game importer. However if the array has a JSON objects ({hi: "hi}), order will not matter, as LONG as you use the correct values, only the array's order itself needs to be in proper order.
- Some files may include additional values for special enemy behaviours.
