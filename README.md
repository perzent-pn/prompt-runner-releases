# Prompt Runner: downloads

A tiny menubar (macOS) / tray (Windows 10/11, Linux) app that shows what each AI coding agent is doing — running, planning, waiting for your approval, asking a question, waiting for a result, or idle — as a little animated pixel character, RunCat style.

- One icon per AI tool with a session count. Click it for every session: project, state, model, terminal/IDE, tokens, context %, and Claude Code's 5-hour / 7-day plan usage, as numbers or as a power bar that drains as you use it (Settings → Appearance).
- Notifications when an agent needs your approval or asks a question.
- An optional floating gadget (off by default): a small always-on-top panel with the character, 5h / 7d usage and every session. Turn it on from the menu or **Settings → Appearance**; drag it anywhere, pick Small / Medium / Large, and pin it to stay on top.
- Works with Claude Code (hooks and its own status files). Several Claude accounts (for example started with `HOME=~/.claude-work claude`) are supported as separate profiles.
- Characters: samurai, knight, viking, soldier, oni, vampire, mage, cat, dog, bunny, robot, minimal, or your own (below). English and Thai.
- Display only, local only: no network, no prompt or code storage, no credential reads, sessions kept in memory.

This repository only hosts the downloads. The source code and the character artwork are not published here.

## Download

Get the latest files from the **[Releases page](../../releases/latest)**:

- `PromptRunner-macOS.zip`: macOS 11 or newer, Apple Silicon and Intel
- `PromptRunner-Windows-x64.zip`: Windows 10/11 (lightly tested)
- `PromptRunner-Linux-x64.tar.gz`: Linux x64, Ubuntu 22.04 or newer, GNOME or KDE (new)

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

## Install on Linux

```sh
tar -xzf PromptRunner-Linux-x64.tar.gz
PromptRunner/install.sh
```

No sudo needed: it installs for your user into `~/.local/share/prompt-runner/app`, adds Prompt Runner to your app launcher and starts it. Then choose **Integrations → Install Claude Code hooks** and **Show Claude plan usage** in its menu, as on the Mac. **Settings → About → Check for updates** updates it in place.

- Needs `libwebkit2gtk-4.1-0` and `libayatana-appindicator3-1` (Ubuntu's desktop has both): `sudo apt install libwebkit2gtk-4.1-0 libayatana-appindicator3-1`.
- The tray icon needs AppIndicator support: built into Ubuntu and KDE. Plain GNOME (for example Fedora) needs the "AppIndicator and KStatusNotifierItem Support" extension; without it Prompt Runner shows the floating gadget instead.
- The 5h / 7d usage next to the tray icon is plain text (Linux top bars show no colours); the gadget has the colours and bars.
- Not on Linux yet: clicking a session to jump to its terminal.

Remove it: `~/.local/share/prompt-runner/app/uninstall.sh` (also takes its hooks out of your Claude settings).

## Floating gadget

Turn it on from the menu (**Show floating gadget**) or **Settings → Appearance**. It shows the most urgent character and your 5h / 7d usage; click the arrow to list every session, and click a session to jump to its terminal. Drag it to move it, right-click for the menu, and click the pin to keep it on top of other windows (gold emblem = pinned, red = not pinned). Size and opacity are in Settings. **Settings → Appearance → Gadget display** lets the gadget show different things from the menubar, for example only the character in the menubar and everything in the gadget.

## Your own characters

**Settings → Appearance → Your own characters → Create a character.** Add one or more pictures for each pose; several play in turn as an animation (frame 1, frame 2, …). Adjust each frame's size and place, set the speed, let it remove a plain or checkered background, and choose each pose's effect (a mark in any colour, a small picture of your own, blinking or not). Characters stay on your computer and are kept through updates; **Export** one to a `.prchar` file to back it up, move it or share it, and **Import** it elsewhere.

## Problems and ideas

**Settings → About → Feedback and problems** fills in a report for you (with the app's own error log if you want), shows it in full, then opens it as an [issue here](../../issues) in your browser, or copies it so you can send it another way. Prompt Runner never sends anything by itself.

## Several Claude accounts

If you start Claude Code with another `HOME` or `CLAUDE_CONFIG_DIR`, open **Settings → AI Agents → Claude Code → Claude profiles**, type the folder (for example `~/.claude-work`) or click **Find running Claude**, and add it. Each profile gets its own hooks and its own 5h / 7d usage line.

---

## ภาษาไทย

แอปเล็กๆ บน menubar (macOS) / tray (Windows 10/11, Linux) ที่แสดงว่า AI เขียนโค้ดแต่ละตัวกำลังทำอะไรอยู่ เป็นตัวละครพิกเซลเคลื่อนไหว ทั้งกำลังทำงาน วางแผน รอการอนุมัติ ถามคำถาม นั่งรอผลลัพธ์ หรือว่าง ทำงานในเครื่องเท่านั้น ไม่ใช้เครือข่าย ไม่เก็บ prompt หรือโค้ด

repo นี้ใช้เก็บไฟล์ดาวน์โหลดเท่านั้น ไม่มีซอร์สโค้ดและภาพตัวละครต้นฉบับ

**ติดตั้งบน Mac:** แตก zip แล้วย้าย `Prompt Runner.app` ไปไว้ใน Applications จากนั้นรันคำสั่งนี้ใน Terminal ครั้งเดียว:

```sh
xattr -dr com.apple.quarantine "/Applications/Prompt Runner.app"
```

เปิดแอป แล้วเลือกในเมนู Integrations → ติดตั้ง hook ของ Claude Code และเปิด "แสดงการใช้พ็อกเกจ" เพื่อดูโควต้า 5h / 7d

**ติดตั้งบน Windows:** แตก zip เก็บ `prompt-runner.exe` กับ `pr-hook.exe` ไว้โฟลเดอร์เดียวกัน แล้วเปิด `prompt-runner.exe`

**ติดตั้งบน Linux:** แตกไฟล์ `PromptRunner-Linux-x64.tar.gz` แล้วรัน `PromptRunner/install.sh` (ไม่ต้องใช้ sudo) ต้องมี `libwebkit2gtk-4.1-0` และ `libayatana-appindicator3-1` ซึ่ง Ubuntu แบบ desktop มีให้แล้ว ถอนการติดตั้งด้วย `~/.local/share/prompt-runner/app/uninstall.sh`

**หลอดพลัง:** ไปที่ ตั้งค่า → รูปลักษณ์ → การแสดงผลบน menubar เลือกแสดงการใช้งานเป็น "หลอดพลัง" ที่ลดลงตามการใช้งาน และเลือกได้ว่าตัวเลข % จะเป็น "ที่ใช้ไป" หรือ "ที่เหลือ" ค่าเริ่มต้นยังเป็นตัวเลขแบบเดิม

**Gadget ลอย:** เปิดจากเมนู หรือ ตั้งค่า → รูปลักษณ์ เป็นแผงเล็กที่ลอยอยู่บนสุด แสดงตัวละคร โควต้า 5h / 7d และทุก session กดลูกศรเพื่อดูรายการ กดที่ session เพื่อกระโดดไปหา ลากเพื่อย้าย คลิกขวาเปิดเมนู และกดหมุดเพื่อให้อยู่บนสุด (หมุดทอง = ปักอยู่ หมุดแดง = ไม่ได้ปัก) ตั้งค่าให้ gadget แสดงต่างจาก menubar ได้ที่ ตั้งค่า → รูปลักษณ์ → การแสดงผลบน gadget เช่น ให้ menubar แสดงแค่ตัวละคร แต่ gadget แสดงครบ

**สร้างตัวละครเอง:** ไปที่ ตั้งค่า → รูปลักษณ์ → ตัวละครของคุณเอง → สร้างตัวละคร ใส่รูปท่าละ 1 รูปขึ้นไป ถ้าใส่หลายรูปจะเล่นเป็น animation (เฟรมที่ 1, เฟรมที่ 2, …) ปรับขนาดและตำแหน่งแต่ละเฟรม ลบพื้นหลัง และเลือก effect ของแต่ละท่าได้ ตัวละครเก็บในเครื่องและไม่หายตอนอัปเดต ส่งออกเป็นไฟล์ .prchar เพื่อสำรองหรือส่งให้เพื่อนนำเข้าได้

**แจ้งปัญหาหรือเสนอไอเดีย:** ไปที่ ตั้งค่า → เกี่ยวกับ → Feedback และแจ้งปัญหา แอปจะเตรียมรายงานให้ ดูทั้งหมดก่อน แล้วเปิดเป็น issue บน GitHub หรือคัดลอกไปส่งทางอื่นก็ได้ แอปไม่ส่งอะไรออกไปเอง

**ใช้ Claude หลายบัญชี:** ไปที่ ตั้งค่า → AI Agents → Claude Code → โปรไฟล์ Claude แล้วพิมพ์โฟลเดอร์ เช่น `~/.claude-work` หรือกด "ค้นหา Claude ที่กำลังรัน" แต่ละโปรไฟล์จะมี hook และโควต้าของตัวเอง
