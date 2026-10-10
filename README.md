# CSSP Senior Mentor Tracker

**CSSP · SR University** (Centre for Student Success & Pathways)

A weekly progress tracking app where **Juniors** submit their LeetCode problem count, **Seniors** verify it live and run weekly mock interviews, and the **Super Admin** oversees every senior and junior across the cohort.

This repository contains the **UI/UX design prompts and exported screens** for all three modules, designed in Google Stitch for both **mobile (390×844)** and **desktop web (1440×900)**.

---

## How it works (the big picture)

```
 Junior  ──submits weekly LeetCode total──▶  Senior  ──verifies live + plans mock──▶  Super Admin
 (Mentee)                                    (Mentor)                                 (Oversight)
```

1. **Super Admin** imports the senior Excel sheets and sets the weekly schedule and plan targets.
2. Each **Junior** logs in, adds profile links and submits the weekly LeetCode total.
3. Each **Senior** reviews the submission, asks the junior to explain one solved problem, marks it Verified or Doubtful, and records the weekly mock interview result.
4. **Super Admin** monitors progress across all seniors and juniors.

---

## Modules

### 1. Admin (Super Admin)
Oversight for the whole programme (about 40 seniors and 480 juniors).

| Screen | What it does |
|---|---|
| Login | Role switch, name selection and 4-digit PIN |
| Overview | Cohort stats (seniors, juniors, updated, pending, below target, missing links, mocks done), global search, list of all seniors |
| Senior Profile | Week status for one senior's juniors, and "Open as this senior" to see the senior's view |
| Junior Profile | Read-only view of profile links, weekly mock, weekly history and mock history |
| Weekly Schedule | Set today's date, week dates and cumulative plan targets |
| Import Data | Upload senior Excel sheets, or one master CSV/Excel, and clear data |
| Help | Login steps, update steps and safety notes |

### 2. Mentor (Senior)
Each senior manages their own group of juniors (about 12).

| Screen | What it does |
|---|---|
| Login | Role switch, name selection and 4-digit PIN |
| Dashboard | Weekly update progress, pending reviews, missing link alerts, stats |
| My Juniors | Searchable and filterable list of juniors with status pills |
| Update Junior | Verify one junior: LeetCode total, problem verification (Verified / Doubtful / Not checked), seriousness (High / Medium / Low), remarks, weekly history |
| Weekly Mock | Schedule mocks, mark done or missed, and record scores (Technical, Communication, Problem solving) |
| All Juniors Updated | Success screen once every junior is updated |
| Help | Login steps, update steps and safety notes |

### 3. Mentee (Junior)
The student's own weekly workspace.

| Screen | What it does |
|---|---|
| Login | Role switch, name selection and 4-digit PIN |
| Home | Plan target vs. latest count, verification status, profile links (add missing ones), submit weekly LeetCode total, weekly mock status, weekly history |
| Help | Login steps and safety notes |

---

## Key concepts

- **Plan target (cumulative):** the number of LeetCode problems a junior should have solved in total by a given week (for example W1 = 98, W8 = 267).
- **Target Met / Below target:** the junior's latest count compared with the plan target.
- **Verification:** the senior asks the junior to explain one solved problem live, then marks it *Verified*, *Doubtful* or *Not checked*.
- **Missing links:** juniors whose LeetCode, HackerRank, GitHub, LinkedIn or Resume link is not provided.
- **Weekly Mock:** a short mock interview per junior per week, scored out of 10.

## Roles and access

| Role | Can do | Cannot do |
|---|---|---|
| Junior | Submit own work, add own links, view own history | See other juniors' data |
| Senior | Update and verify only their own juniors, plan mocks | See other seniors' juniors |
| Super Admin | View everything, set schedule, import data | |

Login uses **role + name + 4-digit PIN** (prototype behaviour).

---

## Design system

Built in Google Stitch using the **Academic Stewardship System**:

| Token | Value |
|---|---|
| Primary (teal) | `#1F4E5A` |
| Secondary (gold) | `#D4A22E` |
| Tertiary (brown) | `#653F20` |
| Neutral | `#64748B` |
| Font | Inter |

Status colours: green = good or verified, amber = pending, red = below target or doubtful, teal = informational.

## Responsive layouts

| Device | Navigation |
|---|---|
| Mobile (390×844) | Top bar and bottom tab bar |
| Desktop (1440×900) | Fixed left sidebar, content area up to 1100px wide |

Navigation items per role:
- **Admin:** Overview, Schedule, Import, Help
- **Mentor:** Dashboard, My Juniors, Weekly Mock, Help
- **Mentee:** Home, Help

---

## Repository structure

```
cssp-mentor-tracker/
├── README.md
├── prompts/
│   ├── admin-prompt.md      # Stitch prompt for all admin screens
│   ├── mentor-prompt.md     # Stitch prompt for all mentor screens
│   └── mentee-prompt.md     # Stitch prompt for all mentee screens
├── admin/                   # Exported admin screens (mobile + desktop)
├── mentor/                  # Exported mentor screens (mobile + desktop)
└── mentee/                  # Exported mentee screens (mobile + desktop)
```

## How to regenerate the screens

1. Open the Stitch project that contains the Login screen and the Academic Stewardship System design system.
2. Open one prompt file from `prompts/`, copy the text inside the code block and paste it into Stitch.
3. Wait for the screens to finish generating, then ask Stitch to continue if some screens are missing.
4. Export the result into the matching folder (`admin/`, `mentor/` or `mentee/`).

Do one role at a time so the style stays consistent.

## Status

| Module | Prompts | Screens exported |
|---|---|---|
| Admin | Ready | Pending |
| Mentor | Ready | Pending |
| Mentee | Ready | Pending |

---

© CSSP · SR University. Internal project.
