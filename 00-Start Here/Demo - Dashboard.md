# Demo Campaign Dashboard

> [!note] How This Demo Works
> This folder (`00-Start Here/`) mirrors `Campaign-Vault/` with sample Pathfinder 1e notes so you can see how templates, wikilinks, embeds, and Dataview queries work together. When you're ready for your real campaign, use `Campaign-Vault/`—it automatically excludes `00-Start Here/` and `templates/`.

> [!abstract] Current Context
> - **Book / Arc:** Book 1: Burnt Offerings
> - **Current Location:** Sandpoint
> - **Current Objective:** Explore the Catacombs of Wrath beneath the Glassworks.

---

## Recent Sessions
```dataview
TABLE WITHOUT ID
  file.link AS "Session",
  date AS "Date",
  location AS "Location"
FROM #session AND "00-Start Here"
SORT date DESC
LIMIT 5
```

> [!info]- All Sessions
> ```dataview
> TABLE WITHOUT ID
>   file.link AS "Session",
>   date AS "Date",
>   location AS "Location"
> FROM #session AND "00-Start Here"
> SORT date DESC
> ```

---

## Unresolved Plot Threads & Leads
```dataview
TASK
FROM #session AND "00-Start Here"
WHERE !completed
SORT file.name DESC
```

---

## Top 5 Important NPCs
*Ranked by how many session notes link to them.*
```dataview
TABLE WITHOUT ID
  file.link AS "NPC",
  length(filter(file.inlinks, (x) => contains(x.file.tags, "#session") AND startswith(x.file.path, "00-Start Here"))) AS "Sessions",
  met-at AS "Met At",
  aliases AS "Aliases"
FROM #npc AND "00-Start Here"
SORT length(filter(file.inlinks, (x) => contains(x.file.tags, "#session") AND startswith(x.file.path, "00-Start Here"))) DESC
LIMIT 5
```

> [!info]- All NPCs
> ```dataview
> TABLE WITHOUT ID
>   file.link AS "NPC",
>   met-at AS "Met At",
>   aliases AS "Aliases"
> FROM #npc AND "00-Start Here"
> SORT file.name ASC
> ```

---

## Party Roster
```dataview
TABLE WITHOUT ID
  file.link AS "Character",
  player AS "Player",
  aliases AS "Aliases"
FROM #pc AND "00-Start Here"
SORT file.name ASC
```

---

## Known Threats & Universal Traits

### Recently Updated Monsters
```dataview
LIST
FROM #monster AND "00-Start Here"
SORT file.mtime DESC
LIMIT 10
```

> [!info]- Universal Traits
> ```dataview
> LIST
> FROM #universal-trait AND "00-Start Here"
> SORT file.name ASC
> ```

---

## Locations
```dataview
TABLE WITHOUT ID
  file.link AS "Location",
  aliases AS "Aliases"
FROM #location AND "00-Start Here"
SORT file.name ASC
```
