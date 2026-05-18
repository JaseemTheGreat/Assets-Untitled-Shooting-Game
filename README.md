# Assets — Untitled Shooting Game

This repository contains the assets and data files used for **Untitled Shooting Game**.

## General Format

Most files use arrays `[]` for data storage and parsing.

---

# Enemy Costumes

Directory:
`/Costumes/Enemies/`

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
| `boss-status` | Whether the enemy is a boss (`true` or `false`) |

---

# Notes

- Array order matters.
- Changing the order of values may break compatibility with the game importer.
- Some files may include additional values for special enemy behaviours.
