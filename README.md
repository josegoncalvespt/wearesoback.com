# wearesoback.com

The So Back website — a single GitHub Pages site at `wearesoback.com` that hosts landing pages, privacy policies, and support docs for every So Back project.

## Stack

- **Jekyll** (the default GitHub Pages renderer — no build step required).
- Plain Markdown files. GitHub renders them to HTML automatically when pushed.
- One shared layout (`_layouts/default.html`) + one stylesheet (`assets/style.css`).
- Custom domain via the `CNAME` file at the root.

## Structure

```
wearesoback.com/
├── _config.yml                 # Jekyll config
├── CNAME                       # wearesoback.com
├── _layouts/default.html       # shared HTML shell
├── assets/style.css            # shared stylesheet
├── index.md                    # https://wearesoback.com/
└── daily-design-challenge/     # one folder per project
    ├── index.md                # https://wearesoback.com/daily-design-challenge/
    ├── privacy.md              # https://wearesoback.com/daily-design-challenge/privacy/
    ├── terms.md                # https://wearesoback.com/daily-design-challenge/terms/
    └── support.md              # https://wearesoback.com/daily-design-challenge/support/
```

## Adding a new project

1. Create a folder at the root, e.g. `cool-new-app/`.
2. Inside, add `index.md`, `privacy.md`, `terms.md`, `support.md` — each with YAML frontmatter:
   ```yaml
   ---
   title: Page Title
   description: One-line description.
   ---
   ```
3. Add a link to the new project in the top-level `index.md`.
4. Commit + push. GitHub Pages rebuilds in ~30 seconds.

That's it. URLs follow the folder structure thanks to `permalink: pretty` in `_config.yml`.

## Local preview (optional)

You don't need this to ship — GitHub builds on push. But if you want to preview:

```bash
# One-time install
brew install rbenv
rbenv install 3.2.2 && rbenv local 3.2.2
gem install bundler

# Install dependencies
bundle init
echo 'gem "github-pages", group: :jekyll_plugins' >> Gemfile
bundle install

# Serve
bundle exec jekyll serve
# -> http://127.0.0.1:4000
```

## Initial deployment — GitHub Pages + DNS

### Step 1 — Create the GitHub repo

```bash
cd ~/Desktop/wearesoback.com
git init
git add .
git commit -m "Initial site"
```

Then on GitHub:

1. Create a new **public** repo (private repos require GitHub Pro for Pages). Name it whatever — `wearesoback.com` is conventional.
2. Push:
   ```bash
   git remote add origin git@github.com:YOUR_USERNAME/wearesoback.com.git
   git branch -M main
   git push -u origin main
   ```

### Step 2 — Enable GitHub Pages

In the repo on GitHub:

1. **Settings → Pages**.
2. **Source**: Deploy from a branch.
3. **Branch**: `main` / `(root)`. Click **Save**.
4. Wait ~30 seconds. A green check appears. Your site is now live at `https://YOUR_USERNAME.github.io/wearesoback.com/`.

### Step 3 — Hook up the custom domain (wearesoback.com)

Still in **Settings → Pages**:

1. **Custom domain**: enter `wearesoback.com`. Click **Save**.
2. GitHub commits the `CNAME` file to your repo (we already have one — it will validate).
3. **DNS check** will fail at first. That's expected — DNS isn't pointed yet.

Now configure DNS at your registrar (where you bought wearesoback.com). The exact provider depends on where you registered, but the records are universal:

#### Apex domain (`wearesoback.com`) — add four `A` records

| Type | Name | Value | TTL |
|---|---|---|---|
| A | @ | 185.199.108.153 | 3600 |
| A | @ | 185.199.109.153 | 3600 |
| A | @ | 185.199.110.153 | 3600 |
| A | @ | 185.199.111.153 | 3600 |

(These are GitHub's published Pages IPs. They never change. Source: [GitHub docs](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site#configuring-an-apex-domain).)

#### `www.wearesoback.com` — add one `CNAME` record

| Type | Name | Value | TTL |
|---|---|---|---|
| CNAME | www | YOUR_USERNAME.github.io. | 3600 |

(Replace `YOUR_USERNAME` with your actual GitHub username. The trailing dot may or may not be required by your registrar.)

#### Where to add DNS records, by registrar

- **Cloudflare**: Dashboard → wearesoback.com → DNS → Records → +Add record. Set proxy status to **DNS only** (grey cloud) initially; you can enable proxy after HTTPS works.
- **Namecheap**: Domain List → wearesoback.com → Advanced DNS → Add New Record.
- **GoDaddy**: My Products → wearesoback.com → DNS → Manage Zones.
- **Google Domains** (now Squarespace Domains): Manage Domain → DNS → Custom records.
- **Porkbun**: Account → Domain Management → wearesoback.com → DNS.

### Step 4 — Wait for DNS propagation (5 min – 24h, usually < 30 min)

Verify with:

```bash
dig wearesoback.com +noall +answer
# Should show 185.199.108.153 etc.
```

Back in **GitHub repo → Settings → Pages**: the DNS check will turn green.

### Step 5 — Enforce HTTPS

In **Settings → Pages**, once DNS is verified, tick **Enforce HTTPS**. GitHub issues a Let's Encrypt cert automatically (takes ~10 minutes after enabling).

## Done

Live URLs:

- `https://wearesoback.com/` — landing
- `https://wearesoback.com/daily-design-challenge/privacy/` — privacy policy
- `https://wearesoback.com/daily-design-challenge/support/` — support

These are the URLs to paste into App Store Connect and the RevenueCat dashboard.
