# AGENTS.md -- Tab Out Remixed: Setup & Onboarding Guide for Coding Agents

You're installing **Tab Out Remixed** for the user. Your job is not just to set it up -- it's to get them excited about using it.

---

## What is Tab Out Remixed?

**Tab Out Remixed** is a modified version of Tab Out that adds Feishu (飞书) document management features while preserving all original functionality.

> **Tab Out Remixed** replaces your new tab page with a clean dashboard of everything you have open, grouped by domain.
>
> Here's what makes it great:
> - **All original Tab Out features** - domain grouping, homepages, swoosh + confetti, duplicate detection, etc.
> - **Feishu Only view** - Filter to show only Feishu document tabs
> - **Opening time display** - See when each tab was opened
> - **Time-based grouping** - Organize Feishu tabs by: Just now, Within 2 hours, Within 8 hours, Yesterday, Earlier
> - **Wider cards for Feishu** - 380px card width in Feishu view for better document readability
>
> It's just a Chrome extension. Setup takes about 1 minute.

---

## Step 1 -- Clone the repo

```bash
git clone https://github.com/anzhang507-eng/tab-out-remixed.git
cd tab-out-remixed
```

---

## Step 2 -- Install the Chrome extension

This is the one step that requires manual action from the user. Make it as easy as possible.

**First**, print the full path to the `extension/` folder:
```bash
echo "Extension folder: $(cd extension && pwd)"
```

**Then**, copy the `extension/` folder path to their clipboard:
- macOS: `cd extension && pwd | pbcopy && echo "Path copied to clipboard"`
- Linux: `cd extension && pwd | xclip -selection clipboard 2>/dev/null || echo "Path: $(pwd)"`
- Windows: `cd extension && echo %CD% | clip`

**Then**, open the extensions page:
```bash
open "chrome://extensions"
```

**Then**, walk the user through it step by step:

> I've copied the extension folder path to their clipboard. Now:
>
> 1. You should see Chrome's extensions page. In the **top-right corner**, toggle on **Developer mode** (it's a switch).
> 2. Once Developer mode is on, you'll see a button called **"Load unpacked"** appear in the top-left. Click it.
> 3. A file picker will open. **Press Cmd+Shift+G** (Mac) or **Ctrl+L** (Windows/Linux) to open the "Go to folder" bar, then **paste** the path I copied (Cmd+V / Ctrl+V) and press Enter.
> 4. Click **"Select"** or **"Open"** and the extension will install.
>
> You should see "Tab Out Remixed" appear in your extensions list.

**Also**, open the file browser directly to the extension folder as a fallback:
- macOS: `open extension/`
- Linux: `xdg-open extension/`
- Windows: `explorer extension\\`

---

## Step 3 -- Show them around

Once the extension is loaded:

> You're all set! Open a **new tab** and you'll see Tab Out Remixed.
>
> Here's how it works:
> 1. **Your open tabs are grouped by domain** in a grid layout.
> 2. **Homepages** (Gmail inbox, X home, YouTube, etc.) are in their own group at the top.
> 3. **Click any tab title** to jump directly to that tab.
> 4. **Click the X** next to any tab to close just that one (with swoosh + confetti).
> 5. **Click "Close all N tabs"** on a group to close the whole thing.
> 6. **Duplicate tabs** are flagged with an amber "(2x)" badge. Click "Close duplicates" to keep one copy.
> 7. **Save a tab for later** by clicking the bookmark icon before closing it. Saved tabs appear in the sidebar.
> 8. **NEW: Feishu Only toggle** - Click to filter only Feishu document tabs
> 9. **NEW: Time-based grouping** - In Feishu Only mode, tabs are grouped by opening time
>
> That's it! No server to run, no config files. Everything works right away.

---

## Key Facts

- Tab Out Remixed is a pure Chrome extension. No server, no Node.js, no npm.
- Based on [Tab Out](https://github.com/zarazhangrui/tab-out) by Zara, remixed by ZhangAn.
- Saved tabs are stored in `chrome.storage.local` (persists across sessions).
- 100% local. No data is sent to any external service.
- To update: `cd tab-out-remixed && git pull`, then reload the extension in `chrome://extensions`.