# 📆 HOWTO 

## Use `ppcalendar` — Your Terminal Calendar Assistant

Welcome to `ppcalendar` — a colorful, fast, and elegant terminal calendar  
with event support and natural controls.

This guide helps **novices** and casual users quickly get the most out of it.

---

## Install

```bash
uv tool install ppcalendar
```

## Update

```bash
uv tool update ppcalendar
```

## 🚀 Quick Start

To display the current month and today's events:

```bash
cal
```

To add a new event:

```bash
cal add
```

To view surrounding months (previous, current, next):

```bash
cal 3
```

To show a full year:

```bash
cal 2025
```

---

## 📅 Monthly Calendar Display

Here’s what you’ll see when running `cal` or `ppcal`:

```
     May 2025      
Su Mo Tu We Th Fr Sa
             1  2  3
 4  5  6  7  8  9 10
11 12 13 14 15 16 17
18 19 20 21 22 23 24
25 26 27 28 29 30 31
```

Then, just below:

```
📅 Events for today:
 - All day 🔵 Python conference
 - 09:00 🔴 День рождения Жени
 - 11:00 Add colors to events in calendar events.py
```

---

## 📝 Adding Events (`cal add`)

You’ll be guided interactively:

```text
📌 Event description (Enter to end): 🎉 John's Birthday
⏰ Time (13:00 / 1300) [Enter = all day]: 
📅 Date (YYYY-MM-DD / MM-DD / DD) [Enter = today]: 
```

### How to Create One Time Only or Repeating Events

* Date (YYYY-MM-DD / MM-DD / DD) [Enter = today]:

* ONE TIME:
- Enter or YYYY-MM-DD

* EVERY YEAR:
- MM-DD

* EVERY MONTH:
- DD

Examples:

* `🎉 Mom’s Birthday` Date (YYYY-MM-DD / MM-DD / DD) [Enter = today]: 15-10
* `🎈 Rent due` Date (YYYY-MM-DD / MM-DD / DD) [Enter = today]: 05
* `🏡 Buy home` Date (YYYY-MM-DD / MM-DD / DD) [Enter = today]: 2026-10-30

---

## 🎨 Event Colors

Events are automatically color-coded:

| Keyword    | Color   | Example             |
| ---------- | ------- | ------------------- |
| `birthday` | 🔴 Red  | "🎉 Birthday lunch" |
| `рождения` | 🔴 Red  | "🎂 День рождения"  |
| `python`   | 🔵 Blue | "🐍 Python meetup"  |
| `rust`     | 🔴 Red  | "🦀 Rust conf"      |

You can extend these in `COLOR_MAP` in `events.py`.

## 📂 Files and Configuration

* Events are saved in a CSV database (for now).
* Layout, colors, and settings are stored in respected files.

All 3 program files after  
`uv tool install ppcalendar`  
will be located here:  
`.local/share/uv/tools/ppcalendar/lib/python3.11/site-packages/ppcalendar/`

(mind Python version that you use, though)

### 🗃️ Your database file

**By default it is in:**

`.local/share/ppcalendar/db/events.csv`

You can change it to any location you like by editing first lines of:
`.local/share/uv/tools/ppcalendar/lib/python3.11/site-packages/ppcalendar/events.py`

---

## 📍 Event Time

Enter time in formats:

* `14:00`
* `1400`
* Leave blank → **All day**

---

## 🔍 Viewing Events

* `cal` → current month + **today’s events**
* `cal 3` → previous/current/next month (no events)
* `cal 2025` → whole year (no events)

Why events only in current month?

Usually, when one looks at three months and year span, interest is not in
current tasks.

To that that the way I like it to be. But you can easily change it by modifying
two lines in main.py. This will give you events in every view:

```python
def main_cli() -> None:
    """CLI entry logic — handles subcommands."""
    if len(sys.argv) > 1 and sys.argv[1] == "add":
        interactive_add_event()
    else:
        main()
        show_today_events()
```

---

## 🧠 Pro Tips

* Use `cal add` to track birthdays, bills, holidays, and programming goals.
* Accept defaults with **Enter** to quickly log today's events.
* Use colors to visually scan your week.
* Works beautifully in any modern terminal.

---

## 🛣️ Planned (and Possible) Features

* [x] Repeating events (explained above)
* [ ] Event editing
* [ ] Weekly/agenda views
* [ ] iCalendar export/import
* [ ] Time conflict alerts

---

📫 Got feedback?  
Open an issue, suggest a keyword color,  
or just enjoy your improved daily planning.

---

