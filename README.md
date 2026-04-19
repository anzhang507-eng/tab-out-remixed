# Tab Out Remixed

**Keep tabs on your tabs. Now with Feishu document management.**

Tab Out Remixed is a modified version of [Tab Out](https://github.com/zarazhangrui/tab-out) that adds Feishu (飞书) document management features while preserving all original functionality.

Repository: https://github.com/anzhang507-eng/tab-out-remixed

---

## What is this?

This is a fork of Tab Out with additional features for managing Feishu (飞书) documents:

- **Feishu Only view** - Filter to show only Feishu document tabs
- **Opening time display** - See when each tab was opened
- **Time-based grouping** - Organize Feishu tabs by time (Just now, Within 2 hours, Within 8 hours, Yesterday, Earlier)
- **Wider cards for Feishu** - 380px card width in Feishu view for better document readability

---

## Features

All original Tab Out features plus:

- **All original Tab Out features** - Domain grouping, homepages group, swoosh + confetti, duplicate detection, etc.
- **Feishu Only toggle** - Switch between showing all tabs or only Feishu documents
- **Tab opening time** - Each card shows when the tab was opened
- **Time-based grouping** - Feishu tabs grouped by: Just now, Within 2 hours, Within 8 hours, Yesterday, Earlier
- **Optimized card width** - 380px width for Feishu view (vs 280px default)

---

## Install

**1. Clone the repo**

```bash
git clone https://github.com/your-repo/tab-out-remixed.git
cd tab-out-remixed
```

**2. Load the Chrome extension**

1. Open Chrome and go to `chrome://extensions`
2. Enable **Developer mode** (top-right toggle)
3. Click **Load unpacked**
4. Navigate to the `extension/` folder and select it

**3. Open a new tab**

You'll see Tab Out Remixed.

---

## How to use

```
You open a new tab
  -> Tab Out shows your open tabs grouped by domain
  -> Toggle "Feishu Only" to filter only Feishu documents
  -> Feishu tabs are grouped by time: Just now, Within 2h, Within 8h, Yesterday, Earlier
  -> Click any tab title to jump to it
  -> Close groups with style (swoosh + confetti)
  -> Save tabs for later before closing them
```

---

## New features in detail

### Feishu Only view

Click the "Feishu Only" toggle in the header to switch between:
- **All tabs** - Shows all open tabs grouped by domain
- **Feishu Only** - Shows only Feishu document tabs, grouped by opening time

### Time-based grouping (Feishu Only mode)

When in Feishu Only mode, tabs are automatically grouped by:

| Group | Criteria |
|-------|----------|
| Just now | Opened within last few minutes |
| Within 2 hours | Opened between 2 min - 2 hours ago |
| Within 8 hours | Opened between 2 - 8 hours ago |
| Yesterday | Opened yesterday |
| Earlier | Opened before yesterday |

### Card display

- In **All tabs** mode: 280px card width
- In **Feishu Only** mode: 380px card width (wider for document readability)

---

## Tech stack

| What | How |
|------|-----|
| Extension | Chrome Manifest V3 |
| Storage | chrome.storage.local |
| Sound | Web Audio API (synthesized, no files) |
| Animations | CSS transitions + JS confetti particles |
| History API | chrome.history for tab opening time |

---

## Credit

Based on [Tab Out](https://github.com/zarazhangrui/tab-out) by [Zara](https://x.com/zarazhangrui)

Remixed by [ZhangAn](https://github.com/anzhang507-eng)

---

## License

MIT