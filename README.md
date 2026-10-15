# CRAFT: The Prompt Lab — Skills Bank | GitHub Pages

One file (`index.html`), no build, no keys, no backend. English / العربية (RTL).

## Publish (GitHub Pages)
1. Create a **public** repo. Upload `index.html` and `.nojekyll` to the root.
2. Settings → Pages → Deploy from branch `main` / root. Wait ~1 minute.
3. Open `https://<user>.github.io/<repo>/` → **Trainer Dashboard** → PIN `2026`.
4. Open the link from the published URL (not the file from your computer, not a preview window).

## How it works
- Trainer: a session with a **5-character code** is created automatically. **+ New session** adds more (up to 6 at once, one tab each). **Reset session** = new code (old one closed). **Projector view** for the big screen.
- Players: open the link (code is filled in) or type the code. Leave the code empty to play solo.
- Six stages: Malfunction → five modules (C, R, A, F, T — each a different mini-game) → Assemble → Simulation → Final challenge → Mission complete.
- Live sync = free public relay `ntfy.sh` (SSE + POST, replay on reconnect, polling fallback, retry on send). Players open the live stream from the final challenge on; trainer sees progress, prompts and reflections as messages arrive.
- Backup if the relay is down: players press *Download backup result*; trainer imports the files (same session code only).
- Optional: add `?relay=https://your-ntfy-server` to the link to use your own ntfy server.

## Scoring (all rule-based, shown to the player)
| Part | Points |
|---|---|
| Each module (x5) | 100, −25 per failed lock (max −50), +20 if no hint on that module → 50–120 |
| Assembly | 20 per CRAFT part detected in the assembled prompt (max 100) |
| Final challenge | 40 per CRAFT part (200) + 10 per key detail (4 details = 40) + 20 safe-prompt = 260 |
| Own-task bonus | details not scored; +50 if all five parts + safe |
Max 960 (standard) / 970 (own task). Coins: 250 at start, hints cost 50 (2 per module + 1 cheat sheet in the final). Coins are the leaderboard tie-breaker.

## Honest limits
- **Final-challenge checks are keyword rules**, not AI. Passing does not prove a good prompt; the screen says so. The real test is pasting the prompt into an AI tool.
- **The AI response in the simulation is pre-written** and labelled as a demonstration. The game never calls a real AI model.
- **Not yet tested on real ntfy.sh or across real devices.** It was tested in a headless browser against a local relay that imitates ntfy (SSE, polling, retries, storage blocked, Arabic, mobile viewport). Do the two-device test below before a live class.
- ntfy.sh free limits are per IP; a large class on one Wi-Fi may hit them (publish limits, 30 live streams per IP). Rehearse; keep the backup/import as the safety net.
- The `2026` PIN only hides the interface; it is not security. The relay is public: no confidential data, use fictional examples. The prompts and reflections players write are sent to the trainer through that public relay.
- Never include real customer data in a prompt (the game teaches [CLIENT_A]-style placeholders).

## Two-device test checklist (do this before the class)
1. Device A (laptop): open the published link → Trainer Dashboard → PIN 2026. Note the 5-character code and `● LIVE`.
2. Device B (phone, mobile data or other Wi-Fi): open the player link (or type the code) → enter a name → **Enter the lab**.
3. A: the player appears within a few seconds; a toast + sound announce the join.
4. B: send the weak prompt, fix the five modules (try one wrong answer and one hint). A: stage, C-R-A-F-T lights, hints, coins, score update.
5. B: assemble → power up → run the simulation → final challenge → submit → write a reflection. A: ✅ complete; click ⌄ to read the main prompt, final prompt, checks and reflection.
6. A: **Reveal leaderboard**. B: the leaderboard opens by itself. **Hide** closes it. Projector view shows the same.
7. Switch language on both (العربية / English); check RTL layout and that the prompt still works.
8. Refresh B in the middle of a mission → **Resume mission** continues where it stopped.
9. A: **Reset session** → new code; a new join on the old code no longer appears in the new tab.
10. Switch Wi-Fi off on B for one answer: the retry message appears; backup download works; import it on A.
11. Check sound ON/OFF and that the page still works with the device in "reduce motion" mode.
