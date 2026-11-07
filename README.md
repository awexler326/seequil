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
- Low-quality picture: about $0.016
- Medium-quality picture: about $0.063
- Memory: a fraction of a cent for every 6 pages

So $5 covers roughly 300 low-quality pictures.

## 4. Seequil's own budget

In **Settings → Spending**, set a **monthly budget** (the default is $3). Seequil keeps a running estimate of what you've spent and stops calling OpenAI or Anthropic when it reaches the budget.

Seequil's figures are estimates. Your OpenAI or Anthropic billing page has the real numbers, and the prepaid credits are the real hard limit.

## 5. Choosing where pictures come from

**Settings → Pictures come from:**
- **ChatGPT images:** uses your OpenAI key.
- **Claude drawings:** Claude draws the scene as vector art. This needs an Anthropic API key from the Claude Console, which is also prepaid.
- **Only my own uploads:** no AI pictures. Use the clipboard button to copy a prompt into any generator (including free ones), then upload the picture or paste it onto the page with Ctrl/Cmd+V.

**Settings → Draw pictures:** by default, Seequil only draws a page when you tap **Draw this page**, so you never pay for pages you didn't want. Switch to *Automatically, for every page* if you'd rather have every page drawn as you read.

Every picture also has redraw, save, copy-prompt and upload buttons.

**Memory and prompts use:** OpenAI (cheapest) or Claude.

## 6. Backups and other devices

Books live in **this browser on this device**. Your phone and your computer each keep their own library.

- **Back up library** (on the library screen) saves one file with all your books, pictures, highlights and memory. It leaves out your API keys.
- **Restore a backup** loads that file on another device or browser.
- Clearing your browser's site data deletes the library, so back up now and then.

## 7. If something stops working

- **"didn't accept your API key":** re-copy the key into Settings.
- **"out of credit or hit its spending limit":** add credits on the provider's billing page.
- **AI model names change over time.** If OpenAI or Anthropic retires a model, update the names under **Settings → Advanced: models and prices**. The defaults are `gpt-5-mini` (text), `gpt-image-1` (pictures), `claude-sonnet-5-5` and `claude-haiku-5-5`.
- **Copy-protected (DRM) EPUBs** from Kindle, Apple Books and similar stores can't be opened. DRM-free EPUBs and PDFs with real text work.
