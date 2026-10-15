# Prompt Runner: downloads

A tiny menubar (macOS) / tray (Windows 10/11) app that shows what each AI coding agent is doing — running, planning, waiting for your approval, asking a question, waiting for a result, or idle — as a little animated pixel character, RunCat style.

- One icon per AI tool with a session count. Click it for every session: project, state, model, terminal/IDE, tokens, context %, and Claude Code's 5-hour / 7-day plan usage.
- Notifications when an agent needs your approval or asks a question.
- An optional floating gadget (off by default): a small always-on-top panel with the character, 5h / 7d usage and every session. Turn it on from the menu or **Settings → Appearance**; drag it anywhere, pick Small / Medium / Large, and pin it to stay on top.
- Works with Claude Code (hooks and its own status files). Several Claude accounts (for example started with `HOME=~/.claude-work claude`) are supported as separate profiles.
- Characters: samurai, knight, viking, soldier, oni, vampire, mage, cat, dog, bunny, robot, minimal. English and Thai.
- Display only, local only: no network, no prompt or code storage, no credential reads, sessions kept in memory.

This repository only hosts the downloads. The source code and the character artwork are not published here.

## Download

Get the latest files from the **[Releases page](../../releases/latest)**:

- `PromptRunner-macOS.zip`: macOS 11 or newer, Apple Silicon and Intel
- `PromptRunner-Windows-x64.zip`: Windows 10/11 (lightly tested)

## Install on macOS

The app is not signed with an Apple Developer ID, so macOS blocks the first launch.

1. Unzip and move `Prompt Runner.app` to `/Applications`.
2. Open Terminal and run this once (it removes the "downloaded from the internet" flag):
   ```sh
   xattr -dr com.apple.quarantine "/Applications/Prompt Runner.app"
   ```
   Or open the app once, then go to **System Settings → Privacy & Security** and click **Open Anyway**.
3. Open **Prompt Runner**. It lives in the menubar only (no Dock icon); later you can open it with Spotlight.
4. In its menu choose **Integrations → Install Claude Code hooks** (full status detection) and **Show Claude plan usage** (5h / 7d numbers).

Remove it: in the same menu uncheck both items (your Claude settings are restored), quit, delete the app.

## Install on Windows

Unzip `PromptRunner-Windows-x64.zip`, keep `prompt-runner.exe` and `pr-hook.exe` in the same folder, and run `prompt-runner.exe` (SmartScreen: More info → Run anyway). The settings window needs Microsoft Edge WebView2, which Windows 10/11 normally has.

## Floating gadget

Turn it on from the menu (**Show floating gadget**) or **Settings → Appearance**. It shows the most urgent character and your 5h / 7d usage; click the arrow to list every session, and click a session to jump to its terminal. Drag it to move it, right-click for the menu, and click the pin to keep it on top of other windows (gold emblem = pinned, red = not pinned). Size and opacity are in Settings.

## Several Claude accounts

If you start Claude Code with another `HOME` or `CLAUDE_CONFIG_DIR`, open **Settings → AI Agents → Claude Code → Claude profiles**, type the folder (for example `~/.claude-work`) or click **Find running Claude**, and add it. Each profile gets its own hooks and its own 5h / 7d usage line.

---

## ภาษาไทย

แอปเล็กๆ บน menubar (macOS) / tray (Windows 10/11) ที่แสดงว่า AI เขียนโค้ดแต่ละตัวกำลังทำอะไรอยู่ เป็นตัวละครพิกเซลเคลื่อนไหว ทั้งกำลังทำงาน วางแผน รอการอนุมัติ ถามคำถาม นั่งรอผลลัพธ์ หรือว่าง ทำงานในเครื่องเท่านั้น ไม่ใช้เครือข่าย ไม่เก็บ prompt หรือโค้ด

repo นี้ใช้เก็บไฟล์ดาวน์โหลดเท่านั้น ไม่มีซอร์สโค้ดและภาพตัวละครต้นฉบับ

**ติดตั้งบน Mac:** แตก zip แล้วย้าย `Prompt Runner.app` ไปไว้ใน Applications จากนั้นรันคำสั่งนี้ใน Terminal ครั้งเดียว:

```sh
xattr -dr com.apple.quarantine "/Applications/Prompt Runner.app"
```

เปิดแอป แล้วเลือกในเมนู Integrations → ติดตั้ง hook ของ Claude Code และเปิด "แสดงการใช้พ็อกเกจ" เพื่อดูโควต้า 5h / 7d

**ติดตั้งบน Windows:** แตก zip เก็บ `prompt-runner.exe` กับ `pr-hook.exe` ไว้โฟลเดอร์เดียวกัน แล้วเปิด `prompt-runner.exe`

**Gadget ลอย:** เปิดจากเมนู หรือ ตั้งค่า → รูปลักษณ์ เป็นแผงเล็กที่ลอยอยู่บนสุด แสดงตัวละคร โควต้า 5h / 7d และทุก session กดลูกศรเพื่อดูรายการ กดที่ session เพื่อกระโดดไปหา ลากเพื่อย้าย คลิกขวาเปิดเมนู และกดหมุดเพื่อให้อยู่บนสุด (หมุดทอง = ปักอยู่ หมุดแดง = ไม่ได้ปัก)

**ใช้ Claude หลายบัญชี:** ไปที่ ตั้งค่า → AI Agents → Claude Code → โปรไฟล์ Claude แล้วพิมพ์โฟลเดอร์ เช่น `~/.claude-work` หรือกด "ค้นหา Claude ที่กำลังรัน" แต่ละโปรไฟล์จะมี hook และโควต้าของตัวเอง
