# How-To Guide: Using Your Pathfinder 1e Campaign Vault

Welcome! If you have never used **Obsidian** before, don't worry—you only need a few simple habits to get the most out of this vault.

This `00-Start Here/` folder is a **working demo**. Look around [[Demo - Dashboard|Demo Dashboard]] and the `Demo - ` notes inside `00-Start Here/` to see everything in action. When you are ready to take notes for your real game, use the **`Campaign-Vault/`** folder instead.

---

## 1. Creating a New Note from a Template

Every type of note (Session, PC, NPC, Monster, Universal Trait, Location) has a ready-made template in `templates/`. There are two ways to create one:

### Option A: Right-click a folder (Fastest)
1. Right-click any folder inside `Campaign-Vault/` (for example, `01-Sessions` or `02-Codex/02.04 Important NPCs`) and click **New note**.
2. Name your note (for example, `Session 04 - The Glassworks` or `Sheriff Belor Hemlock`).
3. **That's it!** Templater automatically inserts the matching template for that folder—do **not** insert a template manually afterward.

### Option B: Create from anywhere (`Ctrl/Cmd + N` → `Ctrl/Cmd + P`)
1. Press `Ctrl + N` (Windows/Linux) or `Cmd + N` (Mac) and name your note.
2. Press `Ctrl/Cmd + P` (or click the **Templater** icon in the left sidebar), type **Templater: Open Insert Template modal**, and press `Enter`. *(Note: `Alt + E` also works on some systems, though it can be intercepted on Windows.)*
3. Pick the template you need:
   - **Session Template** → `Campaign-Vault/01-Sessions/`
   - **PC Template** → `Campaign-Vault/02-Codex/02.03 PCs/`
   - **NPC Template** → `Campaign-Vault/02-Codex/02.04 Important NPCs/`
   - **Monster Template** → `Campaign-Vault/02-Codex/02.01 Monsters/`
   - **Universal Trait Template** → `Campaign-Vault/02-Codex/02.02 Universal Traits/`
   - **Location Template** → `Campaign-Vault/02-Codex/02.05 Locations/`
4. Auto Note Mover will automatically file the note into the right folder based on its tag!

> [!tip] Don't stress about perfection
> These templates are intentionally light. Leave fields blank if you don't know them yet, and add your own headings or bullet points whenever you want to track more.
> - **Multiple locations in one session?** Either pick the **most important location** to keep the Dashboard table tidy, or separate multiple links with commas (e.g., `**Location**:: [[Sandpoint]], [[Glassworks]]`).
> - **Naming the session later?** Drop funny quotes or title ideas under `## Session Title Ideas` at the bottom during play, then rename the note afterward.

---

## 2. How to Link Notes Together (`[[Wikilinks]]`)

Obsidian's superpower is linking notes together so you can click straight from a session to an NPC, PC, Location, or Monster.

- **Basic link:** Type two opening square brackets `[[` and start typing a note's name. Obsidian will show an autocomplete menu—press `Enter` to pick it.
  - Example: `[[Demo - Sheriff Belor Hemlock]]`
- **Custom display text:** Add a `|` (pipe) after the note name to change how the link reads in a sentence.
  - Example: `a band of [[Demo - Goblin|goblins]] ambushed us` displays as: a band of [[Demo - Goblin|goblins]] ambushed us.

### Why linking NPCs matters
Your **Dashboard** automatically finds your **Top 5 Important NPCs** by counting how many *session notes* link to each NPC.
- In the demo, `[[Demo - Sheriff Belor Hemlock]]` is linked in 3 sessions, `[[Demo - Ameiko Kaijitsu]]` in 2, and `[[Demo - Brodert Quink]]` in 1—so the Dashboard automatically ranks them at the top without you doing any extra work!

*(Check [[Demo - Session 01 - Swallowtail Festival]] in `00-Start Here/01-Sessions/` to see this in action.)*

---

## 3. How to Embed Universal Traits in Monster Notes

When you fight a monster with Pathfinder Universal Monster Rules (like *Undead Traits*, *Darkvision*, or *Damage Reduction*), you don't have to copy-paste the rules every time. You can **embed** the trait note directly inside the monster note by putting an exclamation mark `!` in front of a link:

```markdown
> [!info]- Universal Traits
> ![[Demo - Undead Traits (Ex)]]
>
> ![[Demo - Damage Reduction (Ex or Su)]]
```

- Adding `!` before `[[...]]` pulls the full content of that trait note right into the collapsible box.
- Click the arrow next to **Universal Traits** in Reading View to expand or collapse it mid-combat.
- Check [[Demo - Skeleton]] in `00-Start Here/02-Codex/02.01 Monsters/` to see how this looks!

---

## 4. Tracking Plot Threads & Open Questions

During a long Adventure Path, it is easy to lose track of mysteries and side quests. Anytime a question or task comes up during a session, type a checkbox using `- [ ]` anywhere in your session note:

```markdown
- [ ] Ask [[Demo - Brodert Quink|Brodert Quink]] to translate the Thassilonian symbols.
```

- Every unchecked `- [ ]` item in your session notes automatically appears on the **Dashboard** under **Unresolved Plot Threads & Leads**.
- When your party resolves it, click the checkbox on the Dashboard (or in the session note) to check it off (`- [x]`), and it will clear off the Dashboard automatically.

---

## 5. Quick Cheat Sheet

| What you want to do | What to type / press |
| :--- | :--- |
| New note (auto-templated in folder) | Right-click folder → **New note** |
| New note (anywhere) | `Ctrl + N` (Win/Linux) or `Cmd + N` (Mac) |
| Insert template manually | `Ctrl/Cmd + P` → *Templater: Open Insert Template modal* |
| Link to another note | `[[Note Name]]` |
| Link with custom text | `[[Note Name\|custom text]]` |
| Embed a Universal Trait | `![[Trait Name]]` |
| Add a plot thread / to-do | `- [ ] Your note here` |
| Switch Edit / Reading view | `Ctrl + E` (Win/Linux) or `Cmd + E` (Mac) |
