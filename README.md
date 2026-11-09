# Seequil — setup

Seequil is a reading app: text on one side, a picture of the scene on the other, read-aloud, highlights and notes, and a spoiler-free memory of people, places and events.

Everything you add (books, pictures, notes, API keys) is stored **only in your browser on your device**. The website itself holds no books and no keys, so anyone who found the address would just see an empty app.

---

## 1. Put it online (free, GitHub Pages)

1. On github.com, click **New repository**. Name it `seequil`, choose **Public**, and create it.
   *(GitHub only serves free Pages sites from public repositories. That's fine here, because the repository contains only the app's code, never your books or keys.)*
2. In the new repository, click **Add file → Upload files**, drag in **every file from this folder**, and click **Commit changes**.
3. Go to **Settings → Pages**. Under *Build and deployment*, set **Source: Deploy from a branch**, **Branch: main**, folder **/ (root)**, and click **Save**.
4. After a minute or two, your app is live at `https://YOUR-USERNAME.github.io/seequil/`.

## 2. Install it like an app (optional)

- **Computer (Chrome or Edge):** open the site and click the install icon at the right end of the address bar.
- **Android (Chrome):** menu (⋮) → **Install app** or **Add to Home screen**.
- **iPhone (Safari):** Share → **Add to Home Screen**.

## 3. Get an OpenAI API key with a hard spending limit

1. Go to **platform.openai.com** and sign in. This is separate from a ChatGPT subscription.
2. Open **Billing**, add a payment method, and buy credits. **$5 is the minimum.**
3. When buying, **turn off auto-recharge.** With it off, you can never spend more than the credits you loaded.
4. Open **API keys → Create new secret key**, and copy the key. It starts with `sk-`.
5. In Seequil, open **Settings (gear button)**, paste the key into **OpenAI API key**, and switch on **Pictures and memory**.

Rough costs at the default settings:
- Low-quality picture: about $0.007
- Medium-quality picture: about $0.014
- Memory: a fraction of a cent for every 6 pages

So $5 covers roughly 600 low-quality pictures.

## 4. Seequil's own budget

In **Settings → Spending**, set a **monthly budget** (the default is $3). Seequil keeps a running estimate of what you've spent and stops calling OpenAI or Anthropic when it reaches the budget.

Seequil's figures are estimates. Your OpenAI or Anthropic billing page has the real numbers, and the prepaid credits are the real hard limit.

## 5. Choosing where pictures come from

**Settings → Pictures come from:**
- **ChatGPT images:** uses your OpenAI key.
- **Claude drawings:** Claude draws the scene as vector art. This needs an Anthropic API key from the Claude Console, which is also prepaid.
- **Only my own uploads:** no AI pictures. Use the clipboard button to copy a prompt into any generator (including free ones), then upload the picture or paste it onto the page with Ctrl/Cmd+V.

**Picture generation** (in Settings, and at the top left of the picture while you read):
- **Only this page:** Seequil draws a page only when you tap **Draw this page**. This is the default, so you never pay for pages you didn't want.
- **Always:** every page is drawn as you read.
- **The Pictures on/off switch** stops all new pictures. Pictures you already have still show.

Every picture also has redraw, **change this picture** (type what should be different, then either keep the picture and just fix those things, or draw it again with your notes), save, copy-prompt and upload buttons.

**Character portraits** (switch in Settings, off by default): Seequil draws each main character once and sends that portrait as a guide with every ChatGPT picture they're in, so faces stay consistent. A portrait costs about 1¢ once. Each picture costs about 0.6¢ more per character shown. By default only the main characters (the 4 mentioned most so far) get portraits; change the number in Settings, or set any character to Always or Never on their memory card, where you can also redraw, upload or remove their portrait, or switch **Use in pictures** off to stop using it without deleting it. With the switch off, pictures use each character's written look.

**Key places and items** (switches under Character portraits): the most-mentioned places and items (3 of each by default) also get a written look and a reference picture: a wide view for a place, the object on its own for an item. A picture uses at most 3 characters and 2 places or items as guides. Set any of them to Always or Never on their memory card.

**Memory and prompts use:** OpenAI (cheapest) or Claude.

## 6. Full cast (character voices)

**Settings → Full cast** gives each character their own voice when Seequil reads aloud. The narrator keeps the voice you picked.

- Your OpenAI (or Anthropic) key works out who says each quote. This costs a fraction of a cent per page, is saved, and only happens once per page.
- Voices come from your browser. **Microsoft Edge has the best free ones** (names ending in "Online (Natural)").
- To change a character's voice or pitch, tap their name in the text to open their memory card, then use **Voice**. **Hear it** plays a sample.
- If a line goes to the wrong character, select some of the quote and tap **Speaker** in the bar that appears.

## 7. Search this book

The **magnifying glass** on the reading screen searches only the pages you've reached, so it can't spoil anything.

- **Find words** (free): every place a word or name appears, with a snippet. Tap one to jump there.
- **Ask**: a question like "How much is a gold crown worth?" gets a short answer with page numbers you can tap. Only pages up to where you are are sent to the AI. Costs a fraction of a cent.

## 8. Backups and other devices

**Picking up where you left off on another device:** in the book, tap the **phone icon** (on a phone: **⋯ → Continue on another device**). Scan the QR code with your other device's camera, or copy the link, and it opens the same book at the same page. The book has to be on that device too: add the same file there once, or restore a backup.

**Automatic sync (recommended):** Seequil can keep your books, place, highlights, notes, memory and pictures the same on every device, using a private repository in your GitHub account.

1. On github.com, make a new repository named `seequil-library`. Choose **Private** and check **Add a README file**.
2. Go to <https://github.com/settings/personal-access-tokens/new> and make a **fine-grained token**: name it "Seequil sync", pick an expiration, choose **Only select repositories → seequil-library**, and under **Repository permissions** set **Contents** to **Read and write**. Generate and copy it.
3. In Seequil, open **Settings → Sync between devices**, type `yourname/seequil-library`, paste the token, and tap **Connect**. Do the same on each device.

It syncs when you open Seequil, a few seconds after you change something, when you switch back to the app, and every 5 minutes (or tap **Sync now**). If your other device is on a later page, you'll see "Your other device is on page X" with a button to jump there. Turn off **Sync pictures too** if you want it lighter. The token can only reach that one repository, stays on the device, and is never synced or put in backups. API keys and display settings stay per device. When the token expires, make a new one and paste it in.

Without sync, books live in **this browser on this device**, and your phone and your computer each keep their own library.

- **Back up library** (on the library screen) saves one file with all your books, pictures, highlights and memory. It leaves out your API keys and GitHub token.
- **Restore a backup** loads that file on another device or browser.
- Clearing your browser's site data deletes the library, so back up now and then.

## 9. If something stops working

- **"couldn't reach OpenAI" / "Couldn't reach the AI service":** open Settings → **Test connection**. "Blocked" usually means an ad or privacy blocker, or a work or school network blocking AI sites. Try turning blockers off for this site, your phone's hotspot, or another browser.
- **"didn't accept your API key":** re-copy the key into Settings.
- **"out of credit or hit its spending limit":** add credits on the provider's billing page.
- **AI model names change over time.** If OpenAI or Anthropic retires a model, update the names under **Settings → Advanced: models and prices**. The defaults are `gpt-6-luna` (text), `gpt-image-2.5-flare` (pictures), `claude-sonnet-5-5` and `claude-haiku-5-5`.
- **Copy-protected (DRM) EPUBs** from Kindle, Apple Books and similar stores can't be opened. DRM-free EPUBs and PDFs with real text work.
