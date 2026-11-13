# Campaign Dashboard

> [!tip] New to this vault?
> Check [[00-Campaign Setup]] for your Session 1 checklist, or read the [[00-Start Here/How-To Guide|How-To Guide]] and [[Demo - Dashboard|Demo Dashboard]] to see how everything works. *(You can remove this box once you're set up.)*

> [!abstract] Current Context
> - **Book / Arc:** 
> - **Current Location:** 
> - **Current Objective:** 

---

## Recent Sessions
```dataview
TABLE WITHOUT ID
  file.link AS "Session",
  date AS "Date",
  location AS "Location"
FROM #session AND -"templates" AND -"00-Start Here"
SORT date DESC
LIMIT 5
```

> [!info]- All Sessions
> ```dataview
> TABLE WITHOUT ID
>   file.link AS "Session",
>   book AS "Book",
>   date AS "Date",
>   location AS "Location"
> FROM #session AND -"templates" AND -"00-Start Here"
> SORT date DESC
> ```

---

## Unresolved Plot Threads & Leads
```dataview
TASK
FROM #session AND -"templates" AND -"00-Start Here"
WHERE !completed
SORT file.name DESC
```

---

## Top 5 Important NPCs
*Ranked by how many session notes link to them.*
```dataview
TABLE WITHOUT ID
  file.link AS "NPC",
  length(filter(file.inlinks, (x) => contains(x.file.tags, "#session") AND !startswith(x.file.path, "00-Start Here") AND !startswith(x.file.path, "templates"))) AS "Sessions",
  met-at AS "Met At",
  aliases AS "Aliases"
FROM #npc AND -"templates" AND -"00-Start Here"
SORT length(filter(file.inlinks, (x) => contains(x.file.tags, "#session") AND !startswith(x.file.path, "00-Start Here") AND !startswith(x.file.path, "templates"))) DESC
LIMIT 5
```

> [!info]- All NPCs
> ```dataview
> TABLE WITHOUT ID
>   file.link AS "NPC",
>   met-at AS "Met At",
>   aliases AS "Aliases"
> FROM #npc AND -"templates" AND -"00-Start Here"
> SORT file.name ASC
> ```

---

## Party Roster
```dataview
TABLE WITHOUT ID
  file.link AS "Character",
  player AS "Player",
  aliases AS "Aliases"
FROM #pc AND -"templates" AND -"00-Start Here"
WHERE status != "retired" AND status != "deceased"
SORT file.name ASC
```

---

## Locations
```dataview
TABLE WITHOUT ID
  file.link AS "Location",
  aliases AS "Aliases"
FROM #location AND -"templates" AND -"00-Start Here"
SORT file.name ASC
```

---

## Known Threats & Universal Traits

### Recently Updated Monsters
```dataview
LIST
FROM #monster AND -"templates" AND -"00-Start Here"
SORT file.mtime DESC
LIMIT 10
```

> [!info]- Universal Traits
> ```dataview
> LIST
> FROM #universal-trait AND -"templates" AND -"00-Start Here"
> SORT file.name ASC
> ```
