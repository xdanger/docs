# PARA File Organization Guidelines

> Based on Tiago Forte's PARA Method. Token-optimized for AI-assisted organization.

## Core Definition

| Category      | Definition                           | End Date     | Key Question                             |
| ------------- | ------------------------------------ | ------------ | ---------------------------------------- |
| **Projects**  | Short-term efforts with clear goal   | Has deadline | "What am I trying to accomplish?"        |
| **Areas**     | Ongoing responsibilities to maintain | Indefinite   | "What standard must I uphold?"           |
| **Resources** | Topics of interest for future use    | N/A          | "Is this useful (not just interesting)?" |
| **Archives**  | Inactive items from above three      | N/A          | "Is this currently actionable?"          |

## Decision Flowchart

```
New item arrives
    │
    ├─ Is it actionable NOW?
    │   ├─ YES: Has clear goal + deadline?
    │   │       ├─ YES → Projects/
    │   │       └─ NO: Ongoing responsibility?
    │   │               ├─ YES → Areas/
    │   │               └─ NO → Resources/
    │   └─ NO: Was it ever active?
    │           ├─ YES → Archives/
    │           └─ NO → Resources/ (or delete)
    │
    └─ Uncertain? → 0 Inbox/ (process weekly)
```

## Naming Conventions

> See **[Naming-Conventions.md](Naming-Conventions.md)** for complete file/folder naming rules.

| Category  | Folder Style | Example                        |
| --------- | ------------ | ------------------------------ |
| Projects  | Title-Case   | `1_Projects/Website-Redesign/` |
| Areas     | UPPERCASE    | `2_Areas/HEALTH/`              |
| Resources | lowercase    | `3_Resources/cooking-recipes/` |
| Archives  | Date prefix  | `4_Archives/2024-Q4/`          |

**Top-level structure:**

```
0_Inbox/
1_Projects/
2_Areas/
3_Resources/
4_Archives/
```

## Core Principles

### 1. Organize for Action

- Group by **outcome**, not by subject/topic
- Ask: "When will I need this?" not "What type is this?"
- Projects folder = most actionable, smallest, most frequently accessed

### 2. Just-in-Time Organization

- Never create empty folders
- Organize only when you have something to put there
- Minimal structure > elaborate taxonomy

### 3. Keep Things Informal

- Only Projects need precision (clear goal + deadline)
- No nested subfolders beyond 2 levels
- No rigid templates or databases for personal info
- Allow messiness — unexpected connections create value

### 4. Information Flows

Items move between categories as life changes:

- Project completed → Archives
- Resource becomes responsibility → Areas
- Area spawns new effort → Projects
- Interest fades → Archives

**Never duplicate.** Move, link, or tag instead.

## Projects vs Areas (Critical Distinction)

| Aspect         | Project                            | Area                        |
| -------------- | ---------------------------------- | --------------------------- |
| Duration       | Finite (days-months)               | Indefinite                  |
| Success metric | Goal achieved                      | Standard maintained         |
| Feeling        | Sprint                             | Marathon                    |
| Examples       | "Write Q4 report", "Plan vacation" | "Health", "Team management" |

**Red flag:** If your "project" has no end date, it's an Area.
**Red flag:** If your "area" feels urgent with deadline, extract a Project from it.

## Areas vs Resources (Privacy Boundary)

| Aspect         | Areas                         | Resources                           |
| -------------- | ----------------------------- | ----------------------------------- |
| Responsibility | Direct                        | None                                |
| Privacy        | Private by default            | Shareable by default                |
| Content        | Personal standards            | General interest                    |
| Examples       | `HEALTH` (my medical records) | `nutrition research` (general info) |

## Weekly Maintenance (5 min)

1. **Retitle** inbox items with clear names
2. **Sort** items into PARA folders using flowchart
3. **Update** Projects:
   - Archive completed/canceled projects
   - Split large projects into smaller ones
   - Unarchive reactivated projects

## Escape Hatch: Digital Bankruptcy

When overwhelmed:

1. Select ALL existing files
2. Move to `Archives/Archive [Today's date]/`
3. Start fresh with empty Projects folder

**No downside.** Everything remains searchable. Search > perfect organization.

## AI Assistant Instructions

When helping organize files:

1. **Ask first:** "Is this currently actionable for you?"
2. **Default to Resources** when uncertain (lowest commitment)
3. **Never create speculative folders** — wait for actual content
4. **Preserve existing structure** where it works
5. **Batch similar decisions** to reduce cognitive load

### Quick Classification Prompts

For ambiguous items, ask:

- "Does this have a deadline?" → Projects
- "Are you directly responsible for this?" → Areas
- "Is this just interesting or actually useful?" → Resources
- "Have you touched this in 6+ months?" → Archives

## File Type Routing

| Type                  | Destination                     |
| --------------------- | ------------------------------- |
| Appointments/meetings | Calendar (time-based)           |
| Tasks                 | To-do app (Projects/Areas only) |
| Text/notes            | Notes app (best search)         |
| Collaborative docs    | Cloud drive                     |
| Large/special files   | Local filesystem                |
| Sensitive data        | Encrypted storage               |

---

_Simplicity is the goal. If your system is as complex as your life, maintaining it will rob you of time to live that life._
