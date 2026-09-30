# MemorySprout Legal Documents

Source of truth for Privacy Policy and Terms of Use.

**Developer:** ManLin Zhao  
**Public hosting:** Option B — separate public repo `memorysprout-legal` (app source stays private).

## Public URLs (after Pages is enabled on `memorysprout-legal`)

| Doc | URL |
|---|---|
| Privacy (EN) | https://kinwah-leong.github.io/memorysprout-legal/legal/privacy-en.html |
| Terms (EN) | https://kinwah-leong.github.io/memorysprout-legal/legal/terms-en.html |
| 隐私政策 | https://kinwah-leong.github.io/memorysprout-legal/legal/privacy-zh-Hans.html |
| 用户协议 | https://kinwah-leong.github.io/memorysprout-legal/legal/terms-zh-Hans.html |

App Release uses:

```text
MEMORYSPROUT_LEGAL_BASE_URL = https://kinwah-leong.github.io/memorysprout-legal
```

and loads `$BASE/legal/<file>.html`.

## One-time setup

Local tree is prepared at `/Users/aimo/memorysprout-legal` (synced from `web/legal/`).

```bash
# 1) Create empty PUBLIC repo on GitHub named memorysprout-legal (under kinwah-leong)
# 2) Push:
cd /Users/aimo/memorysprout-legal
git remote add origin git@github.com:kinwah-leong/memorysprout-legal.git
git push -u origin main

# 3) GitHub → memorysprout-legal → Settings → Pages
#    Source: Deploy from a branch → main → / (root) → Save
```

`gh` is not logged in on this machine; create the repo in the GitHub website or run `gh auth login` then:

```bash
gh repo create kinwah-leong/memorysprout-legal --public --source=/Users/aimo/memorysprout-legal --remote=origin --push
```

## Update legal content later

From the private MemorySprout repo:

```bash
python3 scripts/generate-legal-html.py
./scripts/sync-legal-public-repo.sh /Users/aimo/memorysprout-legal
cd /Users/aimo/memorysprout-legal && git add -A && git commit -m "Update legal" && git push
```

## Markdown (private MemorySprout)

| Document | English | 简体中文 |
|---|---|---|
| Privacy Policy | `privacy-policy-en.md` | `privacy-policy-zh-Hans.md` |
| Terms of Use | `terms-of-use-en.md` | `terms-of-use-zh-Hans.md` |

Also under `ios/MemorySprout/Legal/*.md` / `*.html` for test builds.

## App loading rule

| Channel | Source |
|---|---|
| Development / Alpha / Beta | Bundled HTML in the app |
| Release | Remote URL only (no local fallback) |

## Still to complete

- Create + push `memorysprout-legal`, enable Pages, confirm URLs open
- Custom domain / monitored emails when ready
- Correspondence address, governing law
