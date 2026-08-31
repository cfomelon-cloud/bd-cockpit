# Put your BD Cockpit online — step-by-step (no coding needed)

This guide takes you from zero to a private, passcode-protected web page you can open from **any browser** (office, home, phone). It uses **GitHub Pages** (free) to host the *page*, while **all your data stays encrypted on your own device** and is backed up in **iCloud**. Nothing personal is ever uploaded to GitHub.

**Time needed:** about 20 minutes. **Cost:** free.

---

## How the security works (read this first — 60 seconds)

Think of it as two separate things:

1. **The app itself** (the `index.html` file) — this is just *software*, like a blank spreadsheet template. It contains **no client data**. This is what lives on GitHub, and it's fine for it to be public.
2. **Your data** (introducers, notes, revenue) — this is created and stored **only inside your browser**, and it is **encrypted with your passcode** (bank-grade AES-256). It is **never** sent to GitHub or anywhere else.

So even though the web address is public, anyone who opens it just sees a **locked screen** asking them to *create their own* passcode on *their own* empty copy. **They cannot see your data** — your data isn't on the internet; it's in your browser and in an encrypted backup file in your iCloud.

> **Golden rule:** Only ever type real introducer information into the running app *after* you've unlocked it. Never type client/introducer data into the GitHub website itself.

---

## Part A — Create a GitHub account (once)

1. Go to **https://github.com** and click **Sign up**.
2. Use a **personal** email (e.g. your `cfo.melon@gmail.com`), not a work login — this is your personal toolbox.
3. Choose a username (e.g. `joe-privatecap`) and a strong password. Verify the email.
4. When asked, the **Free** plan is all you need.

---

## Part B — Create the repository (the folder that holds your page)

1. Once logged in, click the **+** in the top-right → **New repository**.
2. **Repository name:** `bd-cockpit` (lowercase, no spaces).
3. Set it to **Public**. *(This is safe — remember, only the empty software goes here, never your data. Public repos are what get free GitHub Pages hosting.)*
4. Tick **Add a README file**.
5. Click **Create repository**.

---

## Part C — Upload the app file

1. On your new repository page, click **Add file** → **Upload files**.
2. From your Mac, open the folder:
   `iCloud Drive → Work & Ventures → EY Private Capital → personal-bd-system`
3. Drag **`index.html`** into the upload box on the GitHub page.
4. Scroll down and click the green **Commit changes**.

That's it — the file is now on GitHub.

---

## Part D — Turn on GitHub Pages (make it a live website)

1. In your repository, click the **Settings** tab (top of the page).
2. In the left menu, click **Pages**.
3. Under **Build and deployment → Source**, choose **Deploy from a branch**.
4. Under **Branch**, pick **main** and folder **/ (root)**, then click **Save**.
5. Wait ~1–2 minutes, then refresh the page. GitHub shows a green box with your live address, e.g.:
   **`https://joe-privatecap.github.io/bd-cockpit/`**
6. Click it. You'll see the **BD Cockpit lock screen**. 🎉

**Bookmark that address** on your office computer, laptop, and phone.

---

## Part E — First run: set your passcode

1. On the lock screen, type a **strong passcode** (something only you know — there is **no reset**, so make it memorable). Confirm it.
2. Click **Unlock**. The app opens, pre-loaded with **sample data** so you can see how everything works.
3. Look around: **Today**, **Introducers**, **Catch-in Cadence**, **Events**, **Travel**, **Pipeline**, **Revenue**, **Library**.

---

## Part F — Load your real contacts (and make it yours)

Your 229 intermediaries have already been prepared into an import file: **`my-contacts.LOCAL-ONLY.json`** (in the same `personal-bd-system` folder). Load them in one step:

1. In the app, go to **Settings → Contacts → ⬆ Import my contacts (.json)**.
2. Choose **`my-contacts.LOCAL-ONLY.json`** from the `personal-bd-system` folder. You'll see “Imported 229 contacts.”
3. Click **🧹 Remove sample data** to clear the demo introducers/prospects/events. You're now running on your own network.
4. Set your name and catch-in cadences in **Settings** (defaults: Tier A every 42 days, B every 60, C every 90).
5. As you work, **log catch-ins**, update **pipeline** stages, and add **events** and **trips**.

Everything saves automatically and encrypted, in your browser.

> 🔒 **Two files must NEVER be uploaded to GitHub:** `Intermediaries contact list.xlsx` and `my-contacts.LOCAL-ONLY.json`. They contain your introducers' personal data. Keep them in this iCloud folder and only ever load them through the app's **Import** button. **Only `index.html` goes on GitHub.** (If you deployed via the assistant, this is already handled — only the code was pushed.)

---

## Part G — Back up & sync across devices (important)

Your data lives in *the browser you're using*. To use it on another device — or to be safe against a lost laptop — use the encrypted vault backup:

1. In the app: **Settings → ⬇ Export vault (backup)**. This downloads a file like `pc-bd-vault-2026-08-30.json`.
2. **Save that file into your iCloud Drive** (e.g. in the `EY Private Capital` folder). iCloud will sync it to all your devices.
3. On another device: open the same web address, and on the lock screen click **“Restore from an exported vault file →”**, pick the file from iCloud, and enter your passcode.

> **Do this weekly.** The vault file is encrypted — even if someone found it, they'd still need your passcode to read anything.

**Working across office + home?** Simplest rhythm: at the end of a session, **Export** to iCloud; when you start on the other device, **Restore** from iCloud. (A future upgrade can automate this — see the note below.)

---

## Part H — Updating the app later

If I send you an improved `index.html`:
1. Repository → click the existing **`index.html`** → the **pencil (Edit)** icon → delete all, paste the new content → **Commit changes**; *or* use **Add file → Upload files** and drop the new version (it overwrites).
2. Your **data is untouched** (it's in your browser/vault, not the file). Just refresh the page and unlock as normal.

---

## Frequently asked

**Is it really safe that the URL is public?**
Yes. The page is a blank, locked shell. Your data never goes to GitHub — it's encrypted in your browser and in your iCloud vault file. Someone opening your URL just gets prompted to create *their own* empty copy.

**What if I forget my passcode?**
There's no reset (that's what makes it secure). Recover by restoring a vault backup — but you still need the passcode that vault was saved with. So: pick a memorable passcode and keep it in your password manager.

**Can I make the repository private instead?**
You can, but GitHub Pages from a private repo needs a paid plan. It's unnecessary here because no data is ever in the repo.

**Can colleagues use it too?**
This is your *personal* toolbox. If you ever want a shared team version, that's a different build (a real backend with logins) — keep this one personal.

---

---

## Part I — Turn on auto-sync across devices (optional, recommended)

Instead of manually Export/Import, the app can keep an **encrypted** copy in a **private GitHub Gist**, so your office PC, laptop and phone stay in step automatically. GitHub only ever stores ciphertext — your passcode never leaves your device, so no one at GitHub (or anyone who saw the Gist) can read it.

**One-time setup on your main device:**
1. Create a token: **GitHub → your avatar → Settings → Developer settings → Personal access tokens → Tokens (classic) → Generate new token (classic)**. Give it a name, set an expiry, and tick **only the `gist` scope**. Generate and **copy** the token (starts `ghp_…`).
2. In the app: **Settings → Cloud auto-sync**, paste the token, and click **Enable & create cloud sync**. You'll see “Cloud sync created ✓” and a **Vault Gist ID** — note it down.
3. From now on, every change auto-syncs. Use **Pull latest** any time to fetch changes made elsewhere.

**On a new/second device:**
1. Open your bookmarked site → on the lock screen click **“Restore from cloud sync (new device) →”**.
2. Enter your **token**, the **Vault Gist ID**, and your **passcode**. Your data loads and that device is now synced too.
3. **Faster:** on your main device, **Settings → Cloud auto-sync** shows a **QR code**. Point the new phone's camera at it — it opens the app with the Vault Gist ID already filled in, so you only type the token + passcode. (The QR contains *only* the Gist ID — never your token or passcode.)

**Sync status at a glance:** the top bar shows a pill — **Synced ✓** (up to date), **Pull available** (a newer copy is in the cloud — tap to pull), **Syncing…**, or **Sync error**. Tap it any time to sync now.

> The token is stored inside your encrypted vault. Choose a sensible expiry and regenerate if ever needed. This is a personal convenience feature — the manual **Export vault to iCloud** backup (Part G) still works and is a good belt-and-braces habit.

---

## Part J — Day-to-day: prioritise and prune

- **Handpick your Tier-A relationships:** in **Introducers**, just **click any tier badge** to cycle A → B → C. Tier-A people surface first in **Today** and **Catch-in Cadence**, so your priority contacts are always front-of-queue.
- **Focus the list:** use the **★ Tier A only** button to show just your priority relationships, and tick **Hide archived** to drop parked contacts from view.
- **Add an introducer on the fly:** when creating a **Pipeline** opportunity, the **Source** dropdown includes **➕ Add a new introducer…** — fill in a few fields and it's saved into your Introducers automatically, linked to that prospect.
- **Your Clients database:** the **Clients** tab keeps your own client list (individuals, trusts, companies, FICs). Log interactions, set a catch-in cadence, and overdue client catch-ins appear on **Today** (capped, with their own reminder) — so you nurture existing clients, not just chase new ones.
- **Remove or park relationships that are no longer valid:** open a contact → **Edit**. Set **Status → Archived** to keep the history but drop them from your cadence and daily list, or click **Delete** to remove them permanently (linked pipeline items are kept but unlinked).
