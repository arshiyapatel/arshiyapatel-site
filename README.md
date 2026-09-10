# arshiyapatel.com — deployment guide (free hosting via GitHub Pages)

You already own the domain on Namecheap. The free way to host a plain
HTML/CSS site like this one is **GitHub Pages**. Here is the whole path.

## 1. Put the site in a GitHub repo

1. Create a new repository, for example `arshiyapatel-site` (can be
   public or private, GitHub Pages works with both on a free personal
   account as long as the repo is public; a private repo needs GitHub Pro
   for Pages).
2. Upload all files in this folder (`index.html`, the other `.html`
   pages, `css/`, `js/`) to the root of that repo. You can drag and
   drop them in the GitHub web UI, no command line required.

## 2. Turn on GitHub Pages

1. In the repo, go to **Settings > Pages**.
2. Under "Build and deployment," set Source to **Deploy from a
   branch**, branch `main`, folder `/ (root)`. Save.
3. GitHub will give you a URL like `https://yourusername.github.io/arshiyapatel-site`.
   Confirm the site loads there first.

## 3. Point arshiyapatel.com at it

Do this in two places.

**In the GitHub repo (Settings > Pages > Custom domain):**
Enter `arshiyapatel.com` and save. This creates a `CNAME` file in
your repo automatically. Check "Enforce HTTPS" once it becomes
available (can take a few minutes to an hour after DNS is set).

**In Namecheap (Domain List > Manage > Advanced DNS):**
Add these records:

| Type | Host | Value |
|---|---|---|
| A Record | @ | 185.199.108.153 |
| A Record | @ | 185.199.109.153 |
| A Record | @ | 185.199.110.153 |
| A Record | @ | 185.199.111.153 |
| CNAME Record | www | yourusername.github.io |

(Those four IPs are GitHub Pages' current addresses; if GitHub's docs
show different ones when you set this up, use theirs.)

DNS changes can take anywhere from a few minutes to 24 hours to
propagate. Once it does, `https://arshiyapatel.com` will serve this
site, for free, indefinitely.

## Editing later

Every page is a plain HTML file, no build step. To change text,
open the relevant `.html` file and edit it directly, then re-upload
to GitHub (or use GitHub's built-in file editor). Shared look and
feel lives in `css/style.css`.

## Before going live, personalize:

- The "About" page has a note flagging the personal-narrative section
  as a draft. Swap in your own specifics.
- Add a headshot when you have one: drop the image file into `img/`
  and add an `<img>` tag in the hero section of `index.html` and
  `about.html`. The layout has room for one but doesn't require it.
- Double check the LinkedIn and GitHub links point to the right
  profiles.
