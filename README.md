<p align="center">
  <img src="./logo.png" width="220">
</p>

<h1 align="center">Assets — Untitled Shooting Game</h1>

<p align="center">
  Assets and data files for Untitled Shooting Game
</p>

# Assets — Untitled Shooting Game

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
  "hp",
  "speed",
  "turnrate",
  "defense",
  "boss-status"
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

# Notes

- Array order matters.
- Changing the order of values ***WILL*** break compatibility with the game importer.
- Some files may include additional values for special enemy behaviours.
